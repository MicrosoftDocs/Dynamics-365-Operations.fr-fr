---
title: Régularisation des coûts de projet dans les réceptions d’achat
description: Cette rubrique décrit comment les coûts de projet régularisés depuis les réceptions d’achat peuvent être suivis dans Microsoft Dynamics 365 Finance.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: roschlom
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d27fba816ca289e6a84e8684f7f90686864fb0b6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972079"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a><span data-ttu-id="63797-103">Régularisation des coûts de projet dans les réceptions d’achat</span><span class="sxs-lookup"><span data-stu-id="63797-103">Project cost accrual on purchase receipts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63797-104">Cette rubrique décrit comment les coûts de projet régularisés depuis les réceptions d’achat peuvent être suivis dans Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="63797-104">This topic describes how accrued project costs from purchase receipts can be tracked in Microsoft Dynamics 365 Finance.</span></span> 

<span data-ttu-id="63797-105">Les factures pour un projet arrivent souvent plus tard que les marchandises et les services livrés, ce qui peut avoir un impact considérable sur des indicateurs de performance clé (KPIs) du projet.</span><span class="sxs-lookup"><span data-stu-id="63797-105">Invoices for a project often arrive later than the goods and services are delivered, which might have a significant impact on project key performance indicators (KPIs).</span></span> <span data-ttu-id="63797-106">Il est important de pouvroir suivre ces transactions dans des rapports financiers et de projet.</span><span class="sxs-lookup"><span data-stu-id="63797-106">It important to be able to track these transactions in both financial and project reports.</span></span>

<span data-ttu-id="63797-107">L’exemple de scénario suivant illustre cela.</span><span class="sxs-lookup"><span data-stu-id="63797-107">The following example scenario illustrates this.</span></span> 

<span data-ttu-id="63797-108">Contoso Consulting a démarré un nouveau projet de déploiement de cloud.</span><span class="sxs-lookup"><span data-stu-id="63797-108">Contoso Consulting has started a new cloud deployment project.</span></span> <span data-ttu-id="63797-109">Une commande fournisseur est créée pour acheter un ordinateur pour le projet.</span><span class="sxs-lookup"><span data-stu-id="63797-109">A purchase order is created to buy a computer for the project.</span></span> <span data-ttu-id="63797-110">L’ordinateur évalue le coût à $1500 et les services d’installation à $150.</span><span class="sxs-lookup"><span data-stu-id="63797-110">The computer will cost $1500 and installation services will cost $150.</span></span> <span data-ttu-id="63797-111">Le fournisseur a livré et installé l’ordinateur, mais la facture n’est pas encore arrivée chez Contoso Consulting.</span><span class="sxs-lookup"><span data-stu-id="63797-111">The vendor has delivered and installed the computer, but the invoice has not yet reached Contoso Consulting.</span></span> <span data-ttu-id="63797-112">Le chef de projet souhaite voir la régularisation du coût du projet de $1650 pour que la facture soit remise.</span><span class="sxs-lookup"><span data-stu-id="63797-112">The project manager would like to see project cost accrual of $1650 before the invoice gets delivered.</span></span> <span data-ttu-id="63797-113">Le coût doit également être pris en compte dans les tableaux d’analyse du mois de la société.</span><span class="sxs-lookup"><span data-stu-id="63797-113">This cost should also be reflected in the company's month end financial statements.</span></span> 

<span data-ttu-id="63797-114">Les charges à payer doivent être enregistrées au niveau financier et au niveau du projet pour la génération d’états.</span><span class="sxs-lookup"><span data-stu-id="63797-114">The accrued cost needs to be recorded on both the financial level and project level for reporting purposes.</span></span> <span data-ttu-id="63797-115">La mise à jour financière de l’accusé de réception de marchandises peut être appliquée à l’article et aux catégories d’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="63797-115">The financial update of the product receipt can be tracked for the item and procurement categories.</span></span> 

<span data-ttu-id="63797-116">Pour les articles, sur la page **Paramètres de la comptabilité fournisseur**, sélectionnez l’option de **publication des reçus de produits dans la comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="63797-116">For items, on the **Accounts payable parameters** page, select the **Post product receipts to ledger** option.</span></span>
<span data-ttu-id="63797-117">[![Page Paramètres de la comptabilité fournisseur](./media/accruals1-1024x409.png)](./media/accruals1.png)</span><span class="sxs-lookup"><span data-stu-id="63797-117">[![Accounts payable parameters page](./media/accruals1-1024x409.png)](./media/accruals1.png)</span></span> 

