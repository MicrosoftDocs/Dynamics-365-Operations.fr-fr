---
title: Importer les ASN entrants via l’entité de données V2
description: Cette rubrique explique comment gérer l’importation des avis préalables d’expédition (ASN) entrants via l’entité de données ASN entrant V2.
author: GalynaFedorova
ms.date: 05/31/2021
ms.topic: article
ms.search.form: WHSInboundASNV2Entity, WHSInboundASNEntity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-04
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 470cc0c39f211a5d0f106c4c6e193867388e2b53
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249099"
---
# <a name="import-inbound-asns-through-the-v2-data-entity"></a><span data-ttu-id="88ece-103">Importer les ASN entrants via l’entité de données V2</span><span class="sxs-lookup"><span data-stu-id="88ece-103">Import inbound ASNs through the V2 data entity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="88ece-104">Les avis préalables d’expédition (ASN) vous informent des livraisons des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="88ece-104">Advanced shipping notices (ASNs) notify you about vendor deliveries.</span></span> <span data-ttu-id="88ece-105">Ils aident l’expéditeur à décrire le contenu d’un envoi et à donner des informations supplémentaires à son sujet, concernant par exemple les articles et l’emballage.</span><span class="sxs-lookup"><span data-stu-id="88ece-105">They help the sender describe the contents of a shipment and additional information about it, such as the items and packaging.</span></span>

<span data-ttu-id="88ece-106">Les ASN peuvent aider les employés d’entrepôt à savoir ce qui arrive et quand.</span><span class="sxs-lookup"><span data-stu-id="88ece-106">ASNs can help warehouse workers learn what is arriving when.</span></span> <span data-ttu-id="88ece-107">Ils peuvent se préparer en conséquence.</span><span class="sxs-lookup"><span data-stu-id="88ece-107">Therefore, they can prepare.</span></span> <span data-ttu-id="88ece-108">De plus, les magasiniers peuvent utiliser les ASN pour faire correspondre les détails d’une expédition à la commande client associée qui a été créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="88ece-108">In addition, warehouse workers can use ASNs to match the details of a shipment to the related purchase order that was previously created.</span></span>

<span data-ttu-id="88ece-109">Cette rubrique présente une collection de scénarios qui montrent, à travers des exemples, comment utiliser les fichiers ASN.</span><span class="sxs-lookup"><span data-stu-id="88ece-109">This topic presents a collection of scenarios that show, through examples, how to work with ASN files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88ece-110">L’importation des *ASN entrants* ne s’applique qu’aux articles activés pour la gestion avancée des entrepôts (WMS).</span><span class="sxs-lookup"><span data-stu-id="88ece-110">*Inbound ASN* import applies only to items that are enabled for advanced warehouse management (WMS).</span></span> <span data-ttu-id="88ece-111">Avant de recevoir un ASN, une commande client doit être enregistrée dans le système par rapport au fournisseur qui envoie cet ASN.</span><span class="sxs-lookup"><span data-stu-id="88ece-111">Before you receive an ASN, a purchase order must be registered in the system against the vendor who is sending that ASN.</span></span>

## <a name="inbound-asn-v2-entity"></a><span data-ttu-id="88ece-112">Entité ASN entrant V2</span><span class="sxs-lookup"><span data-stu-id="88ece-112">Inbound ASN V2 entity</span></span>

<span data-ttu-id="88ece-113">Vous importez les ASN entrants en utilisant l’entité de données composite *ASN entrant V2*.</span><span class="sxs-lookup"><span data-stu-id="88ece-113">You import inbound ASNs by using the *Inbound ASN V2* composite data entity.</span></span> <span data-ttu-id="88ece-114">*ASN entrant V2* tire parti des entités suivantes :</span><span class="sxs-lookup"><span data-stu-id="88ece-114">*Inbound ASN V2* takes advantage of the following entities:</span></span>

