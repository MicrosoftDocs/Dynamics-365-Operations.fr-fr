---
title: "Intégration pour les accords de service et les projets"
description: "Lorsque vous utilisez des accords de service et des lignes d'accord de service, vous utilisez les données paramétrées dans les zones du module Gestion et comptabilité des projets."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 9f2640eae299411d633c68795bc16883dbb5eeaf
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="integration-for-service-agreements-and-projects"></a><span data-ttu-id="71a1a-103">Intégration pour les accords de service et les projets</span><span class="sxs-lookup"><span data-stu-id="71a1a-103">Integration for service agreements and projects</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="71a1a-104">Lorsque vous utilisez des accords de service et des lignes d'accord de service, vous utilisez les données paramétrées dans les zones suivantes du module **Gestion et comptabilité des projets**.</span><span class="sxs-lookup"><span data-stu-id="71a1a-104">When you work with service agreements and service agreement lines, you use data that is set up in the following areas in **Project management and accounting**.</span></span>

## <a name="project-prices"></a><span data-ttu-id="71a1a-105">Prix du projet</span><span class="sxs-lookup"><span data-stu-id="71a1a-105">Project prices</span></span>

<span data-ttu-id="71a1a-106">Les prix de revient et de vente d'une transaction d'accord de service sont issus du paramétrage du prix de revient qui s'applique au projet associé à l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="71a1a-106">The cost and the sales price for a service agreement transaction are derived from the cost price setup that applies to the project that is attached to the service agreement.</span></span> <span data-ttu-id="71a1a-107">Vous pouvez les paramétrer par projet, employé ou catégorie.</span><span class="sxs-lookup"><span data-stu-id="71a1a-107">Cost and sales prices can be set up by project, employee, and category.</span></span> 

## <a name="project-validation"></a><span data-ttu-id="71a1a-108">Contrôle de projet</span><span class="sxs-lookup"><span data-stu-id="71a1a-108">Project validation</span></span>

<span data-ttu-id="71a1a-109">Les projets, employés et catégories disponibles sur une ligne d'accord de service peuvent être limités par le paramétrage de contrôle dans **Gestion et comptabilité des projets**.</span><span class="sxs-lookup"><span data-stu-id="71a1a-109">The projects, employees, and categories that are available for selection on a service agreement line can be limited by the validation setup in **Project management and accounting**.</span></span> <span data-ttu-id="71a1a-110">À l'aide de ce paramétrage, vous pouvez combiner des employés, des projets et des catégories pour l'accès de contrôle.</span><span class="sxs-lookup"><span data-stu-id="71a1a-110">By using the validation setup, you can combine employees, projects, and categories for control access.</span></span> 

## <a name="project-line-properties"></a><span data-ttu-id="71a1a-111">Propriétés de ligne de projet</span><span class="sxs-lookup"><span data-stu-id="71a1a-111">Project line properties</span></span>

<span data-ttu-id="71a1a-112">Une propriété de ligne est entrée automatiquement pour une ligne d'accord de service.</span><span class="sxs-lookup"><span data-stu-id="71a1a-112">A line property is entered automatically for a service agreement line.</span></span>

<span data-ttu-id="71a1a-113">Les propriétés de ligne sont créées dans l'écran **Propriétés de ligne** dans **Gestion et comptabilité des projets**.</span><span class="sxs-lookup"><span data-stu-id="71a1a-113">Line properties are created in the **Line properties** form in **Project management and accounting**.</span></span> <span data-ttu-id="71a1a-114">La propriété de ligne entrée sur un accord de service est associée au projet sélectionné pour l'accord de service et par conséquent héritée par la ligne d'accord de service.</span><span class="sxs-lookup"><span data-stu-id="71a1a-114">The line property that is entered on a service agreement is attached to the project that is selected for the service agreement and inherited subsequently by the service agreement line.</span></span> 

## <a name="default-offset-accounts"></a><span data-ttu-id="71a1a-115">Comptes de contrepartie par défaut</span><span class="sxs-lookup"><span data-stu-id="71a1a-115">Default offset accounts</span></span>

<span data-ttu-id="71a1a-116">Si vous entrez une transaction de dépense, un compte de contrepartie par défaut pour la dépense est sélectionné automatiquement pour cette transaction.</span><span class="sxs-lookup"><span data-stu-id="71a1a-116">If you enter an expense transaction, a default expense offset account is selected automatically for the transaction.</span></span> <span data-ttu-id="71a1a-117">Le compte de dépenses par défaut est paramétré pour le projet associé à l'accord de service en cours.</span><span class="sxs-lookup"><span data-stu-id="71a1a-117">The default expense account is set up for the project that is attached to the current service agreement.</span></span>

## <a name="project-categories"></a><span data-ttu-id="71a1a-118">Catégories du projet</span><span class="sxs-lookup"><span data-stu-id="71a1a-118">Project categories</span></span>

