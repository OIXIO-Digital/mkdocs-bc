## Pangaga gateway otsekanali lepingu sõlmimine

Business Centralis pangaliidese kasutamiseks on vajalik oma pangas sõlmida *gateway* otsekanali leping ning tellida sertifikaat. Sertifikaadi tellimise juhise saadab pank pärast lepingu sõlmimist. Sertifikaadi faili formaat peab olema .p12 parooliga kaitstud.

### Swedbank

<https://www.swedbank.ee/business/d2d/ebanking/gateway>

Toetatud teenused:

- Maksete edastamine panka (allkirjastamata maksed)

- Konto väljavõte -- automaatselt päritav eelmise päeva väljavõte

- Jooksva päeva kontoväljavõtte päring

### LHV

<https://www.lhv.ee/et/connect>

Toetatud teenused:

- Maksete edastamine panka (allkirjastamata maksed)

- Konto väljavõte -- automaatselt päritav eelmise päeva väljavõte

### SEB

<https://www.seb.ee/ariklient/igapaevapangandus/elektroonilised-kanalid/baltic-gateway>

Toetatud teenused:

- Maksete edastamine panka (allkirjastamata maksed)

- Jooksva päeva kontoväljavõtte päring (tööjärjekorra kanne tuleb seadistada piisava sagedusega, et päeva lõpust ei jääks mõni tehing pangast pärimata)

### COOP Pank

<https://www.cooppank.ee/gateway>

Toetatud teenused:

- Maksete edastamine panka (allkirjastamata maksed)

- Konto väljavõte -- automaatselt päritav eelmise päeva väljavõte

### Turvasertifikaat

Business Centralis tuleb pangaliidese kasutamiseks seadistada turvasertifikaat. Pärast lepingu sõlmimist saadab pank teile juhiseid sertifikaadi tellimiseks. Tegemist on tehniliste sammudega, mistõttu soovitame abi paluda oma IT osakonnast või pöörduda oma BC partneri poole, kes teid abistab.

Vajalik on:

- Sertifikaadipäringu koostamine, sertifikaadi tellimiseks.

- Sertifikaadi- ja privaatvõtmefaili liitmine pfx/p12 failiks ja parooli genereerimine.

- pfx/p12 faili ja parooli seadistamine BC-s.

Swedbank juhend:

<http://dev.swedbankgateway.net/content/general-info/doc/How-to-generate-CSR-and-convert-private-key-to-p12.pdf>

<https://www.swedbank.com/openbanking/swedbank-gateway-go-live.html>

LHV juhend:

<https://partners.lhv.ee/en/connect/#certificates>

SEB juhend:

<https://developer.baltics.sebgroup.com/bgw/documentation/authentication>

Coop Pank juhend:

<https://www.cooppank.ee/s3fs-public/juhendid/Gateway_votmete_genereerimise_juhend.pdf>

## Pangaliidese seadistamine

### Seadistamine kasutades juhendatud seadistust

Mine Juhendatud seadistus ning vali Set-Up OIXIO Bank Link

![]

Avaneb Pangaliidese seadistamine aken, kus tee vajalikud tegevused ning liigu Edasi nupu abil järgmiste sammude juurde.

![][1]

### Manuaalne pangaliidese seadistamine

Ava Business Centralis Pangaliidese seadistus ning vali liidestatav pank Panga kanalid blokist. Seadistatavad väljad on pankadel erinevad.

![][2]

**SWEDBANK SGW** puhul täida Lepingu ID, API võti (Kliendi ID), Parool väljad ning seejärel lae üles sertifikaat kasutades menüüribal nuppu Lisa sertifikaat:

![][3]

**SEB BGW** puhul täida lepingu ID väli ja lisa sertifikaat.

**LHV CONNECT** puhul tuleb ainult lisada sertifikaat.

**COOP CPGW** puhul tuleb ainult lisada sertifikaat.

### Pangakonto seadistus

Ava Pangakontod loend ning ava liidestatava pangakonto kaart, täida OIXIO Pangaliides blokis Panga kanal:

![][4]

Pangakonto kaardil peavad olema täidetud järgmised väljad:

- Maksekorralduste sõnumite numbrid

- Pangakonto konteeringurühm

- SWIFT tähis

- IBAN

- Panga väljavõtte impordi vorming

- Makse ekspordi vorming

### Tööjärjekorra kanded

Pane vastava panga tööjärjekorra kanded valmis olekusse.

![][5]

## Maksete eksportimine panka

Maksežurnaali töölehel tuleb märkida Luba maksete eksporti, et saaks maksefaili panka saata ja Kontrolli makse staatuseid enne konteerimist, et konteerimisel toimuks kontroll, kas mõni makse on tühistatud.

![][6]

Täida maksežurnaal sooritatavate maksetega kas käsitsi või soovitades makseid hankijale.

Maksefaili panka saatmiseks vali menüüribalt Pank -- Saada panka...

![][7]

Maksed liiguvad panka kinnitamata olekus. Need tuleb pangas eraldi kinnitada ja sooritada tehingud.

Pärast maksefaili panka saatmist ilmub mõne aja pärast maksežurnaali factboxi info makse oleku kohta:

![A screenshot of a computer Description automatically generated]

Makse olek näitab, mis seisus makse pangas on.

Võimalikud makse olekud:

- Tagasi lükatud -- makse pangas tagasi lükatud. SEB puhul tähendab Tagasi lükatud staatus, et makse impordifaili kontroll ei olnud edukas

- Ootel - ootab pangas makse kinnitamist ja sooritamist. SEB puhul tähendab Ootel staatus makse impordifaili kontrollimist

- Osaliselt kinnitatud -vähemalt üks makse on kinnitatud

