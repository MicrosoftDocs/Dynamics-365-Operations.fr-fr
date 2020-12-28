---
title: Planification intersociétés
description: Cette rubrique décrit la planification intersociétés et explique comment configurer la planification intersociétés avec l'Optimisation de la planification dans Microsoft Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 25c80ce27498131c6eb92174ab14a592bfa9915a
ms.sourcegitcommit: fe21a3a98dcf6fe4eb9351941493f2c0443d8696
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2020
ms.locfileid: "4672184"
---
# <a name="intercompany-planning"></a><span data-ttu-id="fbe46-103">Planification intersociétés</span><span class="sxs-lookup"><span data-stu-id="fbe46-103">Intercompany planning</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fbe46-104">Pour certaines organisations, les opérations logistiques dépendent d'autres entités juridiques (entreprises) de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="fbe46-104">For some organizations, logistics operations depend on other legal entities (companies) in the organization.</span></span> <span data-ttu-id="fbe46-105">Ces opérations sont gérées en utilisant les ventes et les achats intersociétés, car chaque entité juridique dispose d'un plan comptable distinct.</span><span class="sxs-lookup"><span data-stu-id="fbe46-105">These operations are handled by using intercompany sales and purchases, because each legal entity has a separate chart of accounts.</span></span>

<span data-ttu-id="fbe46-106">Cette rubrique décrit la planification intersociétés et explique comment configurer la planification intersociétés avec l'Optimisation de la planification dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fbe46-106">This topic describes intercompany planning and explains how to configure intercompany planning with Planning Optimization in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="fbe46-107">Cette rubrique utilise les termes intersociétés importants suivants :</span><span class="sxs-lookup"><span data-stu-id="fbe46-107">This topic uses the following important intercompany terms:</span></span>

- <span data-ttu-id="fbe46-108">**En amont** – Une référence relative dans une entreprise ou une chaîne d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="fbe46-108">**Upstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="fbe46-109">Elle indique un mouvement dans la direction du fournisseur de matière première.</span><span class="sxs-lookup"><span data-stu-id="fbe46-109">It indicates movement in the direction of the raw material supplier.</span></span>
- <span data-ttu-id="fbe46-110">**En aval** – Une référence relative dans une entreprise ou une chaîne d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="fbe46-110">**Downstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="fbe46-111">Elle indique un mouvement dans la direction du client.</span><span class="sxs-lookup"><span data-stu-id="fbe46-111">It indicates movement in the direction of the customer.</span></span>
- <span data-ttu-id="fbe46-112">**Demande intersociétés planifiée** – Demande planifiée pour un produit dans une entreprise, basée sur la demande planifiée pour le produit d'une entreprise en aval.</span><span class="sxs-lookup"><span data-stu-id="fbe46-112">**Planned intercompany demand** – Planned demand for a product in a company, based on planned demand for the product from a downstream company.</span></span>

<span data-ttu-id="fbe46-113">Dans la planification, un plan dans une société peut inclure une demande intersociétés planifiée liée à des ordres planifiés d'un plan d'une autre société.</span><span class="sxs-lookup"><span data-stu-id="fbe46-113">In master planning, a plan in one company can include planned intercompany demand that is related to planned orders from a plan in another company.</span></span> <span data-ttu-id="fbe46-114">Cette fonctionnalité est utile, car elle offre une visibilité complète sur les commandes planifiées dans toutes les entreprises.</span><span class="sxs-lookup"><span data-stu-id="fbe46-114">This capability is useful, because it provides full visibility into planned orders across companies.</span></span> <span data-ttu-id="fbe46-115">Elle garantit également que tous les ordres d'approvisionnement planifiés requis sont créés, mais sans exiger que les ordres planifiés soient confirmés pour la demande intersociétés.</span><span class="sxs-lookup"><span data-stu-id="fbe46-115">It also ensures that all required planned supply orders are created, but without requiring that planned orders be firmed for the intercompany demand.</span></span>

<span data-ttu-id="fbe46-116">Si vous exécutez la planification à partir d'un plan directeur qui inclut la demande planifiée en aval, les commandes fournisseur prévisionnelles des fournisseurs intersociétés associés seront incluses dans le plan en tant que demande.</span><span class="sxs-lookup"><span data-stu-id="fbe46-116">If you run master planning from a master plan that includes planned downstream demand, planned purchase orders from the related intercompany vendors will be included in the plan as demand.</span></span>

