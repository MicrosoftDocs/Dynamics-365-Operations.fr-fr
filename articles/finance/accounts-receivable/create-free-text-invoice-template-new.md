---
title: Créer un modèle de facture financière
description: Cette procédure décrit comment créer un modèle de facture financière.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee4fff7b148396faecef899c7a75365d3e1f47f3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991159"
---
# <a name="create-a-free-text-invoice-template"></a><span data-ttu-id="ab0f8-103">Créer un modèle de facture financière</span><span class="sxs-lookup"><span data-stu-id="ab0f8-103">Create a free text invoice template</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ab0f8-104">Pour cette procédure, utilisez la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-104">For this walkthrough, use the USMF demo company.</span></span> <span data-ttu-id="ab0f8-105">Cette procédure est destinée à l’utilisateur chargé de gérer et de traiter des factures de comptes clients.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-105">This procedure is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

## <a name="create-a-template"></a><span data-ttu-id="ab0f8-106">Créer un modèle</span><span class="sxs-lookup"><span data-stu-id="ab0f8-106">Create a template</span></span>

1. <span data-ttu-id="ab0f8-107">Accédez à Comptabilité client > Factures > Factures récurrentes > Modèles de facture financière.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-107">Go to Accounts receivable > Invoices > Recurring invoices > Free text invoice templates.</span></span>
    * <span data-ttu-id="ab0f8-108">Cet écran permet de créer des modèles de facture financière pouvant inclure des lignes de facture, des frais, un modèle de répartition comptable ainsi que des informations de compte général.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-108">Use this form to create free text invoice templates that can include invoice lines, charges, an accounting distribution template, and ledger account information.</span></span>  
2. <span data-ttu-id="ab0f8-109">Cliquez sur Nouveau pour créer un modèle de facture financière.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-109">Click 'New' to create a new free text invoice template.</span></span>
3. <span data-ttu-id="ab0f8-110">Tapez une valeur dans le champ Nom de modèle.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-110">In the Template name field, type a value.</span></span>
    * <span data-ttu-id="ab0f8-111">« Nom de modèle » identifie un modèle de facture financière de façon unique.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-111">‘Template name’ uniquely identifies a free text invoice template.</span></span> <span data-ttu-id="ab0f8-112">Deux modèles ne peuvent pas avoir le même « Nom de modèle ».</span><span class="sxs-lookup"><span data-stu-id="ab0f8-112">No two templates can have the same ‘Template name’.</span></span>  
4. <span data-ttu-id="ab0f8-113">Dans le champ Description, entrez la description du groupe de modèles.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-113">In the Description field, enter a description of the template.</span></span>
5. <span data-ttu-id="ab0f8-114">Développez l’onglet Lignes de facture.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-114">Expand the Invoice lines tab.</span></span>
6. <span data-ttu-id="ab0f8-115">Dans le champ Description, entrez la description de la ligne de facture.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-115">In the Description field, enter a description of the invoice line.</span></span>
7. <span data-ttu-id="ab0f8-116">Dans le champ Compte principal, sélectionnez un compte de produit.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-116">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="ab0f8-117">Vous pouvez sélectionner le compte de transactions de contrepartie d’un crédit client pour le montant total de la facture dans la page Profils de validation client.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-117">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
8. <span data-ttu-id="ab0f8-118">Dans le champ Groupe de taxe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-118">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ab0f8-119">Le groupe de taxe pour la ligne de facture actuelle correspond au groupe de taxe par défaut associé au compte client.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-119">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
9. <span data-ttu-id="ab0f8-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-120">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="ab0f8-121">Dans le champ Groupe de taxe d’article, sélectionnez le groupe de taxe d’article à utiliser pour la ligne de facture actuelle.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-121">In the Item tax group field, select the item sales tax group for the current invoice line.</span></span>
11. <span data-ttu-id="ab0f8-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="ab0f8-123">Dans le champ Prix unitaire, entrez ou affichez le prix par unité pour la ligne de facture.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-123">In the Unit price field, enter or view the price per unit for the invoice line</span></span>
    * <span data-ttu-id="ab0f8-124">Ce montant est automatiquement multiplié par la valeur indiquée dans le champ Quantité afin de déterminer le montant de la ligne de facture.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-124">This amount is multiplied by the Quantity field to determine the invoice line amount.</span></span>  
