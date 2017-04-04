---
title: "Page d&quot;accueil de la fonctionnalité de budget"
description: "Cette rubrique fournit une vue d&quot;ensemble des composants de budgétisation de la fonctionnalité, les outils de budgétisation, et de générer un état des capacités dans Microsoft Dynamics 365 pour les opérations."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: index-page
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106043
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: f7b4efc06b8e64c05da026850b41cb5b68c33ec3
ms.lasthandoff: 03/31/2017


---

# <a name="budgeting-home-page"></a>Page d'accueil de la fonctionnalité de budget

Cette rubrique fournit une vue d'ensemble des composants de budgétisation de la fonctionnalité, les outils de budgétisation, et de générer un état des capacités dans Microsoft Dynamics 365 pour les opérations.

<a name="components-of-budgeting-functionality"></a>Composants de la fonctionnalité de budgétisation
-------------------------------------

Le cycle de planification des ressources pour une société comporte généralement de la planification, de la budgétisation, et la prévision d'activités.
[composants de la budgétisation de fonctionnalités![(]. /media/budgeting-functionality-components.jpg)](. /media/budgeting-functionality-components.jpg) Des processus pour la planification stratégique de long terme et la planification budgétaire annuel sont pris en charge par le biais d'un document de plan budgétaire. Les documents de plan budgétaire sont étroitement intégrés avec Microsoft Excel. Les utilisateurs peuvent configurer des scénarios monétaires et quantitatifs illimités, et définir une hiérarchie organisationnelle de budgétisation pour prendre en charge les méthodes de budgétisation du haut-en-bas et de bas-en-haut. Une fois le budget est établi et approuvé dans Microsoft Dynamics 365 for Operations, vous convertissez le plan budgétaire en écriture du registre budgétaire. Les écritures du registre budgétaires fournissent des outils pour tenir à jour le budget et pour conserver la trace des montants grâce à des codes budgétaires. Les écritures du registre budgétaires permettent de réviser les budgets d'origine, effectuer des transferts et reporter des montants budgétaires de l'année précédente. Selon le budget établi, une société peut activer le contrôle budgétaire. Le niveau de contrôle dépend du niveau de la culture organisationnelle et du niveau de maturité de l'organisation. Les organisations qui ont un faible niveau de maturité peuvent laisser le budget « tel quel » et être plus réactives que proactives si un budget ne respecte pas leurs attentes. D'autres organisations peuvent activer les stratégies de contrôle budgétaire qui empêchent les utilisateurs d'acheter si les fonds budgétaires ne sont pas disponibles. Enfin, les organisations très mûres peuvent créer une culture organisationnelle dans lequel les employés sont instruits sur les cibles organisationnelles et suivre ces cibles via les stratégies par exemple « considèrent la réunion en ligne plutôt qu'un voyage. » Dynamics 365 pour les opérations inclut une zone de contrôle budgétaire qui permet la gestion de la société sélectionner le contrôle ferme (qui empêché les validations qui iraient sur le budget) ou contrôle prudent (lequel les utilisateurs sont prévenus qu'ils vont les fonds budgétaires disponibles mais peuvent décider eux-mêmes comment pour continuer). Enfin, vous pouvez utiliser les prévisions cumulées. Une prévisions cumulées est une comparaison régulier de budget à la réalité et permet de définir le point la société opère par rapport à le budget. Une prévision à court terme permet également d'identifier les tendances. Dans Microsoft Dynamics 365 for Operations, les prévisions à court terme sont prises en charge via un document de plan budgétaire comme activités initiales d'organisation. Les prévisions à court terme peuvent être effectuées {parallèlement avec l'organisation du cycle budgétaire à venir.

-   [Budgétisation de base : vue d'ensemble et configuration](basic-budgeting-overview-configuration.md)
-   [Contrôle budgétaire : vue d'ensemble et configuration](budget-control-overview-configuration.md)
-   [Planification budgétaire : Vue d'ensemble et configuration](budget-planning-overview-configuration.md)
-   [Prévision de poste](position-forecasting.md)
-   [Documents de justification de planification budgétaire] (budget-planning-justification-docs.md)
-   [Modèles de Microsoft Excel pour planification budgétaire] (budget-planning-excel-templates.md)

## <a name="budgeting-tools-in-dynamics-365-for-operations"></a>Outils de budgétisation dans Dynamics 365 for Operations
[outils de budgétisation d'![] (. /media/budgeting-tools.jpg)](. /media/budgeting-tools.jpg) 

D'autres fonctionnalités de planification et de budgétisation sont disponibles dans Dynamics 365 for Operations et sont intégrées aux budgets comptables.

-   **Budgets de personnel** – La budgétisation du personnel inclut la planification des composants du coût budgétaire détaillé pour les postes, les groupes de rémunération, etc.
-   **Budgets d'immobilisations** – Selon les informations d'immobilisation, vous pouvez calculer l'amortissement prévu et enregistrer d'autres transactions prévues liées aux immobilisations.
-   **Budgets de projet** : Dans le module des projets, vous pouvez créer des prévisions de projet détaillées. Les prévisions de projets comprendront des détails sur les heures, les dépenses, les frais, et les articles prévus.
-   ** Prévision de la demande ** – sur les données de transaction historiques, vous pouvez évaluer la prochaine demande de stock et créer des prévisions de la demande.

Pour plus d'informations sur l'entrée de données de planification d'autres modules dans les plans budgétaires, consultez [Intégration de la planification budgétaire avec d'autres modules](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Interface utilisateur et fonctionnalités de génération d'états
Dans Dynamics 365 for Operations, les utilisateurs peuvent créer des plans budgétaires directement dans le client Dynamics 365 for Operations (à l'aide d'une page configurable de document de plan budgétaire) ou à l'aide d'Excel. Excel fournit plusieurs capacités supplémentaires. Par exemple, vous pouvez utiliser des données externes comme source pour un plan budgétaire, effectuer des calculs personnalisés, et utiliser Microsoft PivotTable et des graphiques. La plupart des variables du processus de planification budgétaire peuvent être configurées. Par exemple, vous pouvez définir qui effectue la budgétisation, qu'est-ce qui est budgété, et à quoi ressemble le processus. Bien que vous puissiez utiliser Excel pour la planification de budget, Dynamics 365 for Operations demeure la source unique de la vérité et empêche les problèmes de contrôle budgétaire. Des processus périodiques peuvent être utilisés pour remplir le plan budgétaire avec les données initiales de budgétisation. Pour générer un état, Dynamics 365 for Operations offre un ensemble de pages standard de recherche qui permettent d'afficher et d'analyser les données de budgétisation. Les données du plan budgétaire peuvent être consultées par Management Reporter, et il est possible d'afficher les scénarios de plan budgétaire distincts en colonnes dans l'état de Management Reporter.





