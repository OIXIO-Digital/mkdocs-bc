User Permissions

For a user with limited permissions (not SUPER), assign the permission set **CRF-DS DIGISIGNALL**.

Setup

On the **DigiSign Setup** page, complete the following steps:

- In the **Connection** section, choose **Setup \> Default Setup**. The URL fields are populated automatically.

![][1]

- In the **Certificate Information** section, enter the password and upload the certificate.

![][2]

You can order the certificate from your contact person at OIXIO Digital.

Document Signing

To sign a document, open the **Signing Containers** page and choose **New**.

Enter the file name. In the **Signing Container Documents** section, upload the document by choosing **Upload Files**.

![][3]

In the **Signing Container Signers** section, enter the Signer Name and Personal Code. If the signer exists in the **Employees** list, the fields are filled in automatically from the employee card when you enter **Employee No.**.

![][4]

To sign, choose **Sign**. A new browser page, **Sign Document**, opens, where you can choose the preferred signing method and start the signing process.

![][5]

After successful signing, the following information is shown:

![][6]

If signing is successful, the status changes to **Signed**, and the signing date and time are shown. You can download the signed document by choosing **Download Container File**.

![][7]

Possible signing statuses:

- Draft -- waiting to be signed

- Signing -- signing in progress

- Signed -- fully signed

Bank Payment File Signing

Setup

To sign bank payments, you must assign default signers to the bank account.

To do this, open **Bank Accounts**, select the bank account card, and then choose **Bank Account \> Default Payment File Signers**.

![][8]

Enter the Signer Name and Personal Code. If the signer exists in the **Employees** list, the fields are filled in automatically from the employee card when you enter **Employee No.**.

![][9]

The signers do not have to be Business Central users.

Payment Journal Signing

Open the **Payment Journal**, add the required payments, and choose **Bank \> Sign and Send to Bank**.

![][10]

In the window that opens, the default signers assigned to the bank account are shown. If needed, you can add or remove signers here.

![][11]

When you choose **OK**, you are asked: **Do you want to open the created signing container?**

![][12]

Choose **Yes** if you are one of the signers. This opens the **Signing Container**, where the payment file is already uploaded. In the **Signing Container Documents** section, you can view or download the payment file. By choosing **Upload Files**, you can add additional files for signing.

![][13]

In the **Signing Container Signers** section, you can add new lines, remove signers, and start the signing process.

![][14]

To sign, choose **Sign**. A new browser page, **Sign Document**, opens, where you can choose the preferred signing method and start the signing process.

![][15]

After successful signing, the following information is shown:

![][6]

When all signers have signed the payment file, the container header status changes to **Signed**.

![][16]

When the **Signing Container** status is **Signed**, you can send it to the bank by choosing **Send to Bank** on the action bar,

![][17]

or you can set up a job queue entry to send signed payments to the bank automatically.![][18]

  [1]: ./media/en/image1.png
  [2]: ./media/en/image2.png
  [3]: ./media/en/image3.png
  [4]: ./media/en/image4.png
  [5]: ./media/en/image5.png
  [6]: ./media/en/image6.png
  [7]: ./media/en/image7.png
  [8]: ./media/en/image8.png
  [9]: ./media/en/image9.png
  [10]: ./media/en/image10.png
  [11]: ./media/en/image11.png
  [12]: ./media/en/image12.png
  [13]: ./media/en/image13.png
  [14]: ./media/en/image14.png
  [15]: ./media/en/image15.png
  [16]: ./media/en/image16.png
  [17]: ./media/en/image17.png
  [18]: ./media/en/image18.png

