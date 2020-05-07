---
title: Créer des contrats avancés pour la facturation en fonction de la progression
description: Cette rubrique explique comment créer des contrats de projet afin de pouvoir générer des factures pour les clients, en fonction d'un pourcentage de travail terminé.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282825"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a><span data-ttu-id="dcceb-103">Créer des contrats avancés pour la facturation en fonction de la progression</span><span class="sxs-lookup"><span data-stu-id="dcceb-103">Create advanced contracts for billing based on progress</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="dcceb-104">Cette rubrique explique comment créer des contrats de projet afin de pouvoir créer des factures pour les clients, en fonction d'un pourcentage de travail terminé.</span><span class="sxs-lookup"><span data-stu-id="dcceb-104">This topic explains how to create project contracts so that you can create invoices for customers, based on a percentage of completed work.</span></span> <span data-ttu-id="dcceb-105">Les montants de facture correspondant aux catégories de travail budgétisées définies pour le projet sont calculés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="dcceb-105">Invoice amounts are automatically calculated for the budget categories of work that you set up for a project.</span></span> <span data-ttu-id="dcceb-106">L'échéance des factures est définie lors de la négociation du contrat de projet avec le client.</span><span class="sxs-lookup"><span data-stu-id="dcceb-106">The invoice timing is set when you negotiate the project contract with the customer.</span></span>

<span data-ttu-id="dcceb-107">Utilisez les procédures de cette rubrique pour définir un contrat, un projet associé et les règles de facturation qui calculent les montants de la facture pour les catégories de travail budgétisées définies pour le projet.</span><span class="sxs-lookup"><span data-stu-id="dcceb-107">Use the procedures in this topic to set up a contract, an associated project, and the billing rules that calculate invoice amounts for the budget categories of work that you set up for the project.</span></span>

<span data-ttu-id="dcceb-108">Après la création du contrat et du projet, vous pouvez paramétrer les détails du projet.</span><span class="sxs-lookup"><span data-stu-id="dcceb-108">After you've created the contract and the project, you can set up the details of the project.</span></span> <span data-ttu-id="dcceb-109">Par exemple, vous pouvez définir les activités et affecter des collaborateurs au projet.</span><span class="sxs-lookup"><span data-stu-id="dcceb-109">For example, you can define activities and assign workers to the project.</span></span>

## <a name="example"></a><span data-ttu-id="dcceb-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="dcceb-110">Example</span></span>

<span data-ttu-id="dcceb-111">Votre organisation est une société de développement logiciel.</span><span class="sxs-lookup"><span data-stu-id="dcceb-111">Your organization is a software development firm.</span></span> <span data-ttu-id="dcceb-112">Vous avez convenu de développer un module de gestion des salaires, pour un montant total de 20 000 dollars américains (USD).</span><span class="sxs-lookup"><span data-stu-id="dcceb-112">You agree to develop a payroll accounting package for a customer for a total fee of 20,000 US dollars (USD).</span></span> <span data-ttu-id="dcceb-113">Votre organisation s'est engagée à facturer le client à mesure que certains pourcentages spécifiés du projet sont accomplis.</span><span class="sxs-lookup"><span data-stu-id="dcceb-113">Your organization agrees to invoice the customer as you complete specific percentages of the project.</span></span> <span data-ttu-id="dcceb-114">Vous définissez les catégories de projets suivantes pour le travail, afin de pouvoir les utiliser dans le processus de facturation :</span><span class="sxs-lookup"><span data-stu-id="dcceb-114">You set up the following project categories for the work, so that you can use them in the billing process:</span></span>

- <span data-ttu-id="dcceb-115">Consultance</span><span class="sxs-lookup"><span data-stu-id="dcceb-115">Consulting</span></span>
- <span data-ttu-id="dcceb-116">Mise en page</span><span class="sxs-lookup"><span data-stu-id="dcceb-116">Design</span></span>
- <span data-ttu-id="dcceb-117">Installation</span><span class="sxs-lookup"><span data-stu-id="dcceb-117">Installation</span></span>

<span data-ttu-id="dcceb-118">Vous paramétrez aussi des règles de facturation qui calculent automatiquement les montants à facturer pour le pourcentage de travail du projet réalisé dans chaque catégorie.</span><span class="sxs-lookup"><span data-stu-id="dcceb-118">You also set up billing rules that automatically calculate the invoice amounts for the percentage of project work that is completed in each category.</span></span>

