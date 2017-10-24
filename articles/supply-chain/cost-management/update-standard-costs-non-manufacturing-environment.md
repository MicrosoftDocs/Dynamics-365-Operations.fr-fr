---
title: "Mettre à jour des coûts standard dans un environnement hors fabrication"
description: "Cet article fournit des instructions pour mettre à jour les coûts standard dans un environnement hors fabrication."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a61761a5c9d98befd67682e1790af5377b7a55e1
ms.openlocfilehash: 177bdbf76bd776f0d66499865ba121d645109f8c
ms.contentlocale: fr-fr
ms.lasthandoff: 10/13/2017

---

# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a><span data-ttu-id="1be83-103">Mettre à jour des coûts standard dans un environnement hors fabrication</span><span class="sxs-lookup"><span data-stu-id="1be83-103">Update standard costs in a non-manufacturing environment</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="1be83-104">Cet article fournit des instructions pour mettre à jour les coûts standard dans un environnement hors fabrication.</span><span class="sxs-lookup"><span data-stu-id="1be83-104">This article provides guidance for updating standard costs in a non-manufacturing environment.</span></span>

<span data-ttu-id="1be83-105">Les instructions suivantes supposent que vous utilisez une approche à deux versions pour mettre à jour les coûts standard.</span><span class="sxs-lookup"><span data-stu-id="1be83-105">The following guidelines assume that you use a two-version approach to update standard cost.</span></span> <span data-ttu-id="1be83-106">Dans cette approche, une version d'évaluation des coûts contient les coûts standard définis à l'origine pour la période bloquée et l'autre version d'évaluation des coûts contient les mises à jour incrémentielles.</span><span class="sxs-lookup"><span data-stu-id="1be83-106">In this approach, one costing version contains the standard costs that were originally defined for the frozen period, and the second costing version contains the incremental updates.</span></span> <span data-ttu-id="1be83-107">Chaque mise à jour est entrée comme un enregistrement de coûts inclus dans la deuxième version d'évaluation des coûts, avant d'être finalement activée.</span><span class="sxs-lookup"><span data-stu-id="1be83-107">Each update is entered as a cost record that is enclosed in the second costing version, and eventually it's enabled.</span></span> <span data-ttu-id="1be83-108">Une autre approche à une version consiste à utiliser les coûts standard définis à l'origine.</span><span class="sxs-lookup"><span data-stu-id="1be83-108">An alternative, one-version approach uses the set of standard costs that was originally defined.</span></span> <span data-ttu-id="1be83-109">L'approche à deux versions demande que vous définissiez une deuxième version d'évaluation des coûts.</span><span class="sxs-lookup"><span data-stu-id="1be83-109">The two-version approach requires that you define a second costing version.</span></span> <span data-ttu-id="1be83-110">Voici les instructions pour définir cette version d'évaluation des coûts :</span><span class="sxs-lookup"><span data-stu-id="1be83-110">Here are the guidelines for defining this costing version:</span></span>

-   <span data-ttu-id="1be83-111">Affectez un type d'évaluation des **Coûts standard**.</span><span class="sxs-lookup"><span data-stu-id="1be83-111">Assign a costing type of **Standard costs**.</span></span>
-   <span data-ttu-id="1be83-112">Affectez un identificateur significatif qui communique le contenu de la version d'évaluation des coûts, tel que **2016-UPDATES**.</span><span class="sxs-lookup"><span data-stu-id="1be83-112">Assign a meaningful identifier that indicates the contents of the costing version, such as **2016-UPDATES**.</span></span>
-   <span data-ttu-id="1be83-113">Vérifiez que le contenu comprend des enregistrements de coûts.</span><span class="sxs-lookup"><span data-stu-id="1be83-113">Make sure that the content includes cost records.</span></span>
-   <span data-ttu-id="1be83-114">Autorisez la saisie d'enregistrements des coûts à entrer pour tous les sites.</span><span class="sxs-lookup"><span data-stu-id="1be83-114">Allow cost records to be entered for all sites.</span></span> <span data-ttu-id="1be83-115">Si vous spécifiez un site, les enregistrements de coûts peuvent être entrés uniquement pour ce site.</span><span class="sxs-lookup"><span data-stu-id="1be83-115">If you specify a site, cost records can be entered only for that site.</span></span>
-   <span data-ttu-id="1be83-116">Définissez le principe de secours sur **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="1be83-116">Indicate a fallback principle of **None**.</span></span> <span data-ttu-id="1be83-117">Le principe de secours s'applique uniquement aux calculs de coûts des articles fabriqués.</span><span class="sxs-lookup"><span data-stu-id="1be83-117">The fallback principle applies only to cost calculations for manufactured items.</span></span>

