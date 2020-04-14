---
title: Activer ADLS dans un environnement Dynamics 365 Commerce
description: Cette rubrique explique comment activer et tester Azure Data Lake Storage (ADLS) pour un environnement Dynamics 365 Commerce, ce qui est une condition préalable à l'activation des recommandations de produits.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
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
ms.openlocfilehash: 3c037f5603af5af84917084eefa1edd508891c0d
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154434"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a>Activer ADLS dans un environnement Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cette rubrique explique comment activer et tester Azure Data Lake Storage (ADLS) pour un environnement Dynamics 365 Commerce, ce qui est une condition préalable à l'activation des recommandations de produits.

## <a name="overview"></a>Vue d'ensemble

Dans la solution Dynamics 365 Commerce, toutes les informations sur les produits et les transactions sont suivies dans le magasin des entités de l'environnement. Pour rendre ces données accessibles à d'autres services Dynamics 365, tels que l'analyse de données, le décisionnel et les recommandations personnalisées, il est nécessaire de connecter l'environnement à une solution appartenant au client Azure Data Lake Storage Gen 2 (ADLS).

Comme ADLS est configuré dans un environnement, toutes les données nécessaires sont reflétées à partir du magasin d'entités tout en étant protégées et sous le contrôle du client.

Si des recommandations de produits ou des recommandations personnalisées sont également activées dans l'environnement, la pile de recommandations de produits se verra accorder l'accès au dossier dédié dans ADLS pour récupérer les données du client et calculer des recommandations en fonction de celles-ci.

## <a name="prerequisites"></a>Conditions préalables

Les clients doivent avoir ADLS configuré dans un abonnement Azure qu'ils possèdent. Cette rubrique ne couvre pas l'achat d'un abonnement Azure ni la configuration d'un compte de stockage compatible ADLS.

Pour plus d'informations sur ADLS, voir [Documentation ADLS officielle](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Étapes de configuration

Cette section couvre les étapes de configuration nécessaires pour activer ADLS dans un environnement.

### <a name="enable-adls-in-the-environment"></a>Activer ADLS dans l'environnement

1. Connectez-vous au portail de back-office de l'environnement.
1. Recherchez **Paramètres système** et accédez à l'onglet **Connexions de données**. 
1. Paramétrez **Activer l'intégration de Data Lake** sur **Oui**.
1. Paramétrez **Actualiser le Data Lake** sur **Oui**.
1. Puis entrez les informations requises suivantes :
    1. **ID d'application** // **Secret de l'application** // **Nom DNS** - Nécessaire pour se connecter à KeyVault où le secret ADLS est stocké.
    1. **Nom du secret** - Le nom du secret stocké dans KeyVault et utilisé pour s'authentifier auprès d'ADLS.
1. Enregistrez vos modifications dans le coin supérieur gauche de la page.

L'image suivante présente un exemple de configuration ADLS.

![Exemple de configuration ADLS](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a>Tester la connexion ADLS

1. Testez la connexion à KeyVault à l'aide du lien **Tester Azure Key Vault**.
1. Testez la connexion à ADLS à l'aide du lien **Tester Azure Key Vault**.

> [!NOTE]
> Si les tests échouent, vérifiez que toutes les informations KeyVault ajoutées ci-dessus sont correctes, puis réessayez.

Une fois les tests de connexion réussis, vous devez activer l'actualisation automatique pour le magasin d'entités.

Pour activer l'actualisation automatique pour le magasin d'entités, procédez comme suit.

1. Recherchez **Magasin d'entités**.
1. Dans la liste de gauche, accédez à l'entrée **RetailSales**, puis sélectionnez **Éditer**.
1. Veillez à ce que l'option **Actualisation automatique activée** soit réglée sur **Oui**, sélectionnez **Actualiser**, puis sélectionnez **Enregistrer**.

L'image suivante montre un exemple de magasin d'entités avec l'actualisation automatique activée.

![Exemple de magasin d'entités avec l'actualisation automatique activée](./media/exampleADLSConfig2.png)

ADLS est maintenant configuré pour l'environnement. 

Si ce n'est déjà fait, suivez les étapes pour l'[activation des recommandations de produits et de la personnalisation](enable-product-recommendations.md) pour l'environnement.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des recommandations produit](product-recommendations.md)

[Activer les recommandations produit](enable-product-recommendations.md)

[Activer les recommandations personnalisées](personalized-recommendations.md)

[Désactiver les recommandations personnalisées](personalization-gdpr.md)

[Ajouter des recommandations produit sur PDV](product.md)

[Ajouter des recommandations à l'écran de transaction](add-recommendations-control-pos-screen.md)

[Ajuster des résultats des recommandations AI-ML](modify-product-recommendation-results.md)

[Créer manuellement des recommandations sélectionnées](create-editorial-recommendation-lists.md)

[Créer des recommandations avec des données de démonstration](product-recommendations-demo-data.md)

[FAQ sur les recommandations produit](faq-recommendations.md)


