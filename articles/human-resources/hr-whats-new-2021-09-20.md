---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources 20 septembre 2021
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 20 septembre 2021.
author: marcelbf
ms.date: 09/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 59f1b0e3c35d1dce045b4a3932d99fab398e5516
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069754"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-20-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources 20 septembre 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou sont annoncées dans Microsoft Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4464.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
|---|---|---|
| Activer l’intégration simplifiée de la paie (API d’intégration de la paie) | [Activer l’intégration simplifiée avec des prestataires de paie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md) |
| Permettre aux employés d’être marqués comme prêts à être payés | [Permettre aux employés d’être marqués comme prêts à être payés](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Prêt à payer](/dynamics365/human-resources/hr-compensation-payroll) |

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cet article pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cet article.

| Numéro du problème | Problème | Description |
|---|---|---|
| 619774 | La modification de la description de l’adresse ne se synchronise pas avec Dataverse en temps réel. | Lors de la modification de la description d’une adresse de travailleur, la description mise à jour n’est pas synchronisée en temps réel pour Dataverse. L’abonnement à la table **Emplacement de la logistique** a été mise à jour pour l’envoi d’une mise à jour. |
| 614603| Erreur sur la page **Collaborateur** lorsque le paramètre **Actions de personnel aux collaborateurs** n’est pas sélectionné. | Lors de l’embauche d’un nouveau collaborateur ou de la navigation vers la page **Collaborateur**, l’erreur suivante s’affiche : le "Champ **Type d’action personnelle** doit être rempli", même si les **Actions personnelles** sont désactivées. |
| 615367 | **Congé autorisé** L’onglet affiche un avertissement et s’affiche de manière incorrecte. | Si l’unité de congé est paramétrée sur **Jours** avant d’activer la fonctionnalité **Configurer les unités de congé par type de congé**, l’onglet **Congé autorisé** affiche un avertissement non valide et des colonnes incorrectes. |


## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation et la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
|---|---|---|
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |
| Champs personnalisés dans le traitement de l’admissibilité |[Champs personnalisés pris en charge dans le traitement de l’admissibilité](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Utilisation de champs personnalisés dans le traitement de l’admissibilité](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |
| Relevé des avantages |[Relevé des avantages](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) | [Relevé des avantages](hr-benefits-statement.md) |

### <a name="benefits-statement-known-issues"></a>Problèmes connus liés aux relevés des avantages

| Problème | Description |
|---|---|
| La page **Paramètres du rapport** dans **Espace collaborateur** pour le relevé des avantages est incorrecte. | Lors de la navigation vers le **Relevé des avantages** dans **Espace collaborateur**, la page **Paramètres du rapport** affiche les raccourcis **Enregistrements à inclure** et **Exécuter en arrière-plan**.  Ceux-ci doivent être supprimés. |
| Les périodes fermées et futures sont affichées dans la page **Paramètre de rapports** du relevé des avantages. | Lors de la navigation vers la page de destination **Rapport concernant les relevés d’avantages**, l’utilisateur peut sélectionner des périodes de régimes d’avantages sociaux qui sont clôturées ou à date future, ce qui entraîne une page blanche. Seule la période actuelle du régime d’avantages sociaux doit s’afficher dans la liste. |
|Erreur lors de l’envoi du rapport par e-mail à l’aide de la destination du rapport GER. | Le relevé d’avantages peut être configuré pour utiliser les paramètres de courrier électronique dans la page **Destinations du rapport GER**. Lors de la configuration et de l’impression du rapport, l’utilisateur recevra une erreur de formatage et le relevé de prestations ne sera pas envoyé.|


## <a name="coming-soon"></a>Bientôt disponible

Pour une liste complète des fonctionnalités planifiées et de leurs lancements planifiés, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Fonctionnalité | Détails |
|---|---|
| Platform update 10.0.21 (45) | Le déploiement de la mise à jour de la plateforme 10.0.21 devrait commencer avec la version du service le 4 octobre 2021. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.21 (octobre 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |
|Vue des subordonnés étendus de journaux des performances | Cette fonctionnalité sera activée par défaut lors du prochain déploiement. |


## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2021 vague de publication 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

