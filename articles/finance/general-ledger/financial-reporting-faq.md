---
title: FAQ sur Financial Reporting
description: Cette rubrique répertorie les questions relatives aux états financiers qui ont été posées par d’autres utilisateurs.
author: jiwo
manager: tfehr
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3f9381f5b656d0cc0b46c8828b2ef9d024e296b0
ms.sourcegitcommit: 14785208d84b2c1efd30f140c52df35a2ccd1577
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/27/2021
ms.locfileid: "5070215"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="456fb-103">FAQ sur Financial Reporting</span><span class="sxs-lookup"><span data-stu-id="456fb-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="456fb-104">Cette rubrique répertorie les questions relatives aux états financiers qui ont été posées par d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="456fb-104">This topic lists questions related to financial reporting that other users have had.</span></span> 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="456fb-105">Comment restreindre l’accès à un état à l’aide de la sécurité de l’organigramme ?</span><span class="sxs-lookup"><span data-stu-id="456fb-105">How do I restrict access to a report using Tree security?</span></span>

<span data-ttu-id="456fb-106">Scénario : La société de démonstration USMF a un état Bilan et elle ne souhaite pas que tous les utilisateurs de Financial Reporting puissent l’afficher dans D365.</span><span class="sxs-lookup"><span data-stu-id="456fb-106">Scenario: The USMF demo company has a Balance sheet report that it doesn’t want all Financial reporting users to be able to view in D365.</span></span> <span data-ttu-id="456fb-107">Solution : Vous pouvez utiliser la sécurité de l’organigramme pour restreindre l’accès à un seul état afin que seuls certains utilisateurs puissent y accéder.</span><span class="sxs-lookup"><span data-stu-id="456fb-107">Solution: You can utilize Tree security to restrict access to a single report so that only certain users can access the report.</span></span> 

1.  <span data-ttu-id="456fb-108">Connectez-vous à Financial Reporter Report Designer</span><span class="sxs-lookup"><span data-stu-id="456fb-108">Log into Financial Reporter Report Designer</span></span>

2.  <span data-ttu-id="456fb-109">Créer une définition d’organigramme (Fichier | Nouveau | Définition d’organigramme) a.</span><span class="sxs-lookup"><span data-stu-id="456fb-109">Create a new Tree Definition (File | New | Tree Definition) a.</span></span>    <span data-ttu-id="456fb-110">Double-cliquez sur la ligne **Synthèse** dans la colonne **Sécurité d’unité**.</span><span class="sxs-lookup"><span data-stu-id="456fb-110">Double-click the **Summary** line in the **Unit Security** column.</span></span>
  <span data-ttu-id="456fb-111">i.</span><span class="sxs-lookup"><span data-stu-id="456fb-111">i.</span></span>    <span data-ttu-id="456fb-112">Cliquez sur Utilisateurs et groupes.</span><span class="sxs-lookup"><span data-stu-id="456fb-112">Click Users and Groups.</span></span>  
          <span data-ttu-id="456fb-113">1. Sélectionnez le groupe ou le/les utilisateurs qui souhaitent accéder à ce rapport.</span><span class="sxs-lookup"><span data-stu-id="456fb-113">1.    Select the User(s) or Group that would like to access this report.</span></span> 
          