<span data-ttu-id="1be83-118">Pour corriger, ajuster ou mettre à jour les coûts standard de nouveaux articles, suivez ces étapes.</span><span class="sxs-lookup"><span data-stu-id="1be83-118">To correct, adjust, or update standard costs for new items, follow these steps.</span></span>

1.  <span data-ttu-id="1be83-119">Utilisez la page **Version d'évaluation des coûts** **paramétrage** pour activer les données de coût à entrer dans la deuxième version d'évaluation des coûts.</span><span class="sxs-lookup"><span data-stu-id="1be83-119">Use the **Costing version** **setup** page to enable cost data to be entered into the second costing version.</span></span> <span data-ttu-id="1be83-120">Empêchez éventuellement l'activation de coûts en attente de manière à ce que l'activation soit autorisée lorsque les coûts en attente ont été entièrement et précisément définis.</span><span class="sxs-lookup"><span data-stu-id="1be83-120">Optionally, prevent the activation of pending costs, so that activation will be allowed after pending costs have been completely and accurately defined.</span></span> <span data-ttu-id="1be83-121">Vous pouvez également éventuellement entrer une date dans le champ **Date de début**.</span><span class="sxs-lookup"><span data-stu-id="1be83-121">You can also optionally enter a date in the **From date** field.</span></span> <span data-ttu-id="1be83-122">En général, utilisez la date qui correspond à la période à laquelle vous souhaitez activer les mises à jour incrémentielles.</span><span class="sxs-lookup"><span data-stu-id="1be83-122">As a general guideline, use the date when you intend to enable the incremental updates.</span></span> <span data-ttu-id="1be83-123">Vous pouvez également laisser le champ **Date de début** vide pour la version d'évaluation des coûts, puis entrez une date dans le champ **Date de début** pour chaque enregistrement de coûts.</span><span class="sxs-lookup"><span data-stu-id="1be83-123">Alternatively, leave the **From date** field blank for the costing version, and then enter a date in the **From date** field for each cost record.</span></span>
2.  <span data-ttu-id="1be83-124">Utilisez la page **Prix de l'article** pour entrer des mises à jour comme les enregistrements de coûts d'article qui sont inclus dans la seconde version d'évaluation des coûts.</span><span class="sxs-lookup"><span data-stu-id="1be83-124">Use the **Item price** page to enter updates as item cost records that are enclosed in the second costing version.</span></span>
3.  <span data-ttu-id="1be83-125">Utilisez l'état **Prix de l'article** pour vérifier que les enregistrements de coûts d'article inclus dans la seconde version d'évaluation des coûts sont complets et exacts.</span><span class="sxs-lookup"><span data-stu-id="1be83-125">Use the **Item prices** report to verify the completeness and accuracy of the item cost records that are enclosed in the second costing version.</span></span>
4.  <span data-ttu-id="1be83-126">Utilisez la page **Mise à jour de la version d'évaluation des coûts** pour modifier la balise de blocage afin d'autoriser l'activation des enregistrements de coûts en attente inclus dans la deuxième version d'évaluation des coûts.</span><span class="sxs-lookup"><span data-stu-id="1be83-126">Use the **Costing version maintenance** page to change the blocking flag to allow activation of the pending cost records that are enclosed in the second costing version.</span></span>
5.  <span data-ttu-id="1be83-127">Utilisez la page **Activer les prix** (que vous pouvez ouvrir à partir de la page **Mise à jour de la version d'évaluation des coûts**) pour activer tous les enregistrements de coûts d'article en attente inclus dans la deuxième version d'évaluation des coûts.</span><span class="sxs-lookup"><span data-stu-id="1be83-127">Use the **Activate prices** page (which you open from the **Costing version maintenance** page) to activate all pending item cost records that are enclosed in the second costing version.</span></span> <span data-ttu-id="1be83-128">Vous pouvez également activer les enregistrements des coûts en attente pour des articles individuels en cliquant sur le bouton **Activer les coûts en attente** dans la page **Prix d'article**.</span><span class="sxs-lookup"><span data-stu-id="1be83-128">You can also activate the pending cost records for individual items by clicking the **Activate pending price** button on the **Item price** page.</span></span>
6.  <span data-ttu-id="1be83-129">Afin d'empêcher toute maintenance des données supplémentaire, utilisez la page **Paramétrage de la version d'évaluation des coûts** pour modifier les balises de blocage incluses dans la deuxième version d'évaluation des coûts.</span><span class="sxs-lookup"><span data-stu-id="1be83-129">To prevent additional data maintenance, use the **Costing version setup** page to change the blocking flags that are enclosed in the second costing version.</span></span> <span data-ttu-id="1be83-130">Les stratégies de blocage empêchent la saisie de nouveaux coûts en attente et l'activation de coûts en attente.</span><span class="sxs-lookup"><span data-stu-id="1be83-130">The blocking policies will prevent the entry of new pending costs and the activation of pending costs.</span></span>





