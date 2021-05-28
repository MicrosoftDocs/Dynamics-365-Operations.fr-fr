---
title: Activer les recommandations produit
description: Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l’Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/18/2020
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
ms.openlocfilehash: 873266405638cd277eb748ad7e966ba8a4976b13
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019857"
---
# <a name="enable-product-recommendations"></a>Activer les recommandations produit

[!include [banner](includes/banner.md)]

Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l’Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce. Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d’ensemble des recommandations produit.](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Recommandations avant contrôle

Avant l’activation, notez que les recommandations de produit sont uniquement prises en charge pour les clients Commerce qui ont migré leur stockage pour utiliser Azure Data Lake Storage. 

Les configurations suivantes doivent être activées dans le back-office avant d’activer les recommandations :

1. Assurez-vous qu’Azure Data Lake Storage a été acheté et validé avec succès dans l’environnement. Pour en savoir plus, voir [S’assurer qu’Azure Data Lake Storage a été acheté et validé avec succès dans l’environnement](enable-ADLS-environment.md).
2. Assurez-vous que l’actualisation du magasin d’entités a été automatisée. Pour plus d’informations, voir [S’assurer que l’actualisation du magasin d’entités a été automatisée](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
3. Confirmez que la configuration d’identité Azure AD contient une entrée pour les recommandations. Vous trouverez ci-dessous plus d’informations sur la façon d’effectuer cette action.

En outre, assurez-vous que les mesures RetailSale ont été activées. Pour en savoir plus sur ce processus de configuration, consultez [Utiliser les mesures](/dynamics365/ai/customer-insights/pm-measures).

## <a name="azure-ad-identity-configuration"></a>Configuration de l’identité Azure AD

Cette étape est requise pour tous les clients exécutant une configuration d’infrastructure en tant que service (IaaS). Pour les clients exécutant la structure de service (SF), cette étape doit être automatique et nous vous recommandons de vérifier que le paramètre est configuré comme prévu.

### <a name="setup"></a>Paramétrage

1. Depuis le back office, recherchez la page **Applications Azure Active Directory**.
2. Vérifiez s’il existe une entrée pour « RecommendationSystemApplication-1 ».

Si l’entrée n’existe pas, ajoutez-en une nouvelle avec les informations suivantes :

- **ID client** - d37b07e8-dd1c-4514-835d-8b918e6f9727
- **Nom** - RecommendationSystemApplication-1
- **Identifiant d’utilisateur** - RetailServiceAccount

Sauvegardez et fermez la page. 

## <a name="turn-on-recommendations"></a>Activer les recommandations

Pour activer les recommandations de produit, procédez comme suit.

1. Au siège de Commerce, recherchez **Gestion des fonctionnalités**.
1. Sélectionnez **Tout** pour voir une liste des fonctionnalités disponibles. 
1. Dans la zone de recherche, saisissez **Recommandations**.
1. Sélectionnez la fonctionnalité **Recommandations de produits**.
1. Dans le volet des propriétés **Recommandations de produits**, sélectionnez **Activer maintenant**.

![Activer les recommandations](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> Cette procédure démarre le processus de génération de listes de recommandations de produit. Cette opération peut nécessiter jusqu’à plusieurs heures avant que les listes soient disponibles et puissent s’affichent sur point de vente (PDV) ou dans Dynamics 365 Commerce.

## <a name="configure-recommendation-list-parameters"></a>Configuration des paramètres de la liste des recommandations

Par défaut, la liste des recommandations de produit basée sur Machine Learning - Intelligence artificielle fournit des valeurs suggérées. Vous pouvez modifier les valeurs suggérées par défaut pour les adapter au flux de votre entreprise. Pour en savoir plus sur la manière de modifier les paramètres par défaut, accédez à [Gérer les résultats de recommandation produit fondées sur l’IA et le ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Afficher les recommandations sur les appareils PDV

Après avoir activé les recommandations dans le back-office Commerce, le volet de recommandations doit être ajouté à l’écran du PDV de contrôle à l’aide de l’outil de disposition. Pour en savoir plus sur ce processus, voir [Ajouter un contrôle de recommandations à l’écran de transaction sur les périphériques de PDV](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Activer les recommandations personnalisées

Dans Dynamics 365 Commerce, les détaillants peuvent proposer des recommandations de produit personnalisées (également appelées personnalisation). Ainsi, des recommandations personnalisées peuvent être intégrées dans l’expérience client en ligne et au point de vente. Si la fonctionnalité de personnalisation est activée, le système peut associer les informations d’achat et de produit d’un utilisateur pour générer des recommandations de produit individualisées.

Pour plus d’informations sur les recommandations personnalisées, voir [Activer les recommandations personnalisées](personalized-recommendations.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des recommandations produit](product-recommendations.md)

[Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce](enable-adls-environment.md)

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