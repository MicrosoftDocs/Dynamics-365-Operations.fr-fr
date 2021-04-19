---
title: Créer un hiérarchie de produit
description: Cette rubrique décrit comment créer une hiérarchie de produit dans Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8aef33a501f43105730eaa21a9159eb1398a1b36
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799563"
---
# <a name="create-a-new-product-hierarchy"></a>Créer une hiérarchie de produits


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment créer une hiérarchie de produit dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Dynamics 365 Commerce prend en charge plusieurs canaux de vente au détail. Ces canaux de vente au détail comprennent les magasins en ligne, les centres d’appels et les magasins de vente au détail (également appelés magasins traditionnels). Chaque canal de magasin de vente au détail peut proposer son propre mode de paiement, ses propres groupes de prix, ses propres caisses enregistreuses de PDV, ses propres comptes de revenus et de dépenses et son propre personnel. Vous devez paramétrer tous ces éléments avant de pouvoir créer un canal de magasin de vente au détail. 

Une hiérarchie de produit Commerce est utilisée pour définir la hiérarchie des produits globale pour votre organisation. Vous pouvez utiliser une hiérarchie de produit Commerce pour la promotion des ventes, la tarification et les promotions, la génération d’états et la planification d’assortiment. Une seule hiérarchie de produits Commerce peut être affectée par organisation.

## <a name="create-and-configure-a-product-hierarchy"></a>Créer et configurer une hiérarchie de produit

Pour créer et configurer une hiérarchie de produit Commerce, procédez comme suit.

1. Dans le Volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Produits et catégories \> Hiérarchie de produit Commerce**.
1. Si aucune hiérarchie n’existe encore, dans le **Volet Actions**, sélectionnez **Nouveau** pour créer la racine de la hiérarchie.
1. Sous **Général** :
    1. Dans la zone **Nom**, entrez un nom.
    1. Entrez une description dans la zone **Description**.
    1. Dans la zone **Nom convivial**, entrez un nom convivial.
    1. Paramétrez **Actif** sur **Oui**.

## <a name="add-hierarchy-nodes"></a>Ajouter des nœuds de hiérarchie

Pour ajouter des nœuds de hiérarchie, procédez comme suit.

1. Dans le volet Actions, sélectionnez **Modifier la hiérarchie de catégories**.
1. Sélectionnez le nœud parent auquel vous souhaitez ajouter un nouveau nœud, puis sélectionnez **Nouveau nœud de catégorie**.
1. Dans la section **Général**, fournissez les éléments suivants : **Nom**, **Description**, **Nom convivial** et **Mots clés**.
1. Sous **Général** :
    1. Dans la zone **Nom**, entrez un nom.
    1. Entrez une description dans la zone **Description**.
    1. Dans la zone **Nom convivial**, entrez un nom convivial.
    1. Dans la zone **Mots clés**, saisissez les mots clés pertinents.
    1. Dans la zone **Ordre d’affichage**, entrez un nombre pour l’ordre d’affichage (optionnel).
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Répétez les étapes ci-dessus pour ajouter des nœuds supplémentaires.

L’image suivante montre la création d’un nœud de hiérarchie de produit.

![Créer un hiérarchie de produit](media/create-product-hierarchy.png)

## <a name="other-settings"></a>Autres paramètres

Des groupes d’attributs de catégorie peuvent également être affectés à chaque groupe selon les besoins.  

## <a name="additional-resources"></a>Ressources supplémentaires

[hiérarchies Commerce](retail-hierarchies.md)

[Gérer les produits et catégories de produits ](category-management-product-creation.md)

[Modifier l’ordre de tri pour les entités de promotion des ventes](custom-order-categories-nav-retail-prod-hierarchy.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]