## <a name="required-setup"></a><span data-ttu-id="fbe46-117">Paramétrage requis</span><span class="sxs-lookup"><span data-stu-id="fbe46-117">Required setup</span></span>

<span data-ttu-id="fbe46-118">Pour utiliser la planification intersociétés, vous devez préparer votre système de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="fbe46-118">To use intercompany planning, you must prepare your system in the following way:</span></span>

1. <span data-ttu-id="fbe46-119">Les produits concernés doivent être commercialisés dans toutes les entreprises concernées.</span><span class="sxs-lookup"><span data-stu-id="fbe46-119">The relevant products must be released in all the relevant companies.</span></span> <span data-ttu-id="fbe46-120">Pour plus d'informations, voir [Configurer et utiliser les transactions intersociétés dans Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) sur Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="fbe46-120">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="fbe46-121">La demande en aval doit être couverte par des achats auprès d'un fournisseur qui a une relation intersociétés avec la société en amont et les dimensions de stock par défaut pertinentes (site et entrepôt) sur le client.</span><span class="sxs-lookup"><span data-stu-id="fbe46-121">Downstream demand must be covered by purchases from a vendor that has an intercompany relation to the upstream company and relevant default inventory dimensions (site and warehouse) on the customer.</span></span> <span data-ttu-id="fbe46-122">Pour plus d'informations, voir [Configurer et utiliser les transactions intersociétés dans Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) sur Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="fbe46-122">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="fbe46-123">Le plan directeur de l'entreprise en amont doit inclure la demande planifiée en aval, et l'entreprise et le plan directeur pertinents doivent être spécifiés dans les plans en aval.</span><span class="sxs-lookup"><span data-stu-id="fbe46-123">The master plan in the upstream company must include planned downstream demand, and the relevant company and master plan must be specified in the downstream plans.</span></span>

## <a name="include-planned-downstream-demand"></a><span data-ttu-id="fbe46-124">Inclure la demande prévisionnelle intersociétés</span><span class="sxs-lookup"><span data-stu-id="fbe46-124">Include planned downstream demand</span></span>

<span data-ttu-id="fbe46-125">Procédez comme suit pour configurer votre plan directeur afin qu'il inclue une prévision de la demande en aval.</span><span class="sxs-lookup"><span data-stu-id="fbe46-125">Follow these steps to configure your master plan so that it includes planned downstream demand.</span></span>

1. <span data-ttu-id="fbe46-126">Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.</span><span class="sxs-lookup"><span data-stu-id="fbe46-126">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="fbe46-127">Sélectionnez ou créez un plan général.</span><span class="sxs-lookup"><span data-stu-id="fbe46-127">Select or create a master plan.</span></span>
1. <span data-ttu-id="fbe46-128">Dans le raccourci **Planification intersociétés**, définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="fbe46-128">On the **Intercompany planning** FastTab, set the following fields:</span></span>

    - <span data-ttu-id="fbe46-129">**Inclure la demande en aval planifiée** – Réglez cette option sur *Oui* pour activer la planification intersociétés pour le plan directeur.</span><span class="sxs-lookup"><span data-stu-id="fbe46-129">**Include planned downstream demand** – Set this option to *Yes* to enable intercompany planning for the master plan.</span></span>
    - <span data-ttu-id="fbe46-130">**Plans en aval** – Si vous définissez l'option **Inclure la demande en aval planifiée** sur *Oui*, utilisez la barre d'outils et la grille pour ajouter les plans directeurs souhaités d'autres entreprises.</span><span class="sxs-lookup"><span data-stu-id="fbe46-130">**Downstream plans** – If you set the **Include planned downstream demand** option to *Yes*, use the toolbar and grid to add the desired master plans from other companies.</span></span>

## <a name="peg-across-companies-by-using-multilevel-pegging"></a><span data-ttu-id="fbe46-131">Choisissez entre les entreprises en utilisant l'origine des besoins à plusieurs niveaux</span><span class="sxs-lookup"><span data-stu-id="fbe46-131">Peg across companies by using multilevel pegging</span></span>

