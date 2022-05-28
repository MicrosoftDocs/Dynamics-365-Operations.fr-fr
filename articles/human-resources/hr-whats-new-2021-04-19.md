---
title: Nouveautés et modifications dans Dynamics 365 Human Resources, 19 avril 2021
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 19 avril 2021.
author: marcelbf
ms.date: 04/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6734069b1448999c62a8c538f97d786fc10995e5
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8685740"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-19-2021"></a>Nouveautés et modifications dans Dynamics 365 Human Resources, 19 avril 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou seront bientôt disponibles dans Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 1re vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4113.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Platform update 10.0.17 (41) | -- | [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.17 (avril 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md) |
| Prise en charge des champs personnalisés dans les formulaires Gestion des avantages | [Prise en charge des champs personnalisés dans la gestion des avantages](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management)| [Vue d’ensemble de la gestion des avantages](hr-benefits-management-overview.md)|

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cette rubrique pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cette rubrique.

| Numéro du problème | Sortie |  Description |
| --- | --- | --- |
| 552164 | La **Vue enregistrée** sur **Libre-service des employés > Cours en cours** ne fonctionne pas pour les cours contenant un agenda | Si une vue enregistrée est utilisée sur des cours en cours (ESS) et que l'un d'entre eux est associé à un agenda, la vue n'affichera plus plusieurs lignes pour ce cours. |
| 560614 | Les champs **Avantages > Options d’événement de la vie** affichent les écarts dans la documentation de l'info-bulle et le comportement du code. | Info-bulles des mises à jour dans **Options d'événement de la vie** pour montrer un comportement correct. |
| 560616 | Les champs **Avantages sociaux > Options d'événement de la vie** sont modifiables dans le régime d'avantages sociaux des travailleurs, mais les modifications ne sont pas affectées. | Mise à jour du comportement des commutateurs d'option d'événement de la vie pour activer ou désactiver, en fonction des options dépendantes, selon la documentation de l'info-bulle. |
| 565054 | Impossible d'afficher le contenu de la liste **Collaborateurs sans emploi** quand l'**Accès avancé** est activé. | Cette version résout le problème suivant : quand l'option **Accès avancé** est activée, seuls les administrateurs système peuvent afficher le contenu de la liste **Collaborateurs sans emploi**. Comme ce correctif est un changement de sécurité, vous devrez l'accepter dans la gestion des fonctionnalités. Une fois la fonctionnalité activée, les postes qui ont accès au formulaire verront le contenu, même si l'accès avancé est activé. Pour plus d'informations, voir [Collaborateurs sans emploi](hr-personnel-workers-without-employment.md). |
| 570586 | La validation de la demande de congé échoue lorsque l'emploi se termine avant la dernière transaction pour ce collaborateur dans tous les plans de congé. | À la fin d'un emploi, la validation de la demande de congé n'échoue pas en fonction des transactions de congé des employés.|
| 570783 | L'activation et la désactivation des congés intersociétés dans les paramètres partagés de Human Resources modifient ce que les collaborateurs employés dans une seule entreprise voient dans les demandes de congé. | Les collaborateurs employés dans une seule entreprise ne voient aucun changement dans la demande de congé si le paramètre est activé ou désactivé. |
| 572343 | Le code motif requis ne s'affiche pas lorsque la fonction d'affichage des congés intersociétés est activée. | Lorsque la fonction d'affichage des congés intersociétés est activée, le code motif s'affiche désormais comme prévu. |
| 573676 | Impossible d'ajouter une **Période** à **Gestion des avantages sociaux > Liens > Régimes d’avantages sociaux**. | Correction de bugs où l'option **Période** ne pouvait pas être ajoutée ou mise à jour sur le formulaire **Régime d’avantages sociaux**. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |
| Améliorations de l'expérience du flux de travail sur les congés et les absences | [Améliorations de l'expérience du flux de travail sur les congés et les absences](https://go.microsoft.com/fwlink/?linkid=2147528) | [Demander un congé](hr-employee-self-service-request-time-off.md)|
| Activer l'intégration simplifiée de la paie (API d'intégration de la paie) | [Activer l'intégration simplifiée avec des prestataires de paie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)|

## <a name="coming-soon"></a>Prochainement

| Fonctionnalité | Détails |
| --- | --- |
| Les compétences saisies par un responsable pour ses employés peuvent être approuvées automatiquement par un workflow | Prochainement. |
| Platform update 10.0.18 (42) | La mise à jour de la plateforme 10.0.18 devrait commencer à être déployée avec la version du service le 17 mai 2021. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.18 (mai 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18). |
| Prise en charge des champs personnalisés dans les règles d’admissibilité de gestion des avantages  | [Prise en charge des champs personnalisés pour le traitement de l’admissibilité](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

Pour obtenir la liste complète des fonctionnalités prévues et de leur lancement, voir [Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
