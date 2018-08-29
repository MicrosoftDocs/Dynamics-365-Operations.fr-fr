--- 
title: "Créer et valider une facture de projet pour un client du secteur public (Danemark)"
description: "Cette tâche vous guide dans la création et la validation d'une facture de projet pour un client à l'aide de la facturation électronique OIOUBL."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Denmark
ms.search.industry: Public Sector
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c689087f499330c8d662aed2632fd2e079145fde
ms.openlocfilehash: a781ba3368a41d704d92560d27bbc39435490e90
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="create-and-post-a-project-invoice-for-a-public-sector-customer-denmark"></a><span data-ttu-id="10c62-103">Créer et valider une facture de projet pour un client du secteur public (Danemark)</span><span class="sxs-lookup"><span data-stu-id="10c62-103">Create and post a project invoice for a public sector customer (Denmark)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="10c62-104">Cette tâche vous guide dans la création et la validation d'une facture de projet pour un client à l'aide de la facturation électronique OIOUBL.</span><span class="sxs-lookup"><span data-stu-id="10c62-104">This task walks you through creating and posting a project invoice for a customer using OIOUBL electronic invoicing.</span></span> 



<span data-ttu-id="10c62-105">Cette tâche a été créée avec les données de démonstration de la société fictive USMF, le pays/région de l'adresse principale de l'entité juridique étant actualisé en Danemark.</span><span class="sxs-lookup"><span data-stu-id="10c62-105">This task was created using the demo data company USMF with the country/region of legal entity primary address updated to Denmark.</span></span>



<span data-ttu-id="10c62-106">Il s'agit de la sixième des six procédures illustrant le processus de bout en bout de génération de factures électroniques à l'aide des configurations de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="10c62-106">This is the sixth procedure out of six illustrating end to end process of generating e-invoices using electronic reporting configurations.</span></span> <span data-ttu-id="10c62-107">Elle est basée sur l'exemple de facture électronique OIOUBL, qui est commun au Danemark, à l'Autriche et à la Norvège.</span><span class="sxs-lookup"><span data-stu-id="10c62-107">It is based on OIOUBL e-invoice example which is common for Denmark, Austria and Norway.</span></span> <span data-ttu-id="10c62-108">Afin d'identifier les différences mineures pour d'autres implémentations de facture électronique spécifiques au pays, comme l'espagnol ou l'italien, reportez-vous aux articles WIKI disponibles.</span><span class="sxs-lookup"><span data-stu-id="10c62-108">In order to find minor differences for other country specific e-Invoice implementations, like Spanish or Italian, please refer to available WIKI articles.</span></span>



<span data-ttu-id="10c62-109">Avant d'exécuter cette procédure, vous devez effectuer les procédures suivantes : « Importer les configurations de génération d'état électronique de facturation électronique OIOUBL », « Paramétrer la facturation électronique OIOUBL » et « Paramétrer un compte client pour la facturation électronique OIOUBL ».</span><span class="sxs-lookup"><span data-stu-id="10c62-109">Before you can complete this procedure, you must complete the following procedures: ‘Import OIOUBL electronic invoicing electronic reporting configurations’, ‘Set up OIOUBL electronic invoicing’ and ‘Set up a customer account for OIOUBL electronic invoicing’.</span></span>


## <a name="update-a-project-contract"></a><span data-ttu-id="10c62-110">Mettre à jour un contrat de projet</span><span class="sxs-lookup"><span data-stu-id="10c62-110">Update a project contract</span></span>
1. <span data-ttu-id="10c62-111">Accédez à Gestion et comptabilité des projets > Projets > Contrats de projets.</span><span class="sxs-lookup"><span data-stu-id="10c62-111">Go to Project management and accounting > Projects > Project contracts.</span></span>
2. <span data-ttu-id="10c62-112">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="10c62-112">Use the Quick Filter to find records.</span></span> <span data-ttu-id="10c62-113">Par exemple, appliquez un filtre au champ ID contrat de projet avec une valeur de « 000057 ».</span><span class="sxs-lookup"><span data-stu-id="10c62-113">For example, filter on the Project contract ID field with a value of '000057'.</span></span>
    * <span data-ttu-id="10c62-114">Sélectionnez un contrat de projet ayant une source de financement client qui est activée pour la facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="10c62-114">Select a project contract that has a customer funding source that is enabled for electronic invoicing.</span></span>  
