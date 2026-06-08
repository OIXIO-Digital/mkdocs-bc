## Configurations

User permissions 

A user with limited rights (not SUPER) must be assigned the user permission set CPC-ITR PERMISSION

Purchase configurations

The configurations related to the purchases are on the "Purchase & Payables Setup" page in the " Smart Item Codes " block![][1]

**Item numbers on purchase documents**

![][2]

**Item** **reference numbers on purchase orders**

![][3]

### Sales configurations

The configurations related to sales are on the " Sales & Receivables Setup" page in the " Smart Item Codes " block![][4]

**Item numbers on sales documents**

![][5]

**Item reference numbers on sales orders**

![][6]

### Vendor configurations

Configurations related to the vendor are on the vendor card in the \" Smart Item Codes \" block.

![][7]

### Customer configurations

Configurations related to the customer are on the customer card in the \" Smart Item Codes \" block.

![][8]

## Functionality

The functionalities used are related to the following tables and fields.

- With the table entries in the "Item Reference List" table.

![Pilt, millel on kujutatud tekst, kuvatõmmis, number, Font Tehisintellekti genereeritud sisu võib olla ebatõene.]

- With the fields "Vendors item no." on the items card.

![][9]

- Vendor and customer card in the drop-down menu "Item code on purchase (sales on customer card) documents".

![][7]

### Item number on purchase or sales documents 

Use of different item numbers on the printout of purchase or sales documents. The extension does not affect Microsoft Base printouts, and to use it, a dependency on Suno Item Ref must be added to the corresponding printout extension (for example, Suno Base). An example of a printout where the item number is changed on the printout. Sales & Receivables Setup:

![][10]

![][11]

It is possible to choose between 5 different options in the purchase or sale configuration: Empty (BC standard), Item, Barcode/vendor/Item, Vendor/barcode/item, Vendor\'s item no./item. In the case of sales documents, it is the customer instead of the vendor.

![][12]

It is possible to choose between 5 different options in the purchase or sale configuration: Empty (BC standard), Item, Barcode/vendor/Item, Vendor/barcode/item, Vendor\'s item no./item. In the case of customer cards, it is the customer instead of the vendor.

![][13]

The general logic applies that if an option is selected on the vendor or customer card, it only applies to the given vendor's or customer's documents and does not depend on what is specified in the purchase or sales configuration.

For all the selections, the logic is that the first match found in the sequence is used. For example: Barcode/Vendor/Item.

![][14]

![][15]

For such a purchase order, the barcode reference number found in the \"Item Reference List\" table is used for document printouts. If this value was not found in the table, then the vendor code associated with the item would have been searched, and if it had not been found, then the item number specified on the item would have been used. If none of these searches yield a result, then the BC standard value is used.

![][16]

### Item reference number on purchase or sales order 

Using different reference numbers on a purchase or sales order. Example of a purchase order field item reference number.

![][17]

It is possible to choose between 4 different options in the purchase or sale configuration: Blank (BC standard), Vendor/Barcode, Vendor/Barcode/Unspecified, Barcode/Vendor. In the case of sales order, it is the Customer instead of the Vendor.

![][18]

For all the selections, the logic is that the first match found in the sequence is used. For example: Vendor/Barcode/Unspecified.

![][14]

![][17]

In the case of such a purchase order, the supplier\'s reference number found in the "Item reference list" table, is used in the purchase order line "Item Reference No". If this value was not found in the table, then the barcode related to the item would have been searched, and if it had not been found, then the item code without specifying field "Reference type" would have been searched in the table. If none of these searches yield a result, then the BC standard value is used.

  [1]: ./media/en/image1.png
  [2]: ./media/en/image2.png
  [3]: ./media/en/image3.png
  [4]: ./media/en/image4.png
  [5]: ./media/en/image5.png
  [6]: ./media/en/image6.png
  [7]: ./media/en/image7.png
  [8]: ./media/en/image8.png
  []: ./media/en/image9.png
  [9]: ./media/en/image10.png
  [10]: ./media/en/image11.png
  [11]: ./media/en/image12.png
  [12]: ./media/en/image13.png
  [13]: ./media/en/image14.png
  [14]: ./media/en/image15.png
  [15]: ./media/en/image16.png
  [16]: ./media/en/image17.png
  [17]: ./media/en/image18.png
  [18]: ./media/en/image19.png

