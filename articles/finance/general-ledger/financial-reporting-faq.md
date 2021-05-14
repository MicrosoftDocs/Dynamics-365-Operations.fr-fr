---
title: FAQ sur les états financiers
description: Cette rubrique répertorie les questions relatives aux états financiers qui ont été posées par d’autres utilisateurs.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923023"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="722ab-103">FAQ sur les états financiers</span><span class="sxs-lookup"><span data-stu-id="722ab-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="722ab-104">Cette rubrique fournit des réponses aux questions fréquemment posées sur les états financiers.</span><span class="sxs-lookup"><span data-stu-id="722ab-104">This topic provides answers to frequently asked questions about financial reporting.</span></span> 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="722ab-105">Comment restreindre l’accès à un état à l’aide de la sécurité de l’organigramme ?</span><span class="sxs-lookup"><span data-stu-id="722ab-105">How do I restrict access to a report using tree security?</span></span>

<span data-ttu-id="722ab-106">L’exemple suivant montre comment restreindre l’accès à un état à l’aide de la sécurité de l’organigramme.</span><span class="sxs-lookup"><span data-stu-id="722ab-106">The following example shows how to restrict access to a report using tree security.</span></span>

<span data-ttu-id="722ab-107">La société de démonstration USMF a un rapport de bilan auquel tous les utilisateurs d’états financiers ne devraient pas avoir accès.</span><span class="sxs-lookup"><span data-stu-id="722ab-107">The USMF demo company has a Balance sheet report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="722ab-108">Vous pouvez utiliser la sécurité de l’organigramme pour restreindre l’accès à un seul état afin que seuls certains utilisateurs puissent y accéder.</span><span class="sxs-lookup"><span data-stu-id="722ab-108">To restrict access, you can use tree security to restrict access to a single report so that only certain users can access the report.</span></span> <span data-ttu-id="722ab-109">Suivez ces étapes pour restreindre l’accès :</span><span class="sxs-lookup"><span data-stu-id="722ab-109">Follow these steps to restrict access:</span></span> 

1. <span data-ttu-id="722ab-110">Connectez-vous à Financial Reporter Report Designer.</span><span class="sxs-lookup"><span data-stu-id="722ab-110">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="722ab-111">Créez une définition d’arborescence.</span><span class="sxs-lookup"><span data-stu-id="722ab-111">Create a new tree definition.</span></span> <span data-ttu-id="722ab-112">Allez dans **Fichier > Nouveau > Définition d’organigramme**.</span><span class="sxs-lookup"><span data-stu-id="722ab-112">Go to **File > New > Tree Definition**.</span></span>
3. <span data-ttu-id="722ab-113">Double-cliquez sur la ligne **Synthèse** dans la colonne **Sécurité d’unité**.</span><span class="sxs-lookup"><span data-stu-id="722ab-113">Double-click the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="722ab-114">Cliquez sur **Utilisateurs et groupes**.</span><span class="sxs-lookup"><span data-stu-id="722ab-114">Select **Users and Groups**.</span></span>  
5. <span data-ttu-id="722ab-115">Sélectionnez les utilisateurs ou les groupes qui doivent accéder à cet état.</span><span class="sxs-lookup"><span data-stu-id="722ab-115">Select the users or groups that need access to this report.</span></span> 
6. <span data-ttu-id="722ab-116">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="722ab-116">Select **Save**.</span></span>
7. <span data-ttu-id="722ab-117">Ajoutez votre nouvelle définition d’organigramme dans la définition d’état.</span><span class="sxs-lookup"><span data-stu-id="722ab-117">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="722ab-118">Dans la définition d’organigramme, sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="722ab-118">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="722ab-119">Sous **Sélection d’unité organisationnelle**, sélectionnez **Inclure toutes les unités**.</span><span class="sxs-lookup"><span data-stu-id="722ab-119">Under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a><span data-ttu-id="722ab-120">Comment identifier les comptes qui ne correspondent pas à mes soldes ?</span><span class="sxs-lookup"><span data-stu-id="722ab-120">How do I identify which accounts do not match my balances?</span></span>

