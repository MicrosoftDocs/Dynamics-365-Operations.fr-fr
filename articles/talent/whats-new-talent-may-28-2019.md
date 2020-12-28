---
title: Nouveautés ou modifications dans Dynamics 365 Talent (28 mai 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/28/2019
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
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 29e941ddab1b2746ccd74d6e335fec7742d1391e
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529606"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-28-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (28 mai 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract
Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Bientôt dans Attract

### <a name="job-approvals-on-home-page"></a>Approbations de missions dans la page d'accueil

Les approbations apparaissent dans une section **Approbations** du tableau de bord. Les approbateurs peuvent analyser leurs approbations sous **Affecté à vous**, qui affiche l'ID de mission, le titre, d'autres approbateurs, et la date affectée. Les utilisateurs qui soumettent une mission pour approbation peuvent analyser leurs missions sous **Demandé par vous**, qui affiche les approbateurs qui doivent toujours approuver la mission envoyée.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard
Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR
Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2319.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Prise en charge de l'entité Common Data Service pour les champs personnalisés

Dans cette version, les entités suivantes pour Common Data Service prennent en charge des champs personnalisés : Détail du taux de calcul des avantages, ligne Congés du calendrier de travail et Emploi.

### <a name="copy-position-now-includes-payroll-details"></a>Copier le poste comprend maintenant des détails sur le salaire
Lorsque vous utilisez **Copier le poste** puis sélectionnez des options, les informations de détails sur le salaire sont désormais incluses dans les informations de copie. 

## <a name="in-preview-in-core-hr"></a>En aperçu dans Core HR

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Limitation des types de départ dans les demandes de congés

Les organisations peuvent proposer plusieurs types de congés aux employés. Certains de ces types de départ ne sont pas appropriés pour les employés envoient des congés et sont gérés par les Ressources humaines (RH) à la place. Avec cette version, vous pouvez configurer pour quels types de congés les employés peuvent envoyer des demandes de congés. 

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nouvelle page pour valider les données de la hiérarchie des postes

Les RH et les administrateurs peuvent valider la hiérarchie managériale pour toutes les références circulaires qui peuvent avoir été importées par inadvertance. Vous pouvez accéder à cette nouvelle page depuis **Administration de l'organisation > Liens > Postes > Validation de la hiérarchie des postes**.

### <a name="specify-reason-codes-on-leave-types"></a>Spécifier des codes motif sur les types d'absence

Les organisations peuvent nécessiter des informations supplémentaires sur les demandes de congé. Vous pouvez désormais spécifier les codes motif des types de départ et laisser les employés sélectionner un code motif pour leurs demandes de congé.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Codes motif requis pour des types d'absence spécifiques dans les demandes de congés

Les organisations peuvent exiger des codes motif pour certains types d'absence lorsque les employés envoient des demandes de congé. Cette condition peut exister à cause de la stratégie de la société ou des règlementations. Vous pouvez spécifier les types d'absence qui nécessitent un code motif, et vous pouvez exiger que les employés fournissent un code motif pour le type d'absence dans leurs demandes de congé.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fournir une liste de transactions de congé et d'absence pour les RH

La possibilité de suivre les congés des employés et de comprendre le calcul des congés aide non seulement les RH à répondre aux questions des employés, mais aussi de s'assurer de l'attribution exacte des durées de congé aux employés. Les RH disposent désormais d'une nouvelle vision des transactions (dotations, cumuls, ajustements et demandes) afin que le personnel des RH puisse voir les causes des soldes de congés.
