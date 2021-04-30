---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources 22 octobre 2020
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 22 octobre 2020.
author: jcart1106
ms.date: 10/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c963914e347027552c7a1b2108caebac3f6702c5
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892655"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-22-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources 22 octobre 2020

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou seront bientôt disponibles dans Dynamics 365 Human Resources. Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2020](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.3680.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Platform update 10.0.14(38) | -- | [Mises à jour de la plate-forme pour la version 10.0.14 des applications Finance and Operations (novembre 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-14.md) |
| Améliorations de l’expérience des workflows de gestion de l’organisation et du personnel | [Améliorations de l’expérience de workflow de gestion de l’organisation et du personnel](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Option de configuration pour positionner la liste des éléments de travail qui me sont affectés](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |


### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cette rubrique pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cette rubrique.

| Numéro du problème| Sortie  | Description|
| --- | --- | --- |
| 437922 | L’importation d’heures FMLA à l’aide de l’entité DMF entraîne une erreur de lecture seule. | L’utilisation de l’entité Heures FMLA pour importer les heures associées à un cas FMLA a échoué. Nous avons ajouté une logique pour nous assurer que les heures importées ne dépassent pas les heures restantes pour le cas. |
| 512019 | Montant de **Dernier report** incorrect. | Sur la page **Congés**, la modification de la **Date de référence** au premier jour de la prochaine période fiscale a affiché un montant de **Dernier report** incorrect pour le type **Congé annuel**. Il affiche maintenant le montant correct. |
| 458639 | L’entité **Contacts collaborateurs** ne prend pas en charge le mode de suivi des modifications. | Nous avons mis à jour l’entité **Contacts collaborateurs** afin que vous puissiez l’utiliser pour apporter vos scénarios BYOD.|
| 505347 | Les responsables de la formation pouvaient soumettre une demande de congé pour un employé lorsque la fonction de collaborateur simplifié était activée. | Les rôles autres qu’assistant RH et responsable RH ne sont pas autorisés à soumettre des demandes de congés pour les employés. |
| 513490 | Journalisation de la gestion des avantages : ajoutez la journalisation pour les plans sans options de couverture. | Nous avons activé les résultats de journalisation pour **Plan sans options de couverture**. Ils s’affichent maintenant dans la table **Résultats du processus** et sont triés correctement pour s’afficher en haut. |
| 517021 | Impossible de sélectionner plusieurs plans avec le même code **Type de plan** si **Type de plan** a une inscription par type. | Nous avons modifié les restrictions relatives à la sélection de plans où une seule inscription est autorisée. Les restrictions sont maintenant au niveau du **Code de type de plan** au lieu du **Type de plan**. Ce changement autorise les plans comme HSA et FSA, qui sont tous les deux du même type, mais vous pouvez leur donner un **Code de type de plan** distinct. De cette façon, vous pouvez sélectionner les deux pour la même période d’inscription. |
| 444791 | Impossible d’afficher la rémunération dans le libre-service des employés lorsque **Accès restreint** est activé dans le plan de rémunération. | Dans la carte **Rémunération** du libre-service des employés, le montant actuel de la rémunération et le pourcentage d’augmentation affichaient "0" si l’employé était inscrit à un plan avec **Accès restreint** activé et affecté à des rôles spécifiques. Nous avons résolu ce problème afin que l’employé et le responsable puissent toujours voir les détails de la rémunération pour eux-mêmes et leurs subordonnés directs. |
| 457542 | La mise à jour des détails du cours après la fin du cours ne met pas à jour également les mêmes informations pour l’employé qui a suivi le cours. | Les informations pour les employés sont désormais correctement mises à jour lorsque vous modifiez les détails d’un cours après la fermeture et la réouverture d’un cours. |
| 515342 | Impossible d’insérer des données via **CDSLeaveRequestDetailEntity**. L’entreprise est introuvable ou n’existe pas. | Vous pouvez désormais utiliser **CDSLeaveRequestDetailEntity** pour insérer des données. |
| 514743 | Erreur dans le formulaire **Paramètre de messagerie** lors de l’utilisation de Microsoft Exchange. | Le message "Impossible de charger les fichiers ou l’assembly..." s’affiche dans la page **Paramètres de messagerie** lorsque le fournisseur de messagerie a été défini sur **Exchange**. Ce correctif permet également le chargement et l’enregistrement de la page **Paramètres de messagerie** comme prévu. |


## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Application Human Resources dans Microsoft Teams | [Expérience de congé et d’absence des employés dans Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Application Human Resources de Teams](./hr-admin-teams-leave-app.md)<br>[Gérer les demandes de congés dans Teams](hr-teams-leave-app.md) |
| Demandes et approbations de flux de travail améliorées | [Améliorations de l’expérience de workflow de gestion de l’organisation et du personnel](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Option de configuration pour positionner la liste Éléments de travail qui me sont affectés](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Entités virtuelles dans Dataverse pour Human Resources | [Développer les données de base de Dynamics 365 Human Resources dans Dataverse](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Configurer les entités virtuelles Dataverse](hr-admin-integration-common-data-service-virtual-entities.md) |
| Intégration avec LinkedIn Talent Hub | [Intégration avec LinkedIn Talent Hub](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Intégration avec LinkedIn Talent Hub](./hr-admin-integration-linkedin.md) |
| Liens personnalisés dans le libre-service des responsables | [Liens personnalisés dans le libre-service des responsables](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Liens personnalisés dans le libre-service des responsables](./hr-employee-manager-self-service-custom-links.md) |

## <a name="coming-soon"></a>Prochainement

Pour une liste complète des fonctionnalités planifiées et leurs lancements planifiés, voir [Vue d’ensemble de Dynamics 365 Human Resources 2020 2e vague de lancement](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2020 vague de publication 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]