<span data-ttu-id="dcceb-119">Le responsable du budget crée un budget pour les catégories de projet.</span><span class="sxs-lookup"><span data-stu-id="dcceb-119">The budget manager creates a budget for the project categories.</span></span> <span data-ttu-id="dcceb-120">La quantité de travail réalisé est automatiquement calculée sous forme d'un pourcentage du travail réel comparé aux montants budgétés.</span><span class="sxs-lookup"><span data-stu-id="dcceb-120">The amount of completed work is automatically calculated as a percentage of actual work in comparison to the budgeted amounts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dcceb-121">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="dcceb-121">Prerequisites</span></span>

<span data-ttu-id="dcceb-122">Avant de créer un projet qui utilise des règles de facturation, vous devez configurer les séquences de numéros pour les règles de facturation et un journal des frais utilisé pour valider la facturation par tranche.</span><span class="sxs-lookup"><span data-stu-id="dcceb-122">Before you create a project that uses billing rules, you must set up the number sequences for billing rules and a fee journal that is used to post progress billings.</span></span>

1. <span data-ttu-id="dcceb-123">Accédez à **Gestion de projets et comptabilité** \> **Paramétrage** \> **Paramètres de gestion de projets et de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-123">Go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>
2. <span data-ttu-id="dcceb-124">Sur la page **Paramètres de gestion de projet et de comptabilité**, sur l'onglet **Séquences de numéros**, définissez la séquence de numéros à utiliser lors de la création des règles de facturation.</span><span class="sxs-lookup"><span data-stu-id="dcceb-124">On the **Project management and accounting parameters** page, on the **Number sequences** tab, set up the number sequence that you want to use when billing rules are created.</span></span>
3. <span data-ttu-id="dcceb-125">Accédez à **Intégration dans Gestion de projets et comptabilité** \> **Journaux** \> **Frais**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-125">Go to **Project management and accounting** \> **Journals** \> **Fee**.</span></span>
4. <span data-ttu-id="dcceb-126">Sur la page **Journal des frais**, sélectionnez **Nouveau** et entrez le nom du journal.</span><span class="sxs-lookup"><span data-stu-id="dcceb-126">On the **Fee journal** page, select **New**, and enter the journal name.</span></span>

## <a name="create-a-contract-for-progress-billings"></a><span data-ttu-id="dcceb-127">Création d'un contrat basé sur des facturations par tranche</span><span class="sxs-lookup"><span data-stu-id="dcceb-127">Create a contract for progress billings</span></span>

<span data-ttu-id="dcceb-128">Cette procédure permet de créer un contrat de projet pour un projet à prix fixe.</span><span class="sxs-lookup"><span data-stu-id="dcceb-128">Use this procedure to create a project contract for a fixed-price project.</span></span> <span data-ttu-id="dcceb-129">Vous créez une facture de projet lorsque le travail terminé pour le projet atteint un pourcentage spécifié.</span><span class="sxs-lookup"><span data-stu-id="dcceb-129">You create a project invoice when the work that is completed on the project reaches a specified percentage.</span></span>

1. <span data-ttu-id="dcceb-130">Accédez à **Gestion et comptabilité des projets** \> **Projets** \> **Contrats de projets**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-130">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="dcceb-131">Dans la page **Contrats de projet**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-131">On the **Project contracts** page, select **New**.</span></span>
3. <span data-ttu-id="dcceb-132">Dans la boîte de dialogue **Nouveau contrat de projet**, sélectionnez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="dcceb-132">In the **New project contract** dialog box, set the following fields:</span></span>

    - <span data-ttu-id="dcceb-133">**Nom**</span><span class="sxs-lookup"><span data-stu-id="dcceb-133">**Name**</span></span>
    - <span data-ttu-id="dcceb-134">**Type de financement**</span><span class="sxs-lookup"><span data-stu-id="dcceb-134">**Funding type**</span></span>
    - <span data-ttu-id="dcceb-135">**Source de financement**</span><span class="sxs-lookup"><span data-stu-id="dcceb-135">**Funding source**</span></span>
    - <span data-ttu-id="dcceb-136">**Devise de vente** – Par défaut, cette devise est utilisée pour les factures client associées au contrat de projet.</span><span class="sxs-lookup"><span data-stu-id="dcceb-136">**Sales currency** – By default, this currency is used for customer invoices that are associated with the project contract.</span></span> <span data-ttu-id="dcceb-137">Toutefois, vous pouvez modifier la devise de vente sur une facture client spécifique.</span><span class="sxs-lookup"><span data-stu-id="dcceb-137">However, you can change the sales currency on a specific customer invoice.</span></span>

