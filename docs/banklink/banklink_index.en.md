# Baltic Bank Connect

## Signing a direct channel agreement with the bank gateway

To use the bank interface in Business Central, you need to sign a *gateway* direct channel agreement with your bank and order a certificate. The bank will provide instructions for ordering the certificate after the agreement is signed. The certificate file format must be .p12 and password-protected.

### Swedbank

<https://www.swedbank.ee/business/d2d/ebanking/gateway>

Supported services:

- Sending payments to the bank (unsigned payments)

- Account statement \-- automatically retrieves the previous day's statement

- Query for the current day's account statement

### LHV

<https://www.lhv.ee/et/connect>

Supported services:

- Sending payments to the bank (unsigned payments)

- Account statement \-- automatically retrieves the previous day's statement

### SEB

<https://www.seb.ee/ariklient/igapaevapangandus/elektroonilised-kanalid/baltic-gateway>

Supported services:

- Sending payments to the bank (unsigned payments)

- Query for the current day's account statement (the queue must be configured with sufficient frequency to avoid missing transactions at the end of the day)

### COOP Bank

<https://www.cooppank.ee/gateway>

Supported services:

- Sending payments to the bank (unsigned payments)

- Account statement \-- automatically retrieves the previous day's statement

## Security certificate

To use the bank interface in Business Central, you need to configure a security certificate. After signing the agreement, the bank will send instructions for ordering the certificate. As the steps involve technical details, it is recommended to seek assistance from your IT department or contact your BC partner.

Steps required:

- Generate a certificate request for ordering the certificate.

- Merge the certificate and private key files into a pfx/p12 file and generate a password.

- Configure the pfx/p12 file and password in BC.

Swedbank guide:

<http://dev.swedbankgateway.net/content/general-info/doc/How-to-generate-CSR-and-convert-private-key-to-p12.pdf>

<https://www.swedbank.com/openbanking/swedbank-gateway-go-live.html>

LHV guide:

<https://partners.lhv.ee/en/connect/#certificates>

SEB guide:

<https://developer.baltics.sebgroup.com/bgw/documentation/authentication>

Coop Bank guide:

<https://www.cooppank.ee/s3fs-public/juhendid/Gateway_votmete_genereerimise_juhend.pdf>

## Configuring the bank link setup

### Setting up using assisted setup

Go to Assisted Setup and select Set-up OIXIO Bank Link.

![]

Bank Link Set-up page opens, where you need to perform necessary actions and proceed to the next steps using the Next button.

![][1]

### Manual setup

Open Bank Link Setup in Business Central and select the bank to be integrated from the Bank Channels block. The fields to be configured differ by bank.

![A screenshot of a link setup AI-generated content may be incorrect.]

For **SWEDBANK SGW**, fill in the Agreement ID, API Key (Client ID) and Password fields, then upload the certificate using the Upload Certificate button on the menu bar:

![A screenshot of a computer screen AI-generated content may be incorrect.]

For **SEB BGW**, fill in the Agreement ID field and add the certificate.

For **LHV CONNECT**, only the certificate needs to be added.

For **COOP CPGW**, only the certificate needs to be added.

### Bank account configuration

Open the Bank Accounts list and access the card for the bank account to be integrated. Fill in the OIXIO Bank Interface block:

![A screenshot of a computer screen AI-generated content may be incorrect.][2]

The following fields must be completed on the bank account card:

- Credit Transfer Msg. Nos.

- Bank Acc. Posting Group

- SWIFT Code

- IBAN

- Bank Statement Import Format

- Payment Export Format

### Job queue entries

Set the job queue entries for the respective bank to the ready state.

![][3]

## Exporting payments to the bank

In the Payment Journal Batches, check **Allow Payment Export** to enable sending the payment file to the bank and **Check Payment Statuses** to verify the payment status before posting.

![][4]

Complete the Payment Journal with payments to be made, either manually or by suggesting payments for a vendor.

To send the payment file to the bank, select **Bank - Send To Bank\...** from the menu bar.

![][5]

Payments are sent to the bank in an unsigned state. They must be separately approved and executed in the bank.

After the payment file is sent to the bank, the Payment Journal factbox will display payment status information after a short while.

![A screenshot of a checklist AI-generated content may be incorrect.]

Possible payment statuses:

- **RJCT** - **Rejected** - the payment was rejected by the bank

- **ACTC** - **Pending** - awaiting approval and execution in the bank

- **PDNG** - **Pending** - awaiting confirmation

- **PART** - **Partially approved** - at least one payment is approved

- **ACSP** - **Approved** - the payment is approved but not yet executed

- **ACSC** - **Executed** - the payment has been executed

- **ACWC** - **Accepted with changes** - changes were made and accepted, but the payment is not yet executed

- **Pending** - the payment import file is being verified (SEB)

- **File check successful** - the payment import file verification was successful (SEB)

