---
title: Nouveautés ou modifications dans Dynamics 365 Talent (23 juillet 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/23/2019
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
ms.search.validFrom: 2019-07-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 360574d3c8e0b349119e0987f2453a5d5be21e90
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528145"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-23-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (23 juillet 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

### <a name="pdf-renderer-for-candidate-documents"></a>Convertisseur PDF pour les documents des candidats

Les utilisateurs Attract peuvent maintenant visualiser les pièces jointes au format PDF des candidats dans la visionneuse de documents au lieu de télécharger les pièces jointes.

### <a name="signing-up-for-attract-user-research-group"></a>Inscription au groupe de recherche d'utilisateurs Attract 

Comme nous prévoyons de nouvelles fonctionnalités de produit ou des fonctionnalités en version préliminaire, nous recherchons des utilisateurs pour nous aider à définir l'orientation à suivre. Les utilisateurs intéressés peuvent s'inscrire pour faire partie de notre groupe de recherche d'utilisateurs via le lien d'inscription dans notre application.

### <a name="job-approvals-appear-on-the-home-page"></a>Les approbations des missions s'affichent dans la page d'accueil

Les approbations apparaissent dans une section **Approbations** du tableau de bord. Les approbateurs peuvent analyser leurs approbations sous **Affecté à vous**, qui affiche l'ID de mission, l'intitulé, les autres approbateurs, et la date à laquelle le poste a été affecté. Les utilisateurs qui soumettent une mission pour approbation peuvent analyser leurs missions sous **Demandé par vous**, qui affiche les approbateurs qui doivent toujours approuver la mission envoyée.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard
Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR
Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2394.

### <a name="entity-support-for-custom-fields-in-common-data-service"></a>Prise en charge par les entités des champs personnalisés dans Common Data Service 

Avec cette version, **Calendrier de travail** et **Calendrier de travail** prennent en charge les champs personnalisés dans Common Data Service.

### <a name="restrict-leave-types-in-time-off-requests"></a>Limitation des types d'absence dans les demandes de congés

Les organisations peuvent proposer plusieurs types de congés aux employés. Toutefois, il peut ne pas être pertinent que des employés soumettent leurs demandes de congé pour certains types d'absence. Ces types d'absence peuvent être traités par le service RH. Avec cette version, vous pouvez configurer pour quels types d'absence les employés peuvent envoyer des demandes de congés. 

## <a name="in-preview"></a>En mode aperçu

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Les fonctions d'aperçu sont uniquement activées dans les instances de bac à sable

Lorsque vous provisionnez une nouvelle instance de Talent, vous pouvez indiquer si le type d'instance est **Production** ou **Bac à sable**. Les instances du type **Bac à sable** permettent de tester les nouvelles fonctions en avant-première. Toutes les instances de Talent existantes seront mises à jour avec le type d'instance **Production**. Si vous souhaitez que l'une de vos instances existantes soit mise à jour avec le type d'instance **Bac à sable** (sandbox), contactez le [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) pour initier la demande de modification.

Pour plus d'informations sur la manière dont les modifications sont publiées, voir [Mettre en service Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Afficher les informations étendues des performances dans la gestion en libre service

Une nouvelle option permet aux responsables d'afficher les performances des états directs et de leurs états étendus. Actuellement, les chefs hiérarchiques peuvent affecter et mettre à jour les objectifs de performances et publier de nouvelles révisions, qui sont co-gérées par leurs collaborateurs. En outre, les responsables directs et leurs employés peuvent gérer et tenir à jour les journaux de performances pour garantir que le processus d'examen des performances est fluide. Lorsque cette modification est mise en œuvre, les responsables peuvent afficher et tenir à jour les informations relatives aux performances pour leurs états étendus en plus de leurs états directs. 

## <a name="coming-soon"></a>Prochainement

### <a name="region-support-for-canada-and-southeast-asia"></a>La prise en charge des régions pour le Canada et l'Asie du Sud-Est

Nous sommes ravis d'annoncer que les régions du Canada et de l'Asie du Sud-Est seront disponibles pour Talent le 1er août 2019. Avec ce changement, vous pouvez créer des environnements dans les régions du Canada et de l'Asie, et toutes les données Talent seront gérées uniquement dans ces emplacements. Vous pouvez créer un environnement dans ces nouvelles régions en sélectionnant l'emplacement dans la boîte de dialogue Nouvel environnement et en utilisant cet environnement pour mettre en service Talent dans LCS, comme décrit dans [Mettre en service Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

La migration des données de projets existants dans d'autres régions vers les régions du Canada et d'Asie n'est pas prise en charge. Seuls les nouveaux projets peuvent être mis en service dans ces nouvelles régions prises en charge.
