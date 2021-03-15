---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources 2 décembre 2020
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 2 décembre 2020.
author: marcelbf
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 36d82efa182bff12442d51908d634cbddbd13fa9
ms.sourcegitcommit: fc852ae4939089a294d00fdf9cad8d6372ffb012
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2021
ms.locfileid: "5080036"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-december-2-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources 2 décembre 2020

Cette rubrique décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou seront bientôt disponibles dans Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d'informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2020](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.3788.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Gestionnaires capables de soumettre des demandes de recrutement pour des postes | [Les gestionnaires peuvent soumettre une demande de recrutement pour un poste à pourvoir](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Ajouter une demande de recrutement](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-a-recruiting-request) |
| Profil de candidat amélioré dans la gestion du personnel | [Profil de candidat amélioré dans la gestion du personnel](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Ajouter ou modifier un profil de candidat](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-or-edit-a-candidate-profile) |
| Permettre des intégrations simplifiées avec les prestataires de recrutement | [Permettre des intégrations simplifiées avec les prestataires de recrutement](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Recruter des candidats à un poste](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit) |
| Liens personnalisés dans le libre-service des responsables | [Liens personnalisés dans le libre-service des responsables](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Liens personnalisés dans le libre-service des responsables](https://aka.ms/MSSCustomLinks) |


### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cette rubrique pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cette rubrique.

| Numéro du problème | Sortie | Description |
| --- | --- | --- |
| 514087 | BenefitEligibilityProcessResult doit inclure la date-heure qui a été utilisée dans le traitement. | Le résultat du traitement BenefitEligibity inclut désormais l'horodatage du dernier traitement, qui manquait auparavant. |
| 526903 | L'inscription aux prestations échoue pour les régimes avec personnes à charge lorsque **Désignés à sélection automatique** est activé dans **Paramètres partagés des ressources humaines**. | Correction du problème où l'inscription aux prestations échouait pour les personnes à charge lorsque **Désignés à sélection automatique** l'option a été activée pour les personnes désignées par défaut. |
| 521922 | Le paramètre **Montrer l'absence sans détail** affiche les détails des demandes de congé dans le calendrier des absences de l'équipe. | Le type de congé, la couleur du type de congé et les détails du jour étaient affichés dans le calendrier des absences de l'équipe lorsque **Montrer l'absence sans détail** était réglé sur **Oui** dans **Paramètres de congé et d'absence**. Ce problème a été résolu et maintenant le type de congé ne s'affiche pas et la couleur du type de congé par défaut (bleu foncé) est utilisée pour tous les types de congé du calendrier des absences de l'équipe. |
| 527316 | Les changements de titre pour les notifications d'emploi, de poste et de collaborateur ne se synchronisent pas. | Une relation de titre a été précédemment ajoutée aux entités Emploi, Poste et Collaborateur. La synchronisation de cette relation fonctionne pour la synchronisation de Human Resources avec Dataverse, mais ne fonctionnait pas pour les notifications de Dataverse. Cela a été résolu. |
| 512275 | Supprimer les options de couleur de **Paramètres de congé et d'absence**. | Maintenant que les couleurs sont définies sur le type de congé, les options de couleurs ne sont plus nécessaires dans **Paramètres de congé et d'absence**, ils ont donc été supprimés. |
| 437112 | Texte du message d'erreur trompeur lors de l'affectation du poste d'un employé. | Mise à jour du message d'erreur lors de l'embauche d'un travailleur et de la tentative d'affecter le travailleur à un poste qui n'est pas actif. Message mis à jour **Le poste spécifié n'est pas actif à la date de début de l'emploi. Vérifier la durée de ce poste.** |
| 527816 | Problèmes de performances avec la page **Congé**. | Les performances ont été améliorées sur la page **Congé**. |
| 523158 | BenefitPeriodMigrationUpgrade et BenefitPlanMigrationUpgrade ne s'exécutent pas. | Correction de problèmes avec les emplois de migration de avantages liés à **Période** et **Plan** ne s'exécute pas correctement. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Application Human Resources dans Microsoft Teams | [Expérience de congé et d’absence des employés dans Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Application Human Resources de Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Gérer les demandes de congés dans Teams](hr-teams-leave-app.md) |
| Demandes et approbations de flux de travail améliorées | [Améliorations de l'expérience de workflow de gestion de l'organisation et du personnel](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Option de configuration pour positionner la liste Éléments de travail qui me sont affectés](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Intégration avec LinkedIn Talent Hub | [Intégration avec LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Intégration avec LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-linkedin) |
|Vue transversale des congés pour les managers | [Vue transversale des congés pour les employés](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurer les paramètres de congé et d’absence](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |
|Fournir des informations supplémentaires sur le solde de congé| [Fournir des informations supplémentaires sur le solde de congé](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Gérer les congés des employés](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-manage-employee-leave) |
| Gestionnaires capables de soumettre des demandes de recrutement pour des postes | [Les gestionnaires peuvent soumettre une demande de recrutement pour un poste à pourvoir](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Ajouter une demande de recrutement](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-a-recruiting-request) |
| Profil de candidat amélioré dans la gestion du personnel | [Profil de candidat amélioré dans la gestion du personnel](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Ajouter ou modifier un profil de candidat](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-or-edit-a-candidate-profile) |
| Permettre des intégrations simplifiées avec les prestataires de recrutement | [Permettre des intégrations simplifiées avec les prestataires de recrutement](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Recruter des candidats à un poste](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit) |

## <a name="coming-soon"></a>Prochainement

Pour une liste complète des fonctionnalités planifiées et leurs lancements planifiés, voir [Vue d'ensemble de Dynamics 365 Human Resources 2020 2e vague de lancement](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2020 vague de publication 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]