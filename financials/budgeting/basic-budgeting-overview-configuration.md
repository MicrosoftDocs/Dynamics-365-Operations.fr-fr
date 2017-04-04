---
title: Vue d&quot;ensemble du budget
description: "Presque chaque société qui utilise la fonctionnalité de Finances dans Microsoft Dynamics 365 pour les opérations Avant de pouvoir créer des états de budget et la réalité. Cet article décrit la configuration minimale requise pour pouvoir créer des budgets dans Dynamics 365 pour les opérations ou les charger d&quot;un troisième programme."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 60113
ms.assetid: 28a9793e-d376-47af-a345-69046bad17df
ms.search.region: global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a639e509cf6a3d2f1b850f27481d7b95546522b8
ms.openlocfilehash: b62e14f7c91692ae97bb332b38b0deeb328cc1bd
ms.lasthandoff: 03/31/2017


---

# <a name="budgeting-overview"></a>Vue d'ensemble du budget

Presque chaque société qui utilise la fonctionnalité de Finances dans Microsoft Dynamics 365 pour les opérations Avant de pouvoir créer des états de budget et la réalité. Cet article décrit la configuration minimale requise pour pouvoir créer des budgets dans Dynamics 365 pour les opérations ou les charger d'un troisième programme.

<a name="overview"></a>Vue d'ensemble
--------

Le budget approuvé pour une entité juridique est tenu à jour dans un document appelé une *écriture de registre budgétaire*. Les lignes dans un document d'écriture de registre budgétaire sont désigné comme des entrées d'account* de *budget, et contiennent les informations sur la dimension financière, les dates, et les montants de budget approuvé. Le document d'écriture de registre budgétaire est intégré dans les états et les pages financiers de base de recherche où les montants réels de comptabilité sont comparés aux montants budgétaires. 

Il existe de plusieurs méthodes pour créer des écritures de registre budgétaires dans Dynamics 365 pour les opérations :

-   Entrez manuellement les informations de document sur la page **Écritures de registre budgétaires**.
-   Utilisez le modèle Microsoft Excel que vous pouvez ouvrir en cliquant sur le bouton **Ouvrir dans Excel** de la page **Écritures de registre budgétaires**.
-   Utilisez l'entité de données **Écritures de compte budgétaires** dans le module Gestion des données pour importer les écritures de registre budgétaires. Vous devez envisager d'utiliser cette méthode et de activer ** définissez basé ** ** traitant ** paramètre lorsque vous devez importer plusieurs écritures de compte budgétaires dans le système.
-   Si la société utilise la fonctionnalité de planification budgétaire pour préparer les données du budget, vous pouvez utiliser le processus périodique **Générer une écriture de registre budgétaire**.

L'écriture de registre budgétaire est considérée comme terminée lorsque les soldes budgétaires ont été mis à jour. Sous ** écritures de registre budgétaires ** la page, cliquez sur ** soldes budgétaires de mise à jour ** pour une écriture de registre budgétaire sélectionnée ou plusieurs entrées. Après la mise à jour des soldes budgétaires, le statut de l'écriture de registre budgétaire passe à **Terminé**. Une écriture de registre budgétaire terminée ne peut pas être rouverte pour être modifiée. Par conséquent, si les données de budget doivent être ajustées, vous devez créer une écriture de registre budgétaire au lieu de corriger les données de l'écriture de registre budgétaire terminée.

## <a name="configuration"></a>Configuration
Lorsque vous configurez la budgétisation, démarrez sur la page **Paramètres de budgétisation**. Sur cette page, vous devez définir le journal des budgets, la souche de numéros pour les écritures de registre budgétaires, et le comportement par défaut dans les espaces de travail.

Ensuite, s'il existe des stratégies régissant l'approbation des écritures de registre budgétaires, en fonction du type de budget (par exemple, des transferts ou des révisions), vous devez créer des workflows d'écriture de registre budgétaire sur la page **Workflows de budgétisation**. S'il existe des scénarios dans lesquels les transferts peuvent être autorisés sans approbation de workflow, vous pouvez définir des règles de transfert budgétaire pour prendre en charge ces scénarios. 

Sur la page **Dimensions de budgétisation**, vous devez sélectionner les dimensions financières utilisées pour la budgétisation, en fonction des dimensions utilisées dans le plan de comptes. Vous pouvez sélectionner toutes les dimensions financières ou un sous-ensemble de celles-ci pour la budgétisation.

