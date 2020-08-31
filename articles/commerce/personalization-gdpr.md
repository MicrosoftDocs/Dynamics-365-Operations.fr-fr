---
title: Refuser les recommandations personnalisées
description: Cette rubrique explique comment vous pouvez laisser les clients refuser la réception des recommandations personnalisées dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: a51c8c0e2743b67df9d66a8c45ab7a69597f4002
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "3664928"
---
# <a name="opt-out-of-personalized-recommendations"></a>Refuser les recommandations personnalisées

[!include [banner](includes/banner.md)]

Cette rubrique explique comment vous pouvez laisser les clients refuser la réception des recommandations personnalisées dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Lors de la création d'un compte, la réception des recommandations personnalisées est automatiquement configurée pour les nouveaux clients. Toutefois, Dynamics 365 Commerce offre aux détaillants diverses manières d'autoriser les utilisateurs à refuser de recevoir ces recommandations et de limiter le traitement de leurs données personnelles. Les utilisateurs authentifiés qui refusent de recevoir les recommandations personnalisées cessent immédiatement de voir les listes personnalisées. De plus, toutes les données personnelles collectées pour la personnalisation sont supprimées des modèles de recommandations personnalisées.

Pour plus d'informations sur les recommandations de produit personnalisées, voir [Activer les recommandations personnalisées](personalized-recommendations.md).

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a>Méthodes de mise en œuvre d'une expérience de désinscription côté détaillants

Les détaillants disposent de 3 méthodes pour mettre en œuvre d'une expérience de désinscription.

### <a name="opting-out-on-behalf-of-users"></a>Refus pour le compte des utilisateurs

Dans la gestion de compte dans le back office Commerce, les détaillants peuvent refuser au nom des utilisateurs.

1. Depuis la page d'accueil du back-office, recherchez **tous les clients**.
1. Recherchez et sélectionnez un client, puis sélectionnez l'organisateur **Vente au détail**.

    ![Organisateur Vente au détail](./media/Disablepersonalizationpart1.png)

1. Sous **Confidentialité**, définissez l'option **Désactiver la personnalisation** sur **Oui**.

    ![Paramètres de confidentialité](./media/Disablepersonalizationpart2.png)

1. Cliquez sur **Enregistrer**, puis fermez la page.

### <a name="module-based-opt-out-experience"></a>Expérience de désinscription basée sur les modules

Les détaillants peuvent laisser les utilisateurs authentifiés refuser par eux-mêmes les recommandations personnalisées. Pour proposer cette expérience de désinscription, ajoutez le module de refus utilisateur aux pages du profil de compte client.

### <a name="custom-extensions"></a>Extensions personnalisées

Les détaillants peuvent créer leurs propres extensions pour gérer l'expérience de désinscription pour les utilisateurs. Pour plus d'informations, voir [Appeler les API Retail Server](e-commerce-extensibility/call-retail-server-apis.md) et [Extensibilité des canaux en ligne](e-commerce-extensibility/overview.md).

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a>Obtenir une copie numérique des données de recommandations personnalisées pour le compte d'un utilisateur authentifié

Les clients peuvent souhaiter obtenir une copie numérique de leurs données personnelles et afficher également une vue exportée des résultats de leurs recommandations. Si un client demande ces informations, le détaillant doit créer une extension personnalisée qui appelle l'interface de programmation d'application (API) de Retail Server et demande les résultats complets à partir de la liste **Des choix pour vous**, basée sur l'ID du client. Les résultats peuvent ensuite être exportés au format CSV (valeurs séparées par des virgules) et partagés avec le client.

L'exemple suivant montre comment un détaillant peut réaliser cette tâche.

1. Le détaillant crée une extension personnalisée pour extraire les données de recommandations personnelles pour le compte de l'utilisateur. Pour des informations sur la création de modules, le clonage des modules existants, l'appel des API Retail Server et l'appel des actions de données, voir [Extensibilité des canaux en ligne](e-commerce-extensibility/overview.md).
2. L'extension personnalisée appelle l'action de données essentielles **get-recommendations** et lui transmet les informations requises selon les exigences de la liste. Pour la liste **Des choix pour vous**, l'extension doit transmettre le nom de liste et l'ID client corrects à l'action de données.

    Une façon de créer l'extension personnalisée consiste à cloner le module de collecte de produits existant qui est utilisé pour renvoyer les résultats des recommandations. En clonant ce module existant, un détaillant peut modifier le code existant et ajouter un nouveau bouton qui exporte les résultats des recommandations vers un fichier CSV. Pour plus d'informations, voir [Cloner un module de kit de démarrage](e-commerce-extensibility/clone-starter-module.md) et [Modules de collecte de produits](product-collection-module-overview.md).

    Pour une vue complète de la bibliothèque des API Retail Server, voir [API client et client de Retail Server](dev-itpro/retail-server-customer-consumer-api.md).

3. Après la création de l'extension personnalisée, le détaillant peut exporter un fichier CSV de tous les résultats des recommandations, en fonction de l'ID client unique de l'utilisateur authentifié.
4. Le détaillant peut partager le fichier CSV exporté qui contient la liste personnalisée complète des produits recommandés avec l'utilisateur authentifié.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des recommandations produit](product-recommendations.md)

[Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce](enable-adls-environment.md)

[Activer les recommandations produit](enable-product-recommendations.md)

[Activer les recommandations personnalisées](personalized-recommendations.md)

[Activer les recommandations « acheter des aspects similaires »](shop-similar-looks.md)

[Ajouter des recommandations produit sur PDV](product.md)

[Ajouter des recommandations à l’écran de transaction](add-recommendations-control-pos-screen.md)

[Ajuster des résultats des recommandations AI-ML](modify-product-recommendation-results.md)

[Créer manuellement des recommandations sélectionnées](create-editorial-recommendation-lists.md)

[Créer des recommandations avec des données de démonstration](product-recommendations-demo-data.md)

[FAQ sur les recommandations produit](faq-recommendations.md)
