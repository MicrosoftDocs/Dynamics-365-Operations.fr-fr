---
title: Fusion de l’infrastructure Dynamics 365 Human Resources – Mise à jour de la version 10.0.25
description: Cette rubrique fournit des informations sur Microsoft Dynamics 365 Human Resources, version 10.0.25, qui apporte la première vague de fonctionnalités dans la fusion de l’infrastructure.
author: twheeloc
ms.date: 01/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a80bedd0224f1e31dfec4e9f4c39ad1ed75d7f2f
ms.sourcegitcommit: 948978183a1da949e35585b28b8e85a63b6c12b1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2022
ms.locfileid: "8024565"
---
# <a name="dynamics-365-human-resources-infrastructure-merge---release-10025-update"></a>Fusion de l’infrastructure Dynamics 365 Human Resources – Mise à jour de la version 10.0.25

La version 10.0.25 apporte la première vague de fonctionnalités dans la fusion de l’infrastructure. Lors de la fusion de l’infrastructure, Microsoft Dynamics 365 Human Resources sera fusionné avec l’infrastructure Finances et Opérations. Cependant, il continuera d’être concédé sous licence en tant qu’application indépendante, comme Dynamics 365 Finance et Dynamics 365 Supply Chain Management. Pour plus d’informations sur la fusion de l’infrastructure, voir [FAQ sur la fusion de l’infrastructure Dynamics 365 Human Resources](../human-resources/hr-infrastructure-merge-faq.md).

La fusion offrira aux utilisateurs de Human Resources davantage de cohérence, des manières suivantes :

- [La gestion de l’environnement et les intégrations sont cohérentes entre les applications Human Resources et Finances et Opérations.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/consistent-environment-management-integrations-between-human-resources-finance-operations-apps)

    - Gestion d’environnements dans Microsoft Dynamics Lifecycle Services, recherche de problèmes et Regression Suite Automation Tool.
    - Il existe une base de code unique, où de nouvelles fonctionnalités pour Human Resources sont publiées dans le cadre du processus de mise à jour régulier One Version.
    - La façon dont les mises à niveau, les mises à jour et les correctifs sont appliqués aux environnements est cohérente.

- [Les options d’extensibilité sont améliorées.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/improve-extensibility-options.md)

    - Vous pouvez continuer à utiliser les outils Microsoft Power Platform pour réaliser les extensions souhaitées.
    - Vous pouvez étendre les fonctionnalités via des formulaires, des tables, des méthodes et des interfaces de programmation d’application (API).
    - Vous pouvez créer et étendre des entités.

    Pour plus d’informations sur les options d’extension disponibles, voir [Présentation de l’extensibilité dans Dynamics 365](../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md).

- [Créez un ensemble de fonctionnalités de ressources humaines dans Dynamics 365.](/dynamics365-release-plan/2021wave2/human-resources/create-one-set-human-resources-capabilities-within-dynamics-365.md)

    Dans la version 10.0.25, les capacités fonctionnelles qui n’existaient que dans Human Resources ont été rendues disponibles sur l’infrastructure Finances et Opérations. Pour que les clients puissent tirer parti de ces fonctionnalités dans un environnement Finances et Opérations, les fonctionnalités Human Resources suivantes doivent être activées dans la Gestion des fonctionnalités.

    | Nom de la fonction | Vue d’ensemble | Statut de lancement | 
    |--------------|----------|----------------| 
    | Calcul des années de service | Une option de configuration vous permet de sélectionner la date utilisée pour le calcul des **Années de service**. | Disponibilité générale | 
    | Améliorations de l’expérience de flux de travail | Cette fonctionnalité offre une expérience utilisateur améliorée pour les soumissions et les approbations de flux de travail. | Disponibilité générale | 
    | Imprimer les révisions des performances | Vous pouvez imprimer les évaluations de performance au format PDF. | Disponibilité générale | 
    | Liens personnalisés dans le **Libre-service des responsables** | Vous pouvez créer des liens personnalisés qui apparaissent dans la section **Liens connexes** du **Libre-service des responsables**. | Disponibilité générale | 
    | Vue Rémunération intersociétés | Les utilisateurs peuvent consulter les régimes de rémunération dans le **Libre-service des responsables** sur toutes les entités juridiques, sans avoir à changer de société. | Disponibilité générale | 
    | Configurer plusieurs niveaux de rémunération par tâche\*&dagger; | Les tâches prennent désormais en charge plusieurs niveaux de rémunération. | Version préliminaire | 
    | Gestion des tâches\* | Vous pouvez créer des listes de contrôle et des tâches pour les processus d’intégration, de débarquement et de transition. | Version préliminaire | 
    | Entrée d’employé simplifiée | Cette fonctionnalité offre une expérience utilisateur actualisée sur la page **Collaborateur**. | Version préliminaire | 
    | Améliorations de l’expérience utilisateur des ressources humaines | Voir le tableau dans la section suivante.  | Version préliminaire | 

\* Cette fonction doit être activée avant la fonction **Améliorations de l’expérience utilisateur des ressources humaines**.

&dagger;Cette fonctionnalité ne peut pas être désactivées après son activation.

## <a name="human-resource-user-experience-enhancements"></a>Améliorations de l’expérience utilisateur des ressources humaines

| Nom de la fonction | Vue d’ensemble | 
|--------------|----------| 
| Supprimer l’emploi | Vous pouvez supprimer l’emploi d’un employé. | 
| Familles de tâches | Vous pouvez suivre un groupe de tâches qui impliquent un travail similaire et qui nécessitent une formation, des compétences, des connaissances et une expertise similaires. | 
| Champs d’emploi supplémentaires | Les champs suivants ont été ajoutés : **Catégorie d’emploi**, **Type d’emploi** et **Statut d’emploi**. | 
| Page **Collaborateurs sans emploi** | Une page affiche une liste de collaborateurs qui n’ont pas d’enregistrement d’emploi. | 
| Mise à jour de l’expérience utilisateur de la dimension Poste | Il existe une expérience utilisateur améliorée pour l’attribution des dimensions de poste par entité juridique. | 
| Changements d’adresse dans l’espace de travail **Gestion du personnel** | Cette fonction fournit un décompte de tous les changements d’adresse qui se sont produits pendant un nombre de jours spécifié sur la page **Paramètres Human Resources**. | 
| Enregistrements existants dans l’espace de travail **Gestion du personnel** | Cette fonctionnalité fournit une liste des éléments qui ont expiré ou expireront pour les certificats, les identifications, les périodes d’essai, les présélections ou les tests. | 
| Page **Validation de la hiérarchie des postes** | Un contrôle des références circulaires est effectué dans la hiérarchie des lignes de poste. | 
| Informations sur la paie spécifiques à chaque pays | Des champs de paie supplémentaires sont disponibles sur la page **Emploi du collaborateur**, selon le pays ou la région de l’entité juridique où les collaborateurs sont employés. | 
| Améliorations des rapports de conformité | Des options de rapport supplémentaires sont disponibles pour EEO-1, Vets 4212 et OSHA300a. | 
| Mises à jour apportées à l’espace de travail **Gestion du personnel** | Des mises à jour ont été apportées pour suivre les changements d’adresse et les enregistrements qui expirent. De plus, de nouveaux onglets répertorient les actions des collaborateurs et des postes. | 
