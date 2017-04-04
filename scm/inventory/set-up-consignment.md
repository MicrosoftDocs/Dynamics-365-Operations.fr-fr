---
title: "Consignation de paramétrage"
description: "Cette rubrique explique comment configurer les opérations de stock de consignation entrant."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventJournalOwnershipChange, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 220804
ms.assetid: 88822f78-4de5-462c-a55f-1f766c572719
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: afa59439e06aad9d669eb352a9837a013f447249
ms.openlocfilehash: 48e3f7f33bedf33bee5a7c2882e90743feac8687
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-consignment"></a>Consignation de paramétrage

Cette rubrique explique comment configurer les opérations de stock de consignation entrant. 

Le stock de consignation est le stock qui appartient à un fournisseur, mais stocké à votre site. Lorsque vous êtes prêt à consommer ou à utiliser le stock, vous reprenez la propriété du stock. Cette rubrique décrit le paramétrage nécessaire pour activer les processus de consignation. Pour plus d'informations sur les processus de consignation, voir [Consignation](consignment.md).

## <a name="inventory-owners"></a>Propriétaires du stock
Pour enregistrer le stock de consignation entrant physique, vous devez définir un propriétaire fournisseur. Cette opération s'effectue sur la page **Propriétaire du stock**. Lorsque vous sélectionnez un **Compte fournisseur**, cette option génère des valeurs par défaut pour les champs **Nom** et **Propriétaire**. La valeur du champ **Propriétaire** est visible du fournisseur, vous pouvez le modifier si vos noms de comptes fournisseur ne sont pas faciles à reconnaître pour les personnes extérieures. Il est possible de modifier le champ **Propriétaire**, mais uniquement jusqu'à ce que vous enregistriez l'enregistrement **Propriétaire du stock**. Le champ **Nom** est rempli avec le nom du tiers auquel le compte fournisseur est associé, et il ne peut pas être modifié. 

[stock-propriétaires d'![] (. /media/inventory-owners.png)](. /media/inventory-owners.png)

## <a name="tracking-dimension-group"></a>Groupe de dimension de suivi
Les articles qui vont être utilisés dans les processus de consignation doivent être associés à un **Groupe de dimensions de suivi** dans lequel la dimension **Propriétaire** est définie sur **Active**. La dimension du propriétaire a toujours les options **Stock physique** et **Stock financier** sélectionnées. Le **Plan de couverture par dimension** n 'est jamais sélectionné. 

[groupe de dimensions de suivi d'![] (. /media/tracking-dimension-group.png)](. /media/tracking-dimension-group.png)

## <a name="inventory-ownership-change-journal"></a>Journal des modifications de propriété du stock
Le journal **Modifications de propriété du stock **est utilisé pour enregistrer le transfert de propriété du stock de consignation du fournisseur à l'entité juridique qui le consomme. Comme tout autre journal de stock, il doit être identifié avec un nom de journal de stock. Ces noms sont créés sur la page **Noms des journaux de stock** et **Type de journal** doit être défini sur **Modification de propriété**. 

[stock-propriété-modification-journal d'![] (. /media/inventory-ownership-change-journal.png)](. /media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Collaboration fournisseur dans les processus de consignation
Si vos fournisseurs utilisent l'interface de collaboration fournisseur, ils peuvent utiliser cette option pour contrôler la consommation du stock sur votre site. Pour plus d'informations sur le paramétrage des fournisseurs pour utiliser la collaboration fournisseur, voir [Configuration de sécurité pour les utilisateurs de collaboration fournisseur](../procurement/configure-security-vendor-portal-users.md).


