---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources 26 septembre 2020
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 26 septembre 2020.
author: jcart1106
ms.date: 09/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8b0260c4d1bafe271a08336ceed7dc3742f1d590
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061382"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-26-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources 26 septembre 2020

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Cette rubrique décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou seront bientôt disponibles dans Dynamics 365 Human Resources. Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2020](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.3589-hf.3.

### <a name="new-features"></a>Nouvelles fonctionnalités

La fonctionnalité suivante est généralement disponible avec cette version :

- **La mise à jour de la plate-forme 10.0.13 est maintenant disponible** : Pour plus d’informations sur la mise à jour, consultez [Mises à jour de la plate-forme pour la version 10.0.13 des applications Finances et Opérations (octobre 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-13.md).

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il peut y avoir des mises à jour de cette rubrique pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cette rubrique.

| Numéro du problème | Sortie | Description |
| --- | --- | --- |
| 469495 | Mettre à jour la grille et la boîte de dialogue des dimensions financières par défaut | La grille et la boîte de dialogue des dimensions financières sont mises à jour dans Human Resources. |
| 474887 | L’élément de travail de demande de congé ouvre un lien incorrect dans une décision manuelle | Lorsqu’une configuration de workflow contient une décision manuelle, accéder à la demande de congé depuis **Éléments de travail qui me sont affectés** ouvre le mauvais lien, affichant soit un formulaire vierge, soit une demande de congé créée par l’utilisateur actuel au lieu de celle qui lui est affectée pour la décision manuelle. |
| 474962 | L’entité des paramètres de congé et d’absence a des champs avec des étiquettes ambiguës | Les étiquettes d’entité des paramètres de congé et d’absence sont mises à jour pour être plus claires. |
| 481401 | Le processus de régularisation se bloque lorsque la base de la date de régularisation est postérieure à la date de début de la régularisation et à la fin du mois | Le processus de régularisation est mis à jour pour ne pas avoir de retard lorsque la base de la date de régularisation est postérieure à la date de début de la régularisation et à la fin du mois. |
| 447167 | Les listes d’enregistrements arrivant à expiration incluent les travailleurs inactifs | L’onglet **Enregistrements arrivant à expiration** dans **Gestion du personnel** inclus les travailleurs inactifs. Désormais, il ne comprend que les travailleurs actifs. |
| 486840 | Une demande de congé incorrecte s’ouvre dans **Éléments de travail qui me sont affectés** | La sélection d’une demande de congé dans **Éléments de travail qui me sont affectés** n’ouvre plus la demande de congé la plus récente attribuée à l’utilisateur actuel. |
| 506868 | Champ **Titre** de Dataverse non défini pour l’entité **Poste** | Le champ **Titre** dans les entités **Emploi** et **Poste** est affiché comme non spécifié. Le champ **Titre** s’affiche maintenant. |
| 430359 | Impossible d’accéder aux tâches de la liste de contrôle de départ avec les rôles de responsable et d’employé attribués | Les travailleurs avec une date de fin de contrat à venir ne pouvaient pas accéder aux tâches de leur liste de contrôle s’ils n’avaient qu’un rôle d’employé ou de responsable. Désormais, les utilisateurs avec uniquement un rôle d’employé ou de responsable peuvent accéder aux tâches de départ avec une date de fin de contrat à venir. |
| 458102 | Le nouvel employé n’apparaît pas sur l’entité **Informations sur la paie des collaborateurs** lors de sa création | Les nouveaux employés sont inclus dans l’entité d’informations sur la paie des collaborateur sans avoir à ouvrir les informations sur la paie de l’employé avant d’exporter l’entité. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Application Human Resources dans Microsoft Teams | [Expérience de congé et d’absence des employés dans Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Application Human Resources de Teams](./hr-admin-teams-leave-app.md)<br>[Gérer les demandes de congés dans Teams](hr-teams-leave-app.md) |
| Demandes et approbations de flux de travail améliorées | [Améliorations de l’expérience de workflow de gestion de l’organisation et du personnel](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Option de configuration pour positionner la liste Éléments de travail qui me sont affectés](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |

## <a name="coming-soon"></a>Prochainement

La nouvelle fonctionnalité suivante est prévue pour une prochaine version :

- [Liens personnalisés dans le libre-service des responsables](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service)

Pour une liste complète des fonctionnalités planifiées et leurs lancements planifiés, voir [Vue d’ensemble de Dynamics 365 Human Resources 2019 2e vague de lancement](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>Ressources supplémentaires

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)
[Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2020](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)
[Processus de mise à jour](hr-admin-setup-update-process.md)
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]