- <span data-ttu-id="88ece-115">En-tête de la charge entrante</span><span class="sxs-lookup"><span data-stu-id="88ece-115">Inbound load header</span></span>
- <span data-ttu-id="88ece-116">En-tête d’expédition entrante</span><span class="sxs-lookup"><span data-stu-id="88ece-116">Inbound shipment header</span></span>
- <span data-ttu-id="88ece-117">Structures de conditionnement de la charge entrante</span><span class="sxs-lookup"><span data-stu-id="88ece-117">Inbound load packing structures</span></span>
- <span data-ttu-id="88ece-118">Cas de structure de conditionnement de la charge entrante</span><span class="sxs-lookup"><span data-stu-id="88ece-118">Inbound load packing structure cases</span></span>
- <span data-ttu-id="88ece-119">Lignes de cas de structure de conditionnement de la charge entrante</span><span class="sxs-lookup"><span data-stu-id="88ece-119">Inbound load packing structure case lines</span></span>
- <span data-ttu-id="88ece-120">Lignes de structure de conditionnement de la charge entrante</span><span class="sxs-lookup"><span data-stu-id="88ece-120">Inbound load packing structure lines</span></span>

<span data-ttu-id="88ece-121">L’entité de données composite *ASN entrant V2* est destinée aux scénarios d’intégration asynchrones dans lesquels on utilise des importations basées sur des fichiers XML.</span><span class="sxs-lookup"><span data-stu-id="88ece-121">The *Inbound ASN V2* composite data entity is intended for asynchronous integration scenarios where XML file–based imports are used.</span></span>

## <a name="xml-format-for-importing-asns"></a><span data-ttu-id="88ece-122">Format XML pour l’importation des ASN</span><span class="sxs-lookup"><span data-stu-id="88ece-122">XML format for importing ASNs</span></span>

<span data-ttu-id="88ece-123">Microsoft Dynamics 365 Supply Chain Management prend en charge le format XML suivant pour l’importation des ASN.</span><span class="sxs-lookup"><span data-stu-id="88ece-123">Microsoft Dynamics 365 Supply Chain Management supports the following XML format for importing ASNs.</span></span> <span data-ttu-id="88ece-124">Chaque nœud du fichier XML représente un attribut d’une entité individuelle.</span><span class="sxs-lookup"><span data-stu-id="88ece-124">Each node in the XML file represents an attribute from an individual entity.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity>
        <WHSInboundShipmentHeaderEntity>
            <WHSInboundLoadPackingStructureEntity>
                <WHSInboundLoadPackingStructureCaseEntity>
                    <WHSInboundPackingStructureCaseLineV2Entity>
                    </WHSInboundPackingStructureCaseLineV2Entity>
                </WHSInboundLoadPackingStructureCaseEntity>
                <WHSInboundLoadPackingStructureLineV2Entity>
                </WHSInboundLoadPackingStructureLineV2Entity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="examples"></a><span data-ttu-id="88ece-125">Exemples</span><span class="sxs-lookup"><span data-stu-id="88ece-125">Examples</span></span>

<span data-ttu-id="88ece-126">Les sous-sections suivantes fournissent des exemples de fichiers XML d’importation d’ASN pour les expéditions de fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="88ece-126">The following subsections provide examples of ASN XML import files for vendor shipments.</span></span>

### <a name="example-1"></a><span data-ttu-id="88ece-127">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="88ece-127">Example 1</span></span>

<span data-ttu-id="88ece-128">L’exemple suivant montre un fichier XML pour l’importation d’expéditions de fournisseurs pour une commande client lorsqu’aucun détail d’incident n’est inclus.</span><span class="sxs-lookup"><span data-stu-id="88ece-128">The following example shows an XML file for importing vendor shipments for one purchase order when no case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VENDORADDRESSSTREET = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="1" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-2"></a><span data-ttu-id="88ece-129">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="88ece-129">Example 2</span></span>

<span data-ttu-id="88ece-130">L’exemple suivant montre un fichier XML pour l’importation d’expéditions de fournisseurs pour une commande client lorsque des détails d’incident sont inclus.</span><span class="sxs-lookup"><span data-stu-id="88ece-130">The following example shows an XML file for importing vendor shipments for one purchase order when case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity ESTIMATEDARRIVALDATETIME="2021-04-25T11:00:00+00:00">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="MVR_SNN_0004">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="MVR_SNN_0004" PACKEDTOTALQUANTITY="2.00">
                <WHSInboundLoadPackingStructureCaseEntity PARENTPACKINGSTRUCTURELICENSEPLATENUMBER="MVR_SNN_0004" LICENSEPLATENUMBER="MVR_SNN_0004A" PACKEDTOTALQUANTITY="2.00" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000175" ITEMNUMBER="A0001" PURCHASEORDERLINENUMBER="1" QUANTITY="2.00" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-3"></a><span data-ttu-id="88ece-131">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="88ece-131">Example 3</span></span>

