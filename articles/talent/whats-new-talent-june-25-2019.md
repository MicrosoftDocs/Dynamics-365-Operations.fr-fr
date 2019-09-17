---
title: Nouveautés ou modifications dans Dynamics 365 for Talent (25 juin 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/25/2019
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
ms.search.validFrom: 2019-06-25
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 3c7a13373193a6af4033b4609f0c338c2c6128c6
ms.sourcegitcommit: 1bf6a8b2f872394a4f242f9ff13c67e8e1ae8f65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/03/2019
ms.locfileid: "1856351"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-june-25-2019"></a>Nouveautés ou modifications dans Dynamics 365 for Talent (25 juin 2019)

[!include [banner](includes/banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut les correctifs de bogues mineurs pour Dynamics 365 Talent : Attract.

## <a name="coming-soon-in-attract"></a>Bientôt dans Attract

### <a name="job-approvals-appear-on-the-home-page"></a>Les approbations des missions s'affichent dans la page d'accueil

Les approbations apparaissent dans une section **Approbations** du tableau de bord. Les approbateurs peuvent analyser leurs approbations sous **Affecté à vous**, qui affiche l'ID de mission, l'intitulé, les autres approbateurs, et la date à laquelle le poste a été affecté. Les utilisateurs qui soumettent une mission pour approbation peuvent analyser leurs missions sous **Demandé par vous**, qui affiche les approbateurs qui doivent toujours approuver la mission envoyée.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard
Cette version inclut les correctifs de bogues mineurs pour Dynamics 365 Talent : Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2357.

### <a name="incorrect-value-displayed-for-primary-position-314266"></a>Valeur incorrecte affichée pour le poste principal (314266)

Ces modifications afficheront uniformément le paramètre **Poste principal** sur toutes les pages.

### <a name="cant-edit-after-recalling-the-workflow-in-review-318180"></a>Modification impossible après avoir rappelé le workflow en cours de révision (318180)

Les révisions qui ont été rappelées via un workflow peuvent désormais être modifiées.

### <a name="final-comments-field-in-reviews-isnt-translated-325921"></a>Le champ Commentaires finaux dans les révisions n'est pas traduit (325921)

Le libellé **Commentaires finaux** sera traduit dans Talent.

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Les fonctions d'aperçu sont activées uniquement dans des environnements de bac à sable

Lorsque vous provisionnez une nouvelle instance de Talent, vous pouvez indiquer si le type d'instance est **Production** ou **Bac à sable**. Le type d'instance **Bac à sable** permet de tester les nouvelles fonctions en avant-première. Toutes les instances de Talent existantes seront mises à jour avec le type d'instance **Production**. Si vous souhaitez que l'une de vos instances existantes soit mise à jour avec le type d'instance **Bac à sable** (sandbox), contactez le [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) pour initier la demande de modification.

Pour plus d'informations sur la manière dont les modifications sont publiées, voir [Mettre en service Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

## <a name="in-preview"></a>En mode aperçu

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Limitation des types de départ dans les demandes de congés

Les organisations peuvent proposer de nombreux types d'absence aux employés. Toutefois, il peut ne pas être pertinent que des employés soumettent leurs demandes de congé pour certains types d'absence. Ces types d'absence peuvent être traités par le service RH. Avec cette version, vous pouvez configurer pour quels types d'absence les employés peuvent envoyer des demandes de congés. 

## <a name="coming-soon-in-core-hr"></a>Prochainement dans Core HR

### <a name="feature-management-area-in-talent"></a>Zone de gestion des fonctions dans Talent

La **Gestion des fonctions** sera supprimée de l'**Administration système** en raison de problèmes. Nous réintroduirons la **Gestion des fonctions** dans une version future. 

### <a name="common-data-service-entity-support-for-custom-fields"></a>Prise en charge de l'entité Common Data Service pour les champs personnalisés

Les entités suivantes prendront en charge les champs personnalisés : **Code de rémunération de la paie**, **Événement de rémunération fixe**, **Grille de rémunération**, **Période de rémunération** et **Point de référence de rémunération**. 

### <a name="new-common-data-service-entities"></a>Nouvelles entités Common Data Service

L'entité **Codes motif** sera ajoutée à Common Data Service.

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Afficher les informations de performances pour les états directs et étendus dans la gestion en libre service

Une nouvelle option permet aux responsables d'afficher les performances des états directs et de leurs états étendus. Actuellement, les chefs hiérarchiques peuvent affecter et mettre à jour les objectifs de performances et publier de nouvelles révisions. En outre, les responsables directs et leurs employés peuvent gérer et tenir à jour les journaux de performances pour garantir que le processus d'examen des performances est fluide. Lorsque cette modification est mise en œuvre, les responsables peuvent afficher et tenir à jour les informations relatives aux performances pour leurs états étendus en plus de leurs états directs.

### <a name="print-performance-reviews"></a>Imprimer les évaluations des performances

Les employés, les responsables, et le service des RH peuvent imprimer l'examen des performances d'un employé.