4. <span data-ttu-id="dcceb-138">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-138">Select **OK**.</span></span> <span data-ttu-id="dcceb-139">Les informations sont copiées dans l'en-tête de la page **Contrats de projet**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-139">The information is copied to the header of the **Project contracts** page.</span></span>
5. <span data-ttu-id="dcceb-140">Sur la page **Contrats de projet**, remplissez le reste des informations requises pour le projet.</span><span class="sxs-lookup"><span data-stu-id="dcceb-140">On the **Project contracts** page, fill in the rest of the required information for the project.</span></span>

## <a name="create-a-project-for-progress-billings"></a><span data-ttu-id="dcceb-141">Création d'un projet basé sur des facturations par tranche</span><span class="sxs-lookup"><span data-stu-id="dcceb-141">Create a project for progress billings</span></span>

<span data-ttu-id="dcceb-142">Suivez cette procédure pour créer un projet et d'éventuels sous-projets associés à un contrat de projet.</span><span class="sxs-lookup"><span data-stu-id="dcceb-142">Follow these steps to create a project and any subprojects that are associated with a project contract.</span></span>

1. <span data-ttu-id="dcceb-143">Accédez à **Gestion et comptabilité des projets** \> **Projets** \> **Tous les projets**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-143">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="dcceb-144">Sur la page **Tous les projets**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-144">On the **All projects** page, select **New**.</span></span>
3. <span data-ttu-id="dcceb-145">Dans la boîte de dialogue **Nouveau projet**, dans le champ **Type de projet**, sélectionnez **Temps et matériel**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-145">In the **New project** dialog box, in the **Project type** field, select **Time and material**.</span></span>
4. <span data-ttu-id="dcceb-146">Permet de sélectionner un groupe de projets.</span><span class="sxs-lookup"><span data-stu-id="dcceb-146">Select a project group.</span></span> <span data-ttu-id="dcceb-147">Un groupe de projets définit les informations de validation des projets affectés au groupe.</span><span class="sxs-lookup"><span data-stu-id="dcceb-147">A project group defines the posting information for the projects that are assigned to the group.</span></span>
5. <span data-ttu-id="dcceb-148">Sélectionnez **Créer un projet**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-148">Select **Create project**.</span></span>
6. <span data-ttu-id="dcceb-149">Une fois le projet créé, définissez la phase du projet sur **En cours**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-149">After the project is created, set the project stage to **In process**.</span></span>

## <a name="create-a-budget-for-a-project"></a><span data-ttu-id="dcceb-150">Création d'un budget pour le projet</span><span class="sxs-lookup"><span data-stu-id="dcceb-150">Create a budget for a project</span></span>

<span data-ttu-id="dcceb-151">Les catégories budgétisées permettent de calculer automatiquement les montants à facturer pour le pourcentage de travail réalisé dans chaque catégorie.</span><span class="sxs-lookup"><span data-stu-id="dcceb-151">Budget categories are used to automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="dcceb-152">Suivez ces étapes pour créer des catégories de budget pour les coûts estimés.</span><span class="sxs-lookup"><span data-stu-id="dcceb-152">Follow these steps to create budget categories for the estimated costs.</span></span>

1. <span data-ttu-id="dcceb-153">Accédez à **Gestion et comptabilité des projets** \> **Projets** \> **Tous les projets**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-153">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="dcceb-154">Sur la page **Tous les projets**, sélectionnez et ouvrez le projet souhaité.</span><span class="sxs-lookup"><span data-stu-id="dcceb-154">On the **All projects** page, select and open the project that you want.</span></span>
3. <span data-ttu-id="dcceb-155">Sur la page **Projets**, dans le volet Actions, sur l'onglet **Plan**, dans le groupe **Budget**, sélectionnez **Budget du projet**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-155">On the **Projects** page, on the Action Pane, on the **Plan** tab, in the **Budget** group, select **Project budget**.</span></span>
4. <span data-ttu-id="dcceb-156">Sur la page **Budget du projet**, entrez une estimation du coût pour chaque catégorie du projet.</span><span class="sxs-lookup"><span data-stu-id="dcceb-156">On the **Project budget** page, enter an estimated cost for each category in the project.</span></span>

