---
title: Disponibilité du stock en double écriture
description: Cet article fournit des informations sur la consultation de la disponibilité du stock en double écriture.
author: RamaKrishnamoorthy
ms.date: 05/26/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: efd175dfbe49549561bdb7d697c8bc47016f1d5d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908260"
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

Lorsque vous sélectionnez le bouton **Stock disponible** sur la page **Devis**, **Commandes** ou **Factures**, un appel de double écriture en direct est effectué vers l’API **Stock disponible**. L’API calcule le stock disponible pour le produit donné. Le résultat est stocké dans les tables **InventCDSInventoryOnHandRequestEntity** et **InventCDSInventoryOnHandEntryEntity** , puis est écrit dans Dataverse par la double écriture. Pour utiliser cette fonctionnalité, vous devez exécuter les mappages de double écriture suivants. Ignorez la synchronisation initiale lorsque vous exécutez les mappages.

- Entrées de stock CDS disponibles (msdyn_inventoryonhandentries)
- Demandes de stock CDS disponibles (msdyn_inventoryonhandrequests)

## <a name="templates"></a>Modèles

Les modèles suivants sont disponibles pour exposer les données de stock disponibles.

Applications de finances et d'opérations | Applications Customer Engagement     | Description
---|---|---
[Entrées disponibles dans le stock CDS](mapping-reference.md#145) | msdyn_inventoryonhandentries |
[Demandes disponibles dans le stock CDS](mapping-reference.md#147) | msdyn_inventoryonhandrequests |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
