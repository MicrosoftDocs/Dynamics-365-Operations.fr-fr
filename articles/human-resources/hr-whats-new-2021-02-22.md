---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources 22 février 2021
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources au 22 février 2021.
author: marcelbf
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 53e9c42f718665165be97e5022a9e767b0436e59
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802213"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-22-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources 22 février 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou seront bientôt disponibles dans Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 1re vague de lancement Dynamics 365 Human Resources 2021](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.3988.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Application Dynamics 365 Human Resources pour Microsoft Teams | [Expérience de congé et d’absence des employés dans Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Application Human Resources de Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Gérer les demandes de congés dans Teams](hr-teams-leave-app.md) |

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cette rubrique pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cette rubrique.

| Numéro du problème | Sortie |  Description |
| --- | --- | --- |
| 529994 | Modifier le champ **Connu comme** sur le formulaire **collaborateur** ne déclenche pas la mise à jour de Dataverse | Correction d’un problème où Dataverse ne se met pas à jour lorsque le champ **Connu comme** est mis à jour sur le formulaire **collaborateur**. |
| 532651 | Le rapport PBI d’analyse de la rémunération n’utilise pas la conversion de devise lors du calcul des métriques pour toutes les entreprises | Correction d’un problème où le rapport PBI d’analyse de la rémunération n’effectuait pas correctement les conversions de devises. |
| 552226 | Le traitement des événements de la vie ferme et rouvre les plans plusieurs fois pour un seul événement de la vie  | Correction d’un problème où un employé appartient à plusieurs entités juridiques et qu’un événement de la vie se produit, un enregistrement d’événement de la vie est généré pour chaque entité juridique dans laquelle l’employé appartient. Lors du traitement des événements de la vie, l’entité juridique à traiter doit être sélectionnée. Cependant, la logique de traitement ne se limite pas à cette entité juridique. Au lieu de cela, il traite pour toutes les entités juridiques et ferme et rouvre les plans dans l’entité juridique sélectionnée. Cette action est un événement de la vie à traiter plusieurs fois dans la même entité juridique, entraînant plusieurs fermetures / réouvertures de chaque plan affecté par l’événement de la vie. |
| 518064 | Une seule personne à charge sélectionnée dans le cadre de régimes éligibles lorsque plus d’une est marquée comme désignée par défaut | Correction d’un problème où plusieurs personnes désignées par défaut ne sont pas sélectionnées automatiquement dans les plans éligibles. Vous pouvez également désormais désigner un bénéficiaire principal pour un contact personnel. Le bénéficiaire principal est répertorié à 100 % dans les régimes admissibles lorsqu’il y a plusieurs bénéficiaires. |
| 552365 | Les travaux d’exportation apportez votre propre base de données (BYOD) échouent après la mise à niveau vers Platform update 40 | Correction d’un problème où les exportations BYOD échouaient après l’application de Platform update 40 à l’environnement. |
| 547123 | Limiter le nombre de tâches interrogées dans la liste des tâches sur le tableau de bord | Le nombre de tâches affichées dans la liste des tâches est désormais limité à 15 pour résoudre un problème de performances causé par un nombre excessif de tâches essayant de se charger. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Vue transversale des congés pour les managers | [Vue transversale des congés pour les employés](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurer les paramètres de congé et d’absence](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |
| Empêcher les employés de modifier leurs coordonnées professionnelles | [Empêcher les employés de modifier leurs coordonnées professionnelles](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Restreindre la modification des informations personnelles](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Prochainement

| Fonctionnalité | Détails |
| --- | --- |
| Les compétences saisies par un responsable pour ses employés peuvent être approuvées automatiquement par un workflow | Prochainement. |

Pour obtenir la liste complète des fonctionnalités prévues et de leur lancement, voir [Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Mises à jour de la terminologie pour Microsoft Dataverse

Depuis novembre 2020, Common Data Service s’appelle désormais [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro). Voir l’[annonce officielle](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) sur le blog Power Apps pour en savoir plus. Avec ce changement de nom, certains termes de Dataverse ont été mis à jour. Par exemple, *entité* a été remplacé par *table* et *champ* par *colonne*. Pour plus d’informations, consultez [Mises à jour de la terminologie](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

Dans cette version, la terminologie relative à l’intégration de Dynamics 365 Human Resources avec Dataverse a été mise à jour tout au long de l’application pour refléter ces changements. Par exemple, le formulaire **Intégration de Common Data Service** s’appelle désormais **Intégration de Microsoft Dataverse**.

Pour en savoir plus sur l’intégration de Dynamics 365 Human Resources avec Microsoft Dataverse, voir [Configurer l’intégration de Microsoft Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service) et [Configurer les tables virtuelles Microsoft Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

## <a name="updates-to-service-deployment"></a>Mises à jour du déploiement de service

À partir de la version du 22 février 2021, nous ajustons notre déploiement de mise à jour de service régional. Les ajustements comprendront la rotation de l’ordre dans lequel les régions mondiales reçoivent les mises à jour pour le service Human Resources et des modifications du temps d’attente entre les étapes de mise à jour. Ces changements nous permettent de mieux nous aligner sur les pratiques de déploiement sécurisées (SDP) pour améliorer la stabilité, la qualité et la prise en charge du service.

Nous continuerons de suivre la cadence de déploiement de deux semaines. Cependant, les clients peuvent remarquer que les mises à jour sont généralement appliquées à leurs environnements de Human Resources à un autre jour du cycle de deux semaines que dans les versions précédentes.

Pour plus d’informations sur le processus de mise à jour du service, voir [Processus de mise à jour](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-setup-update-process).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
