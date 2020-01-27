---
title: Nouveautés et modifications dans Dynamics 365 Talent (16 avril 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-04-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a37436eb15ee4c561d5d0c15c90e37815cb80860
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897923"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-16-2019"></a>Nouveautés et modifications dans Dynamics 365 Talent (16 avril 2019)

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

### <a name="process-auditing"></a>Audit de processus

Vous pouvez désormais suivre les modifications apportées aux candidats, aux postes à pourvoir et aux candidatures à un poste. Pour plus d'informations, voir [Effectuer le suivi des données de recrutement](process-auditing.md).

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2239. Les numéros entre parenthèses se rapportent aux numéros de support dans Lifecycle Services (LCS).

### <a name="compensation-region-compensation-level-benefit-option-and-skill-type-entities-in-common-data-service-updated-to-include-customer-field-support"></a>Les entités Région de rémunération, Niveau de rémunération, Option d'avantage et Type de compétence dans Common Data Service ont été mis à jour pour inclure la prise en charge des champs client

Avec cette version, ces entités Common Data Service ont été mises à jour pour comprendre la possibilité d'inclure un champ personnalisé ajouté via Talent : Core HR.

### <a name="new-common-data-service-entity-support-for-compensation-vesting-rules-compensation-variable-plan-variable-compensation"></a>Nouvelle prise en charge d'entité Common Data Service pour : Règles d'acquisition de la rémunération, Régime variable de rémunération, Rémunération variable

Avec cette version, les entités Règles d'acquisition de la rémunération, Régime variable de rémunération et Rémunération variable ont été ajoutées à Common Data Service. Ces entités sont également compatibles avec les champs personnalisés ajoutés via Talent : Core HR.

### <a name="powerbi-refresh-issues-314342"></a>Problèmes d'actualisation de PowerBI (314342)

Cette modification corrige un problème avec les états de PowerBI s'actualisant correctement.

### <a name="unable-to-click-directly-through-on-transition-tasks-in-employee-self-service-303309"></a>Impossible de cliquer directement sur des tâches de transition dans le libre service des employés (303309)

Cette modification permet aux utilisateurs avec le rôle d'employé de sélectionner et de mettre à jour des tâches de transition dans la liste de tâches de Talent.

### <a name="performance-feedback-email-message-updated-309615"></a>Message électronique en rétroaction sur les performances mis à jour (309615)

Avec cette modification, un message de confirmation s'affiche si le commentaire a bien été envoyé.

### <a name="missing-tables-in-word-template-308048"></a>Tableaux manquants dans le modèle Word (308048)

Avec cette modification, lors de la création d'un modèle Word avec des informations sur l'employé et ses compétences, seules les compétences de l'employé sélectionné apparaissent dans le document Word.

### <a name="when-applying-an-offboarding-checklist-an-error-is-displayed-299877"></a>Lors de l'application d'une liste de contrôle de départ, une erreur est affichée. (299877)

Cette modification corrige un problème lors de l'application d'une liste de contrôle de départ directement à partir de l'écran Collaborateur.

## <a name="in-preview"></a>En mode aperçu

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Autoriser les codes motif à être spécifiés sur les types de départ

Les organisations peuvent avoir besoin d'informations supplémentaire sur les demandes de congé. Vous pouvez désormais spécifier les codes motif des types de départ et permettre aux employés de sélectionner un code motif pour leurs demandes de congé.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Codes motif requis pour certains types d'absence dans les demandes de congés

Les organisations peuvent exiger des codes motif pour certains types d'absence lorsque les employés envoient une demande de congé. Cela peut découler d'une stratégie de la société ou d'exigences réglementaires. Vous pouvez désormais spécifier les types d'absence qui nécessitent un code motif, et vous pouvez exiger que les employés fournissent un code motif pour le type d'absence dans leurs demandes de congé.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Fournir une liste de transactions de départ et d'absence pour les RH

Le suivi des congés des employés et la compréhension du calcul des congés aide non seulement les RH à répondre aux questions des employés, mais assure aussi l'attribution exacte des durées de congé aux employés. Les RH disposent désormais d'une nouvelle vision des transactions (dotations, cumuls, ajustements et demandes) pour voir les causes des soldes.

## <a name="coming-soon"></a>Prochainement

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Améliorations apportées à l'interface utilisateur pour la vérification des doublons d'employé

Avec cette modification, les doublons sont détectés au moment de renseigner les champs de nom. Un champ de statut affiche le nombre de doublons trouvés. Vous pouvez sélectionner le lien fourni pour ouvrir une nouvelle page pour évaluer s'il convient d'utiliser la correspondance détectée. Pour éviter d'interrompre la saisie des données, l'écran des doublons ne s'ouvre pas automatiquement.

### <a name="email-support-for-alerts"></a>Prise en charge des alertes par e-mail

Dans Platform Update 25 pour Finance and Operations, les utilisateurs peuvent créer des règles d'alerte qui envoient automatiquement des notifications par e-mail aux contacts lorsque des notifications sont déclenchées par un événement.


