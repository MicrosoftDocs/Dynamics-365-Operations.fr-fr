---
title: Définition d'autorisations utilisateurs dans Attract
description: Cette rubrique fournit des informations sur la sécurité des rôles dans Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: efac512cfa07bb2183f06b8be45f74bef9af0767
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461150"
---
# <a name="set-user-permissions-in-attract"></a>Définition d'autorisations utilisateurs dans Attract

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Talent: Attract utilise la sécurité des rôles. En d'autres termes, l'accès n'est pas accordé aux utilisateurs individuels, mais aux rôles de sécurité affectés aux utilisateurs. Un utilisateur affecté à un rôle de sécurité a accès à l'ensemble de privilèges associé à ce rôle.

Attract propose cinq rôles d'utilisateur de base :

- Administrateur
- Responsable du recrutement
- Recruteur
- Intervieweur
- Lecture seule

Le rôle Administrateur est le seul rôle qui a l'autorisation d'ajouter d'autres utilisateurs et de modifier leurs autorisations.

- **Ajouter** – Dans le centre d'administration, sous l'onglet **Autorisations utilisateur**, sélectionnez **Affecter des rôles**, recherchez l'utilisateur à ajouter, puis affectez des autorisations à cet utilisateur.
- **Modifier** – Recherchez l'utilisateur, ou trouvez l'utilisateur dans la liste, puis sélectionnez **Modifier** pour modifier ses autorisations.
- **Supprimer** – Si vous supprimez les autorisations d'un utilisateur, vous ne supprimez pas l'utilisateur du système. Toutefois, vous limitez l'accès et les privilèges de l'utilisateur dans Attract. Par exemple, Hilda a été affectée au rôle de Responsable du recrutement, et est ajoutée à une mission comme responsable du recrutement. Si Hilda est supprimée ultérieurement du rôle de Responsable du recrutement, elle reste responsable du recrutement dans la mission et a toujours accès à cette mission. Toutefois, elle ne peut pas créer d'autres missions.

Les sections suivantes fournissent une description générale de chaque rôle. Les tableaux ultérieurs dans la rubrique fournissent des informations plus détaillées.

> [!NOTE]
> Certains fonctionnalités sont disponibles uniquement avec le Composant additionnel de recrutement complet pour Attract.

## <a name="administrator"></a>Administrateur

Les utilisateurs affectés au rôle Administrateur peuvent ouvrir et modifier toutes les données dans Attract. Les administrateurs peuvent créer, lire, mettre à jour, et supprimer des données. Ils ont également accès au centre d'administration, dans lequel ils peuvent configurer Attract et paramétrer les informations utilisateur. Nous vous recommandons qu'au moins une personne soit affecté au rôle Administrateur. Par défaut, l'administrateur d'environnement de Microsoft Power Apps est défini comme administrateur dans Attract. Si vous vous êtes inscrit à la version d'évaluation Attract, le rôle Administrateur vous est affecté automatiquement. Actuellement, pour créer des missions, les utilisateurs qui disposent du rôle Administrateur doivent également avoir le rôle de Recruteur ou le rôle Responsable du recrutement.

## <a name="hiring-manager"></a>Responsable du recrutement

Les utilisateurs affectés au rôle de Responsable du recrutement peuvent créer des missions et mettre à jour les missions qu'ils ont créées précédemment. Les responsables du recrutement peuvent exécuter uniquement un ensemble limité d'actions sur une mission et sur les candidatures qui sont associées à cette mission. Seuls les utilisateurs affectés au rôle de Responsable du recrutement peuvent être ajoutés à une équipe de recrutement comme responsables du recrutement.

## <a name="recruiter-role"></a>Rôle Recruteur

Les utilisateurs affectés au rôle Recruteur ont les privilèges complets de lecture, création, mise à jour, et suppression pour les missions qu'ils ont créées. Ils disposent également de privilèges complets pour créer, lire, mettre à jour, et supprimer les candidatures qui sont associées à des missions qu'ils possèdent. Seuls les utilisateurs affectés au rôle de Recruteur peuvent être ajoutés à une équipe de recrutement comme recruteurs.

## <a name="interviewer"></a>Intervieweur

