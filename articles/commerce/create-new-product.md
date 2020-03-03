---
title: Créer un nouveau produit
description: Cette rubrique décrit comment créer un produit dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 356bf91b2a946e7c0f5d5af9e2fe0b64342b856e
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001965"
---
# <a name="create-a-new-product"></a>Créer un nouveau produit


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment créer un produit dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un produit est principalement défini par un numéro, un nom, ainsi qu'une description du produit. Toutefois, d'autres données sont également nécessaires afin de décrire un produit ou un service :

## <a name="create-a-new-product"></a>Créer un nouveau produit

1. Dans le Volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Produits et catégories \> Produits lancés par catégorie**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la liste déroulante **Type de produit**, sélectionnez **Article** ou **Service**.
1. Dans la liste déroulante **Sous-type de produit**, sélectionnez **Produit** (si le produit n'aura pas de variantes) ou **Produit générique** (si le produit aura des variantes).
1. Dans la zone **Numéro de produit**, entrez un numéro de produit s'il n'est pas déjà prérempli.
1. Dans la zone **Nom de produit**, entrez un nom de produit.
1. Dans la zone **Nom de recherche**, entrez un nom de recherche.
1. Dans la liste déroulante **Catégorie de vente au détail**, sélectionnez une catégorie appropriée.
1. Si le produit est un kit, sélectionnez **Oui** pour **Kit de produits**.
1. Si le sous-type de produit est un produit générique, définissez le **Groupe de dimensions de produit** pour inclure les variantes prises en charge. Les options incluent les suivantes : **Couleur**, **Taille**, **Style** et **Configuration**. Vous devrez peut-être créer des groupes de dimensions de produit supplémentaires si nécessaire.
1. Dans la liste déroulante **Technologie de configuration**, sélectionnez une option appropriée.
1. Cliquez sur **OK**.

L'image suivant présente un exemple de produit ajouté.

![Créer un produit](media/create-new-product.png)

Une fois qu'un produit est ajouté, des données supplémentaires peuvent être paramétrées pour lui, telles que **Description du produit**, **Groupes de variantes**, **Groupes de dimensions**, **Attributs du produit** et **Produits connexes**.

L'image suivante montre les détails supplémentaires d'un produit.

![Détails de produit](media/create-new-product-2.png)

### <a name="create-product-variants"></a>Créer des variantes de produits

Si le sous-type de produit est **Produit générique**, des variantes spécifiques devront être créées. 

Pour créer des variantes de produits, procédez comme suit.

1. Dans le volet Actions, sélectionnez **Variantes de produit**.
1. Si des groupes de variantes ont été sélectionnés dans le volet Actions, sélectionnez **Suggestions de variantes*.
1. Sélectionnez les variantes que vous souhaitez prendre en charge pour le produit.
1. Sélectionnez **Créer**.

## <a name="release-a-product"></a>Lancement d'un produit

Pour vendre un produit, il doit d'abord être remis à une entité juridique.

1. Sur la page du produit, sélectionnez **Lancer des produits**.

    ![Lancer des produits](media/create-new-product-3.png)

1. Sélectionnez le produit à lancer, puis sélectionnez **Suivant**.

    ![Choisissez le produit à lancer](media/create-new-product-4.png)

1. Sélectionnez le jeu de variantes de produit à lancer, puis sélectionnez **Suivant**.

    ![Choisissez des variantes à lancer](media/create-new-product-5.png)

1. Sélectionnez l'entité juridique, puis sélectionnez **Suivant**.

    ![Choisir une entité juridique](media/create-new-product-6.png)

1. Sélectionnez **Terminer**.

    ![Terminer le lancement de produit](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a>Configurer un produit lancé

Une fois qu'un produit est lancé, il nécessitera alors une configuration supplémentaire qui comprend l'ajout d'un prix au produit.

1. Dans le Volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Produits et catégories \> Produits lancés par catégorie**.
1. Sélectionnez le nœud de catégorie de produit pour le produit qui a été lancé, puis sélectionnez le produit dans la liste des produits.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans la section **Achat**, configurez toutes les propriétés requises, y compris **Unité**, **Prix**  et **Quantité**.
1. Dans le volet Actions, sélectionnez **Valider** pour garantir qu'aucune erreur n'est signalée pour les champs manquants.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L'image suivante présente un exemple de configuration pour un produit lancé.

![Configurer un produit lancé](media/create-new-product-8.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Créer des entités juridiques](channels-legal-entities.md)

[Créer un groupe de variantes](create-variant-group.md) 