<span data-ttu-id="456fb-114">[![écran de l’utilisateur](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span><span class="sxs-lookup"><span data-stu-id="456fb-114">[![user screen](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span></span>

<span data-ttu-id="456fb-115">[![écran de sécurité](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span><span class="sxs-lookup"><span data-stu-id="456fb-115">[![security screen](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span></span>

  <span data-ttu-id="456fb-116">b.</span><span class="sxs-lookup"><span data-stu-id="456fb-116">b.</span></span>    <span data-ttu-id="456fb-117">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="456fb-117">Click **Save**.</span></span>
  
<span data-ttu-id="456fb-118">[![bouton Enregistrer](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span><span class="sxs-lookup"><span data-stu-id="456fb-118">[![save button](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span></span>

3.  <span data-ttu-id="456fb-119">Dans votre définition d’état, ajoutez votre nouvelle définition d’organigramme</span><span class="sxs-lookup"><span data-stu-id="456fb-119">In your Report Definition add your new Tree Definition</span></span>

<span data-ttu-id="456fb-120">[![formulaire de définition d’organigramme](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span><span class="sxs-lookup"><span data-stu-id="456fb-120">[![tree definition form](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span></span>

<span data-ttu-id="456fb-121">A.</span><span class="sxs-lookup"><span data-stu-id="456fb-121">A.</span></span>  <span data-ttu-id="456fb-122">Dans la définition d’organigramme, cliquez sur Paramètres et sous « Sélection d’unité organisationnelle », cochez « Inclure toutes les unités »</span><span class="sxs-lookup"><span data-stu-id="456fb-122">While in the Tree Definition click on Setting and under “Reporting unit selection” check “Include all units”</span></span>

<span data-ttu-id="456fb-123">[![formulaire de sélection de l’unité organisationnelle](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span><span class="sxs-lookup"><span data-stu-id="456fb-123">[![reporting unit selection form](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span></span>

<span data-ttu-id="456fb-124">**Avant :** [![capture d’écran avant](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span><span class="sxs-lookup"><span data-stu-id="456fb-124">**Before:** [![before screenshot](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span></span>

<span data-ttu-id="456fb-125">**Après :** [![capture d’écran après](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span><span class="sxs-lookup"><span data-stu-id="456fb-125">**After:** [![after screenshot](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span></span>

<span data-ttu-id="456fb-126">Remarque : le message ci-dessus s’affiche car l’utilisateur n’a pas accès à cet état après avoir appliqué la Sécurité d’unité</span><span class="sxs-lookup"><span data-stu-id="456fb-126">Note: Reason for the above message is my user does not have access to that report after applying Unit Security</span></span>



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a><span data-ttu-id="456fb-127">Comment déterminer quels comptes ne correspondent pas à mes soldes dans D365 ?</span><span class="sxs-lookup"><span data-stu-id="456fb-127">How do I determine which account(s) do not matching my balances in D365?</span></span>

<span data-ttu-id="456fb-128">Lorsqu’un état ne correspond pas à vos attentes dans D365, voici quelques étapes à suivre pour identifier les comptes et les écarts qui posent problème.</span><span class="sxs-lookup"><span data-stu-id="456fb-128">When you have a report that doesn't match what you would expect in D365, here are some steps you could take to identify those accounts and the variances.</span></span> 

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="456fb-129">Dans Financial Reporter Report Designer</span><span class="sxs-lookup"><span data-stu-id="456fb-129">In Financial Reporter Report Designer</span></span>

1.  <span data-ttu-id="456fb-130">Créez une définition de ligne a.</span><span class="sxs-lookup"><span data-stu-id="456fb-130">Create a new Row Definition a.</span></span>    <span data-ttu-id="456fb-131">Cliquez sur Modifier | Insérer des lignes à partir de dimensions i.</span><span class="sxs-lookup"><span data-stu-id="456fb-131">Click Edit | Insert Rows from Dimensions i.</span></span>  <span data-ttu-id="456fb-132">Sélectionner MainAccount [![Écran Sélectionner compte principal_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span><span class="sxs-lookup"><span data-stu-id="456fb-132">Select MainAccount [![Select Main screen_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span></span>
    
    <span data-ttu-id="456fb-133">ii.</span><span class="sxs-lookup"><span data-stu-id="456fb-133">ii.</span></span> <span data-ttu-id="456fb-134">Cliquez sur Ok b.</span><span class="sxs-lookup"><span data-stu-id="456fb-134">Click Ok b.</span></span>    <span data-ttu-id="456fb-135">Enregistrez la définition de ligne</span><span class="sxs-lookup"><span data-stu-id="456fb-135">Save the Row Definition</span></span>

2.  <span data-ttu-id="456fb-136">Créer une nouvelle définition de colonne     [![Créer une nouvelle définition de colonne](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span><span class="sxs-lookup"><span data-stu-id="456fb-136">Create a new Column Definition     [![Create a new column definition](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span></span>

3.  <span data-ttu-id="456fb-137">Créez une définition d’état a.</span><span class="sxs-lookup"><span data-stu-id="456fb-137">Create a new Report Definition a.</span></span>    <span data-ttu-id="456fb-138">Cliquez sur Paramètres et décochez [![Formulaire de paramètres](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span><span class="sxs-lookup"><span data-stu-id="456fb-138">Click Settings and uncheck [![Settings form](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span></span>
   
4.  <span data-ttu-id="456fb-139">Générez l’état.</span><span class="sxs-lookup"><span data-stu-id="456fb-139">Generate the Report.</span></span> 

5.  <span data-ttu-id="456fb-140">Exportez l’état vers Excel.</span><span class="sxs-lookup"><span data-stu-id="456fb-140">Export the Report to Excel.</span></span>

### <a name="in-d365"></a><span data-ttu-id="456fb-141">Dans D365 :</span><span class="sxs-lookup"><span data-stu-id="456fb-141">In D365:</span></span> 
1.  <span data-ttu-id="456fb-142">Cliquez sur Comptabilité | Recherches et états | Balance comptable a.</span><span class="sxs-lookup"><span data-stu-id="456fb-142">Click General Ledger | Inquiries and Reports | Trial Balance a.</span></span>    <span data-ttu-id="456fb-143">Paramètres i.</span><span class="sxs-lookup"><span data-stu-id="456fb-143">Parameters i.</span></span>  <span data-ttu-id="456fb-144">Date de début : Début de l’exercice ii.</span><span class="sxs-lookup"><span data-stu-id="456fb-144">From Date: Start of Fiscal Year ii.</span></span> <span data-ttu-id="456fb-145">À ce jour : Date à laquelle vous avez généré l’état pour iii.</span><span class="sxs-lookup"><span data-stu-id="456fb-145">To Date: Date you generated the report for iii.</span></span>    <span data-ttu-id="456fb-146">Ensemble de dimensions financières « Compte principal défini » [![Formulaire de compte principal](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span><span class="sxs-lookup"><span data-stu-id="456fb-146">Financial Dimension Set “Main Account set” [![Main Account Form](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span></span>
      
  <span data-ttu-id="456fb-147">b.</span><span class="sxs-lookup"><span data-stu-id="456fb-147">b.</span></span>    <span data-ttu-id="456fb-148">Cliquez sur Calculer</span><span class="sxs-lookup"><span data-stu-id="456fb-148">Click Calculate</span></span>

2.  <span data-ttu-id="456fb-149">Exporter l’état vers Excel</span><span class="sxs-lookup"><span data-stu-id="456fb-149">Export the report to Excel</span></span>

<span data-ttu-id="456fb-150">Vous devriez maintenant pouvoir copier les données de l’état Excel États financiers et de l’état Balance comptable D365 et comparer les colonnes « Solde de clôture ».</span><span class="sxs-lookup"><span data-stu-id="456fb-150">You should now be able to copy the data from the FR Excel Report and to the D365 Trial Balance report and compare the “Closing Balance” columns.</span></span>