3. <span data-ttu-id="10c62-115">Ouvrir les détails d'un contrat de projet.</span><span class="sxs-lookup"><span data-stu-id="10c62-115">Open details for a project contract.</span></span>
4. <span data-ttu-id="10c62-116">Développez la section Sources de financement.</span><span class="sxs-lookup"><span data-stu-id="10c62-116">Expand the Funding sources section.</span></span>
5. <span data-ttu-id="10c62-117">Cliquez sur Détails.</span><span class="sxs-lookup"><span data-stu-id="10c62-117">Click Details.</span></span>
6. <span data-ttu-id="10c62-118">Développer la section Autre.</span><span class="sxs-lookup"><span data-stu-id="10c62-118">Expand the Other section.</span></span>
7. <span data-ttu-id="10c62-119">Tapez une valeur dans le champ Demande d'achat client.</span><span class="sxs-lookup"><span data-stu-id="10c62-119">In the Customer requisition field, type a value.</span></span>
8. <span data-ttu-id="10c62-120">Tapez une valeur dans le champ Référence client.</span><span class="sxs-lookup"><span data-stu-id="10c62-120">In the Customer reference field, type a value.</span></span>
9. <span data-ttu-id="10c62-121">Dans le champ ID contact, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="10c62-121">In the Contact ID field, enter or select a value.</span></span>
10. <span data-ttu-id="10c62-122">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="10c62-122">Click Save.</span></span>

## <a name="create-a-project-transaction"></a><span data-ttu-id="10c62-123">Créer une transaction de projet</span><span class="sxs-lookup"><span data-stu-id="10c62-123">Create a project transaction</span></span>
1. <span data-ttu-id="10c62-124">Accédez à Gestion de projets et comptabilité > Tâches d'article > Demandes d'articles.</span><span class="sxs-lookup"><span data-stu-id="10c62-124">Go to Project management and accounting > Item tasks > Item requirements.</span></span>
2. <span data-ttu-id="10c62-125">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="10c62-125">Click New.</span></span>
3. <span data-ttu-id="10c62-126">Saisissez ou sélectionnez une valeur dans le champ ID projet.</span><span class="sxs-lookup"><span data-stu-id="10c62-126">In the Project ID field, enter or select a value.</span></span>
    * <span data-ttu-id="10c62-127">Par exemple, vous pouvez utiliser l'ID projet « 000057 ».</span><span class="sxs-lookup"><span data-stu-id="10c62-127">As an example, you may use '000057' project ID.</span></span>  
4. <span data-ttu-id="10c62-128">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="10c62-128">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="10c62-129">Par exemple, vous pouvez utiliser le numéro d'article « D0001 ».</span><span class="sxs-lookup"><span data-stu-id="10c62-129">As an example, you may use 'D0001' item number.</span></span>  
5. <span data-ttu-id="10c62-130">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="10c62-130">On the Action Pane, click Manage.</span></span>
6. <span data-ttu-id="10c62-131">Cliquez sur Validation.</span><span class="sxs-lookup"><span data-stu-id="10c62-131">Click Posting.</span></span>
7. <span data-ttu-id="10c62-132">Cliquez sur Bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="10c62-132">Click Packing slip.</span></span>
8. <span data-ttu-id="10c62-133">Développez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="10c62-133">Expand the Parameters section.</span></span>
9. <span data-ttu-id="10c62-134">Sélectionnez « Tout » dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="10c62-134">In the Quantity field, select 'All'.</span></span>
10. <span data-ttu-id="10c62-135">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="10c62-135">Click OK.</span></span>
11. <span data-ttu-id="10c62-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="10c62-136">Click OK.</span></span>

