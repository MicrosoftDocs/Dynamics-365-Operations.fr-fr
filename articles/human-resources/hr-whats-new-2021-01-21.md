---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (21 janvier 2021)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 21 janvier 2021.
author: marcelbf
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9f1f660b7993804901f5fc9d3b608c141882bff5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901087"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-21-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (21 janvier 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou sont annoncées dans Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2020](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.3866.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Platform update 10.0.16(40) | -- | [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.16 (février 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-16.md) |
| Demandes et approbations de flux de travail améliorées | [Améliorations de l’expérience de workflow de gestion de l’organisation et du personnel](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Option de configuration pour positionner la liste Éléments de travail qui me sont affectés](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Mises à jour de la conformité à la Loi sur les soins abordables (ACA) pour les formulaire 1095-C et 1095-B et génération d’états électroniques dans les avantages hérités | -- | -- | 
| Gestion des avantages prend désormais en charge les rapports de conformité ACA pour les entités juridiques basées aux États-Unis | -- | [Générer des rapports ACA dans Gestion des avantages](hr-benefits-management-aca-reports.md) |
| Gestion des avantages comporte désormais des niveaux de taux de prestations et des entités à deux niveaux de taux de prestations exposées  | -- | -- |

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cet article pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cet article.

| Numéro du problème | Problème |  Description |
| --- | --- | --- |
| 533079 | Erreur de navigation « Le formulaire a été appelé de manière incorrecte » lorsque nous essayons d’examiner les déductions. | Correction d’une erreur lors de la recherche des déductions d’avantages avec la vue **À partir du**. |
| 543641 | Code postal non renseigné sur la génération d’états électroniques.  | Correction d’un bug interne sur le code postal n’apparaissant pas dans les rapports électroniques ACA pour la gestion des avantages lorsque le code de couverture est de M à Q. |
| 542815 | L’écran de contact personnel dans le libre-service des employés permet aux employés de voir les contacts personnels des autres. | Correction d’une erreur où le formulaire **Modifier** pour les contacts personnels en libre-service des employés ne limite pas suffisamment sa requête pour garantir qu’un seul contact personnel est récupéré, ce qui permet à un utilisateur d’utiliser des raccourcis clavier pour afficher les contacts d’autres personnes. |
| 536157 | Impossible d’ouvrir la page **Intégration de Microsoft Dataverse** dans l’administration système en raison de l’appel IsVirtualEntityPackageInstalled(). | Un problème empêche la page **Intégration de Microsoft Dataverse** de se charger dans Human Resources. |
| 533079 | Erreur de navigation « Le formulaire a été appelé de manière incorrecte » lorsque nous essayons d’examiner les déductions. | Correction d’une erreur survenant dans le formulaire **Déductions** pour la gestion des avantages lors de la consultation du champ **À partir du**. |
| 537264 | Raccourci **Informations personnelles** manquant dans le dossier de candidature. | Les informations personnelles du candidat sont désormais disponibles dans le dossier de candidature. |
| 537267 | **Expérience professionnelle** ne s’affiche pas sur les dossiers de candidature internes. | Le raccourci **Expérience professionnelle** s’affiche désormais sur les dossiers de candidature internes. Auparavant, si le candidat était interne, le champ **Expérience professionnelle** était remplacé par **Historique des emplois**, qui est l’historique des emplois du candidat au sein de l’organisation. Les deux sont applicables et doivent s’afficher pour les candidats internes. |
| 537067 | Le champ **Autorisé à contacter l’employeur** ne s’affiche pas. | Le contrôle **Autorisé à contacter l’employeur** a été ajouté au volet **Modifier une expérience professionnelle** pour un dossier de candidature. |
| 525957 | Le champ **Statut de la candidature** ne met pas à jour les candidatures internes une fois le transfert terminé. | Lorsqu’un transfert est terminé (le bouton **Modifier le poste** ou **Continuer** est sélectionné sur la page **Transférer le travailleur vers une nouvelle affectation de poste**), le champ **Statut** sur le dossier du candidat doit être remplacé par **Embauché**. |
| 537051 | Les symboles monétaires de la roupie indienne et de la livre turque ne se synchronisent pas correctement avec Dataverse | Les symboles monétaires de la roupie indienne et de la livre turque se synchronisent désormais correctement avec Dataverse. |
| 534846 | Les tables de recrutement doivent être activées pour la gestion des données. | Les nouvelles tables créées pour les demandes de recrutement et les candidats sont désormais activées pour la gestion des données. Cela permet d’activer le suivi des modifications pour les tables, ce qui permet le suivi des modifications OData sur les tables virtuelles Dataverse. |
| 533474 | Correction de la référence manquante à Microsoft.SqlServer.XEvent.dll. | Des exceptions de chargement d’assembly pour Microsoft.SqlServer.XEvent.dll bloquaient la configuration des tables virtuelles Dataverse dans certains environnements. |
| 481122 | Espace de travail **Personnes** montrant les postes des personnes qui ont pris leur retraite. | Les postes des personnes ayant pris leur retraite étaient affichés comme des postes vacants dans l’espace de travail **Personnes**. Les postes des personnes ayant pris leur retraite ne s’affichent plus. | 
| 541978 | Ajoutez l’adresse e-mail principale à l’entité BaseWorker. | Cette modification a ajouté l’adresse e-mail principale du travailleur à HcmWorkerBaseEntity. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Application Human Resources dans Microsoft Teams | [Expérience de congé et d’absence des employés dans Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Application Human Resources de Teams](./hr-admin-teams-leave-app.md)<br>[Gérer les demandes de congés dans Teams](hr-teams-leave-app.md) |
| Intégration avec LinkedIn Talent Hub | [Intégration avec LinkedIn Talent Hub](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Intégration avec LinkedIn Talent Hub](./hr-admin-integration-linkedin.md) |
| Vue transversale des congés pour les managers | [Vue transversale des congés pour les employés](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurer les paramètres de congé et d’absence](./hr-leave-and-absence-parameters.md) |
|Fournir des informations supplémentaires sur le solde de congé| [Fournir des informations supplémentaires sur le solde de congé](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Gérer les congés des employés](./hr-leave-and-absence-manage-employee-leave.md) |
| Gestionnaires capables de soumettre des demandes de recrutement pour des postes | [Les gestionnaires peuvent soumettre une demande de recrutement pour un poste à pourvoir](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Ajouter une demande de recrutement](./hr-personnel-recruit.md#add-a-recruiting-request) |
| Profil de candidat amélioré dans la gestion du personnel | [Profil de candidat amélioré dans la gestion du personnel](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Ajouter ou modifier un profil de candidat](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| Permettre des intégrations simplifiées avec les prestataires de recrutement | [Permettre des intégrations simplifiées avec les prestataires de recrutement](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Recruter des candidats à un poste](./hr-personnel-recruit.md) |

## <a name="coming-soon"></a>Prochainement
| Fonctionnalité | Détails |
| --- | --- |
| Confirmation par e-mail pour les demandes de prestations | Cette fonction offre la possibilité d’envoyer un e-mail de confirmation aux employés lorsqu’ils quittent les expériences d’inscription aux avantages dans le libre-service des employés. Pour plus d’informations, voir [Configurer les paramètres de gestion des avantages par entreprise](hr-benefits-setup-parameters-per-company.md). |
| Les compétences saisies par un responsable pour ses employés peuvent être approuvées automatiquement par un workflow | Prochainement. |

Pour une liste complète des fonctionnalités planifiées et leurs lancements planifiés, voir [Vue d’ensemble de Dynamics 365 Human Resources 2020 2e vague de lancement](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Mises à jour de la terminologie pour Microsoft Dataverse

Depuis novembre 2020, Common Data Service s’appelle désormais [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Voir l’[annonce officielle](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) sur le blog Power Apps pour en savoir plus. Parallèlement à ce changement de nom, certains termes de Dataverse ont été mis à jour. Par exemple, *entité* a été remplacé par *table* et *champ* par *colonne*. Pour plus d’informations, consultez [Mises à jour de la terminologie](/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

Dans cette version, la terminologie relative à l’intégration de Dynamics 365 Human Resources avec Dataverse a été mise à jour tout au long de l’application pour refléter ces changements. Par exemple, le formulaire **Intégration de Common Data Service** s’appelle désormais **Intégration de Microsoft Dataverse**.

Pour en savoir plus sur l’intégration de Dynamics 365 Human Resources avec Microsoft Dataverse, voir [Configurer l’intégration de Microsoft Dataverse](./hr-admin-integration-common-data-service.md) et [Configurer les tables virtuelles Microsoft Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2020 vague de publication 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]