Tout utilisateur ayant un compte Microsoft Azure Active Directory (Azure AD) dans l'organisation peut être ajouté à une équipe de recrutement en tant qu'intervieweur. Les utilisateurs affectés au rôle Intervieweur peuvent afficher les détails des missions et les données des candidats pour les missions pour lesquels ils font partie de l'équipe de recrutement. Pour ces missions, les intervieweurs peuvent également émettre des recommandations de recrutement et fournir une rétroaction sur les candidats. Toutefois, ils ne peut pas mettre à jour les détails des missions ou les données des candidats.

## <a name="read-only"></a>Lecture seule

Les utilisateurs affectés au rôle Lecture seule ont accès en lecture seule à toutes les données de l'environnement Attract. Toutefois, ils ne peuvent ni créer, ni modifier les données.

## <a name="find-out-which-roles-you-have"></a>Découvrir les rôles dont vous disposez

1.  Dans Attract, cliquez sur le point d'interrogation (**?**) dans le coin supérieur droit de la page.

2.  Cliquez sur **A propos**.

    Vous verrez les rôles dont vous disposez pour Attract dans la fenêtre qui s'affiche :

    ![Afficher votre type de licence Attract](media/attract-license-types.png)
    
## <a name="delegated-roles"></a>Rôles délégués

Pour chaque mission pour laquelle ils font partie de l'équipe de recrutement, les recruteurs et responsables de recrutement peuvent indiquer un ou plusieurs délégués pour eux. Toutefois, ils ne peuvent pas indiquer des délégués pour d'autres personnes de l'équipe de recrutement.

Les délégués ont les mêmes privilèges que la personne qui les a désignés. Par exemple, si un responsable de l'embauche indique un délégué pour lui-même pour une mission, le délégué a les mêmes privilèges que celui du responsable de l'embauche pour cette mission. Les délégués ne peuvent pas supprimer d'autres délégués de l'équipe de recrutement. Ils ne peuvent pas également supprimer les personnes qui les ont désignés comme délégués.

## <a name="job-details-and-actions"></a>Détails des missions et actions

Les utilisateurs qui disposent du rôle Recruteur ou Responsable du recrutement peuvent créer des missions. Les privilèges suivants s'appliquent aux détails de missions et aux actions pouvant être entreprises pour des missions.

