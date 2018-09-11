--- 
title: "Paramétrer le rapprochement automatique des frais de transport"
description: "Cette procédure indique comment paramétrer des données pour le rapprochement automatique des frais de transport."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSFreightBillType, TMSFreightBillTypeAssignment, TMSCarrierCodeLookup, DefaultDashboard, TMSAuditMaster
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 6cbcc9ad54a1c10621b04315e8295c3049567450
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="set-up-automatic-freight-reconciliation"></a><span data-ttu-id="f81a5-103">Paramétrer le rapprochement automatique des frais de transport</span><span class="sxs-lookup"><span data-stu-id="f81a5-103">Set up automatic freight reconciliation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f81a5-104">Cette procédure indique comment paramétrer des données pour le rapprochement automatique des frais de transport.</span><span class="sxs-lookup"><span data-stu-id="f81a5-104">This procedure shows how to set up data for automatic freight reconciliation.</span></span> <span data-ttu-id="f81a5-105">Elle est généralement effectuée par un gestionnaire d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="f81a5-105">This is typically done by a warehouse manager.</span></span> <span data-ttu-id="f81a5-106">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="f81a5-106">You can use this procedure in demo data company USMF.</span></span>


## <a name="set-up-the-freight-bill-type"></a><span data-ttu-id="f81a5-107">Paramétrer le type de facture de frais de transport</span><span class="sxs-lookup"><span data-stu-id="f81a5-107">Set up the freight bill type</span></span>
1. <span data-ttu-id="f81a5-108">Allez dans Gestion du transport > Paramétrage > Rapprochement des frais de transport > Type de facture des frais de transport.</span><span class="sxs-lookup"><span data-stu-id="f81a5-108">Go to Transportation management > Setup > Freight reconciliation > Freight bill type.</span></span>
    * <span data-ttu-id="f81a5-109">Le type de facture des frais de transport définit comment les factures de frais de transport et les factures du transporteur doivent être mises en correspondance.</span><span class="sxs-lookup"><span data-stu-id="f81a5-109">The freight bill type defines how freight bills and carrier invoices  should be matched.</span></span>  
2. <span data-ttu-id="f81a5-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f81a5-110">Click New.</span></span>
3. <span data-ttu-id="f81a5-111">Dans le champ Type de facture des frais de transport, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f81a5-111">In the Freight bill type field, type a value.</span></span>
4. <span data-ttu-id="f81a5-112">Dans le champ Assembly de moteur, tapez « Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer ».</span><span class="sxs-lookup"><span data-stu-id="f81a5-112">In the Engine assembly field, type 'Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer'.</span></span>
    * <span data-ttu-id="f81a5-113">Il s'agit de la gestion de transport standard correspondant à la bibliothèque de code du moteur.</span><span class="sxs-lookup"><span data-stu-id="f81a5-113">This is the standard Transportation management matching engine code library.</span></span>  
5. <span data-ttu-id="f81a5-114">Dans le champ Classe de moteur, tapez « Microsoft.Dynamics.Ax.Tms.dll ».</span><span class="sxs-lookup"><span data-stu-id="f81a5-114">In the Engine class field, type 'Microsoft.Dynamics.Ax.Tms.dll'.</span></span>
    * <span data-ttu-id="f81a5-115">Il s'agit de la gestion de transport standard correspondant à la classe du moteur.</span><span class="sxs-lookup"><span data-stu-id="f81a5-115">This is the standard Transportation management matching engine class.</span></span>  
6. <span data-ttu-id="f81a5-116">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f81a5-116">Click New.</span></span>
7. <span data-ttu-id="f81a5-117">Dans le champ Description, sélectionnez la valeur qui doit correspondre sur la facture des frais de transport et la facture du transporteur.</span><span class="sxs-lookup"><span data-stu-id="f81a5-117">In the Description field, choose the value that should match on the freight bill and the carrier invoice.</span></span>  
8. <span data-ttu-id="f81a5-118">Dans le champ Correspondance nécessaire, sélectionnez « Oui ».</span><span class="sxs-lookup"><span data-stu-id="f81a5-118">In the Match required field, select 'Yes'.</span></span>
    * <span data-ttu-id="f81a5-119">Si vous définissez ce champ sur Oui, cela implique que la valeur sélectionnée dans le champ Description doit correspondre sur la facture des frais de transport et la facture du transporteur.</span><span class="sxs-lookup"><span data-stu-id="f81a5-119">If you set this field to Yes this means that the value selected in the Description field needs to match on both the freight bill and the carrier invoice.</span></span> <span data-ttu-id="f81a5-120">S'il est défini sur Non, le champ peut être vide sur l'un de ces éléments.</span><span class="sxs-lookup"><span data-stu-id="f81a5-120">If you set it to No, the field can be blank on one of these.</span></span>  
9. <span data-ttu-id="f81a5-121">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f81a5-121">Click Save.</span></span>

