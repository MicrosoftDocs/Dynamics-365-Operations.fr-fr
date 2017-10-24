--- 
title: "Démarrer un ordre de fabrication"
description: "Cette procédure indique comment démarrer un ordre de fabrication à l'atelier."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 33558053d33d9fe4a2ecb3576da569b2c441db80
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="start-a-production-order"></a><span data-ttu-id="b15bf-103">Démarrer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="b15bf-103">Start a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b15bf-104">Cette procédure indique comment démarrer un ordre de fabrication à l'atelier.</span><span class="sxs-lookup"><span data-stu-id="b15bf-104">This procedure shows how to start a production order on the shop floor.</span></span> <span data-ttu-id="b15bf-105">La consommation de matières et de temps est déclarée dans ce processus.</span><span class="sxs-lookup"><span data-stu-id="b15bf-105">Time and material consumption are reported in this process.</span></span> <span data-ttu-id="b15bf-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="b15bf-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="b15bf-107">Il s'agit de la cinquième des sept procédures expliquant le cycle de vie de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="b15bf-107">This is the fifth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="start-a-production-order"></a><span data-ttu-id="b15bf-108">Démarrer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="b15bf-108">Start a production order</span></span>
1. <span data-ttu-id="b15bf-109">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="b15bf-109">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="b15bf-110">Sélectionnez un ordre de fabrication ayant le statut Lancé.</span><span class="sxs-lookup"><span data-stu-id="b15bf-110">Select a production order that has the Released status.</span></span>  
2. <span data-ttu-id="b15bf-111">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="b15bf-111">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="b15bf-112">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="b15bf-112">Click Start.</span></span>
    * <span data-ttu-id="b15bf-113">Dans cette page, vous pouvez confirmer le début de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="b15bf-113">On this page, you can confirm the start of the production order.</span></span>  
4. <span data-ttu-id="b15bf-114">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="b15bf-114">Click the General tab.</span></span>
5. <span data-ttu-id="b15bf-115">Dans le champ Du n° opér.,</span><span class="sxs-lookup"><span data-stu-id="b15bf-115">In the From Oper.</span></span> <span data-ttu-id="b15bf-116">N°</span><span class="sxs-lookup"><span data-stu-id="b15bf-116">No.</span></span> <span data-ttu-id="b15bf-117">entrez 10.</span><span class="sxs-lookup"><span data-stu-id="b15bf-117">field, enter '10'.</span></span>
6. <span data-ttu-id="b15bf-118">Dans le champ Consommation de gamme automatique, sélectionnez « Toujours ».</span><span class="sxs-lookup"><span data-stu-id="b15bf-118">In the Automatic route consumption field, select 'Always'.</span></span>
7. <span data-ttu-id="b15bf-119">Cochez la case Valider fiche production maintenant.</span><span class="sxs-lookup"><span data-stu-id="b15bf-119">Click the Post route card now checkbox.</span></span>
8. <span data-ttu-id="b15bf-120">Dans le champ Consommation de nomenclature automatique, sélectionnez « Toujours ».</span><span class="sxs-lookup"><span data-stu-id="b15bf-120">In the Automatic BOM consumption field, select 'Always'.</span></span>
9. <span data-ttu-id="b15bf-121">Cochez la case Valider les prélèvements maintenant.</span><span class="sxs-lookup"><span data-stu-id="b15bf-121">Click the Post picking list now checkbox.</span></span>
10. <span data-ttu-id="b15bf-122">Cochez la case Imprimer les prélèvements.</span><span class="sxs-lookup"><span data-stu-id="b15bf-122">Click the Print picking list checkbox.</span></span>
11. <span data-ttu-id="b15bf-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b15bf-123">Click OK.</span></span>
    * <span data-ttu-id="b15bf-124">Il s'agit de la liste de prélèvements imprimée qui indique les matières utilisées pour l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="b15bf-124">This is the printed picking list that shows the materials used for the production order.</span></span>  
12. <span data-ttu-id="b15bf-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b15bf-125">Close the page.</span></span>

## <a name="validate-the-picking-list"></a><span data-ttu-id="b15bf-126">Valider les prélèvements.</span><span class="sxs-lookup"><span data-stu-id="b15bf-126">Validate the picking list</span></span>
1. <span data-ttu-id="b15bf-127">Cliquez sur Afficher dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="b15bf-127">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="b15bf-128">Cliquez sur Prélèvements.</span><span class="sxs-lookup"><span data-stu-id="b15bf-128">Click Picking list.</span></span>
3. <span data-ttu-id="b15bf-129">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b15bf-129">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="b15bf-130">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b15bf-130">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b15bf-131">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="b15bf-131">Click Edit.</span></span>
6. <span data-ttu-id="b15bf-132">Entrez un nombre dans le champ Consommation.</span><span class="sxs-lookup"><span data-stu-id="b15bf-132">In the Consumption field, enter a number.</span></span>
7. <span data-ttu-id="b15bf-133">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="b15bf-133">Click Post.</span></span>
8. <span data-ttu-id="b15bf-134">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b15bf-134">Click OK.</span></span>
    * <span data-ttu-id="b15bf-135">Dans le journal des prélèvements, les matières consommées par l'ordre de fabrication sont validées.</span><span class="sxs-lookup"><span data-stu-id="b15bf-135">In the picking list journal, the materials consumed by the production order are posted.</span></span> <span data-ttu-id="b15bf-136">Avant de valider le journal, vous pouvez procéder à des ajustements s'il existe une différence entre la quantité estimée et la quantité réelle consommée.</span><span class="sxs-lookup"><span data-stu-id="b15bf-136">Before posting the journal, you can make adjustments if there is a difference between the estimated quantity and the actual consumed quantity.</span></span>  
9. <span data-ttu-id="b15bf-137">Cliquez sur l'onglet Volet de grille.</span><span class="sxs-lookup"><span data-stu-id="b15bf-137">Click the GridPanel tab.</span></span>
10. <span data-ttu-id="b15bf-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b15bf-138">Close the page.</span></span>

## <a name="verify-the-route-card-journal"></a><span data-ttu-id="b15bf-139">Vérifier le journal des fiches production</span><span class="sxs-lookup"><span data-stu-id="b15bf-139">Verify the route card journal</span></span>
1. <span data-ttu-id="b15bf-140">Cliquez sur Afficher dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="b15bf-140">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="b15bf-141">Cliquez sur Fiche production.</span><span class="sxs-lookup"><span data-stu-id="b15bf-141">Click Route card.</span></span>
3. <span data-ttu-id="b15bf-142">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b15bf-142">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="b15bf-143">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b15bf-143">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b15bf-144">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="b15bf-144">Click Edit.</span></span>
6. <span data-ttu-id="b15bf-145">Dans le champ Heures, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="b15bf-145">In the Hours field, enter a number.</span></span>
7. <span data-ttu-id="b15bf-146">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="b15bf-146">Click Post.</span></span>
8. <span data-ttu-id="b15bf-147">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b15bf-147">Click OK.</span></span>
    * <span data-ttu-id="b15bf-148">Dans le journal des fiches production, le temps passé sur les opérations individuelles est enregistré.</span><span class="sxs-lookup"><span data-stu-id="b15bf-148">In the Route card journal, the time spent on the individual operations is recorded.</span></span> <span data-ttu-id="b15bf-149">Les quantités correctes et erronées peuvent également être déclarées.</span><span class="sxs-lookup"><span data-stu-id="b15bf-149">Good and error quantity can also be reported.</span></span>  


