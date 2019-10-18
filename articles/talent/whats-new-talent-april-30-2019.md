---
title: Nouveautés et modifications dans Dynamics 365 Talent (30 avril 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/30/2019
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
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 38158948dbcf8966edf49bcce5b1e5da7eddb8dc
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2026034"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-30-2019"></a>Nouveautés et modifications dans Dynamics 365 Talent (30 avril 2019)

[!include [banner](includes/banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications qui sont décrites dans cette section s'appliquent au numéro de version 8.1.2270. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

### <a name="provide-feedback"></a>Transmettre des commentaires

L'option pour fournir une rétroaction est située dans le menu **Aide** (**?**) dans Talent. Ce menu permet d'accéder aux ressources suivantes :

- Rétroaction
- Affiche l'aide
- Mise en route
- Support
- Idées
- À propos de

### <a name="improvements-to-the-user-interface-for-duplicate-employee-detection"></a>Améliorations apportées à l'interface utilisateur pour la détection des doublons d'employé

En raison de ce changement, les doublons sont maintenant détectés lorsque vous définissez les champs de nom, et un indicateur de statut indique le nombre de doublons détectés. Un lien qui est fourni ouvre une page sur laquelle vous pouvez évaluer si vous devez utiliser l'un des doublons. Pour éviter d'interrompre la saisie des données, la page des doublons ne s'ouvre pas automatiquement. Vous devez sélectionner le lien pour ouvrir la page.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Prise en charge de l'entité Common Data Service pour les champs personnalisés

Dans la version de cette semaine, les entités suivantes prennent en charge désormais les champs personnalisés : Emploi, Type d'avantage, et Cycle de paie.

### <a name="an-error-occurs-when-an-off-boarding-checklist-is-assigned-299877"></a>Une erreur se produit lorsqu'une liste de contrôle de départ est affectée (299877)

Cette modification corrige un message d'erreur qui apparaît lorsque vous affectez une liste de contrôle de départ à un employé en dehors du processus de fin de contrat.

### <a name="the-exited-workers-link-opens-the-wrong-worker-309939"></a>Le lien des collaborateurs partis ouvre un collaborateur erroné (309939)

Cette modification corrige un problème qui se produit lorsque vous rembauchez un employé d'une autre entité juridique et essayez d'accéder à l'employé depuis la liste des collaborateurs étant partis.

### <a name="the-employee-self-service-compensation-card-doesnt-show-summary-values-when-advanced-security-is-turned-on-315231"></a>La carte de rémunération en libre service de l'employé n'affiche pas les valeurs de synthèse lorsque la sécurité avancée est activée (315231)

Cette modification corrige un problème qui se produit lorsque vous utilisez la sécurité de rémunération avancée. Lorsque la sécurité avancée est activée, le libre service de l'employé affiche maintenant les montants de synthèse de rémunération pour les employés et les responsables. Avant cette modification, les valeurs de synthèse affichaient 0 (zéro).

### <a name="if-a-position-without-a-title-is-created-in-common-data-service-no-position-is-created-in-talent-314562"></a>Si un poste sans titre est créé dans Common Data Service, aucun poste n'est créé dans Talent (314562)

Les modifications de cette semaine corrigent un problème qui se produit lorsque vous créez des postes dans Common Data Service sans fournir de titre.

### <a name="error-message-in-performance-journal-entries-in-employee-self-service-314134"></a>Message d'erreur dans les entrées d'un journal de performances dans le libre service de l'employé (314134)

Cette modification corrige un problème qui se produit lorsque vous associez des objectifs de performances aux entrées du journal de performances dans le libre service de l'employé.

## <a name="in-preview"></a>En mode aperçu

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Autoriser les codes motif à être spécifiés sur les types de départ

Les organisations peuvent nécessiter des informations supplémentaires sur les demandes de congé. Vous pouvez désormais spécifier les codes motif des types de départ et laisser les employés sélectionner un code motif pour leurs demandes de congé.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Codes motif requis pour des types d'absence spécifiques dans les demandes de congés

Les organisations peuvent exiger des codes motif pour certains types d'absence lorsque les employés envoient des demandes de congé. Cette condition peut exister à cause de la stratégie de la société ou des règlementations. Vous pouvez désormais spécifier les types d'absence qui nécessitent un code motif, et vous pouvez exiger que les employés fournissent un code motif pour le type d'absence dans leurs demandes de congé.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fournir une liste de transactions de congé et d'absence pour les RH

La possibilité de suivre les congés des employés et de comprendre le calcul des congés aide non seulement les Ressources humaines (RH) à répondre aux questions des employés, mais aussi de s'assurer de l'attribution exacte des durées de congé aux employés. Les RH disposent désormais d'une nouvelle vision des transactions (dotations, cumuls, ajustements et demandes) afin que le personnel des RH puisse voir les causes des soldes.

## <a name="coming-soon"></a>Prochainement

### <a name="email-support-for-alerts"></a>Prise en charge des alertes par e-mail

Dans Platform Update 26 pour Finance and Operations, les utilisateurs peuvent créer des règles d'alerte qui envoient automatiquement des notifications par e-mail aux contacts lorsque des notifications sont déclenchées par un événement.
