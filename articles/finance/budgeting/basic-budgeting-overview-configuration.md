---
title: Vue d'ensemble du budget
description: Presque toutes les sociétés qui utilisent la fonctionnalité Finances dans Microsoft Dynamics 365 Finance pourront créer des états budgétés et réels. Cet article décrit la configuration minimale requise pour créer des budgets dans Finance and Operations ou les charger dans un programme tiers.
author: ShylaThompson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 60113
ms.assetid: 28a9793e-d376-47af-a345-69046bad17df
ms.search.region: global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 36144474defc4849a112a180247f37796de00a27
ms.sourcegitcommit: 1eaa3451275fe4223d4d25b37aaa1cd2b183e803
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2019
ms.locfileid: "2667458"
---
# <a name="budgeting-overview"></a>Vue d'ensemble du budget

[!include [banner](../includes/banner.md)]

Presque toutes les sociétés qui utilisent la fonctionnalité Finances dans Microsoft Dynamics 365 Finance pourront créer des états budgétés et réels. Cet article décrit la configuration minimale requise pour créer des budgets dans Finance and Operations ou les charger dans un programme tiers.

<a name="overview"></a>Vue d'ensemble
--------

Le budget approuvé pour une entité juridique est tenu à jour dans un document appelé une *écriture de registre budgétaire*. Les lignes d'un document d'écriture de registre budgétaire sont appelées écritures de *compte budgétaire*, et contiennent des informations relatives aux dimensions financières, des dates et les montants du budget approuvé. Le document d'écriture de registre budgétaire est intégré aux états financiers de base et aux pages de recherche où les montants réels comptables sont comparés aux montants du budget. 

Il existe plusieurs méthodes permettant la création d'écritures de registre budgétaires :

-   Entrez manuellement les informations de document sur la page **Écritures de registre budgétaires**.
-   Utilisez le modèle Microsoft Excel que vous pouvez ouvrir en cliquant sur le bouton **Ouvrir dans Excel** de la page **Écritures de registre budgétaires**.
-   Utilisez l'entité de données **Écritures de compte budgétaires** dans le module Gestion des données pour importer les écritures de registre budgétaires. Envisagez d'utiliser cette méthode et d'activer le paramètre **Traitement basé sur les jeux** si vous devez importer plusieurs écritures de compte budgétaires dans le système.
-   Si la société utilise la fonctionnalité de planification budgétaire pour préparer les données du budget, vous pouvez utiliser le processus périodique **Générer une écriture de registre budgétaire**.

L'écriture de registre budgétaire est considérée comme terminée lorsque les soldes budgétaires ont été mis à jour. Sur la page **Écritures de registre budgétaires**, cliquez sur **Mettre à jour les soldes budgétaires** pour une ou plusieurs écritures de registre budgétaires sélectionnées. Après la mise à jour des soldes budgétaires, le statut de l'écriture de registre budgétaire passe à **Terminé**. Une écriture de registre budgétaire terminée ne peut pas être rouverte pour être modifiée. Par conséquent, si les données de budget doivent être ajustées, vous devez créer une écriture de registre budgétaire au lieu de corriger les données de l'écriture de registre budgétaire terminée.

## <a name="configuration"></a>Configuration
Lorsque vous configurez la budgétisation, démarrez sur la page **Paramètres de budgétisation**. Sur cette page, vous devez définir le journal des budgets, la souche de numéros pour les écritures de registre budgétaires, et le comportement par défaut dans les espaces de travail.

Ensuite, s'il existe des stratégies régissant l'approbation des écritures de registre budgétaires, en fonction du type de budget (par exemple, des transferts ou des révisions), vous devez créer des workflows d'écriture de registre budgétaire sur la page **Workflows de budgétisation**. S'il existe des scénarios dans lesquels les transferts peuvent être autorisés sans approbation de workflow, vous pouvez définir des règles de transfert budgétaire pour prendre en charge ces scénarios. 

Sur la page **Dimensions de budgétisation**, vous devez sélectionner les dimensions financières utilisées pour la budgétisation, en fonction des dimensions utilisées dans le plan de comptes. Vous pouvez sélectionner toutes les dimensions financières ou un sous-ensemble de celles-ci pour la budgétisation.

Définissez un *modèle de budget* correspondant à tous les budgets ou à certains d'entre eux. Vous pouvez utiliser un modèle de budget unique pour toutes les écritures de registre budgétaires. Sinon, vous pouvez créer des modèles distincts basés sur le type de budget, l'emplacement géographique, ou sur une autre façon de classifier un budget. 

> [!NOTE] 
> Si le contrôle budgétaire est utilisé, vous pouvez associer un seul modèle de budget à une période de cycle budgétaire spécifique. 

Créez des *codes budget* qui identifient le type de transactions budgétaires pour à enregistrer et tout workflow associé. Les codes budget peuvent prendre en charge les types de budget suivants :

-   Budget d'origine
-   Transfert
-   Révision
-   Engagement
-   Engagement préalable
-   Report de budget