Définissez un *that de modèle de *budget correspond à tout ou à certains de vos budgets. Vous pouvez utiliser un modèle de budget unique pour toutes les écritures de registre budgétaires. Sinon, vous pouvez créer des modèles distincts basés sur le type de budget, l'emplacement géographique, ou sur une autre façon de classifier un budget. 

> [!NOTE] 
> Si le contrôle budgétaire est utilisé, vous pouvez associer un seul modèle de budget avec une période de cycle budgétaire spécifique. 

Créez des *codes budget *qui identifient le type de transactions budgétaires pour à enregistrer et tout workflow associé. Les codes budget peuvent prendre en charge les types de budget suivants :

-   Budget d'origine
-   Transfert
-   Révision
-   Engagement
-   Engagement préalable
-   Report de budget

Les codes budget vous permettent de disposer d'une piste d'audit des modifications de budget approuvées tout au long du cycle budgétaire. Si un workflow est associé à un code budgétaire, le workflow est activé pour toutes les écritures de registre budgétaires qui utilisent ce code budget, et les étapes de workflow doivent être effectuées avant que l'écriture de registre budgétaire peut atteindre ** terminé ** le stade.  

Vous pouvez également éventuellement paramétrer le rules* de transfert de *budget. Pour utiliser des règles de transfert budgétaire, sélectionnez ** les utiliser les règles de transfert budgétaire ** sur ** des paramètres de budget ** la page. Lorsque vous utilisez des règles de transfert budgétaire et qu'un utilisateur crée un document à l'aide d'un code budget de type **Transfert**, les soldes budgétaires ne sont pas mises à jour si les règles de transfert budgétaire sont violées. Par exemple, vous pouvez autoriser les documents de transfert budgétaire où le budget des dépenses est transféré entre les comptes principaux pour le département Ventes et marketing, mais interdire le transfert du budget de ou vers ce département sauf si l'approbation de workflow a été autorisé pour ce type d'écriture de compte budgétaire.

## <a name="using-workspaces-and-inquiry-pages-to-track-budget-vs-actuals"></a>Utilisation des espaces de travail et des pages de recherche effectuer le suivi du budget et des chiffres réels
Le responsable du budget peut consulter l'état actuel d'un budget dans l'espace de travail **Budgets comptables et prévisions**. Les onglets **Dépense supérieure au budget** et **Produit inférieur au budget** fournissent un aperçu rapide des combinaisons de dimensions financières dans lesquelles les cibles de budget ne sont pas atteintes ou approchent du seuil. Vous pouvez personnaliser le pourcentage de seuil budgétaire et les ensembles de dimensions financières utilisés sous ces onglets en cliquant sur **Configurer mon espace de travail**. Vous pouvez cliquer sur **Responsable de l'unité** pour afficher les collaborateurs responsables des combinaisons de dimensions financières spécifiques sélectionnées sous ces onglets. Par exemple, si vous constatez que le budget de dépenses du département des opérations va dépasser le seuil budgétaire, vous pouvez facilement rechercher et contacter le responsable du département pour discuter du problème. 

> [!NOTE] 
> ** Responsable de département ** le champ sous ** unités d'organisation ** la page détermine les responsables prennent en charge les combinaisons de dimensions financières spécifiques. Pour plus de détails sur les montants budgétaires/les montants réels, cliquez sur **En voir plus** dans la partie inférieure de l'onglet pour ouvrir la page de recherche **Budget et chiffres réels**. 

La page de recherche **Comparatif Réel/Budget** vous permet de zoomer sur les détails du budget par rapport aux montants réels. Sélectionnez une ligne sur la page de recherche, puis cliquez sur **Soldes de la période** pour afficher les montants du budget et les montants réels répartis sur plusieurs périodes fiscales. La page **Écritures de compte budgétaires** permet d'extraire les détails du montant du budget des écritures de registre budgétaires. La page **Écritures du journal des opérations diverses **affiche les écritures comptables incluses dans le montant **Chiffres réels** calculé. 

Une société qui utilise la fonctionnalité de planification budgétaire peut créer et utiliser les *prévisions budgétaires *dans l'espace de travail **Budgets comptables et prévisions**.