## <a name="create-a-proposal-and-post-an-invoice"></a><span data-ttu-id="10c62-137">Créer une proposition et valider une facture</span><span class="sxs-lookup"><span data-stu-id="10c62-137">Create a proposal and post an invoice</span></span> 
1. <span data-ttu-id="10c62-138">Accédez à Gestion et comptabilité des projets > Factures de projets > Propositions de facture du projet.</span><span class="sxs-lookup"><span data-stu-id="10c62-138">Go to Project management and accounting > Project invoices > Project invoice proposals.</span></span>
2. <span data-ttu-id="10c62-139">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="10c62-139">Click New.</span></span>
3. <span data-ttu-id="10c62-140">Cliquez sur Proposition de facture.</span><span class="sxs-lookup"><span data-stu-id="10c62-140">Click Invoice proposal.</span></span>
4. <span data-ttu-id="10c62-141">Dans le champ Projet, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="10c62-141">In the Project field, enter or select a value.</span></span>
5. <span data-ttu-id="10c62-142">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="10c62-142">Click OK.</span></span>
6. <span data-ttu-id="10c62-143">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="10c62-143">Click Post.</span></span>
7. <span data-ttu-id="10c62-144">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="10c62-144">Click OK.</span></span>
8. <span data-ttu-id="10c62-145">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="10c62-145">Click OK.</span></span>

## <a name="generate-an-oioubl-project-invoice"></a><span data-ttu-id="10c62-146">Générer une facture de projet OIOUBL</span><span class="sxs-lookup"><span data-stu-id="10c62-146">Generate an OIOUBL project invoice</span></span>
1. <span data-ttu-id="10c62-147">Accédez à Gestion et comptabilité des projets > Factures de projets > Factures de projet.</span><span class="sxs-lookup"><span data-stu-id="10c62-147">Go to Project management and accounting > Project invoices > Project invoices.</span></span>
2. <span data-ttu-id="10c62-148">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="10c62-148">Use the Quick Filter to find records.</span></span> <span data-ttu-id="10c62-149">Par exemple, appliquez un filtre au champ ID contrat de projet avec une valeur de « 000057 ».</span><span class="sxs-lookup"><span data-stu-id="10c62-149">For example, filter on the Project contract ID field with a value of '000057'.</span></span>
3. <span data-ttu-id="10c62-150">Dans le volet Actions, cliquez sur Facture de projet.</span><span class="sxs-lookup"><span data-stu-id="10c62-150">On the Action Pane, click Project invoice.</span></span>
4. <span data-ttu-id="10c62-151">Cliquez sur Envoyer.</span><span class="sxs-lookup"><span data-stu-id="10c62-151">Click Send.</span></span>
5. <span data-ttu-id="10c62-152">Cliquez sur Original.</span><span class="sxs-lookup"><span data-stu-id="10c62-152">Click Original.</span></span>

## <a name="view-an-oioubl-electronic-invoice"></a><span data-ttu-id="10c62-153">Afficher une facture électronique OIOUBL</span><span class="sxs-lookup"><span data-stu-id="10c62-153">View an OIOUBL electronic invoice</span></span>
1. <span data-ttu-id="10c62-154">Accédez à Administration d'organisation > Génération d'états électroniques > Tâches d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="10c62-154">Go to Organization administration > Electronic reporting > Electronic reporting jobs.</span></span>
2. <span data-ttu-id="10c62-155">Cliquez sur Afficher les fichiers.</span><span class="sxs-lookup"><span data-stu-id="10c62-155">Click Show files.</span></span>
3. <span data-ttu-id="10c62-156">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="10c62-156">Click Open.</span></span>


