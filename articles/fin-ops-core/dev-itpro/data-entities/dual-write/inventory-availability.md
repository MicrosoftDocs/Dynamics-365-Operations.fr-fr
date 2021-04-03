---
title: Disponibilité du stock en double écriture
description: Cette rubrique fournit des informations sur la consultation de la disponibilité du stock en double écriture.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 48e54c043967ea5db15938857bd8f020dd4dfc64
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566737"
---
# <a name="inventory-availability-in-dual-write"></a>Disponibilité du stock en double écriture

[!include [banner](../../includes/banner.md)]

Grâce à la disponibilité du stock, vous pouvez consulter le stock avant d’ajouter un produit dans les formulaires **Devis**, **Commandes** ou **Factures** dans Microsoft Dynamics 365 Sales. Par exemple, la consultation du stock et la détermination d’une date de réalisation est une tâche clé du processus [prospects en disponibilités](dual-write-prospect-to-cash.md).

Si vous ne disposez pas d’un stock suffisant, vous pouvez estimer une date de livraison en fonction des entrées et sorties de stock prévues. Vous pouvez également vérifier les informations de disponibilité à la vente du produit (DAV), où vous pouvez trouver la quantité DAV dans la plage de temps prédéfinie.

## <a name="on-hand-inventory"></a>Stock disponible

Dans Dynamics 365 Sales, un nouveau bouton **Stock disponible** a été ajouté à l’en-tête des pages **Devis**, **Commandes** et **Factures**. Lorsque vous sélectionnez ce bouton, une boîte de dialogue apparaît et vous pouvez spécifier la société et le produit pour lesquels vous souhaitez vérifier le stock disponible. Cette boîte de dialogue affiche les mêmes informations que [Stock disponible](../../../../supply-chain/inventory/tasks/check-availability-stock.md).

La boîte de dialogue renvoie les informations de stock de Dynamics 365 Supply Chain Management. Ces informations incluent les quantités suivantes :

- Quantité disponible
- Quantité disponible réservée
- Quantité disponible à disposition
- Quantité commandée
- Quantité en commande
- Quantité commandée réservée
- Quantité totale disponible

## <a name="atp-information"></a>Informations sur DAV

Dans Sales, un nouveau bouton **Informations ATP** a été ajouté aux lignes dans les pages **Devis**, **Commandes** et **Factures**. Lorsque vous sélectionnez ce bouton, une boîte de dialogue apparaît et vous pouvez spécifier la société, le produit, le site de stockage, l’entrepôt et la quantité en commande. Cette boîte de dialogue a les mêmes paramètres que ceux décrits dans [Promesse de commande](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).

La boîte de dialogue renvoie les informations ATP de Supply Chain Management. Ces informations incluent les quantités suivantes :

- Quantité DAV
- Quantité de réception
- Quantité de sortie
- Quantité disponible

## <a name="how-it-works"></a>Comment ça fonctionne

Lorsque vous sélectionnez le bouton **Stock disponible** sur la page **Devis**, **Commandes** ou **Factures**, un appel de double écriture en direct est effectué vers l'API **Stock disponible**. L'API calcule le stock disponible pour le produit donné. Le résultat est stocké dans les tables **InventCDSInventoryOnHandRequestEntity** et **InventCDSInventoryOnHandEntryEntity** , puis est écrit dans Dataverse par la double écriture. Pour utiliser cette fonctionnalité, vous devez exécuter les mappages de double écriture suivants. Ignorez la synchronisation initiale lorsque vous exécutez les mappages.

- Entrées de stock CDS disponibles (msdyn_inventoryonhandentries)
- Demandes de stock CDS disponibles (msdyn_inventoryonhandrequests)

## <a name="templates"></a>Modèles
Les modèles suivants sont disponibles pour exposer les données de stock disponibles.

Applications Finance and Operations | Application Customer Engagement | Description  
---|---|---
[Entrées disponibles dans le stock CDS](#145) | msdyn_inventoryonhandentries |
[Demandes disponibles dans le stock CDS](#147) | msdyn_inventoryonhandrequests |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a>Entrées de stock CDS disponibles (msdyn_inventoryonhandentries)

Ce modèle synchronise les données entre les applications Finance and Operations et Dataverse.

Champ Finance and Operations | Type de mise en correspondance | Champ Customer Engagement | Valeur par défaut
---|---|---|---
`REQUESTID` | = | `msdyn_request.msdyn_requestid` |
`INVENTORYSITEID` | = | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | = | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`AVAILABLEONHANDQUANTITY` | > | `msdyn_availableonhandquantity` |
`AVAILABLEORDEREDQUANTITY` | > | `msdyn_availableorderedquantity` |
`ONHANDQUANTITY` | > | `msdyn_onhandquantity` |
`ONORDERQUANTITY` | > | `msdyn_onorderquantity` |
`ORDEREDQUANTITY` | > | `msdyn_orderedquantity` |
`RESERVEDONHANDQUANTITY` | > | `msdyn_reservedonhandquantity` |
`RESERVEDORDEREDQUANTITY` | > | `msdyn_reservedorderedquantity` |
`TOTALAVAILABLEQUANTITY` | > | `msdyn_totalavailablequantity` |
`ATPDATE` | = | `msdyn_atpdate` |
`ATPQUANTITY` | > | `msdyn_atpquantity` |
`PROJECTEDISSUEQUANTITY` | > | `msdyn_projectedissuequantity` |
`PROJECTEDONHANDQUANTITY` | > | `msdyn_projectedonhandquantity` |
`PROJECTEDRECEIPTQUANTITY` | > | `msdyn_projectedreceiptquantity` |
`ORDERQUANTITY` | > | `msdyn_orderquantity` |
`UNAVAILABLEONHANDQUANTITY` | > | `msdyn_unavailableonhandquantity` |

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a>Demandes de stock CDS disponibles(msdyn_inventoryonhandrequests)

Ce modèle synchronise les données entre les applications Finance and Operations et Dataverse.

Champ Finance and Operations | Type de mise en correspondance | Champ Customer Engagement | Valeur par défaut
---|---|---|---
`REQUESTID` | = | `msdyn_requestid` |
`PRODUCTNUMBER` | < | `msdyn_product.msdyn_productnumber` |
`ISATPCALCULATION` | << | `msdyn_isatpcalculation` |
`ORDERQUANTITY` | < | `msdyn_orderquantity` |
`INVENTORYSITEID` | < | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | < | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`REFERENCENUMBER` | < | `msdyn_referencenumber` |
`LINECREATIONSEQUENCENUMBER` | < | `msdyn_linecreationsequencenumber` |






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]