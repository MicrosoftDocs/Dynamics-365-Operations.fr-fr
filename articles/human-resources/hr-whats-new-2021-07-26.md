---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (26 juillet 2021)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 26 juillet 2021.
author: marcelbf
ms.date: 07/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-26
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 14041dfc753b508a0d68b90ee99d79510d07e622
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070078"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-26-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (26 juillet 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou sont annoncées dans Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4384.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Update 10.0.20 de la plateforme | -- | [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.20 (août 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20) |

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cet article pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cet article.

| Numéro du problème | Problème |  Description |
| --- | --- | --- |
| 600422 | Échec de la validation de l’adresse de paie pour Prêt à payer. | La validation a été mise à jour pour n’exiger qu’une seule adresse de type « Lieu de résidence de la paie » et une seule adresse de type « Lieu de travail de la paie ». |
| 601226 | Problème d’intégration des données : le projet d’exportation d’intégration de la paie n’inclut pas l’option de transmission de type push complète | L’intégration de la paie à Ceridian DayForce effectuait une transmission de type push incrémentielle et non de type push complète. Ceridian requiert toujours une actualisation complète. Ce problème est désormais résolu, les entités du projet d’exportation de données ne basculeront plus vers une transmission de type push incrémentielle. |
| 602272 | Les vignettes qui ont été ajoutées à l’espace de travail Libre-service des employés sont désormais manquantes et il n’est plus possible d’ajouter des vignettes | Nous avons résolu le problème de personnalisation du Libre-service des employés. De nouvelles vignettes peuvent être ajoutées à la vue et toute personnalisation existante sera visible par les utilisateurs |
| 600711 | Champ de sélection de définition d’une demi-journée activé pour les demandes de congés d’une journée complète | Ce problème est désormais résolu et le champ de définition d’une demi-journée ne sera activé que lorsque les employés sélectionneront un type de congé avec la définition d’une demi-journée activée et une demi-journée comme valeur de montant sélectionnée |
| 602208 | Unités de taux de régularisation affichant des heures au lieu des jours | Ce problème est désormais résolu. Le formulaire **Congé** indiquera la bonne unité de congé (heures ou jours) pour la colonne **Taux de régularisation**. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |
| Activer l’intégration simplifiée de la paie (API d’intégration de la paie) | [Activer l’intégration simplifiée avec des prestataires de paie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)|
|  Activer un gestionnaire des absences pour gérer les congés | [Activer un gestionnaire des absences pour gérer les congés](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | Avec cette version, nous mettons à jour la vue de l’espace de travail du gestionnaire des absences. Pour plus d’informations, voir [Configurer le rôle de gestionnaire des absences](https://go.microsoft.com/fwlink/?linkid=2168107).|
|  Configurer l’exigence de pièce jointe par type de congé | [Configurer l’exigence de pièce jointe par type de congé](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Configurer les types de congé et d’absence](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Configurer les unités de congé par type de congé | [Configurer les unités de congé par type de congé](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Configurer les types de congé et d’absence](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Permettre aux employés d’être marqués comme prêts à être payés | [Permettre aux employés d’être marqués comme prêts à être payés](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Prêt à payer](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Bientôt disponible

Pour une liste complète des fonctionnalités planifiées et de leurs lancements planifiés, voir [Vue d’ensemble de la 2e vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2021 vague de publication 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

