---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (28 janvier 2021)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources au 28 janvier 2021.
author: marcelbf
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4fbf3034805146c3900b46f5ccce76e63b0805a4
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893075"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-28-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (28 janvier 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou seront bientôt disponibles dans Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 1re vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.3906.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Intégrer les codes motif des avantages dans l’espace de travail **Gestion du personnel** | -- | [Paramétrer des codes motif](hr-benefits-setup-reason-codes.md) |

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cette rubrique pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cette rubrique.


| Numéro du problème | Sortie |  Description |
| --- | --- | --- |
| 539456 | Le calendrier affiche le type de congé dans le texte de survol lorsque le paramètre **Afficher uniquement l’absence sans détails** est activé. | Quand le paramètre **Afficher uniquement l’absence sans détails** est activé, la date de la demande s’affiche maintenant au survol. |
| 528907 | En accordant l’accès à une entité juridique sur le rôle d’employé, les responsables ne peuvent pas voir l’activité du solde des congés des employés dans la zone **Mon équipe** du libre-service des employés. |La définition de cette option permet désormais aux responsables de continuer à voir l’activité du solde des congés. |
| 526280 | Erreur d’autorisations sur HcmWorkerEntity, HcmEmployeeEntity et HcmContractorEntity. | Les utilisateurs dans un rôle d’administrateur non-système n’ont pas pu exporter les entités répertoriées en raison d’une erreur d’autorisations dans le champ NationalityCountryRegion. Les utilisateurs continueront d’avoir besoin des privilèges suivants pour exporter ces informations : HcmWorkerEntityMaintain, HcmWorkerEntityView, HcmEmployeeEntityMaintain, HcmEmployeeEntityMaintain, HcmEmployeeEntityView, HcmContractorEntityMaintain et HCMContractorEntityView. |
| 542147 | Les champs **Numéro de compte bancaire** et **Numéro d’acheminement** sont obligatoires lors de l’ajout d’un compte bancaire via le libre-service des employés. | Nous avons corrigé l’erreur où les employés devaient renseigner les champs **Numéro de compte bancaire** et **Numéro d’acheminement** lors de l’ajout des coordonnées bancaires. Ces champs ne sont plus obligatoires lors de l’enregistrement de nouvelles informations de compte bancaire. |
| 543641 | Le code postal n’est pas renseigné sur la génération d’états électroniques. | Correction d’un bug où le code postal ne s’affichait pas dans le rapport ACA pour les codes de couverture L à Q. |
| 545402 | Ajout d’une modification de routage pour le fichier UserBranding.js pour supprimer les erreurs 404. | L’utilisateur ne devrait plus voir les erreurs 404 dans la console. |

## <a name="in-preview"></a>En mode aperçu   

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Application Human Resources dans Microsoft Teams | [Expérience de congé et d’absence des employés dans Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Application Human Resources de Teams](./hr-admin-teams-leave-app.md)<br>[Gérer les demandes de congés dans Teams](hr-teams-leave-app.md) |
| Vue transversale des congés pour les managers | [Vue transversale des congés pour les employés](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurer les paramètres de congé et d’absence](./hr-leave-and-absence-parameters.md) |

## <a name="coming-soon"></a>Prochainement

| Fonctionnalité | Détails |
| --- | --- |
| Confirmation par e-mail pour les demandes de prestations | Cette fonction offre la possibilité d’envoyer un e-mail de confirmation aux employés lorsqu’ils quittent les expériences d’inscription aux avantages dans le libre-service des employés. Cette fonctionnalité sera disponible le 1er février. Pour plus d’informations, voir [Configurer les paramètres de gestion des avantages par entreprise](hr-benefits-setup-parameters-per-company.md). |
| Les compétences saisies par un responsable pour ses employés peuvent être approuvées automatiquement par un workflow | Prochainement. |

Pour obtenir la liste complète des fonctionnalités prévues et de leur lancement, voir [Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Mises à jour de la terminologie pour Microsoft Dataverse

Depuis novembre 2020, Common Data Service s’appelle désormais [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Voir l’[annonce officielle](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) sur le blog Power Apps pour en savoir plus. Parallèlement à ce changement de nom, certains termes de Dataverse ont été mis à jour. Par exemple, *entité* a été remplacé par *table* et *champ* par *colonne*. Pour plus d’informations, consultez [Mises à jour de la terminologie](/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

Dans cette version, la terminologie relative à l’intégration de Dynamics 365 Human Resources avec Dataverse a été mise à jour tout au long de l’application pour refléter ces changements. Par exemple, le formulaire **Intégration de Common Data Service** s’appelle désormais **Intégration de Microsoft Dataverse**.

Pour en savoir plus sur l’intégration de Dynamics 365 Human Resources avec Microsoft Dataverse, voir [Configurer l’intégration de Microsoft Dataverse](./hr-admin-integration-common-data-service.md) et [Configurer les tables virtuelles Microsoft Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]