| Données ou action    | Recruteur | Responsable du recrutement | Intervieweur |
|-------------------|-----------|----------------|-------------|
| Détails de la mission       | Créer, lire, mettre à jour, et supprimer les missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Créer, lire, mettre à jour, et supprimer les missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Lecture seule |
| Équipe chargée du recrutement       | Créer, lire, mettre à jour, et supprimer les missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Créer, lire, mettre à jour, et supprimer les missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Lecture seule |
| Annonce d'emploi       | Créer, lire, mettre à jour, et supprimer les missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Lecture seule | Lecture seule |
| Processus           | Créer, lire, mettre à jour, et supprimer les missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Créer, lire, mettre à jour, et supprimer les missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Lecture seule |
| Ajouter des candidats    | Ajouter des candidats à des missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Ajouter des candidats à des missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Non autorisé |
| Ajouter des prospects     | Ajouter des prospects à des missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Une option de configuration dans [le paramétrage d'activité de prospect](./activities-attract.md#prospect-activity) contrôle si les intervieweurs peuvent ajouter et afficher des prospects. | Non autorisé |
| Activer une mission      | Activer des missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Activer des missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Non autorisé |
| Clôturer la mission         | Clôturer des missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Non autorisé | Non autorisé |
| Supprimer la tâche        | Supprimer des missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Uniquement si aucun candidat n'a été ajouté à la mission | Non autorisé |
| Supprimer des candidats | Supprimer des candidats si l'utilisateur fait partie de l'équipe de recrutement | Non autorisé | Non autorisé |

## <a name="application-details-and-actions"></a>Détails des candidatures et actions

Les privilèges suivants s'appliquent aux données spécifiques aux missions pour les candidats et aux actions pouvant être entreprises pour des candidatures.

| Données ou action          | Recruteur | Responsable du recrutement | Intervieweur |
|-------------------------|-----------|----------------|-------------|
| Documents de candidature   | Créer, lire, mettre à jour, et supprimer les missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Créer, lire, mettre à jour, et supprimer les missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Lecture seule |
| Notes de candidature       | Créer, lire, mettre à jour, et supprimer les missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Créer, lire, mettre à jour, et supprimer les missions pour lesquelles l'utilisateur fait partie de l'équipe de recrutement | Lecture seule|
| Activité de candidature    | Afficher, si l'utilisateur fait partie de l'équipe de recrutement | Afficher, si l'utilisateur fait partie de l'équipe de recrutement | Lecture seule |
| Rétroaction sur la candidature    | Ajouter et afficher tous les commentaires si l'utilisateur fait partie de l'équipe de recrutement | Ajouter et afficher tous les commentaires si l'utilisateur fait partie de l'équipe de recrutement | Peut ajouter des commentaires\*\* |
| Rejeter la candidature      | Peut rejeter si l'utilisateur fait partie de l'équipe de recrutement | Non autorisé | Non autorisé |
| Changer de stade           | Peut rejeter si l'utilisateur fait partie de l'équipe de recrutement | Peut avancer si l'utilisateur fait partie de l'équipe de recrutement | Non autorisé |
| Lancer la gestion des offres | Peut commencer la gestion des offres | Il existe une option de configuration sur l'activité d'offre. | Non autorisé |


\*\* Une option de configuration dans le [paramétrage d'activité de rétroaction](./activities-attract.md) contrôle si les intervieweurs peuvent afficher les commentaires des uns et des autres.


## <a name="process-templates"></a>Modèles de processus

Les privilèges suivants s'appliquent aux modèles de processus de recrutement. La capacité des membres de l'équipe de créer et de modifier des modèles est configurée dans **Gestion des modèles** dans le centre d'administration. Si la gestion des modèles est activée, les recruteurs et responsables de l'embauche peuvent créer et modifier leurs propres modèles de processus. Si la gestion des modèles est désactivée, seuls les administrateurs peuvent créer et modifier des modèles de processus. Le tableau suivant suppose que la gestion des modèles a été activée.

| Données              | Recruteur                                           | Responsable du recrutement                                      | Intervieweur |
|-------------------|-----------------------------------------------------|-----------------------------------------------------|-------------|
| Modèles de processus | Privilèges complets pour les modèles que l'utilisateur crée | Privilèges complets pour les modèles que l'utilisateur crée | Pas d'accès   |

## <a name="email-and-email-templates"></a>Modèles d'e-mail et e-mails

Les privilèges suivants s'appliquent aux modèles d'e-mails et aux actions pouvant être entreprises pour des e-mails. Seuls les administrateurs peuvent créer et modifier des modèles d'e-mails.

| Données ou action     | Recruteur          | Responsable du recrutement     | Intervieweur |
|--------------------|--------------------|--------------------|-------------|
| Modèles d'e-mail    | Accès en lecture seule   | Accès en lecture seule   | Pas d'accès   |
| Envoyer un e-mail         | Envoyer par activité  | Envoyer par activité  | Pas d'accès   |
| Modifier le contenu de l'e-mail | Modifier le contenu de l'e-mail | Modifier le contenu de l'e-mail | Pas d'accès   |

## <a name="talent-pools"></a>Viviers de talents

Les privilèges suivants s'appliquent aux viviers de talents. Les viviers de talents sont visibles uniquement de la personne qui les a créés, sauf si cette personne choisit de les partager. La recherche de candidat peut être utilisée pour rechercher des candidats qui n'ont pas été ajoutés à un vivier nommé.

| Données ou action   | Recruteur                                       | Responsable du recrutement                                  | Intervieweur |
|------------------|-------------------------------------------------|-------------------------------------------------|-------------|
| Vivier nommé       | Privilèges complets pour les viviers que l'utilisateur crée | Privilèges complets pour les viviers que l'utilisateur crée | Pas d'accès   |
| Partager le vivier       | Seuls les viviers que l'utilisateur crée                | Seuls les viviers que l'utilisateur crée                | Pas d'accès   |
| Recherche de candidat | Capacités de recherche complètes                        | Capacités de recherche complètes                        | Pas d'accès   |

## <a name="candidates"></a>Candidats

Les candidats sont des personnes qui ont été ajoutées à un vivier de talents mais qui ne sont pas associés à une mission.

| Données                        | Recruteur                        | Responsable du recrutement                   | Intervieweur |
|-----------------------------|----------------------------------|----------------------------------|-------------|
| Profil – détails du candidat | Créer, lire, mettre à jour et supprimer | Créer, lire, mettre à jour et supprimer | Pas d'accès   |
| Documents                   | Créer, lire, mettre à jour et supprimer | Créer, lire, mettre à jour et supprimer | Pas d'accès   |
