--- 
title: "Créer et valider une facture client pour un client du secteur public (Danemark)"
description: "Cette procédure vous guide dans la création et la validation d'une facture de commande client pour un client à l'aide de la facturation électronique OIOUBL."
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
ms.openlocfilehash: 846d7b67ca3287a5dbc0e3e18a22804fad847f1e
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="create-and-post-a-customer-invoice-for-a-public-sector-customer-denmark"></a><span data-ttu-id="a084b-103">Créer et valider une facture client pour un client du secteur public (Danemark)</span><span class="sxs-lookup"><span data-stu-id="a084b-103">Create and post a customer invoice for a public sector customer (Denmark)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a084b-104">Cette procédure vous guide dans la création et la validation d'une facture de commande client pour un client à l'aide de la facturation électronique OIOUBL.</span><span class="sxs-lookup"><span data-stu-id="a084b-104">This procedure walks you through creating and posting a sales order invoice for a customer using OIOUBL electronic invoicing.</span></span> 



<span data-ttu-id="a084b-105">Elle a été créée avec les données de démonstration de la société fictive USMF, avec l'adresse principale de l'entité juridique au Danemark.</span><span class="sxs-lookup"><span data-stu-id="a084b-105">It was created using the demo data company USMF with a legal entity primary address in Denmark.</span></span>



<span data-ttu-id="a084b-106">Il s'agit de la cinquième des six procédures illustrant le processus de bout en bout de génération de factures électroniques à l'aide des configurations de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="a084b-106">This is the fifth procedure out of six illustrating end to end process of generating e-invoices using electronic reporting configurations.</span></span> <span data-ttu-id="a084b-107">Elle est basée sur l'exemple de facture électronique OIOUBL, qui est commun au Danemark, à l'Autriche et à la Norvège.</span><span class="sxs-lookup"><span data-stu-id="a084b-107">It is based on OIOUBL e-invoice example which is common for Denmark, Austria and Norway.</span></span> <span data-ttu-id="a084b-108">Afin d'identifier les différences mineures pour d'autres implémentations de facture électronique spécifiques au pays, comme l'espagnol ou l'italien, reportez-vous aux articles WIKI disponibles.</span><span class="sxs-lookup"><span data-stu-id="a084b-108">In order to find minor differences for other country specific e-Invoice implementations, like Spanish or Italian, please refer to available WIKI articles.</span></span>



<span data-ttu-id="a084b-109">Avant d'exécuter cette procédure, vous devez effectuer les procédures suivantes : « Importer les configurations de génération d'état électronique de facturation électronique OIOUBL », « Paramétrer la facturation électronique OIOUBL » et « Paramétrer un compte client pour la facturation électronique OIOUBL ».</span><span class="sxs-lookup"><span data-stu-id="a084b-109">Before you can complete this procedure, you must complete the following procedures: ‘Import OIOUBL electronic invoicing electronic reporting configurations’, ‘Set up OIOUBL electronic invoicing’ and ‘Set up a customer account for OIOUBL electronic invoicing’.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="a084b-110">Créer une commande client</span><span class="sxs-lookup"><span data-stu-id="a084b-110">Create a sales order</span></span>
1. <span data-ttu-id="a084b-111">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="a084b-111">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="a084b-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a084b-112">Click New.</span></span>
3. <span data-ttu-id="a084b-113">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="a084b-113">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="a084b-114">Sélectionnez un client qui est activé pour la facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="a084b-114">Select a customer that is enabled for electronic invoicing.</span></span>  
4. <span data-ttu-id="a084b-115">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a084b-115">Click OK.</span></span>
5. <span data-ttu-id="a084b-116">Sélectionnez une vue d'en-tête de commande client.</span><span class="sxs-lookup"><span data-stu-id="a084b-116">Select a sales order header view.</span></span>
6. <span data-ttu-id="a084b-117">Dans le champ Contact, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a084b-117">In the Contact field, enter or select a value.</span></span>
7. <span data-ttu-id="a084b-118">Tapez une valeur dans le champ Demande d'achat client.</span><span class="sxs-lookup"><span data-stu-id="a084b-118">In the Customer requisition field, type a value.</span></span>
8. <span data-ttu-id="a084b-119">Tapez une valeur dans le champ Référence client.</span><span class="sxs-lookup"><span data-stu-id="a084b-119">In the Customer reference field, type a value.</span></span>
9. <span data-ttu-id="a084b-120">Développez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="a084b-120">Expand the Setup section.</span></span>
10. <span data-ttu-id="a084b-121">Sélectionnez une vue de ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="a084b-121">Select a sales order line view.</span></span>
11. <span data-ttu-id="a084b-122">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="a084b-122">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="a084b-123">Vous pouvez utiliser le numéro d'article « D0001 ».</span><span class="sxs-lookup"><span data-stu-id="a084b-123">You may use an item number 'D0001'.</span></span>  
12. <span data-ttu-id="a084b-124">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a084b-124">Click Save.</span></span>

## <a name="post-an-invoice-for-a-sales-order"></a><span data-ttu-id="a084b-125">Valider une facture pour un commande client</span><span class="sxs-lookup"><span data-stu-id="a084b-125">Post an invoice for a sales order</span></span>
1. <span data-ttu-id="a084b-126">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="a084b-126">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="a084b-127">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="a084b-127">Click Invoice.</span></span>
3. <span data-ttu-id="a084b-128">Développez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="a084b-128">Expand the Parameters section.</span></span>
4. <span data-ttu-id="a084b-129">Sélectionnez « Tout » dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="a084b-129">In the Quantity field, select 'All'.</span></span>
5. <span data-ttu-id="a084b-130">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a084b-130">Click OK.</span></span>
6. <span data-ttu-id="a084b-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a084b-131">Click OK.</span></span>

## <a name="generate-oioubl-electronic-invoice"></a><span data-ttu-id="a084b-132">Générer une facture électronique OIOUBL</span><span class="sxs-lookup"><span data-stu-id="a084b-132">Generate OIOUBL electronic invoice</span></span>
1. <span data-ttu-id="a084b-133">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="a084b-133">Click Invoice.</span></span>
2. <span data-ttu-id="a084b-134">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="a084b-134">On the Action Pane, click Invoice.</span></span>
3. <span data-ttu-id="a084b-135">Cliquez sur Envoyer.</span><span class="sxs-lookup"><span data-stu-id="a084b-135">Click Send.</span></span>
4. <span data-ttu-id="a084b-136">Cliquez sur Original.</span><span class="sxs-lookup"><span data-stu-id="a084b-136">Click Original.</span></span>

## <a name="view-an-oioubl-electronic-invoice"></a><span data-ttu-id="a084b-137">Afficher une facture électronique OIOUBL</span><span class="sxs-lookup"><span data-stu-id="a084b-137">View an OIOUBL electronic invoice</span></span>
1. <span data-ttu-id="a084b-138">Accédez à Administration d'organisation > Génération d'états électroniques > Tâches d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="a084b-138">Go to Organization administration > Electronic reporting > Electronic reporting jobs.</span></span>
2. <span data-ttu-id="a084b-139">Cliquez sur Afficher les fichiers.</span><span class="sxs-lookup"><span data-stu-id="a084b-139">Click Show files.</span></span>
3. <span data-ttu-id="a084b-140">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="a084b-140">Click Open.</span></span>


