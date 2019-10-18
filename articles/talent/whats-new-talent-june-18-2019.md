---
title: Nouveautés ou modifications dans Dynamics 365 Talent (18 juin 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/18/2019
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
ms.search.validFrom: 2019-06-18
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 059a0bad2f56b97a1708b64eab9d2adda6d2c8ad
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009051"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-june-18-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (18 juin 2019)

[!include [banner](includes/banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Bientôt dans Attract

### <a name="job-approvals-appear-on-the-home-page"></a>Les approbations des missions s'affichent dans la page d'accueil

Les approbations apparaissent dans une section **Approbations** du tableau de bord. Les approbateurs peuvent analyser leurs approbations sous **Affecté à vous**, qui affiche l'ID de mission, l'intitulé, les autres approbateurs, et la date à laquelle le poste a été affecté. Les utilisateurs qui soumettent une mission pour approbation peuvent analyser leurs missions sous **Demandé par vous**, qui affiche les approbateurs qui doivent toujours approuver la mission envoyée.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications qui sont décrites dans cette section s'appliquent au numéro de version 8.1.2347.

### <a name="confirmation-of-course-participants-causes-an-error"></a>La confirmation des participants au cours entraîne une erreur

La boîte de dialogue pour imprimer l'état sur les participants au cours a été supprimée. Cet état n'est pas pris en charge dans Talent.

### <a name="the-compensation-section-of-the-transfer-worker-page-isnt-available-in-some-scenarios"></a>La section Rémunération de la page Transférer le collaborateur n'est pas disponible dans certains scénarios

Cette modification permet aux utilisateurs de saisir les données de rémunération lorsqu'ils renseignent la page **Transférer le collaborateur**.

## <a name="in-preview"></a>En mode aperçu

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Les fonctions d'aperçu sont activées uniquement dans des environnements de bac à sable

Pour plus d'informations sur la manière dont les modifications sont publiées, voir [Mettre en service Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

Lorsque vous provisionnez une nouvelle instance de Talent, vous pouvez indiquer si le type d'instance est **Production** ou **Bac à sable**. Le type d'instance **Bac à sable** permet de tester les nouvelles fonctions en avant-première. Toutes les instances de Talent existantes seront mises à jour avec le type d'instance **Production**. Si vous souhaitez que l'une de vos instances existantes soit mise à jour avec le type d'instance **Bac à sable** (sandbox), contactez le [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) pour initier la demande de modification.

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Limitation des types de départ dans les demandes de congés

Les organisations peuvent proposer de nombreux types d'absence aux employés. Toutefois, il peut ne pas être pertinent que des employés soumettent leurs demandes de congé pour certains types d'absence. Ces types d'absence peuvent être traités par le service RH. Avec cette version, vous pouvez configurer pour quels types d'absence les employés peuvent envoyer des demandes de congés. 

## <a name="coming-soon-in-core-hr"></a>Prochainement dans Core HR

### <a name="common-data-service-entity-support-for-custom-fields"></a>Prise en charge de l'entité Common Data Service pour les champs personnalisés

Les entités suivantes prendront en charge les champs personnalisés : Code de rémunération de la paie et Point de référence de la rémunération. 

### <a name="new-common-data-service-entities"></a>Nouvelles entités Common Data Service

L'entité Codes motif est ajoutée à Common Data Service.

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Afficher les informations de performances pour les états directs et étendus dans la gestion en libre service

Une nouvelle option permet aux responsables d'afficher les performances des états directs et de leurs états étendus. Actuellement, les chefs hiérarchiques peuvent affecter et mettre à jour les objectifs de performances et publier de nouvelles révisions. En outre, les responsables directs et leurs employés peuvent gérer et tenir à jour les journaux de performances pour garantir que le processus d'examen des performances est fluide. Lorsque cette modification est mise en œuvre, les responsables peuvent afficher et tenir à jour les informations relatives aux performances pour leurs états étendus en plus de leurs états directs.

### <a name="print-performance-reviews"></a>Imprimer les évaluations des performances

Les employés, les responsables, et le service des RH peuvent imprimer l'examen des performances d'un employé.
