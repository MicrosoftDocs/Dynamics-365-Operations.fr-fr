---
title: Créer une hiérarchie de navigation du canal
description: Cette rubrique décrit comment créer une hiérarchie de navigation de canal dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: e83860667f142adcc85cd8542d521e18f16dbc2c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002034"
---
# <a name="create-a-channel-navigation-hierarchy"></a>Créer une hiérarchie de navigation du canal


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment créer une hiérarchie de navigation de canal dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Une hiérarchie de navigation de canal est utilisée pour regrouper et organiser les produits en catégories afin de pouvoir les parcourir en ligne ou dans un point de vente (PDV).

## <a name="create-a-channel-navigation-hierarchy"></a>Créer une hiérarchie de navigation du canal

Pour créer une hiérarchie de navigation du canal, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Produits et catégories \> Catégories de navigation du canal**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la zone **Nom**, entrez un nom.
1. Entrez une description dans la zone **Description**.
1. Sélectionnez **Créer**.
1. Dans le volet Actions, sélectionnez **Nouveau nœud de catégorie** pour créer un nœud racine.
1. Dans la zone **Nom**, entrez un nom.
1. Entrez une description dans la zone **Description**.
1. Dans la zone **Nom convivial**, entrez un nom convivial.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L'image suivante montre un exemple de nœud racine.

![Exemple de nœud racine](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a>Crer des nœuds de catégorie de navigation

Pour créer des nœuds de catégorie de navigation supplémentaires pour représenter les catégories de produits sur le canal, procédez comme suit.

1. Dans le volet de navigation, sélectionnez le nœud parent auquel ajouter une catégorie.
1. Dans le volet Actions, sélectionnez **Nouveau nœud de catégories**.
1. Dans la zone **Nom**, entrez un nom.
1. Entrez une description dans la zone **Description**.
1. Dans la zone **Nom convivial**, entrez un nom convivial.
1. Dans la zone **Ordre d'affichage**, entrez un ordre d'affichage (optionnel).
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L'image suivante montre un exemple d'une hiérarchie de navigation de canal terminée.

![Exemple de hiérarchie du canal](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a>Ajouter des produits à des nœuds de catégorie

Pour ajouter des produits à des nœuds de catégorie, procédez comme suit.

1. Sélectionnez un nœud de catégorie.
1. Sous **Produits**, sélectionnez **Ajouter**.
1. Recherchez les nouveaux produits que vous souhaitez ajouter à l'aide du numéro de produit ou du nom du produit, puis sélectionnez **OK**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

> [!NOTE]
> L'ajout de produits à un nœud à l'intérieur de la hiérarchie de navigation de canal n'est pas suffisant pour que les produits apparaissent sur un canal sélectionné, les produits doivent également être assortis à un produit.

L'image suivant présente un exemple de nœud avec produits ajoutés.

![Produits ajoutés à un nœud de catégorie](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a>Ajouter des groupes d'attributs de produit à des nœuds de catégorie

> [!NOTE]
> Les groupes d'attributs doivent être créés avant de pouvoir les ajouter à un nœud dans la hiérarchie de navigation des canaux.

Pour ajouter un produit d'un groupe d'attributs à un nœud de catégorie, procédez comme suit.

1. Sélectionnez un nœud de catégorie.
1. Sous **Groupe d'attributs de produit**, sélectionnez **Ajouter**.
1. Recherchez le ou les groupes d'attributs que vous souhaitez ajouter, puis sélectionnez **OK**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L'image suivant présente un exemple de nœud avec des groupes d'attributs de produits ajoutés.

![Groupes d'attributs de produit sur un nœud](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Paramétrer des assortiments](set-up-assortments.md)

[Gérer les attributs et les groupes d'attributs](attribute-attributegroups-lifecycle.md)