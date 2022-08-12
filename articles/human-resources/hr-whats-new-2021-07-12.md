---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (12 juillet 2021)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 12 juillet 2021.
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
ms.search.validFrom: 2021-07-12
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d7fb922a35504b69aa8cc3d92cb981e8fb060290
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067584"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-12-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (12 juillet 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou sont annoncées dans Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 1re vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4353.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
|  Basculement de l’affichage des années de service | |Cette fonction offre la possibilité d’utiliser différentes dates pour calculer les années de service affichées sur la page **Entrée d’employé simplifiée** et sur la page **Personnes**.  Elle sera disponible dans les [paramètres de Human Resources](/dynamics365/human-resources/hr-setup-parameters). |


### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cet article pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cet article.

| Numéro du problème | Problème |  Description |
| --- | --- | --- |
| 595871 | Le volet À propos de Human Resources comporte une terminologie Dataverse incorrecte | Avec le changement de marque de Common Data Service en Dataverse, la terminologie a été mise à jour dans le volet d’information de Microsoft Dynamics 365 Human Resources (**Aide et support > À propos**). |
| 598676 | La tâche d’écrasement du formulaire d’entrée d’employé simplifiée peut créer une erreur lorsqu’elle est utilisée avec la vue enregistrée| Sur la page **Collaborateur**, si la fonction « Entrée d’employé simplifiée » est activée, l’application peut échouer si **Toujours ouvert pour l’édition** est défini sur la vue enregistrée. |
| 592344 |La section Rémunération des collaborateurs sur le poste doit être en lecture seule lorsque la gestion des avantages est activée | Les informations sur la rémunération des collaborateurs sont créées à l’aide de l’ancienne fonctionnalité d’avantages.  Lorsque la gestion des avantages est activée, les champs seront en lecture seule. Lorsque la gestion des avantages est activée et que l’option **Masquer les anciens formulaires d’avantages** est définie sur **Oui** dans les paramètres HR partagés, l’onglet **Rémunération des collaborateurs** sera masqué. |
| 598617 | L’onglet d’activation du formulaire **HcmDiscussion** provoque une boucle infinie lorsque lds personnalisations sont appliquées | Lorsque les vues Grille et Détails ont toutes deux l’option **Toujours ouvert pour l’édition** activée, le code qui active l’onglet dans la méthode de tâche écrasée entre en conflit avec la personnalisation sur la question de quel contrôle doit avoir le focus, et cela engendre une boucle infinie. |
| 593553 | Le champ Date du journal dans le Journal des performances s’affiche en UTC | Le champ **Date du journal** des journaux de performances s’affiche dans le fuseau horaire UTC plutôt que dans le fuseau horaire défini dans la configuration de date du système, ce qui rend la date incorrecte pour certains fuseaux horaires. |
| 586930 | L’ouverture d’activités pour les objectifs de performance ouvre un enregistrement complètement différent | Lorsque la fonctionnalité « Vue de rapport étendu des journaux de performances » est activée dans la Gestion des fonctionnalités, la sélection des objectifs de performances pour les rapports étendus sur l’onglet **Mon équipe** dans le **Libre service employé** ouvre les objectifs d’un employé au lieu de l’employé sélectionné. |
| 569959 |  L’entité HcmPositionWorkerAssignmentV2 n’affecte pas de collaborateur à un poste | Les utilisateurs reçoivent une erreur lors de l’ajout d’un enregistrement d’affectation de poste via l’entité, et la publication échoue. |
| 582259 | Le rapport VETS 4212 utilise le formulaire 2017 au lieu du formulaire 2020 | Mise à jour au format 2020.  Pour charger le nouveau format, accédez à **Configurations de rapport** et supprimez le rapport VETS-4212 dans la colonne de gauche. Accédez **Gestion des états électroniques - Référentiels - Ressources HR** et sélectionnez **Ouvrir**.  Sélectionnez **VETS-4212 Impression PDF** puis sélectionnez **Importer**.|


## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |
| Activer l’intégration simplifiée de la paie (API d’intégration de la paie) | [Activer l’intégration simplifiée avec des prestataires de paie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)|
|  Activer un gestionnaire des absences pour gérer les congés | [Activer un gestionnaire des absences pour gérer les congés](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | [Configurer le rôle de gestionnaire des absences](https://go.microsoft.com/fwlink/?linkid=2168107)|
|  Configurer l’exigence de pièce jointe par type de congé | [Configurer l’exigence de pièce jointe par type de congé](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Configurer les types de congé et d’absence](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Configurer les unités de congé par type de congé | [Configurer les unités de congé par type de congé](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Configurer les types de congé et d’absence](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Permettre aux employés d’être marqués comme prêts à être payés | [Permettre aux employés d’être marqués comme prêts à être payés](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Prêt à payer](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Bientôt disponible

| Fonctionnalité | Détails |
| --- | --- |
| Platform update 10.0.20 (44) | La mise à jour de la plateforme 10.0.20 devrait commencer à être déployée avec la version du service du 26 juillet 2021. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.20 (août 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20). |

Pour obtenir la liste complète des fonctionnalités prévues et de leur lancement, voir [Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