Les codes budget vous permettent de disposer d'une piste d'audit des modifications de budget approuvées tout au long du cycle budgétaire. Si un workflow est associé à un code budget, le workflow est activé pour toutes les écritures de registre budgétaires qui utilisent ce code budget, et les étapes de workflow doivent être effectuées avant que l'écriture de registre budgétaire atteigne le stade **Terminé**.  

Le cas échéant, vous pouvez également paramétrer les *règles de transfert budgétaire*. Pour utiliser des règles de transfert budgétaire, sélectionnez **Utiliser des règles pour les transferts budgétaires** sur la page **Paramètres budgétaires**. Lorsque vous utilisez des règles de transfert budgétaire et qu'un utilisateur crée un document à l'aide d'un code budget de type **Transfert**, les soldes budgétaires ne sont pas mises à jour si les règles de transfert budgétaire sont violées. Par exemple, vous pouvez autoriser les documents de transfert budgétaire où le budget des dépenses est transféré entre les comptes principaux pour le département Ventes et marketing, mais interdire le transfert du budget de ou vers ce département sauf si l'approbation de workflow a été autorisé pour ce type d'écriture de compte budgétaire.

La fonctionnalité qui a été introduite dans la version 10.0.7 de Microsoft Dynamics 365 Finance (janvier 2020) a apporté capacité et flexibilité aux écritures de registre budgétaires. Pour activer ces améliorations, accédez à l'espace de travail **Gestion des fonctionnalités** et sélectionnez **Écritures de registre budgétaires pour la quantité uniquement** et/ou **Défaillance d'écritures de registre budgétaires de type de montant**.

La fonctionnalité **Écritures de registre budgétaires pour la quantité** uniquement vous permet de valider une écriture de registre budgétaire avec des montants réservés à la quantité. Par exemple, vous pouvez valider une écriture budgétaire avec une quantité de 32 et un prix de zéro, qui induit un montant à zéro. Vous pouvez ensuite utiliser cette quantité dans le contexte d'un rapport financier pour déterminer un prix par quantité. Notez qu'aucune recherche ou état n'a été mis à jour dans le cadre de cette fonctionnalité ; celle-ci permet simplement de valider un montant de zéro.

La fonctionnalité **Défaillance d'écritures de registre budgétaires de type de montant** autorise que le type de montant par défaut dans une écriture de registre budgétaire soit un type de montant autre qu'une dépense. La ligne d'écriture de registre budgétaire prend désormais comme valeurs par défaut les dépenses lorsque le type de compte principal est celui des dépenses ; elle prend comme valeur par défaut le produit lorsque le type de compte principal est celui des dépenses ; et prend comme valeur par défaut la dépense pour tous les autres types de comptes.

## <a name="using-workspaces-and-inquiry-pages-to-track-budget-vs-actuals"></a>Utilisation des espaces de travail et des pages de recherche effectuer le suivi du budget et des chiffres réels
Le responsable du budget peut consulter l'état actuel d'un budget dans l'espace de travail **Budgets comptables et prévisions**. Les onglets **Dépense supérieure au budget** et **Produit inférieur au budget** fournissent un aperçu rapide des combinaisons de dimensions financières dans lesquelles les cibles de budget ne sont pas atteintes ou approchent du seuil. Vous pouvez personnaliser le pourcentage de seuil budgétaire et les ensembles de dimensions financières utilisés sous ces onglets en cliquant sur **Configurer mon espace de travail**. Vous pouvez cliquer sur **Responsable de l'unité** pour afficher les collaborateurs responsables des combinaisons de dimensions financières spécifiques sélectionnées sous ces onglets. Par exemple, si vous constatez que le budget de dépenses du département des opérations va dépasser le seuil budgétaire, vous pouvez facilement rechercher et contacter le responsable du département pour discuter du problème. 

> [!NOTE] 
> Le champ **Responsable de département** de la page **Unités d'organisation** détermine quels responsables prennent en charge des combinaisons de dimensions financières spécifiques. Pour plus de détails sur les montants budgétaires/les montants réels, cliquez sur **En voir plus** dans la partie inférieure de l'onglet pour ouvrir la page de recherche **Budget et chiffres réels**. 

La page de recherche **Comparatif Réel/Budget** vous permet de zoomer sur les détails du budget par rapport aux montants réels. Sélectionnez une ligne sur la page de recherche, puis cliquez sur **Soldes de la période** pour afficher les montants du budget et les montants réels répartis sur plusieurs périodes fiscales. La page **Écritures de compte budgétaires** permet d'extraire les détails du montant du budget des écritures de registre budgétaires. La page **Écritures du journal des opérations diverses** affiche les écritures comptables incluses dans le montant **Chiffres réels** calculé. 

Une société qui utilise la fonctionnalité de planification budgétaire peut créer et utiliser les *prévisions budgétaires* dans l'espace de travail **Budgets comptables et prévisions**.



