---
title: Configurer l’authentification service à service
description: Cette rubrique décrit comment configurer l’authentification de service à service dans Microsoft Dynamics 365 Commerce pour appeler en toute sécurité les API de service pour les évaluations et les avis.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: da780de5f15d72bdac85a261eae809125c830260
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968518"
---
# <a name="configure-service-to-service-authentication"></a>Configurer l’authentification service à service

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment configurer l’authentification de service à service (S2S) dans Microsoft Dynamics 365 Commerce pour appeler en toute sécurité les interfaces de programmation d’application (API) de service pour les évaluations et les avis.

Dynamics 365 Commerce offre les [évaluations et avis](ratings-reviews-overview.md) en tant que solution omnicanal. Cette solution permet d’accéder aux API de service depuis l’extérieur de Commerce, afin que diverses tâches puissent être effectuées. Ces tâches incluent l’importation de notes et d’avis depuis votre système externe vers Commerce, et l’exportation de notes et d’avis depuis Commerce. Pour permettre à Commerce d’appeler en toute sécurité les API du service d’évaluation et d’avis, vous devez d’abord configurer l’authentification S2S en suivant les procédures décrites dans cette rubrique.

## <a name="add-a-new-app-registration"></a>Ajouter un nouvel enregistrement d’application

Avant d’ajouter une nouvelle inscription d’application, vous devez créer une application à l’aide du [Portail Azure](https://portal.azure.com). Pour enregistrer une application dans Azure Active Directory (Azure AD) et activer l’authentification, suivez les étapes de [Utiliser Azure Active Directory avec un connecteur personnalisé dans Power Automate](/connectors/custom-connectors/azure-active-directory-authentication).

Collectez les ID suivants à partir du portail Azure. Vous aurez besoin de ces ID dans les étapes qui suivent.

- ID application cliente
- ID du répertoire client (locataire)

Pour ajouter une inscription d’application dans le générateur de site Commerce, procédez comme suit.

1. Accédez à **Accueil \> Évaluations \> Paramètres**.
1. En dessous de **Authentification de service à service (S2S)**, sélectionnez **Gérer**.

    ![Bouton Gérer dans la section Authentification de service à service (S2S) dans le générateur de site Commerce.](media/Ratings-reviews-settings-service-to-service-authentication.png)

1. Dans le volet **Entrées d’application S2S** qui apparaît à droite, sélectionnez **Ajouter une nouvelle inscription d’application S2S**.
1. Dans la boîte de dialogue **Ajouter une entrée d’application S2S**, entrez les informations requises suivantes. Utilisez les valeurs de votre inscription d’application Azure.

    - **Nom** – Entrez le nom de votre application (par exemple, **Fabrikam App**).
    - **ID d’appli client** – Entrez l’ID d’application (par exemple **00000000-0000-0000-0000-000000000000**).
    - **ID de répertoire (locataire)** – Entrez l’ID du répertoire (par exemple, **00000000-0000-0000-0000-000000000000**).

    ![Boîte de dialogue Ajouter une entrée d’application S2S dans le générateur de site Commerce.](media/Ratings-reviews-settings-S2S-APP-entry.png)

1. Sélectionnez **Soumettre**. Le nom de votre application S2S doit apparaître dans la liste du volet **Entrées d’application S2S**.
1. Fermez le volet **Entrées d’application S2S**.
1. Cliquez sur **Enregistrer**.

## <a name="edit-an-existing-app-registration"></a>Modifier une inscription d’application existante

Pour modifier une inscription d’application existante dans le générateur de site Commerce, procédez comme suit.

1. Accédez à **Accueil \> Évaluations \> Paramètres**.
1. En dessous de **Authentification de service à service (S2S)**, sélectionnez **Gérer**.
1. Dans le volet **Entrées d’application S2S**, sélectionnez le symbole du crayon à côté de l’entrée que vous souhaitez modifier.
1. Mettez à jour les valeurs dans les champs **Nom**, **ID d’application client** et **ID de répertoire (locataire)** selon les besoins.
1. Sélectionnez **Soumettre**.
1. Fermez le volet **Entrées d’application S2S**.
1. Cliquez sur **Enregistrer**.

## <a name="remove-an-existing-app-registration"></a>Supprimer une inscription d’application existante

Pour supprimer une inscription d’application existante dans le générateur de site Commerce, procédez comme suit.

1. Accédez à **Accueil \> Évaluations \> Paramètres**.
1. En dessous de **Authentification de service à service (S2S)**, sélectionnez **Gérer**.
1. Dans le volet **Entrées d’application S2S**, sélectionnez le symbole de corbeille de l’entrée que vous souhaitez supprimer. L’entrée est supprimée de la liste.
1. Fermez le volet **Entrées d’application S2S**.
1. Cliquez sur **Enregistrer**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des évaluations et avis](ratings-reviews-overview.md)

[Choix d’utilisation des évaluations et avis](opt-in-ratings-reviews.md)

[Gestion des évaluations et avis](manage-reviews.md)

[Configuration des évaluations et avis](configure-ratings-reviews.md)

[Synchronisation des évaluations de produit](sync-product-ratings.md)

[Activer la publication manuelle des évaluations et des avis par un modérateur](manual-publish-rating-reviews.md)

[Importation et exportation des évaluations et des avis](import-export-reviews.md)

[FAQ sur les évaluations et avis](ratings-reviews-faq.md) 
