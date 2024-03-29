---
title: Gestion des évaluations et avis
description: Cet article explique comment gérer les évaluations et les avis dans le générateur de site Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: b42ebff9b68b01e195e9c6a9641add45b6c7e2a9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286463"
---
# <a name="manage-ratings-and-reviews"></a>Gestion des évaluations et avis

[!include [banner](includes/banner.md)]

Cet article explique comment gérer les évaluations et les avis dans le générateur de site Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce utilise le service cognitif de Microsoft Azure pour modérer automatiquement du texte d’évaluation en effaçant les mots grossiers. De plus, les modérateurs peuvent utiliser le générateur de site Dynamics 365 Commerce pour implémenter les tâches manuelles suivantes :

- Modérez les évaluations en y répondant ou en les supprimant.
- Supprimez les évaluations d’un client à la requête du client.
- Importez en bloc les données des classements et des évaluations pour tous les produits dans un modèle Microsoft Power BI, afin que les tendances des classements et des évaluations puissent être analysées.

## <a name="read-a-review"></a>Lecture d’une évaluation 

Pour consulter une évaluation dans le générateur de site Commerce, suivez ces étapes.

1. Accédez à **Accueil \> Évaluations \> Modération**.
1. Utilisez le champ de recherche en haut à droite de la page pour filtrer les évaluations affichées par ID produit, nom du produit, ou texte d’évaluation.

Des filtres supplémentaires vous permettent de limiter les évaluations par période, classement, canal ou statut de préoccupation (retiré, répondu ou signalé).

