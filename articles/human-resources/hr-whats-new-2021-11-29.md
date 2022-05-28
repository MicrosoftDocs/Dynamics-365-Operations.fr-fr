---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (19 novembre 2021)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources autonome à la date du 19 novembre 2021.
author: marcelbf
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f28057c370b27dbdad4bfe1104e9289f7df65621
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691944"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-november-19-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (19 novembre 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou seront bientôt disponibles dans Microsoft Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [2e vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version contient les correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4591.

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cette rubrique pour inclure des correctifs de bogues qui auront été intégrés à la version après la publication initiale de cette rubrique.

| Numéro du problème | Problème | Description |
|---|---|---|
| 626178 | La navigation est manquante dans les vignettes des collaborateurs dans **Responsable en libre-service** | Ce problème est désormais résolu. La navigation est disponible pour voir les détails du rapport dans **Libre-service des responsables**. |
| 632573 | Il n’y a pas d’erreur de validation lors de l’enregistrement d’un **Cours** | Ce problème est désormais résolu. Lors de la création d’un cours dont le **Nombre minimum de participants** était supérieur à 0, l’enregistrement était toujours possible même avec un **Nombre maximum de participants** de 0. |
| 615955 | Erreur : « Le champ **Objectif** doit être renseigné » lors de la création d’un nouvel emplacement de demande de recrutement. | Lors de la création d’une adresse pour un emplacement de demande de recrutement, vous obtenez l’erreur : Le champ « Objectif » doit être renseigné. Cependant, le champ **Objectif** n’est pas disponible sur la page. |
| 620797 | Erreur trompeuse à propos du champ **Genre** vide | Lorsqu’un genre n’est pas saisi pour un contact personnel, le rapport affiche « Cliquez ou appuyez ici pour saisir du texte », ce qui est trompeur car rien ne peut être saisi dans le champ. |
| 620800 | Le lien du relevé des avantages est masqué | Le relevé des avantages n’est pas visible par défaut dans le **Libre-service des employés**.  Un lien a été ajouté sur le côté droit du **Libre-service des employés** sous la section **Liens** |
| 629778 | Problème de performances avec l’intégration de CDS. | La demande liée à l’autorisation a causé un problème de performances. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation et la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
|---|---|---|
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |


## <a name="coming-soon"></a>Bientôt disponible
Pour obtenir la liste complète des fonctionnalités planifiées et de leurs lancements planifiés, voir [Dynamics 365 et les clouds du secteur : 2e vague de lancement 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