- **Rejected** - the payment import file verification was unsuccessful (SEB)

Bank Payment File Signing

Setup

To sign bank payments, you must assign default signers to the bank account.

To do this, open **Bank Accounts**, select the bank account card, and then choose **Bank Account \> Default Payment File Signers**.

![][6]

Enter the Signer Name and Personal Code. If the signer exists in the **Employees** list, the fields are filled in automatically from the employee card when you enter **Employee No.**.

![][7]

The signers do not have to be Business Central users.

Payment Journal Signing

Open the **Payment Journal**, add the required payments, and choose **Bank \> Sign and Send to Bank**.

![][8]

In the window that opens, the default signers assigned to the bank account are shown. If needed, you can add or remove signers here.

![][9]

When you choose **OK**, you are asked: **Do you want to open the created signing container?**

![][10]

Choose **Yes** if you are one of the signers. This opens the **Signing Container**, where the payment file is already uploaded. In the **Signing Container Documents** section, you can view or download the payment file. By choosing **Upload Files**, you can add additional files for signing.

![][11]

In the **Signing Container Signers** section, you can add new lines, remove signers, and start the signing process.

![][12]

To sign, choose **Sign**. A new browser page, **Sign Document**, opens, where you can choose the preferred signing method and start the signing process.

![][13]

After successful signing, the following information is shown:

![][14]

When all signers have signed the payment file, the container header status changes to **Signed**.

![][15]

When the **Signing Container** status is **Signed**, you can send it to the bank by choosing **Send to Bank** on the action bar,

![][16]

or you can set up a job queue entry to send signed payments to the bank automatically.![][17]

## Importing bank statements

### Manual import

In the Payment Reconciliation Journal, select **Bank Link Import Transactions**:

![][18]

In the window that opens, choose the type of statement to import for the desired bank:

![A screenshot of a bank account statement AI-generated content may be incorrect.]

- **End of Day Statement** - only the end date can be specified. All unimported bank transactions for this date will be retrieved into BC.

- **Past Days Statement** - specify a period for retrieving the bank statement into BC.

- **Intraday** - retrieves the BC's work date statement.

After setting the filters, a message will appear:

![A close-up of a computer screen AI-generated content may be incorrect.]

This means the query has been sent to the bank and it will take some time for the bank statement to appear in BC. SEB statements appear immediately.

## Automatic import of bank statements

To automatically import the previous day's bank statement, configure the **Job** **Queue Entries** for an automatic task.

Go to **Job** **Queue Entries** and click **New**.

Fill in the **Object Type to Run** with **Report** and **Object ID to Run** with 24009901, and set the **Earliest Start Date/Time**:

![][19]

Set the desired time for retrieving the previous day's statement into BC.

Then check the box for **Report Request Page Options**:

![A screenshot of a report AI-generated content may be incorrect.]

A view identical to **Bank Link Account Statement Request** in the Payment Reconciliation Journal will open.

Fill in the **Bank Account** field for the bank statement to be imported automatically and select **End of Day Statement** in the Statement Type field. Leave the **Start Date** and **End Date** fields blank.

![A screenshot of a login form AI-generated content may be incorrect.]

In the **Recurrence** section, specify which days the query should run and set the **No. Of Minutes between Runs** to **1440** to ensure the query is run daily.

![][20]

A separate queue entry must be created for each bank account.

  []: ./media/en/image1.png
  [1]: ./media/en/image2.png
  [A screenshot of a link setup AI-generated content may be incorrect.]: ./media/en/image3.png
  [A screenshot of a computer screen AI-generated content may be incorrect.]: ./media/en/image4.png
  [2]: ./media/en/image5.png
  [3]: ./media/en/image6.png
  [4]: ./media/en/image7.png
  [5]: ./media/en/image8.png
  [A screenshot of a checklist AI-generated content may be incorrect.]: ./media/en/image9.png
  [6]: ./media/en/image10.png
  [7]: ./media/en/image11.png
  [8]: ./media/en/image12.png
  [9]: ./media/en/image13.png
  [10]: ./media/en/image14.png
  [11]: ./media/en/image15.png
  [12]: ./media/en/image16.png
  [13]: ./media/en/image17.png
  [14]: ./media/en/image18.png
  [15]: ./media/en/image19.png
  [16]: ./media/en/image20.png
  [17]: ./media/en/image21.png
  [18]: ./media/en/image22.png
  [A screenshot of a bank account statement AI-generated content may be incorrect.]: ./media/en/image23.png
  [A close-up of a computer screen AI-generated content may be incorrect.]: ./media/en/image24.png
  [19]: ./media/en/image25.png
  [A screenshot of a report AI-generated content may be incorrect.]: ./media/en/image26.png
  [A screenshot of a login form AI-generated content may be incorrect.]: ./media/en/image27.png
  [20]: ./media/en/image28.png