<span data-ttu-id="71a1a-119">Les catégories disponibles pour les lignes d'accord de service sont paramétrées dans l'écran **Catégories de projets** dans **Gestion et comptabilité des projets**.</span><span class="sxs-lookup"><span data-stu-id="71a1a-119">The categories that are available for service agreement lines are set up in the **Project categories** form in **Project management and accounting**.</span></span> 

> [!NOTE]
> <P><span data-ttu-id="71a1a-120">Les catégories dont la case à cocher <STRONG>Actif/active dans les journaux</STRONG> est activée sous l'onglet <STRONG>Projet</STRONG> de l'écran <STRONG>Catégories de projets</STRONG> sont disponibles pour sélection.</span><span class="sxs-lookup"><span data-stu-id="71a1a-120">Categories that have the <STRONG>Active in journals</STRONG> check box selected on the <STRONG>Project</STRONG> tab in the <STRONG>Project categories</STRONG> form are available for selection.</span></span> <span data-ttu-id="71a1a-121">Toutefois, si la case à cocher <STRONG>Catégories inactives</STRONG> est activée sous l'onglet <STRONG>Journaux</STRONG> de l'écran <STRONG>Paramètres de gestion et comptabilité des projets</STRONG>, toutes les catégories sont disponibles pour sélection.</span><span class="sxs-lookup"><span data-stu-id="71a1a-121">However, if the <STRONG>Inactive categories</STRONG> check box is selected on the <STRONG>Journals</STRONG> tab in the <STRONG>Project management and accounting parameters</STRONG> form, all categories are available for selection.</span></span></P>

## <a name="project-parameters"></a><span data-ttu-id="71a1a-122">Paramètres de projet</span><span class="sxs-lookup"><span data-stu-id="71a1a-122">Project parameters</span></span>

<span data-ttu-id="71a1a-123">Si le champ **Collaborateurs dont le contrat est terminé** sous l'onglet **Journaux** de l'écran **Paramètres de gestion et comptabilité des projets** est sélectionné, vous pouvez sélectionner des employés inactifs et des employés actifs dans les écrans **Accords de service** et **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="71a1a-123">If the **Terminated workers** field on the **Journals** tab in the **Project management and accounting parameters** form is selected, you can select inactive employees and active employees in the **Service agreements** and **Service orders** forms.</span></span>

<span data-ttu-id="71a1a-124">Vous pouvez également activer les champs **Date de début** et **Date de fin** sous l'onglet **Projet** de l'écran **Commandes de service** pour entrer les heures de début et de fin dans les lignes de commande de service.</span><span class="sxs-lookup"><span data-stu-id="71a1a-124">Also, you can enable the **Start time** and **End time** fields on the **Project** tab in the **Service orders** form to enter starting and ending times on service order lines.</span></span>

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a><span data-ttu-id="71a1a-125">Activation de la fonctionnalité d'heures de début et de fin pour les commandes de service</span><span class="sxs-lookup"><span data-stu-id="71a1a-125">Enable the starting and ending time feature for service orders</span></span>

1.  <span data-ttu-id="71a1a-126">Cliquez sur **Gestion et comptabilité des projets** \> **Paramétrage** \> **Paramètres de gestion et comptabilité des projets**.</span><span class="sxs-lookup"><span data-stu-id="71a1a-126">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="71a1a-127">Cliquez sur l'onglet **Journaux**, puis activez la case à cocher **Afficher les heures de début/fin**.</span><span class="sxs-lookup"><span data-stu-id="71a1a-127">Click the **Journals** tab, and then select the **Show start/end times** check box.</span></span>

3.  <span data-ttu-id="71a1a-128">Cliquez sur **Gestion et comptabilité des projets** \> **Paramétrage** \> **Journaux** \> **Noms de journal**.</span><span class="sxs-lookup"><span data-stu-id="71a1a-128">Click **Project management and accounting** \> **Setup** \> **Journals** \> **Journal names**.</span></span>

4.  <span data-ttu-id="71a1a-129">Sélectionnez le nom de journal associé à la commande de service.</span><span class="sxs-lookup"><span data-stu-id="71a1a-129">Select the journal name that is attached to the service order.</span></span>

5.  <span data-ttu-id="71a1a-130">Cliquez sur l'onglet **Général**, puis activez la case à cocher **Afficher les heures de début/fin**.</span><span class="sxs-lookup"><span data-stu-id="71a1a-130">Click the **General** tab, and then select the **Show start/end times** check box.</span></span>


> [!NOTE]
> <P><span data-ttu-id="71a1a-131">Sélectionnez le nom de journal pour la commande de service dans le champ <STRONG>Heure</STRONG> sous l'onglet <STRONG>Journaux</STRONG> de l'écran <STRONG>Paramètres de gestion des services</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="71a1a-131">Select the journal name for the service order in the <STRONG>Hour</STRONG> field on the <STRONG>Journals</STRONG> tab in the <STRONG>Service management parameters</STRONG> form.</span></span></P>






