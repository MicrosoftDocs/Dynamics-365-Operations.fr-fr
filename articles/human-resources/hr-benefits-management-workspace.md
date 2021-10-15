---
title: Espace de travail de gestion des avantages
description: Cette rubrique décrit l’espace de travail Gestion des avantages dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6cc1432e108c74706dea124a62024272e65b6c1
ms.sourcegitcommit: 47a3ad71210c7ac84d0c25e913c440b5ba205282
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7512472"
---
# <a name="benefits-management-workspace"></a>Espace de travail de gestion des avantages

[!include [applies to](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

Cette rubrique décrit l’espace de travail **Gestion des avantages** dans Dynamics 365 Human Resources.

> [!NOTE]
> Pour voir l’espace de travail **Gestion des avantages**, vous devez d’abord activer la fonctionnalité **(version préliminaire) Espace de travail Gestion des avantages** dans la gestion des fonctionnalités. Pour plus d’informations sur l’activation des fonctionnalités en version préliminaire, consultez [Gérer les fonctionnalités](hr-admin-manage-features.md).<br><br>![Activer l’espace de travail de gestion des avantages.](./media/hr-benefits-management-workspace-enable.png)

L’espace de travail **Gestion des avantages** vous donne un aperçu rapide des avantages qui nécessitent votre attention. Sur cette page vous pouvez voir :

- Totaux des éléments en attente d’action
- Collaborateurs avec des sélections non confirmées
- Collaborateurs qui ont récemment adhéré à des prestations
- Collaborateurs avec des événements de la vie futurs
- Les nouvelles recrues qui ne sont pas inscrites
- Collaborateurs avec des événements de la vie actifs
- Collaborateurs avec des inscriptions ouvertes qui n’ont opté pour aucun plan

![Espace de travail de gestion des avantages.](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a>Afficher les éléments d’action

Vous pouvez afficher vos actions en sélectionnant une vignette ou un onglet. Si vous sélectionnez un onglet, vous pouvez afficher et sélectionner des Collaborateurs directement sur la page de l’espace de travail.

![Éléments d’action.](./media/hr-benefits-management-workspace-action-items.png)

Si vous sélectionnez une vignette, vous accédez à la page de cette zone. Par exemple, la sélection de l’une de ces vignettes affiche la page **Régimes d’avantages sociaux des collaborateurs**, filtrée pour les employés sur lesquels vous devez agir :

- **Sélections non confirmées**
- **Ouvrir les inscriptions sans plans extraits**
- **Inscrit aux avantages**
- **Nouvelle recrue non inscrite**

![Plans d’avantages des collaborateurs.](./media/hr-benefits-management-workspace-plans.png)

Le fait de sélectionner **Événements de la vie active** ou **Événements futurs de la vie** vous renvoie à une liste d’événements de la vie actifs ou futurs.

![Événements de vie.](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a>Traitement en cours

Pour traiter l’éligibilité des inscriptions, les événements de la vie ou les mises à jour des changements de taux, sélectionnez l’élément approprié dans la barre de navigation.

![Traitement.](./media/hr-benefits-management-workspace-processing.png)

Pour afficher les résultats de processus, sélectionnez **Résultats du processus** sur la page.

![Traiter les résultats.](./media/hr-benefits-management-workspace-process-results.png)

Pour plus d’informations sur le traitement des avantages, voir :

- [Traiter l’éligibilité à l’inscription](hr-benefits-process-enrollment-eligibility.md)
- [Traiter les modifications des événements de vie](hr-benefits-process-life-event-changes.md)
- [Traiter l’éligibilité aux événements de vie](hr-benefits-process-life-event-eligibility.md)
- [Traiter les événements de vie](hr-benefits-process-life-events.md)
- [Traiter les modifications de taux](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a>Modification de la période

Pour afficher une période de prestations différente, sélectionnez-la dans la liste déroulante **Période**.

![Modification de la période.](./media/hr-benefits-management-workspace-period.png)


## <a name="open-enrollment-tab"></a>Onglet Inscription ouverte

Vous pouvez afficher les actions en sélectionnant une vignette ou un onglet. Si vous sélectionnez un onglet, vous pouvez afficher et sélectionner des Collaborateurs directement sur la page de l’espace de travail.
L'onglet **Inscription ouverte** fournit des mesures clés pour le processus d'inscription ouvert. 

Les informations concernant les inscriptions ouvertes seront affichées 30 jours avant la **Date de début d'inscription**. Ceci est défini dans la configuration **Périodes** dans **Gestion des avantages** > **Liens** > **Périodes**, dans le champ **Date de début d'inscription**.  Pour modifier ce paramètre, accédez à **Paramètres partagés des ressources humaines** > **Gestion des avantages** > **Options d'inscription ouvertes** et mettez à jour le champ **Nombre de**.  

Les informations suivantes sont disponibles dans l'onglet **Inscription ouverte** :
 - Employés qui n'ont pas commencé le processus d'inscription ouverte
 - Employés qui ont des élections en cours
 - Employés ayant terminé le processus électoral
 - Sélections non confirmées

**Vignettes récapitulatives**

- **Pas commencé** - La vignette **Pas commencé** affiche le nombre d'employés qui n'ont pas commencé le processus d'inscription. La vignette **Pas commencé** est une liste filtrée qui affiche uniquement les employés qui n'ont aucun plan sélectionné, supprimé ou extrait pour la période de plan d'inscription ouverte. Les plans obligatoires sont ignorés et non inclus car ils sont sélectionnés par défaut pour l'employé.  Vous pouvez revenir en arrière sur cette vignette pour voir une liste des employés qui n'ont pas commencé le processus d'inscription ouvert sur la page **Régime d'avantages sociaux des travailleurs**.

  > [!NOTE]
  > Si vous ne souhaitez pas suivre la progression des inscriptions ouvertes pour un **Type de régime**, vous pouvez l'exclure en vous rendant sur **Gestion des avantages** > **Liens** > **Paramètres du libre-service des employés** > **Configuration des vignettes des plans d'avantages** et la mise à jour du champ **Suivre la progression des inscriptions ouvertes**.  Par exemple, vous pouvez avoir des plans créés où **Type de régime** = **Autre**. Ces plans peuvent être des plans facultatifs pour lesquels vous ne souhaitez pas suivre la progression de l'inscription. Si vous ne sélectionnez pas ce type de plan, les plans de ces types seront ignorés lors du suivi de la progression ou de l'achèvement de l'inscription dans l'onglet **Inscription ouverte**. Ce paramètre s'applique au type de plan sélectionné pour toutes les périodes et entités juridiques.

- **En cours** - La vignette **En cours** donne le nombre d'employés qui ont des élections en cours. La vignette **En cours** est une liste filtrée qui affiche uniquement les employés qui ont au moins un plan qui est supprimé ou sélectionné. Les plans obligatoires sont ignorés et non inclus car ils sont sélectionnés par défaut pour l'employé. Vous pouvez revenir en arrière à partir de cette vignette pour voir les plans sélectionnés et annulés sur la page **Mise à jour en bloc des régimes d'avantages des collaborateurs**.

- **Inscrit aux avantages** - La vignette **Inscrit aux avantages** donne le nombre d'employés qui sont pleinement inscrits aux avantages. La vignette **Inscrits aux avantages** est une liste filtrée qui montre les employés qui ont sélectionné ou renoncé à tous les plans. La requête exclura les plans qui ne sont pas suivis pour l'inscription ouverte sur la page **Paramètres du libre-service des employés**. Vous pouvez revenir en arrière à partir de cette vignette pour voir une liste des employés sur la page **Régimes d'avantages sociaux des travailleurs**.

- **Sélections non confirmées** - La vignette **Sélections non confirmées** affiche le nombre d'employés dont les plans sont sélectionnés ou annulés et doivent être confirmés. Vous pouvez revenir en arrière à partir de cette vignette pour voir la page **Mise à jour en bloc des régimes d'avantages des collaborateurs**.

**Activité**

- **Pas commencé** - L'onglet **Pas commencé** affiche une liste des employés qui n'ont pas commencé le processus d'inscription. La vignette **Pas commencé** est une liste filtrée qui affiche les employés qui n'ont aucun plan sélectionné, supprimé ou extrait pour la période de plan d'inscription ouverte. Les plans obligatoires sont ignorés et non inclus car ils sont sélectionnés par défaut pour l'employé. Vous pouvez explorer le travailleur pour afficher la page **Détails des régimes d'avantages sociaux des collaborateurs**.

- **Élections en cours** - L'onglet **Élections en cours** affiche la liste des employés qui ont des élections en cours. L'onglet **Élections en cours** est une liste filtrée qui affiche uniquement les employés qui ont au moins un plan qui est supprimé ou sélectionné. Les plans obligatoires sont ignorés et non inclus car ils sont sélectionnés par défaut pour l'employé. Vous pouvez explorer le travailleur pour afficher la page **Détails des régimes d'avantages sociaux des collaborateurs**.

## <a name="view-more-options"></a>Voir plus d’options

Pour afficher plus d’informations ou des actions supplémentaires, sélectionnez **Liens**.

![Liens.](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a>Voir également :

[Vue d’ensemble de la gestion des avantages](hr-benefits-management-overview.md)