<span data-ttu-id="63797-118">Pour les catégories d’approvisionnement, sur la page **Règle de stratégie de catégorie**, sélectionnez les politiques **d’achat**, puis sélectionnez **Provisionner les dépenses d’achat à la réception** pour chaque catégorie d’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="63797-118">For procurement categories, on the **Category policy rule** page, select **Purchasing** policies, and then select **Accrue purchase expense on receipt** for each procurement category.</span></span>
<span data-ttu-id="63797-119">[![Page de la règle de stratégie de catégorie](./media/accruals2-1024x569.png)](./media/accruals2.png)</span><span class="sxs-lookup"><span data-stu-id="63797-119">[![Category policy rule page](./media/accruals2-1024x569.png)](./media/accruals2.png)</span></span> 

<span data-ttu-id="63797-120">Les comptes **Dépenses d’achat, non facturées** et **Régularisation d’achat** dans **Paramétrage de la validation** seront utilisés lorsque les documents associés à l’accusé de réception de marchandises seront publiés.</span><span class="sxs-lookup"><span data-stu-id="63797-120">The **Purchase expenditure un-invoiced** and **Purchase accrual** accounts in **Posting setup** will be used when vouchers that are related to the product receipt are posted.</span></span>

<span data-ttu-id="63797-121">En utilisant ce même scénario, voyons comment la publication d’un reçu de produit aura une incidence sur les informations de comptabilité et de projet.</span><span class="sxs-lookup"><span data-stu-id="63797-121">Using this same scenario, let's see how posting a product receipt will impact General ledger and Project information.</span></span> 

<span data-ttu-id="63797-122">**Étape 1 :** Création et confirmation d’un nouveau bon de commande pour le projet afin d’enregistrer l’achat d’un ordinateur pour $1500 et les services d’installation pour $150.</span><span class="sxs-lookup"><span data-stu-id="63797-122">**Step 1:** Create and confirm a new purchase order for the project to record the purchase of a computer for $1500 and installation services for $150.</span></span>
<span data-ttu-id="63797-123">[![Créer une commande fournisseur](./media/accruals4-1024x497.png)](./media/accruals4.png)</span><span class="sxs-lookup"><span data-stu-id="63797-123">[![Create new purchase order](./media/accruals4-1024x497.png)](./media/accruals4.png)</span></span> 

<span data-ttu-id="63797-124">Lorsque la commande fournisseur est confirmée, les transactions pour le coût engagé sont créées pour le projet.</span><span class="sxs-lookup"><span data-stu-id="63797-124">When the purchase order is confirmed, transactions for the committed cost are created for the project.</span></span> 
<span data-ttu-id="63797-125">[![Transactions créées](./media/accruals5-1024x219.png)](./media/accruals5.png)</span><span class="sxs-lookup"><span data-stu-id="63797-125">[![Transactions created](./media/accruals5-1024x219.png)](./media/accruals5.png)</span></span> 

> [!NOTE]
> <span data-ttu-id="63797-126">Les transactions pour le coût engagé auront le champ **Origine de la transaction** défini sur **Bon de commande**.</span><span class="sxs-lookup"><span data-stu-id="63797-126">The transactions for the committed cost will have the **Transaction Origin** field set to **Purchase Order**.</span></span> <span data-ttu-id="63797-127">La création et la confirmation d’une commande fournisseur ne créent pas de transaction pour un projet.</span><span class="sxs-lookup"><span data-stu-id="63797-127">Creating and confirming a purchase order does not create transactions for a project.</span></span> 

<span data-ttu-id="63797-128">**Étape 2 :** Les marchandises et les services sont livrés et un accusé de réception de marchandises est enregistré.</span><span class="sxs-lookup"><span data-stu-id="63797-128">**Step 2:** Goods and services get delivered and a product receipt is registered.</span></span> 

<span data-ttu-id="63797-129">Valider un accusé de réception de marchandises génère et valide un document dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="63797-129">Posting a product receipt will generate and post a voucher to the ledger.</span></span> <span data-ttu-id="63797-130">Le N° document débite le compte non facturée de dépense d’achat et le compte de régularisation des achats à crédit.</span><span class="sxs-lookup"><span data-stu-id="63797-130">The voucher will debit the purchase expenditure, un-invoiced account, and credit purchase accrual account.</span></span> 
<span data-ttu-id="63797-131">[![Pièces comptables](./media/accruals6-1024x214.png)](./media/accruals6.png)</span><span class="sxs-lookup"><span data-stu-id="63797-131">[![Voucher transactions](./media/accruals6-1024x214.png)](./media/accruals6.png)</span></span>

