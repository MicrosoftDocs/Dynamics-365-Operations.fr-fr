--- 
title: "Rechercher ou résoudre les exceptions"
description: "Les stratégies de facture fournisseur sont exécutées lorsque vous validez une facture fournisseur à l'aide de la page Facture fournisseur et lorsque vous ouvrez la page Violations de stratégie de la facture fournisseur."
author: abruer
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: eb539d207906560eaf6f70ffea6ed6f21f003af0
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---
# <a name="research-or-resolve-exceptions"></a><span data-ttu-id="8b295-103">Rechercher ou résoudre les exceptions</span><span class="sxs-lookup"><span data-stu-id="8b295-103">Research or resolve exceptions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8b295-104">Les stratégies de facture fournisseur sont exécutées lorsque vous validez une facture fournisseur à l'aide de la page Facture fournisseur et lorsque vous ouvrez la page Violations de stratégie de la facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="8b295-104">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="8b295-105">Vous pouvez également configurer le workflow de facture fournisseur de manière à exécuter des stratégies de facture fournisseur chaque fois que vous envoyez une facture dans le workflow.</span><span class="sxs-lookup"><span data-stu-id="8b295-105">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

<span data-ttu-id="8b295-106">Les stratégies de facture fournisseur ne s'appliquent pas aux factures créées dans le registre des factures ou dans le journal des factures.</span><span class="sxs-lookup"><span data-stu-id="8b295-106">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span> 

<span data-ttu-id="8b295-107">Le contrôle du rapprochement de factures ne fait pas appel aux stratégies de facture fournisseur. Au lieu de cela, il est paramétré sur la page Paramètres de la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="8b295-107">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>

<span data-ttu-id="8b295-108">La société fictive USMF sert d'exemple dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="8b295-108">This recording uses the USMF demo company.</span></span> <span data-ttu-id="8b295-109">Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable.</span><span class="sxs-lookup"><span data-stu-id="8b295-109">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="8b295-110">Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8b295-110">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="8b295-111">Préparation de la création des stratégies de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="8b295-111">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="8b295-112">Accédez à Comptabilité fournisseur > Paramétrage > Paramètres de la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="8b295-112">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="8b295-113">Cliquez sur l'onglet Contrôle de la facture.</span><span class="sxs-lookup"><span data-stu-id="8b295-113">Click the Invoice validation tab.</span></span>
3. <span data-ttu-id="8b295-114">Activez ou désactivez la case à cocher Mettre à jour automatiquement le statut d'en-tête des factures.</span><span class="sxs-lookup"><span data-stu-id="8b295-114">Select or clear the Automatically update invoice header status check box.</span></span>
4. <span data-ttu-id="8b295-115">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="8b295-115">Click OK.</span></span>
5. <span data-ttu-id="8b295-116">Sélectionnez une option dans le champ Valider la facture avec les non-correspondances.</span><span class="sxs-lookup"><span data-stu-id="8b295-116">In the Post invoice with discrepancies field, select an option.</span></span>
6. <span data-ttu-id="8b295-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8b295-117">Close the page.</span></span>
7. <span data-ttu-id="8b295-118">Accédez à Comptabilité fournisseur > Paramétrage de la stratégie > Stratégies de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="8b295-118">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
8. <span data-ttu-id="8b295-119">Cliquez sur Paramètres.</span><span class="sxs-lookup"><span data-stu-id="8b295-119">Click Parameters.</span></span>
9. <span data-ttu-id="8b295-120">Cliquez sur btnAdd.</span><span class="sxs-lookup"><span data-stu-id="8b295-120">Click btnAdd.</span></span>
10. <span data-ttu-id="8b295-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8b295-121">Close the page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="8b295-122">Création de types de règles de stratégie pour les factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="8b295-122">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="8b295-123">Accédez à Comptabilité fournisseur > Paramétrage de la stratégie > Types de règles de stratégie de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="8b295-123">Go to Accounts payable > Policy setup > Vendor invoice policy rule types.</span></span>
2. <span data-ttu-id="8b295-124">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8b295-124">Click New.</span></span>
3. <span data-ttu-id="8b295-125">Tapez une valeur dans le champ Nom de la règle.</span><span class="sxs-lookup"><span data-stu-id="8b295-125">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="8b295-126">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8b295-126">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8b295-127">Dans le champ Nom de la requête, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="8b295-127">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="8b295-128">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="8b295-128">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="8b295-129">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8b295-129">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8b295-130">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8b295-130">Click Save.</span></span>
9. <span data-ttu-id="8b295-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8b295-131">Close the page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="8b295-132">Définition d'une stratégie de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="8b295-132">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="8b295-133">Accédez à Comptabilité fournisseur > Paramétrage de la stratégie > Stratégies de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="8b295-133">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
2. <span data-ttu-id="8b295-134">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8b295-134">Click New.</span></span>
3. <span data-ttu-id="8b295-135">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="8b295-135">In the Name field, type a value.</span></span>
4. <span data-ttu-id="8b295-136">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8b295-136">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8b295-137">Développez ou réduisez la section Organisations de stratégie.</span><span class="sxs-lookup"><span data-stu-id="8b295-137">Expand or collapse the Policy organizations section.</span></span>
6. <span data-ttu-id="8b295-138">Dans l'arborescence, sélectionnez Contoso Entertainment System USA.</span><span class="sxs-lookup"><span data-stu-id="8b295-138">In the tree, select 'Contoso Entertainment System USA'.</span></span>
7. <span data-ttu-id="8b295-139">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="8b295-139">Click Add.</span></span>
8. <span data-ttu-id="8b295-140">Développez ou réduisez la section Règles de stratégie.</span><span class="sxs-lookup"><span data-stu-id="8b295-140">Expand or collapse the Policy rules section.</span></span>
9. <span data-ttu-id="8b295-141">Cliquez sur Créer une règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="8b295-141">Click Create policy rule.</span></span>
10. <span data-ttu-id="8b295-142">Tapez une valeur dans le champ Description de la règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="8b295-142">In the Policy rule description field, type a value.</span></span>
11. <span data-ttu-id="8b295-143">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="8b295-143">Click Filter.</span></span>
12. <span data-ttu-id="8b295-144">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="8b295-144">Click Add.</span></span>
13. <span data-ttu-id="8b295-145">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8b295-145">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="8b295-146">Dans le champ de table, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="8b295-146">In the Table field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="8b295-147">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8b295-147">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="8b295-148">Dans le champ Table dérivée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="8b295-148">In the Derived table field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="8b295-149">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8b295-149">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="8b295-150">Dans le champ Champ, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="8b295-150">In the Field field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="8b295-151">Tapez une valeur dans le champ Champ.</span><span class="sxs-lookup"><span data-stu-id="8b295-151">In the Field field, type a value.</span></span>
20. <span data-ttu-id="8b295-152">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8b295-152">Close the page.</span></span>
21. <span data-ttu-id="8b295-153">Tapez une valeur dans le champ Critères.</span><span class="sxs-lookup"><span data-stu-id="8b295-153">In the Criteria field, type a value.</span></span>
22. <span data-ttu-id="8b295-154">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="8b295-154">Click OK.</span></span>
23. <span data-ttu-id="8b295-155">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="8b295-155">Click OK.</span></span>
24. <span data-ttu-id="8b295-156">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8b295-156">Close the page.</span></span>
25. <span data-ttu-id="8b295-157">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8b295-157">Close the page.</span></span>


