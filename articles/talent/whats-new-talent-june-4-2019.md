---
title: Nouveautés ou modifications dans Dynamics 365 Talent (4 juin 2019)
description: Cette rubrique décrit les fonctionnalités inédites ou ayant fait l'objet de modifications dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/04/2019
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
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4a42a3b817024447e2ff26cfcb3cdd0df1351158
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528039"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-june-4-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (4 juin 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Bientôt dans Attract

### <a name="job-approvals-on-the-home-page"></a>Approbations des missions dans la page d'accueil

Les approbations apparaissent dans une section **Approbations** du tableau de bord. Les approbateurs peuvent examiner leurs approbations sous **Affecté à vous**. Cette section affiche l'identifiant du poste, l'intitulé, les autres approbateurs, et la date à laquelle le poste a été affecté. Les utilisateurs qui soumettent un poste à approbation peuvent examiner leurs postes sous **Demandé par vous**. Cette section affiche les approbateurs qui doivent toujours approuver le poste soumis.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications qui sont décrites dans cette section s'appliquent au numéro de version 8.1.2330.

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nouvelle page pour valider les données de la hiérarchie des postes

Le personnel et les administrateurs des Ressources humaines (RH) peuvent valider la hiérarchie managériale pour toutes les références circulaires qui ont été importées par inadvertance. Vous pouvez accéder à cette nouvelle page depuis **Administration de l'organisation \> Liens \> Postes \> Validation de la hiérarchie des postes**.

### <a name="specify-reason-codes-on-leave-types"></a>Spécifier des codes motif sur les types d'absence

Les organisations peuvent nécessiter des informations supplémentaires sur les demandes de congé. Vous pouvez désormais spécifier les codes motif des types de départ et laisser les employés sélectionner un code motif pour leurs demandes de congé.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Codes motif requis pour des types d'absence spécifiques dans les demandes de congés

Les organisations peuvent exiger des codes motif pour certains types d'absence lorsque les employés envoient des demandes de congé. Cette condition peut exister à cause de la stratégie de la société ou des règlementations. Vous pouvez spécifier les types d'absence qui nécessitent un code motif, et vous pouvez exiger que les employés fournissent un code motif pour le type d'absence dans leurs demandes de congé.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fournir une liste de transactions de congé et d'absence pour les RH

La possibilité de suivre les congés des employés et de comprendre le calcul des congés aide non seulement les RH à répondre aux questions des employés, mais aussi de s'assurer de l'attribution exacte des durées de congé aux employés. Les RH disposent désormais d'une nouvelle vision des transactions (dotations, cumuls, ajustements et demandes) afin que le personnel des RH puisse voir les causes des soldes de congés.

### <a name="deleting-a-record-from-talent-doesnt-remove-the-record-from-common-data-service"></a>La suppression d'un enregistrement de Talent ne supprime pas l'enregistrement de Common Data Service

Les enregistrements qui sont supprimés de Talent : Core HR sont désormais également supprimés de Common Data Service.

### <a name="variable-compensation-plan-valid-fromto-dates-arent-being-honored"></a>Les date de début et de fin de validité du régime de rémunération variable ne sont pas respectées.

Dans cette version, vous ne pouvez pas inscrire un employé à un régime de rémunération variable si la date de début est antérieure à la date de début du plan ou la date de fin est postérieure à la date de fin du plan. 

### <a name="performance-review-comments-are-removed-when-users-select-cancel"></a>Les commentaires de l'examen des performances sont supprimés lorsque l'utilisateur sélectionne Annuler

Cette version corrige un problème : les commentaires de révision sont supprimés si l'utilisateur commence à modifier un commentaire, mais sélectionne **Annuler**. 

## <a name="in-preview"></a>En mode aperçu

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Les fonctions d'aperçu sont uniquement activées dans les instances de bac à sable

Lorsque vous provisionnez une nouvelle instance de Talent, vous pouvez indiquer si le type d'instance est **Production** ou **Bac à sable**. Les instances du type **Bac à sable** permettent de tester les nouvelles fonctions en avant-première. Toutes les instances de Talent existantes seront mises à jour avec le type d'instance **Production**. Si vous souhaitez que l'une de vos instances existantes soit mise à jour avec le type d'instance **Bac à sable** (sandbox), contactez le [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) pour initier la demande de modification.

Pour plus d'informations sur la manière dont les modifications sont publiées, voir [Mettre en service Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Limitation des types d'absence dans les demandes de congés

Les organisations peuvent proposer plusieurs types de congés aux employés. Toutefois, il peut ne pas être pertinent que des employés soumettent leurs demandes de congé pour certains types d'absence. Ces types d'absence peuvent être traités par le service RH. Avec cette version, vous pouvez configurer pour quels types d'absence les employés peuvent envoyer des demandes de congés. 

## <a name="coming-soon-in-core-hr"></a>Prochainement dans Core HR

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Afficher les informations étendues des performances dans la gestion en libre service

Une nouvelle option permet aux responsables d'afficher les performances des états directs et de leurs états étendus. Actuellement, les chefs hiérarchiques peuvent affecter et mettre à jour les objectifs de performances et publier de nouvelles révisions, qui sont co-gérées par leurs collaborateurs. En outre, les responsables directs et leurs employés peuvent gérer et tenir à jour les journaux de performances pour garantir que le processus d'examen des performances est fluide. Lorsque cette modification est mise en œuvre, les responsables peuvent afficher et tenir à jour les informations relatives aux performances pour leurs états étendus en plus de leurs états directs. 

### <a name="print-performance-reviews"></a>Imprimer les évaluations des performances

Les employés, les responsables, et le service des RH peuvent imprimer l'examen des performances d'un employé.


[!INCLUDE[footer-include](../includes/footer-banner.md)]