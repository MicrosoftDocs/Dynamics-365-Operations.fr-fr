---
title: Ajouter un canal à une hiérarchie d'organisation
description: Cette rubrique décrit comment ajouter un canal à une hiérarchie d'organisation dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 297bd34f9bde23d5cc7de266b8e8f49b1a752662
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993691"
---
# <a name="add-a-channel-to-an-organizational-hierarchy"></a>Ajouter un canal à une hiérarchie d'organisation


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment ajouter un canal à une hiérarchie d'organisation dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Les canaux doivent être associés à une ou plusieurs hiérarchies d'organisation. Avant de créer des canaux, vous devez confirmer que vos hiérarchies d'organisation ont été configurées.  

Voir [Hiérarchies d'organisation](channels-org-hierarchies.md) pour plus de détails sur la création de hiérarchies d'organisation.

## <a name="select-a-hierarchy"></a>Sélectionner une hiérarchie

Pour sélectionner une hiérarchie, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Hiérarchies d'organisation**.
1. Dans la liste, sélectionnez la hiérarchie d'organisation à laquelle vous allez ajouter le canal.
1. Dans le volet Actions, sélectionnez **Afficher** pour afficher les détails de la hiérarchie.

L'image suivante montre les détails de la hiérarchie d'organisation pour la hiérarchie sélectionnée.

![Détails de la hiérarchie d'organisation pour la hiérarchie sélectionnée](media/channel-add-to-org-hierarchy-1.png)

## <a name="add-a-channel-to-a-hierachy-node"></a>Ajouter un canal à un nœud de hiérarchie

Pour ajouter un canal à un nœud de hiérarchie, procédez comme suit.

1. Dans le volet Actions, sélectionnez **Modifier**.
1. Sélectionnez le nœud de hiérarchie auquel vous souhaitez ajouter le canal, puis dans la liste déroulante **Insérer**, sélectionnez **Canal de vente au détail**. 
1. Sélectionnez le canal à ajouter, puis le bouton **OK**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le volet Actions, sélectionnez **Publier** et fournissez une **Date d'effet** dans le passé pour que cette action entre en vigueur immédiatement.

L'image suivante montre comment sélectionner un canal à ajouter à un nœud de hiérarchie.

![Sélectionner un canal à ajouter à un nœud de hiérarchie](media/channel-add-to-org-hierarchy-2.png)

L'image suivante montre une hiérarchie avec plusieurs canaux ajoutés.

![Une hiérarchie avec plusieurs canaux ajoutés](media/channel-add-to-org-hierarchy-3.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation des canaux](channels-overview.md)

[Configuration requise pour le paramétrage de canaux](channels-prerequisites.md)

[Vue d'ensemble des organisations et des hiérarchies d'organisation](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planifier votre hiérarchie d'organisation](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Hiérarchies de l'organisation](channels-org-hierarchies.md)

[Paramétrer un canal de vente au détail](channel-setup-retail.md)
    
[Paramétrer un canal en ligne](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]