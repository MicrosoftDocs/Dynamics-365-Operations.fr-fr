---
title: Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams
description: Cet article présente une vue d’ensemble de l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 0b674f40b6bb433bc5e2c9216d649a7f15169442
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887086"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a>Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams

[!include [banner](includes/banner.md)]

Cet article présente une vue d’ensemble de l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.

Dynamics 365 Commerce s’intègre à Teams pour aider les clients et leurs employés à améliorer leur productivité en synchronisant la gestion des tâches entre les deux applications. La gestion transparente des tâches fournie par l’intégration de Commerce et Teams permet aux directeurs de magasin et aux employés de créer des listes de tâches, d’attribuer des tâches à plusieurs magasins et de suivre le statut des tâches dans les différents magasins, à partir de l’une ou l’autre application.

L’intégration de Commerce et Teams est disponible à partir de la version Commerce 10.0.18.

## <a name="key-features"></a>Fonctions principales

Voici quelques-unes des principales fonctionnalités offertes par l’intégrité de Commerce et Microsoft Teams :

- Configurez Teams en tirant parti des informations bien définies de Commerce, telles que la structure organisationnelle et les informations sur les magasins, les employés, les autorisations et le contexte commercial.
- Synchronisez facilement les changements en cours (par exemple, l’ajout de nouveaux magasins ou l’embauche de nouveaux employés) entre Commerce et Teams, mais gardez Commerce comme source principale des données de structure organisationnelle.
- Intégrez la gestion des tâches entre Commerce et Teams pour aider les employés de magasin, les directeurs de magasin, les directeurs régionaux et les responsables de la communication à gérer les tâches à partir de l’une ou l’autre des applications.

## <a name="prerequisites-for-using-integration-features"></a>Conditions préalables à l’utilisation des fonctionnalités d’intégration

Les conditions préalables suivantes doivent être en place avant de pouvoir commencer à utiliser les fonctionnalités d’intégration de Microsoft Teams :

- Licence Microsoft 365 Business Standard (Cette licence inclut Teams.)
- Comptes Azure Active Directory(Azure AD) pour tous les directeurs et employés de magasin
- Systèmes de point de vente (PDV) configurés avec l’authentification Azure AD

## <a name="conceptual-architecture"></a>Architecture conceptuelle

L’illustration suivante montre l’architecture conceptuelle de l’intégration de Dynamics 365 Commerce et Microsoft Teams, en prenant un magasin de San Francisco comme exemple. Teams et l’application de PDV Commerce utilisent Microsoft Planner comme référentiel afin que les tâches publiées à partir de Teams apparaissent dans l’application de PDV et que les tâches ponctuelles créées par les directeurs de magasin dans l’application de PDV apparaissent dans Teams, ce qui se traduit par une expérience de gestion des tâches cohérente entre les applications.    

![Architecture de l’intégration de Commerce et Teams.](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams](enable-teams-integration.md)

[Configuration de Microsoft Teams à partir de Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gérer les rôles utilisateur dans Microsoft Teams](manage-user-roles-teams.md)

[Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams](map-stores-existing-teams.md)

[FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams](teams-integration-faq.md)
