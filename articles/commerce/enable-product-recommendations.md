---
title: Activer les recommandations produit
description: Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l'Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d38d7b0e98d84e23d7a51c5d8ee65df4a3b9e4a7
ms.sourcegitcommit: dbff1c6bb371a443a0cd2a310f5a48d5c21b08ca
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2020
ms.locfileid: "3259792"
---
# <a name="enable-product-recommendations"></a>Activer les recommandations produit

[!include [banner](includes/banner.md)]

Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l'Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce. Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d'ensemble des recommandations produit.](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Recommandations avant contrôle

Avant l'activation, notez que les recommandations de produit sont uniquement prises en charge pour les clients Commerce qui ont migré leur stockage pour utiliser Azure Data Lake Storage (ADLS). 

Les configurations suivantes doivent être activées dans le back-office avant d'activer les recommandations :

1. Assurez-vous qu'ADLS a été acheté et validé avec succès dans l'environnement. Pour en savoir plus, voir [S'assurer qu'ADLS a été acheté et validé avec succès dans l'environnement](enable-ADLS-environment.md).
2. Assurez-vous que l'actualisation du magasin d'entités a été automatisée. Pour plus d'informations, voir [S'assurer que l'actualisation du magasin d'entités a été automatisée](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
3. Confirmez que la configuration d'identité Azure AD contient une entrée pour les recommandations. Vous trouverez ci-dessous plus d'informations sur la façon d'effectuer cette action.

En outre, assurez-vous que les mesures RetailSale ont été activées. Pour en savoir plus sur ce processus de configuration, consultez [Utiliser les mesures](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).

## <a name="azure-ad-identity-configuration"></a>Configuration de l'identité Azure AD

Cette étape est requise pour tous les clients exécutant une configuration d'infrastructure en tant que service (IaaS). Pour les clients exécutant la structure de service (SF), cette étape doit être automatique et nous vous recommandons de vérifier que le paramètre est configuré comme prévu.

### <a name="setup"></a>Paramétrage

1. Depuis le back office, recherchez la page **Applications Azure Active Directory**.
2. Vérifiez s'il existe une entrée pour « RecommendationSystemApplication-1 ».

Si l'entrée n'existe pas, ajoutez-en une nouvelle avec les informations suivantes :

- **ID client** - d37b07e8-dd1c-4514-835d-8b918e6f9727
- **Nom** - RecommendationSystemApplication-1
- **Identifiant d'utilisateur** - RetailServiceAccount

Sauvegardez et fermez la page. 

## <a name="turn-on-recommendations"></a>Activer les recommandations

Pour activer les recommandations de produit, procédez comme suit.

1. Accédez à **Commerce et vente au détail &gt; Recommandations de produit &gt; Paramètres des recommandations**.
1. Dans la liste des paramètres partagés, sélectionnez **Listes des recommandations**.
1. Définissez l'option **Activer les recommandations** sur **Oui**.

![Activer les recommandations](./media/enablepersonalization.png)

> [!NOTE]
> Cette procédure démarre le processus de génération de listes de recommandations de produit. Cette opération peut nécessiter jusqu'à plusieurs heures avant que les listes soient disponibles et puissent s'affichent sur point de vente (PDV) ou dans Dynamics 365 Commerce.

## <a name="configure-recommendation-list-parameters"></a>Configuration des paramètres de la liste des recommandations

Par défaut, la liste des recommandations de produit basée sur Machine Learning - Intelligence artificielle fournit des valeurs suggérées. Vous pouvez modifier les valeurs suggérées par défaut pour les adapter au flux de votre entreprise. Pour en savoir plus sur la manière de modifier les paramètres par défaut, accédez à [Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Afficher les recommandations sur les appareils PDV

Après avoir activé les recommandations dans le back-office Commerce, le volet de recommandations doit être ajouté à l'écran du PDV de contrôle à l'aide de l'outil de disposition. Pour en savoir plus sur ce processus, voir [Ajouter un contrôle de recommandations à l'écran de transaction sur les périphériques de PDV](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Activer les recommandations personnalisées

Dans Dynamics 365 Commerce, les détaillants peuvent proposer des recommandations de produit personnalisées (également appelées personnalisation). Ainsi, des recommandations personnalisées peuvent être intégrées dans l'expérience client en ligne et au point de vente. Si la fonctionnalité de personnalisation est activée, le système peut associer les informations d'achat et de produit d'un utilisateur pour générer des recommandations de produit individualisées.

Pour plus d'informations sur les recommandations personnalisées, voir [Activer les recommandations personnalisées](personalized-recommendations.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des recommandations produit](product-recommendations.md)

[Activer ADLS dans un environnement Dynamics 365 Commerce](enable-adls-environment.md)

[Activer les recommandations personnalisées](personalized-recommendations.md)

[Désactiver les recommandations personnalisées](personalization-gdpr.md)

[Ajouter des recommandations produit sur PDV](product.md)

[Ajouter des recommandations à l'écran de transaction](add-recommendations-control-pos-screen.md)

[Ajuster des résultats des recommandations AI-ML](modify-product-recommendation-results.md)

[Créer manuellement des recommandations sélectionnées](create-editorial-recommendation-lists.md)

[Créer des recommandations avec des données de démonstration](product-recommendations-demo-data.md)

[FAQ sur les recommandations produit](faq-recommendations.md)

