---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources, 3 mai 2021
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 3 mai 2021.
author: marcelbf
ms.date: 05/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-05-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 01ebd15e09e181a7ea0ec5bf70c8df731d2169c0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902858"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-3-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources, 3 mai 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou sont annoncées dans Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 1re vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4140.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Ajoutez une barre d’informations lorsque des événements de la vie sont créés. | - | Lorsque vous créez un événement personnel, la barre d’informations affiche un message indiquant le type d’événement personnel créé.

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cet article pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cet article.

| Numéro du problème | Problème |  Description |
| --- | --- | --- |
| 559312 |  Le niveau n’est pas affiché lors de la création d’un plan de rémunération fixe pour un employé. |  En cas de non-concordance de fuseau horaire entre le fuseau horaire de l’utilisateur et le fuseau horaire de l’entreprise, le niveau de rémunération du travail ne pouvait pas être lu. La requête a été mise à jour pour être extraite en fonction de l’heure UTC. |
| 573676  | Impossible d’ajouter une nouvelle période dans l’écran **Plan d’avantages**. | Mise à jour du formulaire afin que le bouton **Nouveau** soit activé sous le raccourci **Période** dans l’onglet **Plans d’avantages**. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |
| Améliorations de l’expérience du flux de travail sur les congés et les absences | [Améliorations de l’expérience du flux de travail sur les congés et les absences](https://go.microsoft.com/fwlink/?linkid=2147528) | [Demander un congé](hr-employee-self-service-request-time-off.md)|
| Activer l’intégration simplifiée de la paie (API d’intégration de la paie) | [Activer l’intégration simplifiée avec des prestataires de paie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)|
| Audit des transactions de régularisation de congés | - | [Audit des transactions de régularisation de congés](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>Bientôt disponible

| Fonctionnalité | Détails |
| --- | --- |
| Platform update 10.0.18 (42) | La mise à jour de la plateforme 10.0.18 devrait commencer à être déployée avec la version du service le 17 mai 2021. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.18 (mai 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18). |
| Prise en charge des champs personnalisés dans les règles d’admissibilité de gestion des avantages  | [Prise en charge des champs personnalisés pour le traitement de l’admissibilité](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

Pour obtenir la liste complète des fonctionnalités prévues et de leur lancement, voir [Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
