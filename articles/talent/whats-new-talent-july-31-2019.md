---
title: Nouveautés ou modifications dans Dynamics 365 Talent (30 juillet 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 311042caf6a391a06c7e2d8c4c2c2f6e1f855437
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461196"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-30-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (30 juillet 2019)

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract
Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard
Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR
Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2409.


### <a name="region-support-for-canada-and-southeast-asia"></a>La prise en charge des régions pour le Canada et l'Asie du Sud-Est

Nous sommes ravis d'annoncer que les régions du Canada et de l'Asie du Sud-Est seront disponibles pour Talent le 1er août 2019. Avec ce changement, vous pouvez créer des environnements dans les régions du Canada et de l'Asie, et toutes les données Talent seront gérées uniquement dans ces emplacements. Vous pouvez créer un environnement dans ces nouvelles régions en sélectionnant l'emplacement dans la boîte de dialogue Nouvel environnement et en utilisant cet environnement pour mettre en service Talent dans LCS, comme décrit dans [Mettre en service Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

La migration des données de projets existants dans d'autres régions vers les régions du Canada et d'Asie n'est pas prise en charge. Seuls les nouveaux projets peuvent être mis en service dans ces nouvelles régions prises en charge.

### <a name="new-active-positions-list-page"></a>Nouvelle page de liste Postes actifs

Les options pour les listes de postes incluent maintenant : **Tous les postes**, **Postes actifs**, **Postes vacants** et **Postes inactifs**. La nouvelle page de liste **Postes actifs** affiche uniquement les postes, vacants ou pourvus, qui sont actifs à la date actuelle. 

### <a name="allow-course-participants-to-be-added-to-open-courses"></a>Autoriser l'ajout de participants aux cours actifs

Les modifications de cette semaine corrigent le problème où seuls les états directs peuvent être enregistrés pour les cours actifs.

### <a name="fte-analysis-displaying-incorrect-fte-number"></a>L'analyse FTE affiche un numéro FTE non valide

L'**Analyse FTE** a été corrigée sous l'onglet **Analyses** de la **Gestion du personnel**.

### <a name="final-comments-label-translation"></a>Traduction du libellé Commentaires finaux

Le libellé **Commentaires finaux** est maintenant traduit dans le formulaire de révision.

## <a name="in-preview"></a>En mode aperçu

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Les fonctions d'aperçu sont uniquement activées dans les instances de bac à sable

Lorsque vous provisionnez une nouvelle instance de Talent, vous pouvez indiquer si le type d'instance est **Production** ou **Bac à sable**. Les instances du type **Bac à sable** permettent de tester les nouvelles fonctions en avant-première. Toutes les instances de Talent existantes seront mises à jour avec le type d'instance **Production**. Si vous souhaitez que l'une de vos instances existantes soit mise à jour avec le type d'instance **Bac à sable** (sandbox), contactez le [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) pour initier la demande de modification.

Pour plus d'informations sur la manière dont les modifications sont publiées, voir [Mettre en service Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Afficher les informations étendues des performances dans la gestion en libre service

Une nouvelle option permet aux responsables d'afficher les performances des états directs et de leurs états étendus. Actuellement, les chefs hiérarchiques peuvent affecter et mettre à jour les objectifs de performances et publier de nouvelles révisions. En outre, les responsables directs et leurs employés peuvent gérer et tenir à jour les journaux de performances pour garantir que le processus d'examen des performances est fluide. Lorsque cette modification est mise en œuvre, les responsables peuvent afficher et tenir à jour les informations relatives aux performances pour leurs états étendus en plus de leurs états directs.
