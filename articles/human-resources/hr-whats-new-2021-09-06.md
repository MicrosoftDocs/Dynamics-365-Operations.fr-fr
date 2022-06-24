---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources 6 septembre 2021
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 6 septembre 2021.
author: marcelbf
ms.date: 09/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 776498b32f8323b1a06f39b518cdc1ae534f9bcc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872150"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-6-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources 6 septembre 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou sont annoncées dans Microsoft Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4443.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
|---|---|---|
| Activer un gestionnaire des absences pour gérer les congés | [Activer un gestionnaire des absences pour gérer les congés](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | Dans cette version, nous mettons à jour la vue de l’espace de travail du gestionnaire des absences. Pour plus d’informations, voir [Configurer le rôle de gestionnaire des absences](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Configurer l’exigence de pièce jointe par type de congé | [Configurer l’exigence de pièce jointe par type de congé](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) | [Configurer les types de congé et d’absence](https://go.microsoft.com/fwlink/?linkid=2168108) |
| Configurer les unités de congé par type de congé | [Configurer les unités de congé par type de congé](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) | [Configurer les types de congé et d’absence](https://go.microsoft.com/fwlink/?linkid=2168215) |

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cet article pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cet article.

| Numéro du problème | Problème | Description |
|---|---|---|
| 610128 | Erreur lors de la publication des données lors de l’utilisation de l’entité HcmDiscussionOverallCommentEntity | Lorsque les données sont publiées à partir d’un classeur Excel vers l’entité HcmDiscussionOverralCommentEntity, l’erreur suivante se produit : « Impossible de localiser l’enregistrement de source de données de type HcmTopicOverrall ». |
| 589073 | L’état EEO-1 compte les valeurs « Non spécifiques » et les valeurs vides pour le champ **Genre** comme valeur « Féminin ». | Si **Masculin** n’est pas spécifié pour le champ **Genre**, l’état EEO-1 génère une valeur par défaut de type **Féminin**. |
| 589617 | Les soldes de type Solde de congés, Disponible à l’achat, Disponible à la vente n’apparaissent pas lorsque les rôles d’utilisateur sont limités à une entité juridique spécifique. | Si l’utilisateur (rôle d’employé) est limité à une entité juridique spécifique, les soldes n’apparaissent pas correctement sur la fiche **Soldes de congés**, et dans les champs **Disponible à l’achat** et **Disponible à la vente**. |
| 604310 | L’onglet Gestionnaire d’absences doit être masqué lorsque l’utilisateur n’a pas de hiérarchie d’absences affectée. | Pour une personne morale donnée, l’onglet **Gestionnaire des absences** doit être masqué dans le portail libre-service à moins que le paramètre inter-sociétés ne soit activé et qu’au moins une hiérarchie d’absence soit associée à l’utilisateur. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation et la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
|---|---|---|
| Activer l’intégration simplifiée de la paie (API d’intégration de la paie) | [Activer l’intégration simplifiée avec des prestataires de paie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md) |
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |
| Permettre aux employés d’être marqués comme prêts à être payés | [Permettre aux employés d’être marqués comme prêts à être payés](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Prêt à payer](/dynamics365/human-resources/hr-compensation-payroll) |
| Champs personnalisés dans le traitement de l’admissibilité |[Champs personnalisés pris en charge dans le traitement de l’admissibilité](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Utilisation de champs personnalisés dans le traitement de l’admissibilité](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |

## <a name="coming-soon"></a>Bientôt disponible

Pour une liste complète des fonctionnalités planifiées et de leurs lancements planifiés, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Fonctionnalité | Détails |
|---|---|
| Platform update 10.0.21 (45) | Le déploiement de la mise à jour de la plateforme 10.0.21 devrait commencer avec la version du service le 4 octobre 2021. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.21 (octobre 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |
| Relevé des avantages | Relevé des avantages sociaux pour afficher les choix d’avantages sociaux actuels d’un employé. Pour plus d’informations, voir [Relevé des avantages](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) dans le document Vague de lancement. |

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2021 vague de publication 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
