---
title: Activer les recommandations de produit personnalisées
description: Cette rubrique explique comment proposer des recommandations de produit personnalisées aux clients dans Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4103096f23e5568cc2bf64f21720c7c16d3e0cd1
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "3664856"
---
# <a name="enable-personalized-recommendations"></a>Activer les recommandations personnalisées

[!include [banner](includes/banner.md)]

Cette rubrique explique comment proposer des recommandations de produit personnalisées aux clients dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Dans Dynamics 365 Commerce, les détaillants peuvent proposer des recommandations de produit personnalisées (également appelées personnalisation). Ainsi, des recommandations personnalisées peuvent être intégrées dans l'expérience client en ligne et au point de vente (PDV). Si la fonctionnalité de personnalisation est activée, le système peut associer les informations d'achat et de produit d'un utilisateur pour générer des recommandations de produit individualisées.

## <a name="personalization-prerequisites"></a>Conditions préalables à la personnalisation

Avant de proposer des recommandations de produit personnalisées aux clients, notez que les recommandations de produit ne sont prises en charge que pour les utilisateurs Commerce qui ont migré leur stockage vers Azure Data Lake Store. Pour que les clients puissent recevoir les recommandations de produit personnalisées, les détaillants doivent [activer les recommandations de produit](enable-product-recommendations.md).

> [!NOTE]
> En activant les recommandations de produit, vous activez également la personnalisation. Cependant, si vous désactivez la personnalisation, vous ne désactivez pas les autres types de recommandations de produit.

Pour plus d'informations sur les recommandation de produit, voir [Vue d'ensemble des recommandations de produit](product-recommendations.md).

## <a name="turn-on-personalization"></a>Activer la personnalisation

Pour activer la personnalisation, procédez comme suit.

1. Accédez à **Retail et Commerce \> Recommandations de produit \> Paramètres des recommandations**.
1. Dans la liste des paramètres partagés de Retail, sélectionnez **Listes des recommandations**.
1. Définissez l'option **Activer la personnalisation** sur **Oui**.

![Activation de la personnalisation](./media/enablepersonalization.png)

> [!NOTE]
> Lorsque vous activez la personnalisation, la génération des listes de recommandations de produit personnalisées démarre. Un jour peut être nécessaire avant que ces listes soient disponibles et visibles en ligne et au point de vente.

## <a name="personalized-lists"></a>Listes personnalisées

Outre l'autorisation de la personnalisation des listes générées par machine existantes, le service des recommandations permet de personnaliser l'expérience de découverte des produits en ligne et au point de vente.

Après l'activation de la personnalisation, les détaillants peuvent montrer aux acheteurs des listes personnalisées « Nos choix pour vous » en ligne ou des listes « Recommandé pour le client » sur les terminaux de PDV. De plus, les détaillants peuvent appliquer la personnalisation aux listes de recommandations de produit existantes et fournir des expériences de désactivation du Règlement général sur la protection des données (RGPD) aux utilisateurs authentifiés. Si vous désactivez la personnalisation, vous désactivez également ces fonctionnalités.

### <a name="online-picks-for-you-lists"></a>Listes « Nos choix pour vous » en ligne

Une liste « Nos choix pour vous » est une liste d'apprentissage machine basée sur l'intelligence artificielle (AI-ML) qui communique à un utilisateur authentifié une liste personnalisée de produits suggérés. Cette liste est basée sur l'historique d'achat omnicanal de l'utilisateur. Les recommandations personnalisées sont mises à jour dynamiquement à mesure que l'utilisateur effectue plus d'achats. Ce type de liste prend également en charge le filtrage par catégorie, afin que les détaillants puissent afficher les meilleurs choix, en fonction des hiérarchies de navigation.

Pour pouvoir afficher la liste « Nos choix pour vous » sur une page de commerce électronique, les exigences utilisateur suivantes doivent être remplies :

- L'utilisateur doit être connecté. Les utilisateurs anonymes n'affichent pas les recommandations personnalisées.
- L'utilisateur doit avoir au moins un achat sur le compte.
- Les utilisateurs doivent accepter la réception des recommandations personnalisées.

L'illustration suivante donne l'exemple d'une liste « Nos choix pour vous » sur la page d'une boutique en ligne.

![Listes Nos choix pour vous en ligne](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a>Listes « Recommandé pour le client » au point de vente

Pour améliorer leur expérience de clientèle, les détaillants peuvent personnaliser les pages de détails client existantes en ajoutant une liste contextuelle « Recommandé pour le client ».

L'illustration suivante donne l'exemple d'une liste « Recommandé pour le client » sur un terminal de PDV.

![Listes Recommandé pour le client au point de vente](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a>Appliquer la personnalisation aux listes de recommandations existantes

Les détaillants peuvent appliquer la personnalisation aux listes de recommandations existantes, telles que « Nouveau », « Tendance », « Meilleure vente », « D'autres clients aiment également » et « Fréquemment achetés ensemble ». Lorsque la personnalisation est appliquée aux listes existantes, les articles précédemment achetés par un utilisateur connecté sont supprimés de ces listes. Pour les utilisateurs anonymes et les utilisateurs qui ont refusé de recevoir les recommandations personnalisées, les versions par défaut des listes existantes sont affichées. Par conséquent, les détaillants n'ont pas à gérer manuellement des expériences de page distinctes.

Par exemple, un utilisateur connecté a déjà acheté la montre noire et les bottes de travail marron qui apparaissent dans la liste « Tendance - Par défaut » dans l'illustration suivante. Par conséquent, l'utilisateur affiche de nouveaux produits en remplacement de ces produits, comme indiqué dans la liste « Tendance - Personnalisée ».

![Application de la personnalisation](./media/applypersonalization.png)

Pour appliquer la personnalisation à une liste de recommandations existante dans le générateur de site Commerce, procédez comme suit.

1. Ouvrez une page de générateur de site existante qui contient un module de collecte de produits.
1. Dans le volet de navigation de gauche, sélectionnez le module de collecte de produits.
1. Dans le volet de navigation de droite, sous **Produits**, sélectionnez la liste.
1. Dans la boîte de dialogue **Sélectionner la configuration de liste de produit**, sous **Type**, sélectionnez le type de liste.
1. Cochez la case **Appliquer la personnalisation**, puis sélectionnez **OK**.

    ![Application de la personnalisation à une liste de tendances](./media/ApplyPersonalizationToTrending.PNG)

1. Enregistrez la page, terminez de la modifier, puis publiez-la. Après la publication de la page, les utilisateurs connectés affichent les listes de tendances personnalisées.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des recommandations produit](product-recommendations.md)

[Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce](enable-adls-environment.md)

[Activer les recommandations produit](enable-product-recommendations.md)

[Activer les recommandations « acheter des aspects similaires »](shop-similar-looks.md)

[Désactiver les recommandations personnalisées](personalization-gdpr.md)

[Ajouter des recommandations produit sur PDV](product.md)

[Ajouter des recommandations à l'écran de transaction](add-recommendations-control-pos-screen.md)

[Ajuster des résultats des recommandations AI-ML](modify-product-recommendation-results.md)

[Créer manuellement des recommandations sélectionnées](create-editorial-recommendation-lists.md)

[Créer des recommandations avec des données de démonstration](product-recommendations-demo-data.md)

[FAQ sur les recommandations produit](faq-recommendations.md)
