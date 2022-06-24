---
title: Créer un groupe de variantes
description: Cet article décrit comment créer un groupe de variantes de taille, de style ou de couleur pour un produit dans Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: a46dc9fd5cdb848818964e771d373924b217147a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874959"
---
# <a name="create-a-variant-group"></a>Créer un groupe de variantes


[!include [banner](includes/banner.md)]

Cet article décrit comment créer un groupe de variantes de taille, de style ou de couleur pour un produit dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Dynamics 365 Commerce prend en charge plusieurs variantes pour les produits. Il est idéal de configurer des groupes de variantes pour différentes catégories de produits. Par exemple, un groupe de tailles peut être créé pour les t-shirts de tailles XS, S, M, L et XL, ou un groupe de couleurs peut être créé pour inclure toutes les couleurs disponibles d’un produit. Les groupes de variantes doivent être ajoutés avant l’ajout de produits.

Dans cet article, un groupe de tailles sera créé et configuré. Des procédures similaires peuvent être utilisées pour ajouter et configurer des groupes de styles et des groupes de couleurs.

## <a name="create-a-size-group"></a>Créer un groupe de tailles

Pour créer un groupe de tailles, procédez comme suit.
 
1. Dans le Volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Produits et catégories \> Groupes de variantes \> Groupes de tailles**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la zone **Groupe de tailles**, entrez un nom unique pour le groupe de tailles.
1. Entrez une description adéquate dans la zone **Description**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

## <a name="add-attributes-to-the-size-group"></a>Ajouter des attributs au groupe de tailles

Pour ajouter des attributs à un groupe de tailles procédez comme suit.

1. Dans le Volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Produits et catégories \> Groupes de variantes \> Groupes de tailles**.
1. Dans le volet de navigation, sélectionnez un groupe de tailles.
1. Sous **Lignes de groupe de tailles**, sélectionnez **Ajouter**.
1. Dans la zone **Taille**, entrez une chaîner représentant la taille (par exemple, « XL »).
1. Dans la zone **Nom de la taille**, entrez un nom pour la taille (par exemple, « Extra Large »).
1. Dans la zone **Poids de réapprovisionnement**, entrez un nombre représentant le poids de réapprovisionnement.
1. Dans la zone **Numéro dans le code-barres**, entrez un nombre représentant le code-barres.
1. Dans la zone **Ordre d’affichage**, entrez un nombre représentant l’ordre d’affichage.
1. Lorsque vous avez terminé d’ajouter des tailles, sélectionnez **Enregister** dans le volet Actions.

L’image suivante montre un exemple de groupe de tailles pour « Tailles de chemises décontractées ».

![Créer un groupe de tailles.](media/create-variant-group.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des informations sur le produit](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[Paramétrer les produits vendus au détail](set-up-retail-products.md)

[Dimensions de produit](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]