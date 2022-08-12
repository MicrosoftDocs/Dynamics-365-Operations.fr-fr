---
title: Nouveautés et modifications dans Dynamics 365 Human Resources, 5 avril 2021
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 5 avril 2021.
author: marcelbf
ms.date: 04/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9388b2f43762bedf07c89a7a565935d2043ee90c
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067999"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-5-2021"></a>Nouveautés et modifications dans Dynamics 365 Human Resources, 5 avril 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou sont annoncées dans Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 1re vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4074.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Empêcher les employés de modifier leurs coordonnées professionnelles | [Empêcher les employés de modifier leurs coordonnées professionnelles](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Restreindre la modification des informations personnelles](./hr-employee-self-service-restrict-editing.md)|

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cet article pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cet article.

| Numéro du problème | Problème |  Description |
| --- | --- | --- |
| 550852 | Le bouton **Approbation** ne se valide pas avec les champs obligatoires définis sur le formulaire **Révision**. | Lorsque vous définissez un champ du formulaire **Révision** comme obligatoire et publiez les modifications pour le rôle Responsable, le formulaire ne se valide pas comme prévu. |
| 559564 | Les actions historiques des collaborateurs pour la modification de la rémunération fixe génèrent une erreur pour les utilisateurs dont le contrat a pris fin. | L’action de collaborateur de la rémunération d’un collaborateur qui a quitté l’entreprise génère une erreur. Après le terme du contrat d’un employé, l’action de collaborateur de promotion avant la fin de contrat génère une erreur. |
| 560074 | Le menu déroulant des catégories d’emploi ne filtre pas le **Type de collaborateur** et affiche les catégories pour les employés et les sous-traitants. | Sur le formulaire **Employé**, le menu déroulant **Catégorie d’emploi** doit afficher les catégories d’employés ou de prestataires, en fonction du type de collaborateur de l’employé. |
| 567388 | Certaines informations relatives aux employés nouvellement créés ne sont pas synchronisées immédiatement avec la table **cdm_worker** dans Dataverse. | Lors de la création d’un nouvel enregistrement d’employé, le nouvel enregistrement doit se synchroniser avec la table **cdm_worker** dans Dataverse, mais toutes les propriétés ne sont pas incluses dans l’enregistrement Dataverse. |
| 563837 | Des fonctionnalités qui ne sont pas disponibles dans Human Resources s’affichent. | Plusieurs fonctionnalités qui ne s’appliquent pas à Human Resources s’affichent dans la Gestion des fonctionnalités. Ces fonctionnalités sont désormais supprimées de la liste des fonctionnalités disponibles à activer dans Human Resources. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |

## <a name="coming-soon"></a>Prochainement

| Fonctionnalité | Détails |
| --- | --- |
| Les compétences saisies par un responsable pour ses employés peuvent être approuvées automatiquement par un workflow | Prochainement. |
| Platform update 10.0.17 (41) | La mise à jour Platform update 10.0.17 devrait commencer à être déployée avec la prochaine version, le 19 avril 2021. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.17 (avril 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md). |

Pour obtenir la liste complète des fonctionnalités prévues et de leur lancement, voir [Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