<span data-ttu-id="fbe46-132">Dans l'origine des besoins à plusieurs niveaux, vous pouvez afficher l'origine des besoins entre les entreprises pour voir la source initiale de la demande qui est couverte par une approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="fbe46-132">In multilevel pegging, you can view pegging across companies to see the initial source of demand that is being covered by a supply.</span></span>

<span data-ttu-id="fbe46-133">Pour afficher les informations d'origine des besoins à plusieurs niveaux, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="fbe46-133">To view multilevel pegging information, follow these steps.</span></span>

1. <span data-ttu-id="fbe46-134">Accédez à **Planification \> Planification \> Ordres prévisionnels**.</span><span class="sxs-lookup"><span data-stu-id="fbe46-134">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="fbe46-135">Sélectionnez ou ouvrez un ordre prévisionnel.</span><span class="sxs-lookup"><span data-stu-id="fbe46-135">Select or open a planned order.</span></span>
1. <span data-ttu-id="fbe46-136">Dans le volet Actions, sous l'onglet **Afficher**, dans le groupe **Besoins**, sélectionnez **Origine des besoins à plusieurs niveaux**.</span><span class="sxs-lookup"><span data-stu-id="fbe46-136">On the Action Pane, on the **View** tab, in the **Requirements** group, select **Multilevel pegging**.</span></span>

### <a name="intercompany-example-that-involves-two-companies"></a><span data-ttu-id="fbe46-137">Exemple intersociétés impliquant deux entreprises</span><span class="sxs-lookup"><span data-stu-id="fbe46-137">Intercompany example that involves two companies</span></span>

<span data-ttu-id="fbe46-138">Pour cet exemple, un ordre de fabrication planifié est créé dans la société USMF pour couvrir une commande client dans la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="fbe46-138">For this example, a planned production order is created in the USMF company to cover a sales order in the DEMF company.</span></span> <span data-ttu-id="fbe46-139">Dans USMF, la demande directe est la demande intersociétés planifiée.</span><span class="sxs-lookup"><span data-stu-id="fbe46-139">In USMF, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="fbe46-140">Pour faire apparaître cette demande dans USMF, la planification est d'abord exécutée dans DEMF, puis dans USMF.</span><span class="sxs-lookup"><span data-stu-id="fbe46-140">To make this demand appear in USMF, master planning is run first in DEMF and then in USMF.</span></span>

<span data-ttu-id="fbe46-141">L'illustration suivante montre comment cet exemple peut apparaître sur la page **Origine des besoins à plusieurs niveaux** pour l'ordre de fabrication planifié.</span><span class="sxs-lookup"><span data-stu-id="fbe46-141">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Exemple intersociétés impliquant deux entreprises](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a><span data-ttu-id="fbe46-143">Exemple intersociétés impliquant trois entreprises</span><span class="sxs-lookup"><span data-stu-id="fbe46-143">Intercompany example that involves three companies</span></span>

<span data-ttu-id="fbe46-144">Pour cet exemple, une commande fournisseur prévisionnelle est créé dans la société USMF pour couvrir une commande client dans la société FRRT.</span><span class="sxs-lookup"><span data-stu-id="fbe46-144">For this example, a planned purchase order is created in the USMF company to cover a sales order in the FRRT company.</span></span> <span data-ttu-id="fbe46-145">Dans les sociétés DEMF et USMF, la demande directe est la demande intersociétés planifiée.</span><span class="sxs-lookup"><span data-stu-id="fbe46-145">In the DEMF and USMF companies, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="fbe46-146">Pour faire apparaître cette demande dans USMF, la planification est d'abord exécutée dans FRRT, puis dans DEMF et enfin dans ESMF.</span><span class="sxs-lookup"><span data-stu-id="fbe46-146">To make this demand appear in USMF, master planning is run first in FRRT, then in DEMF, and finally in USMF.</span></span>

<span data-ttu-id="fbe46-147">L'illustration suivante montre comment cet exemple peut apparaître sur la page **Origine des besoins à plusieurs niveaux** pour l'ordre de fabrication planifié.</span><span class="sxs-lookup"><span data-stu-id="fbe46-147">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Exemple intersociétés impliquant trois entreprises](media/IntercompanyPlanning2.png)