## <a name="create-billing-rules-for-progress-billings"></a><span data-ttu-id="dcceb-157">Création de règles de facturation pour un contrat basé sur des facturations par tranche</span><span class="sxs-lookup"><span data-stu-id="dcceb-157">Create billing rules for progress billings</span></span>

1. <span data-ttu-id="dcceb-158">Accédez à **Gestion et comptabilité des projets** \> **Projets** \> **Contrats de projets**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-158">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="dcceb-159">Sur la page **Contrats de projet**, sélectionnez et ouvrez un contrat de projet.</span><span class="sxs-lookup"><span data-stu-id="dcceb-159">On the **Project contracts** page, select and open a project contract.</span></span>
3. <span data-ttu-id="dcceb-160">Sur la page du contrat de projet, sur l'organisateur **Règles de facturation**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-160">On the project contract page, on the **Billing rules** FastTab, select **Add**.</span></span>
4. <span data-ttu-id="dcceb-161">Sur la page **Règle de facturation**, dans le champ **Type de ligne**, sélectionnez **Progression**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-161">On the **Billing rule** page, in the **Line type** field, select **Progress**.</span></span>
5. <span data-ttu-id="dcceb-162">Dans l'organisateur **Détails de la ligne de règle de facturation**, dans le champ **Valeur du contrat**, entrez la valeur totale du contrat.</span><span class="sxs-lookup"><span data-stu-id="dcceb-162">On the **Billing rule line details** FastTab, in the **Contract value** field, enter the total value of the contract.</span></span>
6. <span data-ttu-id="dcceb-163">Dans le champ **Catégorie**, sélectionnez la catégorie dans laquelle valider la transaction de frais.</span><span class="sxs-lookup"><span data-stu-id="dcceb-163">In the **Category** field, select the category to post the fee transaction to.</span></span>
7. <span data-ttu-id="dcceb-164">Dans le champ **Projet**, sélectionnez le projet qui utilise cette règle de facturation.</span><span class="sxs-lookup"><span data-stu-id="dcceb-164">In the **Project** field, select the project that uses this billing rule.</span></span>
8. <span data-ttu-id="dcceb-165">Facultatif : Affectez la règle de facturation à d'autres projets.</span><span class="sxs-lookup"><span data-stu-id="dcceb-165">Optional: Assign the billing rule to additional projects.</span></span> <span data-ttu-id="dcceb-166">Sur l'organisateur **Projet**, dans la section **Projets disponibles**, sélectionnez un projet, puis cliquez sur le bouton fléché vers la droite pour ajouter le projet à la section **Projets sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="dcceb-166">On the **Project** FastTab, in the **Available projects** section, select a project, and then select the right arrow button to add the project to the **Selected projects** section.</span></span>
9. <span data-ttu-id="dcceb-167">Facultatif : Calculez le montant du pourcentage retenu par le client sur le paiement d'une facture.</span><span class="sxs-lookup"><span data-stu-id="dcceb-167">Optional: Calculate the percentage amount that the customer withholds from payments on an invoice.</span></span> <span data-ttu-id="dcceb-168">Dans l'organisateur **Conditions de rétention de paiement**, sélectionnez la source de financement, puis, dans le champ **Pourcentage de rétention**, entrez le pourcentage de rétention.</span><span class="sxs-lookup"><span data-stu-id="dcceb-168">On the **Payment retention terms** FastTab, select the funding source, and then, in the **Retention percentage** field, enter the retention percentage.</span></span>
10. <span data-ttu-id="dcceb-169">Répétez ces étapes pour créer d'autres règles de facturation pour le contrat de projet.</span><span class="sxs-lookup"><span data-stu-id="dcceb-169">Repeat these steps to create additional billing rules for the project contract.</span></span>