![Page d’accueil Modération.](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a>Réponse à une évaluation 

Parfois, les clients qui ont acheté un produit expriment leur satisfaction ou mécontentement, ou ne comprennent pas comment utiliser le produit. Comme modérateur, vous pouvez publier une réponse à une évaluation. Cette réponse apparaît avec l’évaluation sur le site. 

Pour répondre à une évaluation dans le générateur de site Commerce, suivez ces étapes.

1. Accédez à **Accueil \> Évaluations \> Modération**.
1. Recherchez et sélectionnez l’évaluation nécessitant une réponse.
1. Dans le volet de propriétés de droite, sélectionnez **Ajouter une réponse**.
1. Entrez le texte de réponse et le nom qui doivent être affichés pour le répondeur. Le nom par défaut du répondeur est **Modérateur**.
1. Lorsque vous avez terminé, sélectionnez **Publier la réponse**.

![Répondre à une évaluation.](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a>Retirer une révision 

Parfois, il existe une justification commerciale pour les modérateurs de retirer des évaluations de clients. 

Pour retirer une évaluation dans le générateur de site Commerce, suivez ces étapes.

1. Accédez à **Accueil \> Évaluations \> Modération**.
1. Recherchez et sélectionnez l’évaluation qui doit être retirée.
1. Dans le volet de propriétés de droite, sélectionnez un motif de retrait sous **Retirer l’évaluation**, puis sélectionnez **Retirer**.
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a>Supprimer les évaluations d’un client à la requête du client 

Parfois, les clients souhaitent que les données de leurs classements et évaluations soient supprimées définitivement d’un site web e-commerce. Un modérateur qui reçoit une requête de suppression d’un client peut supprimer les données du client à l’aide de la fonctionnalité de suppression d’évaluation. Pour rechercher et supprimer les données d’un client, le modérateur nécessite l’adresse e-mail que ce client a utilisée pour se connecter et fournir des évaluations. 

Pour rechercher et supprimer des données client dans le générateur de site Commerce, suivez ces étapes.

1. Accédez à **Accueil \> Évaluations \> Supprimer**.
1. Dans la zone **Rechercher des utilisateurs par adresse e-mail**, entrez l’adresse e-mail du client, puis sélectionnez **Rechercher**.
1. Si le client a une activité d’évaluation (par exemple, des soumissions d’évaluation, des votes sur l’utilité des évaluations d’un autre client, ou des commentaires sur l’évaluation d’un autre client), les résultats s’affichent. Pour chaque article, il existe un bouton **Supprimer**.
1. Pour chaque article qui doit être supprimé, sélectionnez **Supprimer**. Lorsque vous êtes invité à confirmer, sélectionnez **Oui**. 
    
![Suppression de données client.](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - La suppression totale des données du système peut prendre jusqu’à sept jours. Les modérateurs doivent informer les clients de ce retard.
> - Si les clients ont modifié leur nom dans leurs paramètres de compte, plusieurs articles peuvent apparaître dans les résultats de la recherche. Dans ce cas, pour supprimer complètement les données client, le modérateur doit sélectionner **Supprimer** pour chaque article. 

## <a name="download-ratings-and-reviews-data"></a>Téléchargement des données de classement et d’évaluation

Le générateur de site Commerce permet aux modérateurs d’importer des classements et des évaluations en masse afin d’analyser les tendances. Un modèle Power BI qui inclut les mesures de base est disponible. Les modérateurs peuvent utiliser ce modèle pour connecter les données importées en bloc et afficher un tableau de bord. Ils n’ont pas besoin de créer un tableau de bord personnalisé. Les modérateurs peuvent également personnaliser le modèle Power BI en fonction de leurs besoins spécifiques. 

Pour télécharger les données de classement et d’évaluation dans le générateur de site Commerce, suivez ces étapes.

1. Accédez à **Accueil \> Évaluations \> Génération d’états**.
1. Sélectionnez **Télécharger les données d’évaluation** pour télécharger les données de classement et d’évaluation en vrac dans un format de valeurs séparées par des virgules (CSV).

## <a name="view-ratings-and-reviews-trends"></a>Afficher les tendances des classements et des évaluations

Les modérateurs peuvent télécharger le modèle Power BI afin d’afficher les tendances dans un tableau de bord.

Pour afficher les tendances des classements et des évaluations dans le générateur de site Commerce, suivez ces étapes.

1. Accédez à **Accueil \> Évaluations \> Rapport**.
1. Sélectionnez **Modèle PowerBI** pour télécharger le modèle.

    ![Télécharger le modèle Power BI.](media/rnr-moderation-reports.png) 

1. Ouvrez le modèle téléchargé à l’aide de l’application Power BI. Fermez la boîte de dialogue **Accès au contenu web** qui apparaît, puis fermez le message d’erreur « Actualisation » qui s’affiche.
1. Accédez à **Accueil**, sélectionnez **Modifier les requêtes**, puis sélectionnez **Paramètres de la source de données**.
1. Dans la boîte de dialogue **Paramètres de la source de données**, sélectionnez **Modifier la source**.
1. Dans le champ **URL**, entrez le chemin des données d’évaluations que vous avez téléchargées dans la procédure précédente (par exemple, **c :\\évaluations\\ReviewsData.csv**).

    ![Champ URL dans la boîte de dialogue Valeurs séparées par des virgules.](media/rnr-powerbi-datasource-settings.png) 

1. Sélectionnez **OK**, puis **Appliquer les modifications**. Une à deux minutes sont nécessaires pour appliquer les modifications à la source de données.
1. Sélectionnez **Feuille de tendances** pour afficher les tendances des classements et des évaluations.

    ![Tendances des classements et des évaluations.](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des évaluations et avis](ratings-reviews-overview.md)

[Choix d’utilisation des évaluations et avis](opt-in-ratings-reviews.md)

[Configuration des évaluations et avis](configure-ratings-reviews.md)

[Synchronisation des évaluations de produit dans Dynamics 365 Retail](sync-product-ratings.md)

[Activer la publication manuelle des évaluations et des avis par un modérateur](manual-publish-rating-reviews.md)

[Importation et exportation des évaluations et des avis](import-export-reviews.md)

[Configurer l’authentification service à service](service-to-service-auth.md)

[FAQ sur les évaluations et avis](ratings-reviews-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
