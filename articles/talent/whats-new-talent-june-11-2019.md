---
title: Nouveautés ou modifications dans Dynamics 365 Talent (11 juin 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/11/2019
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
ms.search.validFrom: 2019-06-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 20dc0768463d9a5d6762cb062deb0bdbe4d53fe3
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528667"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-june-11-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (11 juin 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

### <a name="search-engine-optimization-for-job-posts"></a>Optimisation du moteur de recherche pour les offres d'emploi

Après avoir activé l'**Optimisation du moteur de recherche** dans le centre d'administration de Dynamics 365 Talent: Attract, Attract informe l'API d'indexation Google d'analyser la page Web chaque fois que vous activez et publiez une nouvelle offre d'emploi ou en mettez une existante à jour. De cette manière, l'offre d'emploi s'affiche dans les résultats de la recherche Google et d'autres moteurs de recherche.

De même, lorsque vous annulez la publication d'une offre d'emploi, Attract en informe l'API d'indexation, de sorte que l'offre d'emploi n'apparaîtra plus dans les résultats de la recherche.

> [!NOTE]
> Les robots d'indexation Web n'ont pas de plage de temps définie pour parcourir les pages Web ou mettre à jour les résultats de la recherche.

## <a name="coming-soon-in-attract"></a>Bientôt dans Attract

### <a name="job-approvals-appear-on-the-home-page"></a>Les approbations des missions s'affichent dans la page d'accueil

Les approbations apparaissent dans une section **Approbations** du tableau de bord. Les approbateurs peuvent analyser leurs approbations sous **Affecté à vous**, qui affiche l'ID de mission, l'intitulé, les autres approbateurs, et la date à laquelle le poste a été affecté. Les utilisateurs qui soumettent une mission pour approbation peuvent analyser leurs missions sous **Demandé par vous**, qui affiche les approbateurs qui doivent toujours approuver la mission envoyée.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications qui sont décrites dans cette section s'appliquent au numéro de version 8.1.2337.

### <a name="platform-update-27-for-finance-and-operations"></a>Mise à jour de la plateforme 27 pour Finance and Operations

Pour des informations complémentaires sur Platform Update 27 pour Finance and Operations, voir [Fonctionnalités en version préliminaire dans Dynamics 365 Finance and Operations Platform Update 27 (juin 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-27).

### <a name="feature-management-workspace-in-talent"></a>Espace de travail de la gestion des fonctions dans Talent

L'espace de travail **Gestion des fonctions** dans **Administration système** permet d'afficher, activer, désactiver, et planifier les fonctions fournies dans chaque version. Par défaut, les nouvelles fonctionnalités sont désactivées. Vous pouvez utiliser l'espace de travail **Gestion des fonctions** pour les activer et consulter la documentation les concernant.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Prise en charge de l'entité Common Data Service pour les champs personnalisés

L'entité Agence émettrice prend désormais en charge les champs personnalisés.

### <a name="new-common-data-service-entities"></a>Nouvelles entités Common Data Service

L'entité Groupe de tâches a été ajoutée.

## <a name="in-preview"></a>En mode aperçu

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Les fonctions d'aperçu sont activées uniquement dans des environnements de bac à sable

Pour plus d'informations sur la manière dont les modifications sont publiées, voir [Mettre en service Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

Lorsque vous provisionnez une nouvelle instance de Talent, vous pouvez indiquer si le type d'instance est Production ou Bac à sable. Le type d'instance Bac à sable permet de tester les nouvelles fonctions en avant-première. Toutes les instances de Talent existantes seront mises à jour avec le type d'instance **Production**. Si vous souhaitez que l'une de vos instances existantes soit mise à jour avec le type d'instance **Bac à sable** (sandbox), contactez le [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) pour initier la demande de modification.

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Limitation des types de départ dans les demandes de congés

Les organisations peuvent proposer de nombreux types d'absence aux employés. Toutefois, il peut ne pas être pertinent que des employés soumettent leurs demandes de congé pour certains types d'absence. Ces types d'absence peuvent être traités par le service RH. Avec cette version, vous pouvez configurer pour quels types d'absence les employés peuvent envoyer des demandes de congés. 

## <a name="coming-soon-in-core-hr"></a>Prochainement dans Core HR

### <a name="view-extended-information-about-report-performance-in-manager-self-service"></a>Afficher les informations étendues sur les performances des états dans la gestion en libre service

Une nouvelle option permet aux responsables d'afficher les performances des états directs et de leurs états étendus. Actuellement, les chefs hiérarchiques peuvent affecter et mettre à jour les objectifs de performances et publier de nouvelles révisions. En outre, les responsables directs et leurs employés peuvent gérer et tenir à jour les journaux de performances pour garantir que le processus d'examen des performances est fluide. Lorsque cette modification est mise en œuvre, les responsables peuvent afficher et tenir à jour les informations relatives aux performances pour leurs états étendus en plus de leurs états directs.

### <a name="print-performance-reviews"></a>Imprimer les évaluations des performances

Les employés, les responsables, et le service des RH peuvent imprimer l'examen des performances d'un employé.
