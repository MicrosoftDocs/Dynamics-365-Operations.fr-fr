---
title: Importer les APE entrants via l’entité de données V3
description: Cet article explique comment gérer l’importation des avis préalables d’expédition (ASN) entrants via l’entité de données ASN entrant.
author: GalynaFedorova
ms.date: 05/11/2022
ms.topic: article
ms.search.form: WHSInboundASNV3Entity, WHSInboundASNEntity, DMFEntity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-06-04
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 66ed258ebddaadb5a306f41dea3e439e9b5a7be3
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065861"
---
# <a name="import-inbound-asns-through-the-v3-data-entity"></a>Importer les APE entrants via l’entité de données V3

[!include [banner](../../includes/banner.md)]

Les avis préalables d’expédition (ASN) vous informent des livraisons des fournisseurs. Ils aident l’expéditeur à décrire le contenu d’un envoi et à donner des informations supplémentaires à son sujet, concernant par exemple les articles et l’emballage.

Les ASN peuvent aider les employés d’entrepôt à savoir ce qui arrive et quand. Ils peuvent se préparer en conséquence. De plus, les magasiniers peuvent utiliser les ASN pour faire correspondre les détails d’une expédition à la commande client associée qui a été créée précédemment.

Cet article présente une collection de scénarios qui montrent, à travers des exemples, comment utiliser les fichiers ASN.

> [!IMPORTANT]
> L’importation des *ASN entrants* ne s’applique qu’aux articles activés pour les processus de gestion des entrepôts (WMS). Avant de recevoir un ASN, une commande client doit être enregistrée dans le système par rapport au fournisseur qui envoie cet ASN.

## <a name="inbound-asn-v3-entity"></a>Entité ASN entrant V3

Vous importez les ASN entrants en utilisant l’entité de données composite *ASN entrant V3*. *ASN entrant V3* tire parti des entités suivantes :

- En-tête de la charge entrante
- En-tête d’expédition entrante
- Structures de conditionnement de la charge entrante
- Cas de structure de conditionnement de la charge entrante
- Lignes de cas de structure de conditionnement de la charge entrante
- Lignes de structure de conditionnement de la charge entrante

L’entité de données composite *ASN entrant V3* est destinée aux scénarios d’intégration asynchrones dans lesquels on utilise des importations basées sur des fichiers XML.

## <a name="xml-format-for-importing-asns"></a>Format XML pour l’importation des ASN

Microsoft Dynamics 365 Supply Chain Management prend en charge le format XML suivant pour l’importation des ASN. Chaque nœud du fichier XML représente un attribut d’une entité individuelle.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity>
        <WHSInboundShipmentHeaderEntity>
            <WHSInboundLoadPackingStructureEntity>
                <WHSInboundLoadPackingStructureCaseEntity>
                    <WHSInboundPackingStructureCaseLineV3Entity>
                    </WHSInboundPackingStructureCaseLineV3Entity>
                </WHSInboundLoadPackingStructureCaseEntity>
                <WHSInboundLoadPackingStructureLineV3Entity>
                </WHSInboundLoadPackingStructureLineV3Entity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="examples"></a>Exemples

Les sous-sections suivantes fournissent des exemples de fichiers XML d’importation d’ASN pour les expéditions de fournisseurs.

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre un fichier XML pour l’importation d’expéditions de fournisseurs pour une commande client lorsqu’aucun détail d’incident n’est inclus.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VENDORADDRESSSTREET = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="1" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant montre un fichier XML pour l’importation d’expéditions de fournisseurs pour une commande client lorsque des détails d’incident sont inclus.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity ESTIMATEDARRIVALDATETIME="2021-04-25T11:00:00+00:00">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="MVR_SNN_0004">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="MVR_SNN_0004" PACKEDTOTALQUANTITY="2.00">
                <WHSInboundLoadPackingStructureCaseEntity PARENTPACKINGSTRUCTURELICENSEPLATENUMBER="MVR_SNN_0004" LICENSEPLATENUMBER="MVR_SNN_0004A" PACKEDTOTALQUANTITY="2.00" />
                <WHSInboundLoadPackingStructureLine3Entity PURCHASEORDERNUMBER="00000175" ITEMNUMBER="A0001" PURCHASEORDERLINENUMBER="1" QUANTITY="2.00" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-3"></a>Exemple 3

L’exemple suivant montre un fichier XML pour l’importation d’expéditions de fournisseurs pour plusieurs commandes client lorsque des détails d’incident sont inclus.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="100" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_02" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="200" UNITSYMBOL="ea" />
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="P0004" QUANTITY="300" UNITSYMBOL="ea" ITEMBATCHNUMBER="BN0001" />
            </WHSInboundLoadPackingStructureEntity>
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_002">
                <WHSInboundLoadPackingStructureCaseEntity LICENSEPLATENUMBER="LP_ASN_002_C01">
                    <WHSInboundLoadPackingStructureCaseLineV3Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="400" UNITSYMBOL="ea" />
                </WHSInboundLoadPackingStructureCaseEntity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="inspect-the-results-of-importing-an-asn-file"></a>Inspecter les résultats de l’importation d’un fichier ASN

Procédez comme suit pour inspecter les résultats de l’importation d’un fichier ASN.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Recherchez et ouvrez un chargement qui a été créé dans le cadre d’une importation d’ASN.
1. Dans le raccourci **Chargement**, vous devez voir les valeurs basées sur le fichier XML.
1. Dans le raccourci **Lignes de chargement**, vous devez voir les numéros de commande client et les détails des articles basés sur le fichier XML.
1. Dans le volet Actions, dans l’onglet **Expédier et recevoir**, dans le groupe **Recevoir**, sélectionnez **Structure de conditionnement** pour examiner la structure de conditionnement du chargement.
1. Dans le raccourci **Palettes**, vous devez voir les contenants basés sur le fichier XML.
1. Dans le raccourci **Incidents**, vous devez voir les incidents basés sur le fichier XML.
1. Dans le raccourci **Articles**, vous devez voir les articles et quantités basés sur le fichier XML.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