## <a name="set-up-the-freight-bill-type-assignment"></a><span data-ttu-id="f81a5-122">Paramétrer l'affectation du type de facture de frais de transport</span><span class="sxs-lookup"><span data-stu-id="f81a5-122">Set up the freight bill type assignment</span></span>
1. <span data-ttu-id="f81a5-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f81a5-123">Close the page.</span></span>
2. <span data-ttu-id="f81a5-124">Allez dans Gestion du transport > Paramétrage > Rapprochement des frais de transport > Affectations du type de facture des frais de transport.</span><span class="sxs-lookup"><span data-stu-id="f81a5-124">Go to Transportation management > Setup > Freight reconciliation > Freight bill type assignments.</span></span>
    * <span data-ttu-id="f81a5-125">L'affectation du type de facture de frais de transport permet de spécifier le type de facture de frais de transport utilisé pour un transporteur particulier.</span><span class="sxs-lookup"><span data-stu-id="f81a5-125">The freight bill type assignment is used to specify which freight bill type is used for a particular carrier.</span></span>   
3. <span data-ttu-id="f81a5-126">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f81a5-126">Click New.</span></span>
4. <span data-ttu-id="f81a5-127">Dans le champ Mode, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f81a5-127">In the Mode field, enter or select a value.</span></span>
5. <span data-ttu-id="f81a5-128">Dans le champ Transporteur, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f81a5-128">In the Shipping carrier field, enter or select a value.</span></span>
6. <span data-ttu-id="f81a5-129">Dans le champ Type de facture des frais de transport, sélectionnez le type de facture des frais de transport que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="f81a5-129">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
7. <span data-ttu-id="f81a5-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f81a5-130">Close the page.</span></span>

## <a name="set-up-the-audit-master"></a><span data-ttu-id="f81a5-131">Paramétrer les données principales d'audit</span><span class="sxs-lookup"><span data-stu-id="f81a5-131">Set up the audit master</span></span>
1. <span data-ttu-id="f81a5-132">Allez dans Gestion du transport > Paramétrage > Rapprochement des frais de transport > Données principales d'audit.</span><span class="sxs-lookup"><span data-stu-id="f81a5-132">Go to Transportation management > Setup > Freight reconciliation > Audit master.</span></span>
    * <span data-ttu-id="f81a5-133">La table maître d'audit définit les limites de tolérance pour le rapprochement automatique des frais de transport.</span><span class="sxs-lookup"><span data-stu-id="f81a5-133">The audit master defines the tolerance limits for automatic freight reconciliation.</span></span> <span data-ttu-id="f81a5-134">Elle spécifie dans quelle mesure les montants en devises sur la facture des frais de transport et la facture de transporteur peuvent différer tout en autorisant le rapprochement.</span><span class="sxs-lookup"><span data-stu-id="f81a5-134">It specifies by how much the monetary amounts on the freight bill and the carrier invoice can differ and still allow reconciliation to occur.</span></span> <span data-ttu-id="f81a5-135">Elle définit également comment gérer les différences.</span><span class="sxs-lookup"><span data-stu-id="f81a5-135">It also defines how to handle discrepancies.</span></span>  
2. <span data-ttu-id="f81a5-136">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f81a5-136">Click New.</span></span>
3. <span data-ttu-id="f81a5-137">Dans le champ ID données principales d'audit, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f81a5-137">In the Audit master ID field, type a value.</span></span>
4. <span data-ttu-id="f81a5-138">Dans le champ Transporteur, sélectionnez le même transporteur que celui sélectionné précédemment.</span><span class="sxs-lookup"><span data-stu-id="f81a5-138">In the Shipping carrier  field, select the same shipping carrier as you did earlier.</span></span>
5. <span data-ttu-id="f81a5-139">Dans le champ Type de facture des frais de transport, sélectionnez le type de facture des frais de transport que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="f81a5-139">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
6. <span data-ttu-id="f81a5-140">Développez la section Tolérance.</span><span class="sxs-lookup"><span data-stu-id="f81a5-140">Expand the Tolerance section.</span></span>
7. <span data-ttu-id="f81a5-141">Dans le champ Niveau de tolérance minimal, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="f81a5-141">In the Minimum tolerance level field, enter a number.</span></span>
8. <span data-ttu-id="f81a5-142">Dans le champ Niveau de tolérance maximal, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="f81a5-142">In the Maximum tolerance level field, enter a number.</span></span>
9. <span data-ttu-id="f81a5-143">Développez la section Résultat.</span><span class="sxs-lookup"><span data-stu-id="f81a5-143">Expand the Result section.</span></span>
10. <span data-ttu-id="f81a5-144">Dans le champ Code motif du trop-perçu, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f81a5-144">In the Overpayment reason code field, enter or select a value.</span></span>
    * <span data-ttu-id="f81a5-145">Si les montants en devises diffèrent sur la facture des frais de transport et la facture du transporteur, les codes motif du trop-perçu/moins-perçu spécifient les comptes sur lesquels la différence doit être enregistrée, tant qu'elle entre dans les niveaux de tolérance.</span><span class="sxs-lookup"><span data-stu-id="f81a5-145">If the monetary amounts differ on the freight bill and the carrier invoice, the overpayment and underpayment reason codes specify the accounts that the difference should be registered on, as long as the difference is within the tolerance levels.</span></span>  
11. <span data-ttu-id="f81a5-146">Dans le champ Code motif du moins-perçu, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f81a5-146">In the Underpayment reason code field, enter or select a value.</span></span>
12. <span data-ttu-id="f81a5-147">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f81a5-147">Close the page.</span></span>


