---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources 5 octobre 2021
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 5 octobre 2021.
author: marcelbf
ms.date: 10/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ba24afd16a471abb36a6f7bc9a8610acec374190
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067969"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-5-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources 5 octobre 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou sont annoncées dans Microsoft Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4485.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
|---|---|---|
| Platform update 10.0.21 (45) | -- | [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.21 (octobre 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21) |


### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cet article pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cet article.

| Numéro du problème | Problème | Description |
|---|---|---|
| 598896 | Le montant de l’employé ne s’affiche qu’une fois que l’employé a terminé l’inscription | Sur la page **Libre-service pour les employés**, le montant de l’employé pour l’avantage n’était pas affiché. Le montant de l’employé s’affiche désormais sur la page **Libre-service des avantages**.  |
| 613440 | Impossible d’exporter les données de **Gestion de données** | Lors de l’exportation des données d’un projet dans **Gestion de données**, l’exportation échoue de manière inattendue. |
| 618327 | Les périodes fermées et futures sont affichées dans la page **Paramètres de rapports** du relevé des avantages. | Lors de la navigation vers le **Relevé des avantages** dans **Espace collaborateur**, la page **Paramètres du rapport** affiche les raccourcis **Enregistrements à inclure** et **Exécuter en arrière-plan**. Ces sections ont été supprimées.|
| 618326 | Une page **Paramètres du rapport** inappropriée s’affiche dans **Espace collaborateur** pour le relevé des avantages.| Lors de la navigation vers la page de destination **Rapport concernant les relevés d’avantages**, l’utilisateur pouvait sélectionner des périodes de régimes d’avantages sociaux qui sont clôturées ou à date future, ce qui entraîne une page blanche. Seule la période actuelle du régime d’avantages sociaux doit s’afficher dans la liste. |

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
|Erreur lors de l’envoi du rapport par e-mail à l’aide de la **destination du rapport GER** | Le relevé d’avantages peut être configuré pour utiliser les paramètres de courrier électronique dans la page **Destinations du rapport GER**. Lors de la configuration et de l’impression du rapport, l’utilisateur recevra une erreur de formatage et le relevé de prestations ne sera pas envoyé.|

## <a name="feature-management-changes"></a>Changements de la gestion des fonctionnalités

| Fonctionnalité | Description |
|---|---|
|Vue des états étendus de journaux des performances | Cette fonctionnalité sera activée par défaut dans cette version. |

## <a name="coming-soon"></a>Bientôt disponible

Pour une liste complète des fonctionnalités planifiées et de leurs lancements planifiés, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Fonctionnalité | Détails |
|---|---|
| Platform update 10.0.22 (46) | Le déploiement de la mise à jour de la plateforme 10.0.22 devrait commencer avec la version du service le 1er novembre 2021. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.22 (novembre 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22). |



## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2021 vague de publication 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

