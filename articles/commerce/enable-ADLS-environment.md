---
title: Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce
description: Cet article fournit des instructions sur la façon de connecter une solution Azure Data Lake Storage Gen 2 à un magasin d’entités d’un environnement Dynamics 365 Commerce. Il s’agit d’une étape obligatoire avant d’activer les recommandations de produits.
author: bebeale
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail, eCommerce
ms.search.form: ''
ms.openlocfilehash: d7995e826a838796f714ced2f30220201a157f93
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284743"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a>Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cet article fournit des instructions sur la façon de connecter une solution Azure Data Lake Storage Gen2 à un magasin d’entités d’un environnement Dynamics 365 Commerce. Il s’agit d’une étape obligatoire avant d’activer les recommandations de produits.

Dans la solution Dynamics 365 Commerce, les données nécessaires au calcul des recommandations, des produits et des transactions sont agrégées dans le magasin d’entités de l’environnement. Pour rendre ces données accessibles à d’autres services Dynamics 365, tels que l’analyse de données, le décisionnel et les recommandations personnalisées, il est nécessaire de connecter l’environnement à une solution appartenant au client Azure Data Lake Storage Gen2.

Une fois les étapes ci-dessus terminées, toutes les données client du magasin d’entités de l’environnement sont automatiquement mises en miroir dans la solution Azure Data Lake Storage Gen2 du client. Lorsque les fonctionnalités de recommandations sont activées via l’espace de travail Gestion des fonctionnalités dans Commerce Headquarters, la pile de recommandations aura accès à la même solution Azure Data Lake Storage Gen2.

Pendant tout le processus, les données des clients restent protégées et sous leur contrôle.

## <a name="prerequisites"></a>Conditions préalables

Un magasin d’entités de l’environnement Dynamics 365 Commerce doit être connecté à un compte de stockage Azure Data Lake Gen2 et aux services associés.

Pour plus d’informations sur Azure Data Lake Storage Gen2 et sa configuration, voir [Documentation officielle d’Azure Data Lake Storage Gen2](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Étapes de configuration

Cette section couvre les étapes de configuration nécessaires pour activer Azure Data Lake Storage Gen2 dans un environnement en ce qui concerne les recommandations de produits.
Pour une vue d’ensemble plus approfondie des étapes requises pour activer Azure Data Lake Storage Gen2, voir [Rendre le magasin des entités disponible en tant que Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).

### <a name="enable-azure-data-lake-storage-in-the-environment"></a>Activer Azure Data Lake Storage dans l’environnement

1. Connectez-vous au portail de back-office de l’environnement.
1. Recherchez **Paramètres système** et accédez à l’onglet **Connexions de données**. 
1. Paramétrez **Activer l’intégration de Data Lake** sur **Oui**.
1. Puis entrez les informations requises suivantes :
    1. **ID d’application** // **Secret de l’application** // **Nom DNS** - Nécessaire pour se connecter à KeyVault où le secret Azure Data Lake Storage est stocké.
    1. **Nom du secret** - Le nom du secret stocké dans KeyVault et utilisé pour s’authentifier auprès d’Azure Data Lake Storage.
1. Enregistrez vos modifications dans le coin supérieur gauche de la page.

L’image suivante présente un exemple de configuration Azure Data Lake Storage.

![Exemple de configuration Azure Data Lake Storage.](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a>Tester la connexion Azure Data Lake Storage

1. Testez la connexion à KeyVault à l’aide du lien **Tester Azure Key Vault**.
1. Testez la connexion à Azure Data Lake Storage à l’aide du lien **Tester le stockage Azure**.

> [!NOTE]
> Si l’un des tests ci-dessus échoue, vérifiez que toutes les informations KeyVault ajoutées ci-dessus sont correctes, puis réessayez.

Une fois les tests de connexion réussis, vous devez activer l’actualisation automatique pour le magasin d’entités.

Pour activer l’actualisation automatique pour le magasin d’entités, procédez comme suit.

1. Recherchez **Magasin d’entités**.
1. Dans la liste de gauche, accédez à l’entrée **RetailSales**, puis sélectionnez **Éditer**.
1. Veillez à ce que l’option **Actualisation automatique activée** soit réglée sur **Oui**, sélectionnez **Actualiser**, puis sélectionnez **Enregistrer**.

L’image suivante montre un exemple de magasin d’entités avec l’actualisation automatique activée.

![Exemple de magasin d’entités avec l’actualisation automatique activée.](./media/exampleADLSConfig2.png)

Azure Data Lake Storage est maintenant configuré pour l’environnement. 

Si ce n’est déjà fait, suivez les étapes pour l’[activation des recommandations de produits et de la personnalisation](enable-product-recommendations.md) pour l’environnement.

## <a name="additional-resources"></a>Ressources supplémentaires

[Rendre le magasin des entités disponible en tant que Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[Vue d’ensemble des recommandations produit](product-recommendations.md)

[Activer les recommandations produit](enable-product-recommendations.md)

[Activer les recommandations personnalisées](personalized-recommendations.md)

[Désactiver les recommandations personnalisées](personalization-gdpr.md)

[Activer les recommandations « acheter des aspects similaires »](shop-similar-looks.md)

[Ajouter des recommandations produit sur PDV](product.md)

[Ajouter des recommandations à l’écran de transaction](add-recommendations-control-pos-screen.md)

[Ajuster des résultats des recommandations AI-ML](modify-product-recommendation-results.md)

[Créer manuellement des recommandations sélectionnées](create-editorial-recommendation-lists.md)

[Créer des recommandations avec des données de démonstration](product-recommendations-demo-data.md)

[FAQ sur les recommandations produit](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