<span data-ttu-id="88ece-132">L’exemple suivant montre un fichier XML pour l’importation d’expéditions de fournisseurs pour plusieurs commandes client lorsque des détails d’incident sont inclus.</span><span class="sxs-lookup"><span data-stu-id="88ece-132">The following example shows an XML file for importing vendor shipments for multiple purchase orders when case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="100" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_02" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="200" UNITSYMBOL="ea" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="P0004" QUANTITY="300" UNITSYMBOL="ea" ITEMBATCHNUMBER="BN0001" />
            </WHSInboundLoadPackingStructureEntity>
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_002">
                <WHSInboundLoadPackingStructureCaseEntity LICENSEPLATENUMBER="LP_ASN_002_C01">
                    <WHSInboundLoadPackingStructureCaseLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="400" UNITSYMBOL="ea" />
                </WHSInboundLoadPackingStructureCaseEntity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="inspect-the-results-of-importing-an-asn-file"></a><span data-ttu-id="88ece-133">Inspecter les résultats de l’importation d’un fichier ASN</span><span class="sxs-lookup"><span data-stu-id="88ece-133">Inspect the results of importing an ASN file</span></span>

<span data-ttu-id="88ece-134">Procédez comme suit pour inspecter les résultats de l’importation d’un fichier ASN.</span><span class="sxs-lookup"><span data-stu-id="88ece-134">Follow these steps to inspect the results of importing an ASN file.</span></span>

1. <span data-ttu-id="88ece-135">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="88ece-135">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="88ece-136">Recherchez et ouvrez un chargement qui a été créé dans le cadre d’une importation d’ASN.</span><span class="sxs-lookup"><span data-stu-id="88ece-136">Find and open a load that was created as part of an ASN import.</span></span>
1. <span data-ttu-id="88ece-137">Dans le raccourci **Chargement**, vous devez voir les valeurs basées sur le fichier XML.</span><span class="sxs-lookup"><span data-stu-id="88ece-137">On the **Load** FastTab, you should see values that are based on the XML file.</span></span>
1. <span data-ttu-id="88ece-138">Dans le raccourci **Lignes de chargement**, vous devez voir les numéros de commande client et les détails des articles basés sur le fichier XML.</span><span class="sxs-lookup"><span data-stu-id="88ece-138">On the **Load lines** FastTab, you should see purchase order numbers and item details that are based on the XML file.</span></span>
1. <span data-ttu-id="88ece-139">Dans le volet Actions, dans l’onglet **Expédier et recevoir**, dans le groupe **Recevoir**, sélectionnez **Structure de conditionnement** pour examiner la structure de conditionnement du chargement.</span><span class="sxs-lookup"><span data-stu-id="88ece-139">On the Action Pane, on the **Ship and receive** tab, in the **Receive** group, select **Packing structure** to review the packing structure of the load.</span></span>
1. <span data-ttu-id="88ece-140">Dans le raccourci **Palettes**, vous devez voir les contenants basés sur le fichier XML.</span><span class="sxs-lookup"><span data-stu-id="88ece-140">On the **Pallets** FastTab, you should see license plates that are based on the XML file.</span></span>
1. <span data-ttu-id="88ece-141">Dans le raccourci **Incidents**, vous devez voir les incidents basés sur le fichier XML.</span><span class="sxs-lookup"><span data-stu-id="88ece-141">On the **Cases** FastTab, you should see cases that are based on the XML file.</span></span>
1. <span data-ttu-id="88ece-142">Dans le raccourci **Articles**, vous devez voir les articles et quantités basés sur le fichier XML.</span><span class="sxs-lookup"><span data-stu-id="88ece-142">On the **Items** FastTab, you should see items and quantities that are based on the XML file.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