13. <span data-ttu-id="ab0f8-125">Ajoutez une nouvelle ligne au modèle de facture financière.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-125">Add a new line to free text invoice template.</span></span>
14. <span data-ttu-id="ab0f8-126">Dans le champ Description, entrez la description de la ligne de facture.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-126">In the Description field, enter a description of the invoice line.</span></span>
15. <span data-ttu-id="ab0f8-127">Dans le champ Compte principal, sélectionnez un compte de produit.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-127">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="ab0f8-128">Vous pouvez sélectionner le compte de transactions de contrepartie d’un crédit client pour le montant total de la facture dans la page Profils de validation client.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-128">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
16. <span data-ttu-id="ab0f8-129">Dans le champ Groupe de taxe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-129">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ab0f8-130">Le groupe de taxe pour la ligne de facture actuelle correspond au groupe de taxe par défaut associé au compte client.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-130">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
17. <span data-ttu-id="ab0f8-131">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="ab0f8-132">Dans le champ Groupes de taxe d’article : cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ab0f8-133">Groupe de taxe d’article pour la ligne de facture actuelle.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-133">The item sales tax group for the current invoice line.</span></span>  
19. <span data-ttu-id="ab0f8-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-134">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="ab0f8-135">Entrez ou affichez le nombre d’unités pour la ligne de facture.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-135">Enter or view the number of units for the invoice line</span></span>
    * <span data-ttu-id="ab0f8-136">Ce nombre est multiplié par la valeur indiquée dans le champ Prix unitaire afin de déterminer le montant de la ligne de facture.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-136">This number is multiplied by the value in the Unit price field to determine the invoice line amount.</span></span>  
21. <span data-ttu-id="ab0f8-137">Permet d’entrer ou d’afficher le prix par unité pour la ligne de facture.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-137">Enter or view the price per unit for the invoice line.</span></span> 
    * <span data-ttu-id="ab0f8-138">Ce montant est multiplié par la valeur indiquée dans le champ Quantité afin de déterminer le montant de la ligne de facture.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-138">This amount is multiplied by the value in the Quantity field to determine the invoice line amount.</span></span>  
22. <span data-ttu-id="ab0f8-139">Affichez et modifiez les répartitions comptables pour une ligne individuelle et toutes les lignes enfants.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-139">View and modify the accounting distributions for an individual line and any child lines.</span></span>
    * <span data-ttu-id="ab0f8-140">Les répartitions comptables définissent la façon dont un montant sera pris en compte, par exemple, la manière dont le produit, la taxe ou les frais seront reportés sur une facture financière.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-140">Accounting distributions define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span>  
23. <span data-ttu-id="ab0f8-141">Mettez à jour les répartitions comptables pour la ligne de facture sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-141">Update the accounting distributions for the selected invoice line.</span></span>
24. <span data-ttu-id="ab0f8-142">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-142">Click Close.</span></span>

## <a name="save-a-free-text-invoice-as-a-template"></a><span data-ttu-id="ab0f8-143">Enregistrer une facture financière comme modèle</span><span class="sxs-lookup"><span data-stu-id="ab0f8-143">Save a free text invoice as a template</span></span>
<span data-ttu-id="ab0f8-144">Vous pouvez également enregistrer une facture financière existante comme modèle.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-144">You can also save an existing free text invoice as a template.</span></span> <span data-ttu-id="ab0f8-145">Lorsque vous sélectionnez Enregistrer dans le modèle sous l’onglet Facture, entrez un nom et une description pour le modèle.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-145">When you select Save to template from the Invoice tab, provide a name and a description for the template.</span></span> <span data-ttu-id="ab0f8-146">Si un modèle portant le nom existe déjà, une notification s’affiche pour indiquer qu’un modèle portant ce nom existe déjà.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-146">If a template with the name already exists, you will see a notification that a template with that name already exists.</span></span> <span data-ttu-id="ab0f8-147">Vous pouvez toujours cliquer sur OK pour le remplacer.</span><span class="sxs-lookup"><span data-stu-id="ab0f8-147">You can still click on Ok to replace it.</span></span> 
