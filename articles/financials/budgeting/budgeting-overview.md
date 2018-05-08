---
title: "Page d'accueil de la fonctionnalité de budgétisation"
description: "Cette rubrique fournit une vue d'ensemble des composants de la fonctionnalité de budgétisation, des outils de budgétisation et des fonctionnalités de génération d'états dans Microsoft Dynamics 365 for Finance and Operations."
author: twheeloc
manager: AnnBe
ms.date: 08/09/2017
ms.topic: index-page
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanningWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 106043
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: efe348d9967ab7594afd22a3ebb4df76dc6607f8
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="budgeting-home-page"></a>Page d'accueil de la fonctionnalité de budgétisation

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d'ensemble des composants de la fonctionnalité de budget, des outils de budgétisation et des fonctionnalités de génération d'états dans Finance and Operations. 

<a name="components-of-budgeting-functionality"></a>Composants de la fonctionnalité de budgétisation
-------------------------------------

Le cycle de planification des ressources pour une société comporte généralement des activités de planification, de budgétisation et de prévision.

[![Composants de la fonctionnalité de budgétisation](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg)

Les processus de planification stratégique à long terme et de planification budgétaire annuelle sont pris en charge par un document de plan budgétaire. Les documents de plan budgétaire sont étroitement intégrés avec Microsoft Excel. Les utilisateurs peuvent configurer des scénarios monétaires et quantitatifs illimités, et définir une hiérarchie organisationnelle de budgétisation pour prendre en charge les méthodes de budgétisation du haut-en-bas et de bas-en-haut. Une fois que le budget est établi et approuvé dans Finance and Operations, vous devez convertir le plan budgétaire en écriture du registre budgétaire. Les écritures du registre budgétaires fournissent des outils pour tenir à jour le budget et pour conserver la trace des montants grâce à des codes budgétaires. Les écritures du registre budgétaires permettent de réviser les budgets d'origine, effectuer des transferts et reporter des montants budgétaires de l'année précédente. Selon le budget établi, une société peut activer le contrôle budgétaire. Le niveau de contrôle dépend du niveau de la culture organisationnelle et du niveau de maturité de l'organisation. Les organisations qui ont un faible niveau de maturité peuvent laisser le budget « tel quel » et être plus réactives que proactives si un budget ne respecte pas leurs attentes. D'autres organisations peuvent activer les stratégies de contrôle budgétaire qui empêchent les utilisateurs d'acheter si les fonds budgétaires ne sont pas disponibles.

Enfin, les organisations très mûres peuvent créer une culture organisationnelle dans laquelle les employés sont instruits des cibles organisationnelles et les poursuivent via des stratégies telles que « Envisagez une réunion en ligne plutôt qu'un déplacement ». Finance and Operations inclut une structure de contrôle budgétaire qui permet à la direction de la société de choisir un contrôle ferme (qui empêche les validations qui excéderaient le budget) ou souple (où les utilisateurs sont prévenus s'ils dépassent les fonds budgétaires disponibles et peuvent décider par eux-mêmes). Enfin, vous pouvez utiliser des prévisions à court terme. Une prévision à court terme est une comparaison régulière du budget avec les chiffres réels et elle sert à définir avec quel succès la société exploite son budget. Une prévision à court terme permet également d'identifier les tendances. Dans Finance and Operations, les prévisions à court terme sont prises en charge via un document de plan budgétaire en tant qu'activités initiales de planification. Les prévisions à court terme peuvent être effectuées parallèlement avec l'organisation du cycle budgétaire à venir.

-   [Budgétisation de base : vue d'ensemble et configuration](basic-budgeting-overview-configuration.md)
-   [Contrôle budgétaire : vue d'ensemble et configuration](budget-control-overview-configuration.md)
-   [Planification budgétaire : vue d'ensemble et configuration](budget-planning-overview-configuration.md)
-   [Prévision des postes](position-forecasting.md)
-   [Documents justificatifs du plan budgétaire](budget-planning-justification-docs.md)
-   [Modèles Microsoft Excel pour la planification budgétaire](budget-planning-excel-templates.md)

## <a name="budgeting-tools-in-finance-and-operations"></a>Outils de budgétisation dans Finance and Operations
[![Outils de budgétisation](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

D'autres fonctionnalités de planification et de budgétisation sont disponibles dans Finance and Operations et sont intégrées aux budgets comptables.

-   **Budgets de personnel** – La budgétisation du personnel inclut la planification des composants du coût budgétaire détaillé pour les postes, les groupes de rémunération, etc.
-   **Budgets d'immobilisations** – Selon les informations d'immobilisation, vous pouvez calculer l'amortissement prévu et enregistrer d'autres transactions prévues liées aux immobilisations.
-   **Budgets de projet** : Dans le module des projets, vous pouvez créer des prévisions de projet détaillées. Les prévisions de projets comprendront des détails sur les heures, les dépenses, les frais, et les articles prévus.
-   **Prévision de la demande** : En fonction des données de transaction historiques, vous pouvez estimer la demande de stock future et créer des prévisions de la demande.

Pour plus d'informations sur l'entrée de données de planification d'autres modules dans les plans budgétaires, consultez [Intégration de la planification budgétaire avec d'autres modules](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Interface utilisateur et fonctionnalités de génération d'états
Dans Finance and Operations, les utilisateurs peuvent créer des plans budgétaires directement dans le client Finance and Operations (à l'aide d'une page configurable de document de plan budgétaire) ou à l'aide d'Excel. Excel fournit plusieurs capacités supplémentaires. Par exemple, vous pouvez utiliser des données externes comme source pour un plan budgétaire, effectuer des calculs personnalisés, et utiliser Microsoft PivotTable et des graphiques. La plupart des variables du processus de planification budgétaire peuvent être configurées. 

Par exemple, vous pouvez définir qui effectue la budgétisation, qu'est-ce qui est budgété, et à quoi ressemble le processus. Bien que vous puissiez utiliser Excel pour la planification de budget, Finance and Operations demeure la source unique de la vérité et empêche les problèmes de contrôle budgétaire. Des processus périodiques peuvent être utilisés pour remplir le plan budgétaire avec les données initiales de budgétisation. Pour générer un état, Finance and Operations offre un ensemble de pages standard de recherche qui permettent d'afficher et d'analyser les données de budgétisation. Les données du plan budgétaire peuvent être consultées par Management Reporter, et il est possible d'afficher les scénarios de plan budgétaire distincts en colonnes dans l'état de Management Reporter.







