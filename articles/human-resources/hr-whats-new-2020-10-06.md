---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (6 octobre 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 6 octobre 2020.
author: jcart1106
ms.date: 10/06/2020
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
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8fe6d8a4ca42cd1f3c3b26a9c52f1a639170252c
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894604"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-6-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (6 octobre 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou seront bientôt disponibles dans Dynamics 365 Human Resources. Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2020](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.3636.

### <a name="new-features"></a>Nouvelles fonctionnalités

La fonctionnalité suivante est mise à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Informations supplémentaires sur les calendriers de congé | [Fournir des informations supplémentaires sur les vues calendrier de congé](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-leave-calendar-views) | [Afficher le calendrier des équipes et de la société](hr-employee-self-service-calendar.md) |

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

>[!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il peut y avoir des mises à jour de cette rubrique pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cette rubrique.

| Numéro du problème | Sortie | Description |
| --- | --- | --- |
| 448806 | **Type d’identification par défaut** s’exporte comme **RecID** dans les paramètres HCM | Cette modification de l’entité des paramètres Human Resources ajoute une colonne supplémentaire qui affiche le **Type d’identification par défaut**. |
| 492923 | Les enregistrements de tâches ne sont pas enregistrés dans Lifecycle Services (LCS) | Les enregistrements de tâches peuvent maintenant être enregistrés dans LCS. |
| 429950 | La rémunération fixe n’expire pas correctement lors du changement de poste | Lors du changement de poste d’un travailleur sur la page **Transférer le collaborateur**, la date de fin de rémunération était fixée un jour avant la fin du poste. La date de fin de rémunération est désormais la même que la date de fin du poste. |
| 467214 | **Analyse salariale** s’affiche uniquement si **Nom de conversion du taux de salaire** est défini sur **Annuel** | Les taux de salaire avec un nom autre que **Annuel** n’apparaissait pas dans l’analyse de la rémunération. Avec cette mise à jour, l’analyse de la rémunération utilise désormais toutes les conversions de taux de salaire. Lors de l’exécution des rapports par **Horaire** ou **Salaire**, toute conversion de taux de salaire qui utilise une période autre qu’horaire est incluse dans le filtre **Salaire**. Seuls les taux de salaire avec une période **Horaire** sont inclus dans le filtre **Horaire** . |
| 482464 | Lors de l’affichage des **Évaluations**, la vue **Détails** ne passe pas à la vue de grille après avoir appliqué un filtre | Après avoir appliqué un filtre, la grille des évaluations s’affiche comme prévu. |
| 483184 | Human Resources ne génère pas de cumul de congés lorsque vous sélectionnez **Base de niveau** comme **Date de début de contrat ajustée** dans l’enregistrement **Inscription aux congés** |La **Date de début de contrat ajustée** est renseignée et utilisée lors de la génération des cumuls de congés.  |
| 509731 | La demande de congé pour un future travailleur licencié pose un problème s’il demande un congé après la date de fin de contrat | Les demandes de congé peuvent maintenant être soumises pour les employés ayant une date de fin de contrat future tant que la demande est antérieure à la date de fin de contrat. |
| 510716 | L’analyse de la rémunération comprend à la fois les employés masculins et féminins pour **Salaire horaire moyen d’un homme** | Dans l’analyse de la rémunération, le **Salaire horaire moyen d’un homme** sur l’**Analyse démographique de la rémunération** incluait le salaire moyen des femmes. Maintenant, il ne comprend que les hommes. |
| 511348 | Le libre-service des avantages ne doit afficher que les plans d’avantages valables d’aujourd’hui à la fin de la période de l’avantage | Les plans d’avantages expirés étaient affichés aux employés sur la page **Inscription aux avantages**. Ce correctif supprime ces plans. |
| 512706 | Définissez les champs suivants en lecture seule :<ul><li>BenefitPlanEmployeeEntity</li><li>EnrollmentConfirmed</li><li>EnrollmentConfirmedBy</li><li>EnrollmentConfirmedDateTime | Les boutons **Ajouter** et **Supprimer** pour les détails de dimension n’étaient pas activés correctement une fois l’action terminée. Cette mise à jour de la page **Détail de l’action liée aux postes** rend les champs non modifiables une fois l’action terminée. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Application Human Resources dans Microsoft Teams | [Expérience de congé et d’absence des employés dans Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Application Human Resources de Teams](./hr-admin-teams-leave-app.md)<br>[Gérer les demandes de congés dans Teams](hr-teams-leave-app.md) |
| Demandes et approbations de flux de travail améliorées | [Améliorations de l’expérience de workflow de gestion de l’organisation et du personnel](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Option de configuration pour positionner la liste Éléments de travail qui me sont affectés](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Entités virtuelles dans Dataverse pour Human Resources | [Développer les données de base de Dynamics 365 Human Resources dans Dataverse](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Configurer les entités virtuelles Dataverse](hr-admin-integration-common-data-service-virtual-entities.md) |

## <a name="coming-soon"></a>Prochainement

Les nouvelles fonctionnalités suivantes sont prévues pour de prochaines versions :

- **Entités de liste de contrôle incluses dans Dataverse** : les entités de liste de contrôle pour les processus d’intégration, de départ, de transfert et d’entreprise seront bientôt disponibles dans Dataverse.

- **Codes de motif de gestion des avantages** : les codes de motif de gestion des avantages seront bientôt combinés aux codes de motif existants dans Human Resources. Si vous avez créé des codes raison dans la gestion des avantages de plus de 15 caractères, vous devez modifier le nom du code motif dans le formulaire **Codes motif** de la gestion des avantages sur 15 caractères ou moins. Une fois le nom mis à jour, le code motif apparaîtra sous le formulaire de code motif existant dans la gestion du personnel. Ce changement sera disponible à l’avenir et n’affectera pas les fonctionnalités existantes.

- **Liens personnalisés dans le libre-service pour responsables** : pour soutenir les responsables, nous étendons les capacités du libre-service pour responsables. Nous ajoutons la possibilité d’ajouter des liens personnalisés sur l’onglet **Mon équipe**. Cette fonctionnalité est similaire à la fonctionnalité de liens personnalisés dans l’onglet **Mes informations** du libre-service des employés. Pour plus d’informations, voir [Liens personnalisés dans le libre service pour responsables](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service).

Pour une liste complète des fonctionnalités planifiées et leurs lancements planifiés, voir [Vue d’ensemble de Dynamics 365 Human Resources 2019 2e vague de lancement](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>Ressources supplémentaires

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2020 vague de publication 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]