---
title: Démarrer un ordre de fabrication
description: Cette procédure indique comment démarrer un ordre de fabrication à l'atelier.
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e770c905079461c1f4f0117f61f6c10b86ddaf6
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146604"
---
# <a name="start-a-production-order"></a><span data-ttu-id="c6730-103">Démarrer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="c6730-103">Start a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c6730-104">Cette procédure indique comment démarrer un ordre de fabrication à l'atelier.</span><span class="sxs-lookup"><span data-stu-id="c6730-104">This procedure shows how to start a production order on the shop floor.</span></span> <span data-ttu-id="c6730-105">La consommation de matières et de temps est déclarée dans ce processus.</span><span class="sxs-lookup"><span data-stu-id="c6730-105">Time and material consumption are reported in this process.</span></span> <span data-ttu-id="c6730-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="c6730-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c6730-107">Il s'agit de la cinquième des sept procédures expliquant le cycle de vie de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="c6730-107">This is the fifth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="start-a-production-order"></a><span data-ttu-id="c6730-108">Démarrer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="c6730-108">Start a production order</span></span>
1. <span data-ttu-id="c6730-109">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="c6730-109">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="c6730-110">Sélectionnez un ordre de fabrication ayant le statut Lancé.</span><span class="sxs-lookup"><span data-stu-id="c6730-110">Select a production order that has the Released status.</span></span>  
2. <span data-ttu-id="c6730-111">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="c6730-111">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="c6730-112">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="c6730-112">Click Start.</span></span>
    * <span data-ttu-id="c6730-113">Dans cette page, vous pouvez confirmer le début de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="c6730-113">On this page, you can confirm the start of the production order.</span></span>  
4. <span data-ttu-id="c6730-114">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="c6730-114">Click the General tab.</span></span>
5. <span data-ttu-id="c6730-115">Dans le champ Du n° opér.,</span><span class="sxs-lookup"><span data-stu-id="c6730-115">In the From Oper.</span></span> <span data-ttu-id="c6730-116">N°</span><span class="sxs-lookup"><span data-stu-id="c6730-116">No.</span></span> <span data-ttu-id="c6730-117">entrez 10.</span><span class="sxs-lookup"><span data-stu-id="c6730-117">field, enter '10'.</span></span>
6. <span data-ttu-id="c6730-118">Dans le champ Consommation de gamme automatique, sélectionnez « Toujours ».</span><span class="sxs-lookup"><span data-stu-id="c6730-118">In the Automatic route consumption field, select 'Always'.</span></span>
7. <span data-ttu-id="c6730-119">Cochez la case Valider fiche production maintenant.</span><span class="sxs-lookup"><span data-stu-id="c6730-119">Click the Post route card now checkbox.</span></span>
8. <span data-ttu-id="c6730-120">Dans le champ Consommation de nomenclature automatique, sélectionnez « Toujours ».</span><span class="sxs-lookup"><span data-stu-id="c6730-120">In the Automatic BOM consumption field, select 'Always'.</span></span>
9. <span data-ttu-id="c6730-121">Cochez la case Valider les prélèvements maintenant.</span><span class="sxs-lookup"><span data-stu-id="c6730-121">Click the Post picking list now checkbox.</span></span>
10. <span data-ttu-id="c6730-122">Cochez la case Imprimer les prélèvements.</span><span class="sxs-lookup"><span data-stu-id="c6730-122">Click the Print picking list checkbox.</span></span>
11. <span data-ttu-id="c6730-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c6730-123">Click OK.</span></span>
    * <span data-ttu-id="c6730-124">Il s'agit de la liste de prélèvements imprimée qui indique les matières utilisées pour l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="c6730-124">This is the printed picking list that shows the materials used for the production order.</span></span>  
12. <span data-ttu-id="c6730-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c6730-125">Close the page.</span></span>

## <a name="validate-the-picking-list"></a><span data-ttu-id="c6730-126">Valider les prélèvements.</span><span class="sxs-lookup"><span data-stu-id="c6730-126">Validate the picking list</span></span>
1. <span data-ttu-id="c6730-127">Cliquez sur Afficher dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="c6730-127">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="c6730-128">Cliquez sur Prélèvements.</span><span class="sxs-lookup"><span data-stu-id="c6730-128">Click Picking list.</span></span>
3. <span data-ttu-id="c6730-129">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c6730-129">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="c6730-130">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c6730-130">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="c6730-131">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="c6730-131">Click Edit.</span></span>
6. <span data-ttu-id="c6730-132">Entrez un nombre dans le champ Consommation.</span><span class="sxs-lookup"><span data-stu-id="c6730-132">In the Consumption field, enter a number.</span></span>
7. <span data-ttu-id="c6730-133">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="c6730-133">Click Post.</span></span>
8. <span data-ttu-id="c6730-134">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c6730-134">Click OK.</span></span>
    * <span data-ttu-id="c6730-135">Dans le journal des prélèvements, les matières consommées par l'ordre de fabrication sont validées.</span><span class="sxs-lookup"><span data-stu-id="c6730-135">In the picking list journal, the materials consumed by the production order are posted.</span></span> <span data-ttu-id="c6730-136">Avant de valider le journal, vous pouvez procéder à des ajustements s'il existe une différence entre la quantité estimée et la quantité réelle consommée.</span><span class="sxs-lookup"><span data-stu-id="c6730-136">Before posting the journal, you can make adjustments if there is a difference between the estimated quantity and the actual consumed quantity.</span></span>  
9. <span data-ttu-id="c6730-137">Cliquez sur l'onglet Volet de grille.</span><span class="sxs-lookup"><span data-stu-id="c6730-137">Click the GridPanel tab.</span></span>
10. <span data-ttu-id="c6730-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c6730-138">Close the page.</span></span>

## <a name="verify-the-route-card-journal"></a><span data-ttu-id="c6730-139">Vérifier le journal des fiches production</span><span class="sxs-lookup"><span data-stu-id="c6730-139">Verify the route card journal</span></span>
1. <span data-ttu-id="c6730-140">Cliquez sur Afficher dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="c6730-140">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="c6730-141">Cliquez sur Fiche production.</span><span class="sxs-lookup"><span data-stu-id="c6730-141">Click Route card.</span></span>
3. <span data-ttu-id="c6730-142">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c6730-142">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="c6730-143">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c6730-143">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="c6730-144">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="c6730-144">Click Edit.</span></span>
6. <span data-ttu-id="c6730-145">Dans le champ Heures, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="c6730-145">In the Hours field, enter a number.</span></span>
7. <span data-ttu-id="c6730-146">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="c6730-146">Click Post.</span></span>
8. <span data-ttu-id="c6730-147">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c6730-147">Click OK.</span></span>
    * <span data-ttu-id="c6730-148">Dans le journal des fiches production, le temps passé sur les opérations individuelles est enregistré.</span><span class="sxs-lookup"><span data-stu-id="c6730-148">In the Route card journal, the time spent on the individual operations is recorded.</span></span> <span data-ttu-id="c6730-149">Les quantités correctes et erronées peuvent également être déclarées.</span><span class="sxs-lookup"><span data-stu-id="c6730-149">Good and error quantity can also be reported.</span></span>  
