## <a name="product-number-identified-barcode-to-msdyn_productbarcodes"></a>Code-barres identifié par le numéro de produit vers msdyn_productbarcodes

Ce modèle synchronise les données entre les applications Finance and Operations et Common Data Service.

Champ Finance and Operations | Type de mappage | Autre champ Dynamics 365 | Valeur par défaut
---|---|---|---
PRODUCTNUMBER | > | msdyn_productnumberid.msdyn_productnumber | 
BARCODE | > | msdyn_name | 
BARCODE | > | msdyn_barcode | 
PRODUCTQUANTITY | > | msdyn_productquantity | 
PRODUCTDESCRIPTION | > | msdyn_productdescription | 
BARCODESETUPID | > | msdyn_barcodesetupid | 
PRODUCTQUANTITYUNITSYMBOL | > | msdyn_unitofmeasureid.msdyn_symbol | 
ISDEFAULTSCANNEDBARCODE | >> | msdyn_isdefaultscannedbarcode | 
ISDEFAULTPRINTEDBARCODE | >> | msdyn_isdefaultprintedbarcode | 
ISDEFAULTDISPLAYEDBARCODE | >> | msdyn_isdefaultdisplayedbarcode | 