> [!NOTE]
> <span data-ttu-id="63797-132">L’affichage d’un reçu de produit utilisera la configuration de publication pour les catégories et produits d’approvisionnement, et non la configuration de publication pour les catégories de projet.</span><span class="sxs-lookup"><span data-stu-id="63797-132">Posting a product receipt will use the posting setup for procurement categories and products, and not the posting setup for the project categories.</span></span> <span data-ttu-id="63797-133">Afin de refléter correctement l’impact financier des régularisations d’achat, cette configuration doit être alignée.</span><span class="sxs-lookup"><span data-stu-id="63797-133">In order to correctly reflect financial impact of purchase accruals, this setup needs to be aligned.</span></span> 

<span data-ttu-id="63797-134">Il est possible de mettre en correspondance des catégories d’approvisionnement avec des catégories de projet sur la page **Catégorie d’approvisionnement**.</span><span class="sxs-lookup"><span data-stu-id="63797-134">It is possible to map procurement categories to project categories on the **Procurement category** page.</span></span>
<span data-ttu-id="63797-135">[![Page de catégorie d’approvisionnement](./media/accruals7-1024x390.png)](./media/accruals7.png)</span><span class="sxs-lookup"><span data-stu-id="63797-135">[![Procurement category page](./media/accruals7-1024x390.png)](./media/accruals7.png)</span></span>

<span data-ttu-id="63797-136">**Étape 3 :** Création d’un brouillon de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="63797-136">**Step 3:** Create a draft vendor invoice.</span></span> 

<span data-ttu-id="63797-137">La validation d’un accusé de réception de marchandises ne concerne pas les informations de projet.</span><span class="sxs-lookup"><span data-stu-id="63797-137">Posting a product receipt does not impact project information.</span></span> <span data-ttu-id="63797-138">Comme contournement, vous pouvez générer un brouillon de facture fournisseur après avoir validé la réception.</span><span class="sxs-lookup"><span data-stu-id="63797-138">As a workaround, you could generate a draft vendor invoice right after posting the purchase receipt.</span></span> <span data-ttu-id="63797-139">Accédez à la page **Commande fournisseur** &gt; **Onglet Facture** &gt; **Générer** &gt; **Facture**.</span><span class="sxs-lookup"><span data-stu-id="63797-139">Go to the **Purchase Order** page &gt; **Invoice tab** &gt; **Generate** &gt; **Invoice**.</span></span> <span data-ttu-id="63797-140">Cette action crée un document de facture en attente qui met les informations de projet à jour.</span><span class="sxs-lookup"><span data-stu-id="63797-140">This creates a pending invoice document that updates project information.</span></span> 

<span data-ttu-id="63797-141">La création d’un brouillon de facture fournisseur génère des transactions de projet en attente.</span><span class="sxs-lookup"><span data-stu-id="63797-141">Creating a draft vendor invoice will generate pending project transactions.</span></span> 
<span data-ttu-id="63797-142">[![Transactions de projet en attente](./media/accruals8-1024x225.png)](./media/accruals8.png)</span><span class="sxs-lookup"><span data-stu-id="63797-142">[![Pending project transactions](./media/accruals8-1024x225.png)](./media/accruals8.png)</span></span> 

<span data-ttu-id="63797-143">Dans la page **Coût engagé**, les enregistrements créés à l’étape 1 seront fermés et de nouveaux enregistrements seront créés pour refléter l’engagement de coût provenant de la facture du fournisseur en attente.</span><span class="sxs-lookup"><span data-stu-id="63797-143">In the **Committed cost** page, records created in step 1 will be closed and new records will be created to reflect cost commitment coming from the pending vendor invoice.</span></span> <span data-ttu-id="63797-144">Le champ **Origine de la transaction** pour le coût engagé est défini sur **Facture fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="63797-144">The **Transaction origin** field for the committed cost will be set to **Vendor invoice**.</span></span>
<span data-ttu-id="63797-145">[![Pages des coûts engagés](./media/accruals9-1024x200.png)](./media/accruals9.png)</span><span class="sxs-lookup"><span data-stu-id="63797-145">[![Commited costs page](./media/accruals9-1024x200.png)](./media/accruals9.png)</span></span>

<span data-ttu-id="63797-146">La facture fournisseur reste à l’état d’attente en attendant l’arrivée de la facture fournisseur réelle.</span><span class="sxs-lookup"><span data-stu-id="63797-146">The vendor invoice will remain in a pending state until the actual vendor invoice arrives.</span></span>



