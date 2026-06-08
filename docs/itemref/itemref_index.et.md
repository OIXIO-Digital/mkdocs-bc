# **Smart Item Codes**

## Seadistused

Kasutajaõigused 

Kasutajale, kellel on piiratud õigused (mitte SUPER), peab määrama kasutaja õiguste komplekti

CPC-ITR PERMISSION

## Ostu seadistus

Ostuga seotud seadistused on „Ostude ja ostuv. seadistus" lehel plokis „Smart Item Codes"

![][1]

### Kaubakood ostudokumendil

![][2]

### Kauba viitenumber ostutellimusel

![][3]

## Müügi seadistus

Müügiga seotud seadistused on „Müügi ja müügivõlgade seadistus" lehel plokis „Smart Item Codes"

![][4]

### Kaubakood müügidokumendil

![][5]

### Kauba viitenumber müügitellimusel

![][6]

## Hankija seadistus

Hankijaga seotud seadistused on hankija kaardil plokis „Smart Item Codes".

![][7]

## Kliendi seadistus

Kliendiga seotud seadistused on kliendi kaardil plokis „Smart Item Codes".

![][8]

# Funktsionaalsused

Kasutatavad funktsionaalsused on seotud järgneva tabeli ja väljadega.

- Tabeli „Kaubaviidete loend" kirjetega.

![Pilt, millel on kujutatud tekst, Font, number, järjekord Tehisintellekti genereeritud sisu võib olla ebatõene.]

- Kaubakaardil olevate väljadega „Hankija kauba nr."

![][9]

- Hankija ja kliendi kaardil rippmenüüs „Kaubakood ostu(kliendi kaardil müügi)dokumendil"

![][7]

## Kaubakood ostu- või müügidokumendil 

Erinevate kaubakoodide kasutamine ostu- või müügidokumentide väljatrükil. Laiendus ei mõjuta Microsoft Base väljatrükke ja kasutamiseks tuleb vastavale väljatrüki laiendusele (näiteks Suno Base) lisada sõltuvus Suno Item Ref'ile.

Väljatrüki näide, kus muudetakse kaubakoodi väljatrükil. Müügi ja müügivõlgade seadistuses:

![][10]

![][11]

Võimalik on valida 5 erineva võimaluse vahel ostu või müügi seadistustes: Tühi (BC standard), Kaup, Vöötkood/hankija/Kaup, Hankija/vöötkood/kaup, Hankija kauba nr./kaup. Müügidokumentide puhul on Hankija asemel Klient.

![][12]

Võimalik on valida 5 erineva võimaluse vahel hankija või kliendi kaardil: Tühi (BC standard), Kaup, Vöötkood/hankija/Kaup, Hankija/vöötkood/kaup, Hankija kauba nr./kaup. Kliendi kaardi puhul on Hankija asemel Klient.

![][13]

Kehtib üldine loogika, et kui hankija või kliendi kaardil on mingi valik valitud, siis kehtib see ainult antud kliendi või hankija dokumentide puhul ja ühtlasi ei sõltu sellest, et mis on määratud ostu või müügi seadistustes.

Kõikide valikute puhul kehtib loogika, et iga valiku puhul kasutatakse järjekorras esimest leitud vastet. Näiteks: Vöötkood/hankija/kaup.

![][14]

![][15]

Sellise ostutellimuse puhul kasutatakse dokumentide väljatrükkide puhul tabelis „Kaubaviidete loend" leitud vöötkoodi viitenumbrit. Kui seda väärtust ei oleks tabelist leitud, siis oleks otsitud kaubaga seotud hankija koodi ja kui seda ei oleks ka leitud, siis oleks kasutatud kauba peal määratud kaubakoodi. Kui ükski neist otsingutest ei anna tulemust, siis lisatakse BC standard väärtus.

![][16]

## Kauba viitenumber ostu- või müügitellimusel 

Erinevate viitenumbrite kasutamine ostu- või müügitellimusel. Näide ostutellimuse välja Kauba viitenr. kohta.

![][17]

Võimalik on valida 4 erineva võimaluse vahel ostu või müügi seadistustes: Tühi (BC standard), Hankija/Vöötkood, Hankija/Vöötkood/Määramata, Vöötkood/Hankija. Müügitellimuste puhul on Hankija asemel Klient.

![][18]

Kõikide valikute puhul kehtib loogika, et iga valiku puhul kasutatakse järjekorras esimest leitud vastet. Näiteks: Hankija / Vöötkood /Määramata.

![][14]

![][17]

Sellise ostutellimuse puhul kasutatakse ostutellimuse real välja „Kauba viitenr." puhul tabelis „Kaubaviidete loend" leitud hankija viitenumbrit. Kui seda väärtust ei oleks tabelist leitud, siis oleks otsitud kaubaga seotud vöötkoodi ja kui seda ei oleks ka leitud, siis oleks otsitud tabelist määramata välja „Viite liik" seotud kaubakoodi. Kui ükski neist otsingutest ei anna tulemust, siis lisatakse BC standardi väärtus.

  [1]: ./media/et/image1.png
  [2]: ./media/et/image2.png
  [3]: ./media/et/image3.png
  [4]: ./media/et/image4.png
  [5]: ./media/et/image5.png
  [6]: ./media/et/image6.png
  [7]: ./media/et/image7.png
  [8]: ./media/et/image8.png
  [Pilt, millel on kujutatud tekst, Font, number, järjekord Tehisintellekti genereeritud sisu võib olla ebatõene.]: ./media/et/image9.png
  [9]: ./media/et/image10.png
  [10]: ./media/et/image11.png
  [11]: ./media/et/image12.png
  [12]: ./media/et/image13.png
  [13]: ./media/et/image14.png
  [14]: ./media/et/image15.png
  [15]: ./media/et/image16.png
  [16]: ./media/et/image17.png
  [17]: ./media/et/image18.png
  [18]: ./media/et/image19.png

