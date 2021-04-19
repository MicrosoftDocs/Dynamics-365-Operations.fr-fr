---
title: Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce
description: Cette rubrique décrit comment synchroniser la gestion des tâches entre Microsoft Teams et les points de vente (PDV) Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ca0cb32ac3ee508ddcd5346a895fb9904fa92517
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842664"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a>Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique décrit comment synchroniser la gestion des tâches entre Microsoft Teams et les points de vente (PDV) Dynamics 365 Commerce.

L’un des principaux objectifs de l’intégration de Teams est de permettre la synchronisation de la gestion des tâches entre l’application de PDV et Teams. De cette façon, les employés du magasin peuvent utiliser l’application de PDV ou Teams pour gérer les tâches et n’ont pas à changer d’application.

Étant donné que le planificateur est utilisé comme référentiel pour les tâches dans Teams, il doit y avoir un lien entre Teams et Dynamics 365 Commerce. Ce lien est établi à l’aide d’un ID de plan spécifique pour une équipe de magasin donnée.

Les procédures suivantes montrent comment configurer la synchronisation de la gestion des tâches entre les applications de PDV et Teams.

## <a name="publish-a-test-task-list-in-teams"></a>Publier une liste de tâches de test dans Teams

La procédure suivante suppose que les équipes de votre magasin utilisent l’intégration de la gestion des tâche de Microsoft Teams avec Commerce pour la première fois.

Pour publier une liste de tâches de test dans Teams, procédez comme suit.

1. Connectez-vous à Teams en tant que responsable de la communication. En règle générale, les responsables de la communication sont des utilisateurs qui ont le rôle **Directeur régional** dans Commerce.
1. Dans le volet de navigation de gauche, sélectionnez **Tâches du planificateur**.
1. Sur l’onglet **Listes publiées**, sélectionnez **Nouvelle liste** en bas à gauche, et nommez la nouvelle liste **Liste des tâches de test**.
1. Sélectionnez **Créer**. La nouvelle liste apparaît sous **Brouillons**.
1. Sous **Titre de la tâche**, donnez le titre à la première tâche **Test de l’intégration de Teams**. Sélectionnez ensuite **Entrée**.
1. Dans la liste **Brouillons**, sélectionnez la liste des tâches. Puis sélectionnez  **Publier**  dans le coin supérieur droit.
1. Dans la boîte de dialogue **Sélectionner les destinataires de la publication**, sélectionnez les équipes qui doivent recevoir la liste des tâches de test.
1. Sélectionnez **Suivant** pour examiner votre plan de publication. Si vous devez apporter des modifications, sélectionnez  **Retour**. 
1. Sélectionnez **Confirmer pour continuer**, puis sélectionnez **Publier**.
1. Une fois la publication terminée, un message en haut de l’onglet **Listes publiées** indique si votre liste de tâches a été livrée avec succès.

Pour plus d’informations, consultez [Publier des listes de tâches pour créer et suivre le travail dans votre organisation](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).

## <a name="link-pos-and-teams-for-task-management"></a>Lier le point de vente et Teams pour la gestion des tâches

Pour lier les applications de PDV et Microsoft Teams pour la gestion des tâches dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Gestion des tâches \> Intégration des tâches avec Microsoft Teams**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Définissez l’option **Activer l’intégration de la gestion des tâches** sur **Oui**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le volet Actions, sélectionnez **Configurer la gestion des tâches**. Vous devriez recevoir une notification indiquant qu’un travail par lots nommé **Configuration de Teams** est en cours de création.
1. Accédez à **Administration système \> Recherches \> Traitements par lots** et recherchez le travail le plus récent ayant la description **Configuration de Teams**. Attendez que ce travail soit terminé.
1. Exécutez la **Tâche CDX 1070** pour publier l’ID du plan et stocker les références à Retail Server.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams](commerce-teams-integration.md)

[Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams](enable-teams-integration.md)

[Configuration de Microsoft Teams à partir de Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Gérer les rôles utilisateur dans Microsoft Teams](manage-user-roles-teams.md)

[Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams](map-stores-existing-teams.md)

[FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams](teams-integration-faq.md)
