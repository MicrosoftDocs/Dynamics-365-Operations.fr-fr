---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources, 20 mai 2021
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 20 mai 2021.
author: marcelbf
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-05-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 36d490832edcef025cb24a06288eb021eb794bd9
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068482"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-20-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources, 20 mai 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou sont annoncées dans Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 1re vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4189.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Platform update 10.0.18 (42) | -- | [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.18 (mai 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18) |
| L’application Human resources pour Microsoft Teams prend désormais en charge les définitions de la demi-journée et la fonction de fractionnement de la journée | -- | [Gérer les demandes de congés dans Teams](/dynamics365/human-resources/hr-teams-leave-app#create-a-new-request) |

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cet article pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cet article.

| Numéro du problème | Problème |  Description |
| --- | --- | --- |
| 583776 | Les inscriptions en masse des employés à des plans de congé entraînent une erreur d’enregistrement en double | Ce bogue a été corrigé avec la dernière version et les inscriptions en masse au plan de congé devraient être traitées correctement. |
| 582263 | Impossible d’exécuter le traitement des événements de vie pour tous les collaborateurs en même temps | Lorsque le champ **Collaborateur** est laissé vide pour le traitement des événements de vie, tous les collaborateurs seront traités. |
| 558383 | Le bénéficiaire principal n’est pas marqué comme 100 % si la personne désignée par défaut n’est pas sélectionnée | Ce bogue a été corrigé pour que l’utilisateur sélectionne simplement le bouton bascule du bénéficiaire principal.|
| 509404 | L’analyse des effectifs des services ne prend pas en compte le transfert des employés entre les services |L’analyse a été mise à jour pour inclure les transferts des employés entre les services|
| 579420 | La fonctionnalité Figeage des colonnes dans les grilles n’est pas encore disponible | La fonctionnalité **Figeage des colonnes dans les grilles**, qui n’est pas disponible dans Human Resources, a été répertoriée comme disponible dans Gestion des fonctionnalités. La fonctionnalité a été supprimée de la liste des fonctionnalités à activer. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Prise en charge des champs personnalisés dans les règles d’admissibilité de gestion des avantages | [Prise en charge des champs personnalisés pour le traitement de l’admissibilité](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Configuration des règles d’éligibilité](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |
| Améliorations de l’expérience du flux de travail sur les congés et les absences | [Améliorations de l’expérience du flux de travail sur les congés et les absences](https://go.microsoft.com/fwlink/?linkid=2147528) | [Demander un congé](hr-employee-self-service-request-time-off.md)|
| Activer l’intégration simplifiée de la paie (API d’intégration de la paie) | [Activer l’intégration simplifiée avec des prestataires de paie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)|
| Audit des transactions de régularisation de congés | - | [Audit des transactions de régularisation de congés](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>Bientôt disponible

| Fonctionnalité | Détails |
| --- | --- |
|  Activer un gestionnaire des absences pour gérer les congés | [Activer un gestionnaire des absences pour gérer les congés](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |

Pour obtenir la liste complète des fonctionnalités prévues et de leur lancement, voir [Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