<span data-ttu-id="722ab-121">Lorsqu’un état contient des soldes qui ne correspondent pas, voici quelques étapes à suivre pour identifier chacun de ces comptes et les écarts qui posent problème.</span><span class="sxs-lookup"><span data-stu-id="722ab-121">If you have a report that doesn't have matching balances, here are some steps you can take to identify each of the accounts and variances.</span></span> 

<span data-ttu-id="722ab-122">**Financial Reporter Report Designer**</span><span class="sxs-lookup"><span data-stu-id="722ab-122">**Financial Reporter Report Designer**</span></span>
1. <span data-ttu-id="722ab-123">Dans Financial Reporter Report Designer, créez une nouvelle définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="722ab-123">In Financial Reporter Report Designer, create a new row definition.</span></span> 
2. <span data-ttu-id="722ab-124">Cliquez sur **Modifier > Insérer des lignes à partir de dimensions**.</span><span class="sxs-lookup"><span data-stu-id="722ab-124">Select **Edit > Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="722ab-125">Cliquez sur **MainAccount**.</span><span class="sxs-lookup"><span data-stu-id="722ab-125">Select **MainAccount**.</span></span>  
4. <span data-ttu-id="722ab-126">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="722ab-126">Select **OK**.</span></span>
5. <span data-ttu-id="722ab-127">Enregistrez la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="722ab-127">Save the row definition.</span></span>
6. <span data-ttu-id="722ab-128">Créer une définition de colonne</span><span class="sxs-lookup"><span data-stu-id="722ab-128">Create a new column definition</span></span>
7. <span data-ttu-id="722ab-129">Créez une définition d’état.</span><span class="sxs-lookup"><span data-stu-id="722ab-129">Create a new report definition.</span></span>
8. <span data-ttu-id="722ab-130">Sélectionnez **Paramètres** et décochez cette option.</span><span class="sxs-lookup"><span data-stu-id="722ab-130">Select **Settings** and unmark this option.</span></span>  
9. <span data-ttu-id="722ab-131">Générez l’état.</span><span class="sxs-lookup"><span data-stu-id="722ab-131">Generate the report.</span></span> 
10. <span data-ttu-id="722ab-132">Exportez l’état vers Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="722ab-132">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="722ab-133">**Dynamics 365 Finance**</span><span class="sxs-lookup"><span data-stu-id="722ab-133">**Dynamics 365 Finance**</span></span> 
1. <span data-ttu-id="722ab-134">Dans Dynamics 365 Finance, allez dans **Comptabilité > Recherches et états > Balance comptable**.</span><span class="sxs-lookup"><span data-stu-id="722ab-134">In Dynamics 365 Finance, go to **General Ledger > Inquiries and Reports > Trial Balance**.</span></span>
2. <span data-ttu-id="722ab-135">Définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="722ab-135">Set the following parameters:</span></span>
   - <span data-ttu-id="722ab-136">**Date de début** : Saisissez le début de l’année fiscale.</span><span class="sxs-lookup"><span data-stu-id="722ab-136">**From Date** - Enter the start of the fiscal year.</span></span>
   - <span data-ttu-id="722ab-137">**À ce jour** : Saisissez la date pour laquelle vous générez l’état.</span><span class="sxs-lookup"><span data-stu-id="722ab-137">**To Date** - Enter the date you are generating the report for.</span></span>
   - <span data-ttu-id="722ab-138">**Dimension financière** : Définissez ce champ sur **Compte principal défini**.</span><span class="sxs-lookup"><span data-stu-id="722ab-138">**Financial Dimension** - Set this field to **Main Account set**.</span></span>
 3. <span data-ttu-id="722ab-139">Sélectionnez **Calculer**.</span><span class="sxs-lookup"><span data-stu-id="722ab-139">Select **Calculate**.</span></span>
 4. <span data-ttu-id="722ab-140">Exportez l’état vers Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="722ab-140">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="722ab-141">Vous devriez maintenant pouvoir copier les données de l’état Excel Financial Reporter et de l’état Balance comptable et comparer les colonnes **Solde de clôture**.</span><span class="sxs-lookup"><span data-stu-id="722ab-141">You should now be able to copy the data from the Financial Reporter Excel report to the Trial Balance report, so you can compare the **Closing Balance** columns.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]