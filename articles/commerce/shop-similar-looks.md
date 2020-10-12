---
title: Activer les recommandations « acheter des aspects similaires »
description: Cette rubrique décrit comment activer les recommandations de produits « Acheter des aspects similaires » dans Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/06/2020
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
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: da957850072e233a41a042d5857f81ddbf178f7a
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818372"
---
# <a name="enable-shop-similar-looks-recommendations"></a>Activer les recommandations « acheter des aspects similaires »

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment activer les recommandations de produits « Acheter des aspects similaires » dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

La fonctionnalité de recommandations « Acheter des aspects similaires » dans Dynamics 365 Commerce utilise la puissance de l’intelligence artificielle et du Machine Learning (IA-ML) pour fournir des recommandations pour des produits visuellement similaires aux clients. En mettant à disposition des recommandations de type « acheter des aspects similaires » pour tous les canaux de vente au détail dans Commerce, les détaillants peuvent accroître la satisfaction de leurs clients en aidant les clients à trouver facilement ce qu’ils veulent.

La fonctionnalité de recommandations « Acheter des aspects similaires » utilise des images de produits de variantes de produits initiaux pour rechercher et recommander des produits visuellement similaires dans le catalogue de produits d’un détaillant. 

Les recommandations « Acheter des aspects similaires » sont disponibles dans les expériences de point de vente (PDV) et d’e-commerce.

### <a name="example-scenarios"></a>Exemple de scénarios

- Un client regarde un pull rayé noir et reçoit une recommandation pour un pull similaire en rouge. Le client sélectionne le produit recommandé au lieu du produit initialement consulté, puis reçoit des recommandations pour des produits similaires en rouge. 
- Un client utilise les recommandations « Acheter des aspects similaires » pour découvrir des boucles d’oreilles assorties à une bague qu’il souhaite acheter.

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a>Activer les recommandations « Acheter des aspects similaires » au siège Commerce

Les recommandations de produit sont uniquement prises en charge pour les utilisateurs de Commerce qui ont migré leur stockage pour utiliser Azure Data Lake Gen2.

### <a name="prerequisites"></a>Conditions préalables

Avant que les détaillants puissent commencer à montrer aux clients des recommandations « Acheter des aspects similaires », il y a deux étapes préalables :

- [Activer les recommandations de produits](enable-product-recommendations.md) au siège Commerce.
- Confirmez que le serveur multimédia prend en charge les appels HTTPS.

Pour que le moteur de recommandations accède aux images des produits, les détaillants doivent générer les URL des produits. Pour générer des URL de produits dans le siège Commerce, procédez comme suit.

1. Accédez à **Images de produits**.
1. Dans le volet Actions, sélectionnez **Définir le modèle de support**.
1. Dans le volet des propriétés **Définir le modèle de support**, sous **URL de support**, sélectionnez **Générer des URL**.

> [!NOTE]
> Lorsque vous activez la fonction de recommandations « Acheter des aspects similaires », le processus de génération de listes de recommandations de produits commence. Un jour peut être nécessaire avant que ces listes soient disponibles et visibles en ligne et aux terminaux de PDV.

Pour activer la fonctionnalité de recommandations « Acheter des aspects similaires » au siège Commerce, procédez comme suit.

1. Accédez à **Gestion des fonctionnalités**.
1. Dans la liste des fonctionnalités disponibles, recherchez et sélectionnez **Achetez des aspects similaires**.
1. Dans le volet droit, sélectionnez **Activer** pour activer le service.

L’illustration suivante montre la fonctionnalité **Acheter des aspects similaires** sur la page **Gestion des fonctionnalités** au siège Commerce.

![La fonctionnalité Acheter des aspects similaires sur la page Gestion des fonctionnalités du siège Commerce](./media/enableshopsimilarlooks.png)

Une fois les tâches précédentes terminées, les terminaux de PDV sont automatiquement améliorés avec un volet **Acheter des produits similaires**. En sélectionnant **En savoir plus**, les utilisateurs de terminaux de PDV peuvent être redirigés vers une page dédiée à la page « Acheter des aspects similaires » qui peut être filtrée davantage.

> [!NOTE]
> Si vous désactivez la fonctionnalité de recommandations « Acheter des aspects similaires », aucun autre type de recommandation de produit n’est affecté. Pour plus d’informations sur les recommandation de produit, voir [Vue d’ensemble des recommandations de produits](product-recommendations.md).

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a>Ajouter un bouton Acheter des aspects similaires aux pages de détails du produit à l’aide du générateur de site Commerce

Une fois que vous avez activé la fonctionnalité de recommandations « Acheter des aspects similaires » dans le siège Commerce, une option dans le générateur de site Commerce permet aux détaillants d’ajouter un bouton **Achetez des aspects similaires** dans la zone d’achat de n’importe quelle page de détails de produit (PDP). Un client qui clique sur ce bouton est redirigé vers une page dédiée « Acheter des aspects similaires » qui renvoie des produits visuellement similaires. Là, le client peut utiliser des sélecteurs pour filtrer davantage les produits.

Pour ajouter un bouton **Acheter des aspects similaires** à une PDP à l’aide du générateur de site Commerce, procédez comme suit.

1. Ouvrez une page de générateur de site existante qui contient un module de zone d’achat.
1. Dans le volet de navigation de gauche, sélectionnez le module de zone d’achat.
1. Dans le volet de navigation de droite, cochez la case **Activer le lien Acheter des aspects similaires**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier. Une fois la page publiée, la PDP comprendra un bouton **Achetez des aspects similaires**.

L’illustration suivante montre la case à cocher **Activer le lien Acheter des aspects similaires** et le bouton **Achetez des aspects similaires** sur un exemple de PDP dans le générateur de site.

![Case à cocher Activer le lien Acheter des aspects similaires et le bouton Achetez des aspects similaires sur une PDP dans le générateur de site](./media/SSLecomtooling.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des recommandations produit](product-recommendations.md)

[Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce](enable-adls-environment.md)

[Activer les recommandations produit](enable-product-recommendations.md)

[Désactiver les recommandations personnalisées](personalization-gdpr.md)

[Ajouter des recommandations produit sur PDV](product.md)

[Ajouter des recommandations à l’écran de transaction](add-recommendations-control-pos-screen.md)

[Ajuster des résultats des recommandations AI-ML](modify-product-recommendation-results.md)

[Créer manuellement des recommandations sélectionnées](create-editorial-recommendation-lists.md)

[Créer des recommandations avec des données de démonstration](product-recommendations-demo-data.md)

[FAQ sur les recommandations produit](faq-recommendations.md)