- Kinnitatud -- makse on kinnitatud, kuid ülekanne veel tegemata

- Teostatud -- makse on sooritatud

- Aktsepteeritud koos muudatusega -- tehtud mõned muudatused ja aktsepteeritud, kuid ülekanne veel tegemata

- Faili kontroll edukas -makse impordifaili kontroll edukas (SEB)

## Panga maksefaili allkirjastamine

Panga maksefail on võimalik allkirjastada ka juba Business Centralis ja saata see panka allkirjastatud kujul. Selleks on vajalik DigiSign äpp.

### Seadistus

Panga maksete allkirjastamiseks määra pangakontole vaikimisi allkirjastajad.

Ava Pangakontod, mine pangakonto kaardile ja vali menüüribalt Pangakonto -\> Maksefaili vaikimisi allkirjastajad.

![][8]

Sisesta allkirjastaja nimi ja isikukood.

![][9]

Allkirjastajad ei pea olema BC kasutajad.

### Maksežurnaali allkirjastamine

Ava Maksežurnaal, lisa vajalikud maksed ja vali menüüribalt Pank -\> Allkirjasta ja saada panka.

![][10]

Avanevas aknas kuvatakse pangakontole määratud vaikimisi allkirjastajad. Vajadusel saad neid lisada või eemaldada.

![][11]

Pärast OK vajutamist küsitakse, kas soovid avada loodud allkirjastamise konteineri.

![][12]

Vali Jah, kui oled ise üks allkirjastajatest.

Avanevas allkirjastamise konteineris on juba üles laaditud maksefail. ![][13]

Plokis Allkirjastamise konteineri allkirjastajad saad lisada uusi ridu, kustutada allkirjastajaid ja alustada allkirjastamist.![][14]

Allkirjastamiseks vali Allkirjasta. Brauseris avaneb uus leht, kus saad valida sobiva allkirjastamise viisi ja alustada allkirjastamist.

![][15]

Pärast edukat allkirjastamist kuvatakse vastav teade.

![][16]

Kui kõik allkirjastajad on maksefaili allkirjastanud, muutub konteineri olek väärtuseks Allkirjastatud.

![][17]

Allkirjastatud konteineri saad panka saata menüüriba nupuga Saada panka

![][18]

või seadistada tööjärjekorra kande, mis saadab allkirjastatud maksed panka automaatselt.

![][19]

## Pangaväljavõtte import

### Käsitsi importimine

Maksete sobitamise žurnaalis vali Pangaliidese maksete importimine:

![][20]

Avanevas aknas vali, millise panga millist väljavõtte tüüpi soovid importida:

![][21]

**Päevalõpu väljavõte** -- saad määrata ainult lõppkuupäeva. BC-sse päritakse kõik selleks kuupäevaks importimata pangatehingud.

**Väljavõte** -- saad määrata perioodi, mille kohta pangaväljavõte päritakse BC-sse

**Päevasisene väljavõte** -- päritakse BC töökuupäeva väljavõte

Pärast filtrite määramist tuleb teade:

![A white background with black text Description automatically generated]

See tähendab, et päring on panga saadetud ja läheb natukene aega enne kui pangaväljavõte BC-sse ilmub. SEB väljavõte tekib kohe.

## Pangaväljavõtte automaatne import

Eelmise päeva kohta automaatselt imporditava pangaväljavõtte saamiseks tuleb seadistada Tööjärjekorra kanded all automaatne töö.

Mine Tööjärjekorra kanded ja vajuta Uus

Täida Käivitatava objekti liik Aruanne ja Käivitatava objekti ID 24009901, Varaseim alustamise kuup/kl:

![][22]

Varaseim alustamise kuup/kl täida sellega, millal soovid, et eelmise päeva väljavõte BC-sse päritakse.

Seejärel vajuta sisse marker Aruande päringuakna valikud:

![][23]

Avaneb sama vaade, mis maksete sobitamise žurnaalis Pangaliidese maksete importimine nupu vajutamisel.

Täida Pank, mille väljavõtet automaatselt importida soovid ja Väljavõtte liik lahtrist vali Päevalõpu väljavõte. Algkuupäev ja Lõppkuupäev väljad jäta tühjaks.

![][24]

Täida Korduvus blokis, mis päeviti päring teostatakse ja Minutite arv käivitamise vahel määra 1440, et kord päevas toimuks pangaväljavõtte päring:

![][25]

Iga pangakonto kohta tuleb teha eraldi tööjärjekorra kanne.

  []: ./media/et/image1.png
  [1]: ./media/et/image2.png
  [2]: ./media/et/image3.png
  [3]: ./media/et/image4.png
  [4]: ./media/et/image5.png
  [5]: ./media/et/image6.png
  [6]: ./media/et/image7.png
  [7]: ./media/et/image8.png
  [A screenshot of a computer Description automatically generated]: ./media/et/image9.png
  [8]: ./media/et/image10.png
  [9]: ./media/et/image11.png
  [10]: ./media/et/image12.png
  [11]: ./media/et/image13.png
  [12]: ./media/et/image14.png
  [13]: ./media/et/image15.png
  [14]: ./media/et/image16.png
  [15]: ./media/et/image17.png
  [16]: ./media/et/image18.png
  [17]: ./media/et/image19.png
  [18]: ./media/et/image20.png
  [19]: ./media/et/image21.png
  [20]: ./media/et/image22.png
  [21]: ./media/et/image23.png
  [A white background with black text Description automatically generated]: ./media/et/image24.png
  [22]: ./media/et/image25.png
  [23]: ./media/et/image26.png
  [24]: ./media/et/image27.png
  [25]: ./media/et/image28.png

