---
title: Activer les recommandations produit
description: Cet article explique comment faire des recommandations de produit basées sur le Machine Learning et l’Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fc1b43fa70e6652d38b1141e2d93cf323f70a756
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460019"
---
# <a name="enable-product-recommendations"></a>Activer les recommandations produit

[!include [banner](includes/banner.md)]

Cet article explique comment faire des recommandations de produit basées sur le Machine Learning et l’Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce. Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d’ensemble des recommandations produit.](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Recommandations avant contrôle

1. Assurez-vous de disposer d'une licence Recommandations Dynamics 365 Commerce valide.
1. Assurez-vous que le magasin d'entités est connecté à un compte Azure Data Lake Storage Gen2 appartenant à un client. Pour en savoir plus, voir [S’assurer qu’Azure Data Lake Storage a été acheté et validé avec succès dans l’environnement](enable-ADLS-environment.md).
1. Confirmez que la configuration d’identité Azure AD contient une entrée pour les recommandations. Vous trouverez ci-dessous plus d’informations sur la façon d’effectuer cette action.
1. Assurez-vous que le magasin d'entités s'actualise quotidiennement sur Azure Data Lake Storage Gen2. Pour plus d’informations, voir [S’assurer que l’actualisation du magasin d’entités a été automatisée](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
1. Activez les mesures RetailSale pour le magasin d'entités. Pour plus d'informations sur la configuration de ce processus, consultez [Utiliser les mesures](/dynamics365/ai/customer-insights/pm-measures).
1. Veillez à ce que votre environnement ait configuré les régions de diffusion et de préparation dans les régions actuellement prises en charge, comme suit :

    - **Régions de préparation prises en charge :** UE/US/CA/AU.
    - **Régions de diffusion prises en charge :** UE/US/CA/AU. Si la région de diffusion ne correspond pas à l’une des régions prises en charge existantes, le service de recommandations sélectionnera la région de diffusion prise en charge la plus proche.

Une fois les étapes ci-dessus réalisées, vous serez prêt à activer les recommandations.

> [!NOTE]
> Il existe un problème connu où les recommandations n’apparaissent pas une fois les étapes suivantes terminées. Ce problème est lié à des problèmes de flux de données dans l’environnement. Si votre environnement n’affiche pas les résultats des recommandations, configurez les données alternatives pour le service de recommandations en suivant les étapes de la section [Configurer un autre flux de données pour les recommandations](set-up-alternate-data-flow.md). Vous devez disposer des autorisations d’administrateur Azure pour effectuer ces étapes. Si vous avez besoin d’aide, contactez votre représentant FastTrack.

## <a name="azure-ad-identity-configuration"></a>Configuration de l’identité Azure AD

Cette étape n’est requise que pour les clients exécutant une configuration d’infrastructure en tant que service (IaaS). Le configuration des identités Azure AD est automatique pour les clients exécutant Azure Service Fabric, mais il est recommandé de vérifier que les paramètres sont configurés comme prévu.

### <a name="setup"></a>Paramétrage

1. Dans Commerce Headquarters, recherchez la page **Applications Azure Active Directory**.
1. Vérifiez s’il existe une entrée pour **RecommendationSystemApplication-1**. S'il n'existe pas d'entrée, créez-en une en utilisant les informations suivantes :

    - **ID client** : d37b07e8-dd1c-4514-835d-8b918e6f9727
    - **Nom** : RecommendationSystemApplication-1
    - **Identifiant d’utilisateur** : RetailServiceAccount

1. Sauvegardez et fermez la page. 

## <a name="turn-on-recommendations"></a>Activer les recommandations

Pour activer les recommandations de produit, procédez comme suit.

1. Dans Commerce Headquarters, recherchez **Gestion des fonctionnalités**.
1. Sélectionnez **Tout** pour voir une liste des fonctionnalités disponibles. 
1. Dans la zone de recherche, saisissez **Recommandations**.
1. Sélectionnez la fonctionnalité **Recommandations de produits**.
1. Dans le volet des propriétés **Recommandations de produits**, sélectionnez **Activer maintenant**.

![Activer les recommandations.](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> - La procédure ci-dessus démarre le processus de génération de listes de recommandations de produit. Cette opération peut nécessiter jusqu’à plusieurs heures avant que les listes soient disponibles et puissent s’affichent sur point de vente (PDV) ou dans Dynamics 365 Commerce.
> - Cette configuration n'active pas toutes les fonctionnalités de recommandations. Les fonctionnalités avancées telles que les recommandations personnalisées, « Acheter des aspects similaires » et « Acheter une description similaire » sont contrôlées par des entrées dédiées de la gestion des fonctionnalités. Pour plus d'informations sur l'activation de ces fonctionnalités dans Commerce Headquarters, consultez [Activer les recommandations personnalisées](personalized-recommendations.md), [Activer les recommandations « Acheter des aspects similaires »](shop-similar-looks.md) et [Activer les recommandations « Acheter une description similaire »](shop-similar-description.md).

## <a name="configure-recommendation-list-parameters"></a>Configuration des paramètres de la liste des recommandations

Par défaut, la liste des recommandations de produit basée sur Machine Learning - Intelligence artificielle fournit des valeurs suggérées. Vous pouvez modifier les valeurs suggérées par défaut pour les adapter au flux de votre entreprise. Pour en savoir plus sur la manière de modifier les paramètres par défaut, accédez à [Gérer les résultats de recommandation produit fondées sur l’IA et le ML](modify-product-recommendation-results.md).

## <a name="include-recommendations-in-e-commerce-experiences"></a>Inclure des recommandations dans les expériences de commerce électronique

Après avoir activé les recommandations dans Commerce Headquarters, les modules Commerce utilisés pour afficher les résultats des recommandations pour les expériences de commerce électronique sont prêts à être configurés. Pour plus d’informations, voir [Modules de collecte de produits](product-collection-module-overview.md).

## <a name="show-recommendations-on-pos-devices"></a>Afficher les recommandations sur les appareils PDV

Après avoir activé les recommandations dans Commerce Headquarters, le volet de recommandations doit être ajouté à l’écran du PDV de contrôle à l’aide de l’outil de disposition. Pour en savoir plus sur ce processus, voir [Ajouter un contrôle de recommandations à l’écran de transaction sur les périphériques de PDV](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Activer les recommandations personnalisées

Dans Dynamics 365 Commerce, les détaillants peuvent proposer des recommandations de produit personnalisées (également appelées personnalisation). Ainsi, des recommandations personnalisées peuvent être intégrées dans l’expérience client en ligne et au point de vente. Si la fonctionnalité de personnalisation est activée, le système peut associer les informations d’achat et de produit d’un utilisateur pour générer des recommandations de produit individualisées.

Pour plus d’informations sur les recommandations personnalisées, voir [Activer les recommandations personnalisées](personalized-recommendations.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des recommandations produit](product-recommendations.md)

[Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce](enable-adls-environment.md)

[Configurer un autre flux de données pour les recommandations](set-up-alternate-data-flow.md)

[Activer les recommandations personnalisées](personalized-recommendations.md)

[Activer les recommandations « acheter des aspects similaires »](shop-similar-looks.md)

[Désactiver les recommandations personnalisées](personalization-gdpr.md)

[Ajouter des recommandations produit sur PDV](product.md)

[Ajouter des recommandations à l’écran de transaction](add-recommendations-control-pos-screen.md)

[Ajuster des résultats des recommandations AI-ML](modify-product-recommendation-results.md)

[Créer manuellement des recommandations sélectionnées](create-editorial-recommendation-lists.md)

[Créer des recommandations avec des données de démonstration](product-recommendations-demo-data.md)

[FAQ sur les recommandations produit](faq-recommendations.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]
