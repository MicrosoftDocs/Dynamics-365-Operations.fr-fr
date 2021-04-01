---
title: Atelier de création de chargement
description: Cette rubrique décrit comment utiliser l’atelier de création de charge.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 480006a6d091acdf5c88fdbf0d9e625088d660d4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247236"
---
# <a name="load-building-workbench"></a><span data-ttu-id="adf55-103">Atelier de création de chargement</span><span class="sxs-lookup"><span data-stu-id="adf55-103">Load building workbench</span></span>

<span data-ttu-id="adf55-104">L’atelier de création de charges vous permet d’appliquer des stratégies de création de charges lorsque vous créez des charges.</span><span class="sxs-lookup"><span data-stu-id="adf55-104">The load building workbench lets you apply load building strategies when you create loads.</span></span>

## <a name="create-a-load-building-strategy"></a><span data-ttu-id="adf55-105">Créer une stratégie de création de chargement</span><span class="sxs-lookup"><span data-stu-id="adf55-105">Create a load building strategy</span></span>

<span data-ttu-id="adf55-106">Vous utilisez des stratégies de création de charges pour créer automatiquement des charges.</span><span class="sxs-lookup"><span data-stu-id="adf55-106">You use load building strategies to automatically build loads.</span></span> <span data-ttu-id="adf55-107">Cette capacité peut être bénéfique dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="adf55-107">This capability can be beneficial in the following situations:</span></span>

- <span data-ttu-id="adf55-108">Si vous expédiez régulièrement un ensemble spécifique de produits, les stratégies de chargement vous permettent de gagner du temps, car vous n’avez pas à créer la même charge à chaque fois.</span><span class="sxs-lookup"><span data-stu-id="adf55-108">If you regularly ship a specific set of products, load strategies help save time, because you don't have to build the same load every time.</span></span>
- <span data-ttu-id="adf55-109">Si vous souhaitez éviter les charges à moitié pleines pour maximiser l’efficacité, les stratégies de charge peuvent aider à remplir chaque charge autant que possible.</span><span class="sxs-lookup"><span data-stu-id="adf55-109">If you want to avoid half-full loads to maximize efficiency, load strategies can help fill each load as much as possible.</span></span>

<span data-ttu-id="adf55-110">Une classe de stratégie de création de charge nommée `TMSLoadBuildingVolumeStrategy` fournit une stratégie de création de charge nommée *Stratégie de création de charge basée sur le volume*.</span><span class="sxs-lookup"><span data-stu-id="adf55-110">A load building strategy class that is named `TMSLoadBuildingVolumeStrategy` provides a load building strategy that is named *Volume-based load building strategy*.</span></span> <span data-ttu-id="adf55-111">Cette stratégie vous permet d’utiliser les valeurs maximales spécifiées pour la hauteur et le poids dans le modèle de chargement, sinon vous pouvez remplacer les paramètres en entrant de nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="adf55-111">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="adf55-112">Cette stratégie est la seule stratégie qui est incluse prête à l’emploi.</span><span class="sxs-lookup"><span data-stu-id="adf55-112">This strategy is the only strategy that is included out of the box.</span></span> <span data-ttu-id="adf55-113">(Cependant, vous pouvez avoir des stratégies personnalisées.)</span><span class="sxs-lookup"><span data-stu-id="adf55-113">(However, you might have some custom strategies.)</span></span>

<span data-ttu-id="adf55-114">Pour utiliser la *Stratégie de création de charge basée sur le volume* prête à l’emploi, sélectionnez-la dans le champ **Stratégie de construction de charge** sur la page **Atelier de création de chargement** (**Gestion des transports &gt; Planification &gt; Atelier de création de chargement**).</span><span class="sxs-lookup"><span data-stu-id="adf55-114">To use the out-of-box *Volume-based load building strategy* strategy, select it in the **Load building strategy** field on the **Load building workbench** page (**Transportation management &gt; Planning &gt; Load building workbench**).</span></span>

<span data-ttu-id="adf55-115">Pour créer une stratégie de création de chargement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="adf55-115">To create a load building strategy, follow these steps.</span></span>

1. <span data-ttu-id="adf55-116">Aller à **Gestion des transports &gt; Configurer &gt; Création de charge &gt; Stratégies de création de charge**.</span><span class="sxs-lookup"><span data-stu-id="adf55-116">Go to **Transportation management &gt; Setup &gt; Load building &gt; Load building strategies**.</span></span>
1. <span data-ttu-id="adf55-117">Dans le volet Actions, sélectionnez **Générer une liste de classes** pour vous assurer que vous disposez des dernières versions de toutes les classes disponibles.</span><span class="sxs-lookup"><span data-stu-id="adf55-117">On the Action Pane, select **Generate class list** to make sure that you have the latest versions of all available classes.</span></span>
1. <span data-ttu-id="adf55-118">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="adf55-118">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="adf55-119">Saisissez un nom unique pour la stratégie, sélectionnez la classe de stratégie de création de charge correspondante et saisissez une description.</span><span class="sxs-lookup"><span data-stu-id="adf55-119">Enter a unique name for the strategy, select the load building strategy class for it, and enter a description.</span></span>
1. <span data-ttu-id="adf55-120">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="adf55-120">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="adf55-121">Sélectionnez **Paramètres** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="adf55-121">On the Action Pane, select **Parameters**.</span></span>
1. <span data-ttu-id="adf55-122">Sur la page **Paramètres de stratégie de création de charge**, sélectionnez **Capacité de volume** dans la liste, puis, dans le champ **Valeur**, entrez le pourcentage de la capacité volumique totale de la charge qui doit être appliqué pour la nouvelle stratégie de création de charge.</span><span class="sxs-lookup"><span data-stu-id="adf55-122">On the **Load building strategy parameters** page, select **Volume capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total volume capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="adf55-123">Sélectionnez **Capacité de poids** dans la liste, puis, dans le champ **Valeur**, entrez le pourcentage de la capacité de poids totale de la charge qui doit être appliqué pour la nouvelle stratégie de création de charge.</span><span class="sxs-lookup"><span data-stu-id="adf55-123">Select **Weight capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total weight capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="adf55-124">Fermez la page **Paramètres de stratégie de création de charge**.</span><span class="sxs-lookup"><span data-stu-id="adf55-124">Close the **Load building strategy parameters** page.</span></span>
1. <span data-ttu-id="adf55-125">Fermez la page **Stratégie de création de charge**.</span><span class="sxs-lookup"><span data-stu-id="adf55-125">Close the **Load building strategies** page.</span></span>

<span data-ttu-id="adf55-126">Vous pouvez maintenant affecter la stratégie de création de charge à un modèle de création de charge.</span><span class="sxs-lookup"><span data-stu-id="adf55-126">You can now assign the load building strategy to a load building template.</span></span> <span data-ttu-id="adf55-127">Vous pouvez également l’utiliser directement dans l’atelier de planification de la charge.</span><span class="sxs-lookup"><span data-stu-id="adf55-127">Alternatively, you can use it directly in the load planning workbench.</span></span>

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a><span data-ttu-id="adf55-128">Utilisez une stratégie de création de charge dans l’atelier de création de charge</span><span class="sxs-lookup"><span data-stu-id="adf55-128">Use a load building strategy in the load building workbench</span></span>

1. <span data-ttu-id="adf55-129">Accédez à **Gestion du transport &gt; Planification &gt; Atelier de création de charge**.</span><span class="sxs-lookup"><span data-stu-id="adf55-129">Go to **Transportation management &gt; Planning &gt; Load building workbench**.</span></span>
1. <span data-ttu-id="adf55-130">Utilisez l’une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="adf55-130">Follow one of these steps:</span></span>

    - <span data-ttu-id="adf55-131">Sélectionnez une stratégie dans le champ **Stratégie de création de charge**.</span><span class="sxs-lookup"><span data-stu-id="adf55-131">Select a strategy in the **Load building strategy** field.</span></span>
    - <span data-ttu-id="adf55-132">Si vous avez défini un modèle de création de charge et lui avez attribué la stratégie de création de charge, dans le volet Actions, sur l’onglet **Gérer les modèles**, sélectionnez **Appliquer le modèle**.</span><span class="sxs-lookup"><span data-stu-id="adf55-132">If you've defined a load building template and assigned the load building strategy to it, on the Action Pane, on the **Manage templates** tab, select **Apply template**.</span></span> <span data-ttu-id="adf55-133">Puis, dans la boîte de dialogue déroulante **Appliquer le modèle de création de charge**, sélectionnez un modèle dans le champ **Nom du modèle de création de charge**.</span><span class="sxs-lookup"><span data-stu-id="adf55-133">Then, in the **Apply load building template** drop-down dialog box, select a template in the **Load building template name** field.</span></span>

1. <span data-ttu-id="adf55-134">Sur le raccourci **Séquence des modèles de charges**, sélectionnez un ou plusieurs [modèles de charges](load-template.md).</span><span class="sxs-lookup"><span data-stu-id="adf55-134">On the **Load templates sequence** FastTab, select one or more [load templates](load-template.md).</span></span> <span data-ttu-id="adf55-135">L’atelier essaiera d’adapter la charge dans ces types de conteneurs, dans l’ordre spécifié ici.</span><span class="sxs-lookup"><span data-stu-id="adf55-135">The workbench will try to fit the load into these types of containers, in the sequence that is specified here.</span></span> <span data-ttu-id="adf55-136">En règle générale, vous devez placer les plus petits conteneurs en haut de la liste pour vous assurer que le plus petit conteneur possible est sélectionné en premier.</span><span class="sxs-lookup"><span data-stu-id="adf55-136">Typically, you should put the smallest containers at the top of the list to ensure that the smallest possible container is selected first.</span></span>
1. <span data-ttu-id="adf55-137">Dans le volet Actions, sélectionnez **Proposer des charges**.</span><span class="sxs-lookup"><span data-stu-id="adf55-137">On the Action Pane, select **Propose loads**.</span></span>
1. <span data-ttu-id="adf55-138">Passez en revue les charges proposées et les lignes de charge proposées.</span><span class="sxs-lookup"><span data-stu-id="adf55-138">Review the proposed loads and proposed load lines.</span></span>
1. <span data-ttu-id="adf55-139">Dans le volet Actions, sélectionnez **Créer des charges** pour créer des charges basées sur les lignes du document source sur le raccourci **Lignes de charge proposées**.</span><span class="sxs-lookup"><span data-stu-id="adf55-139">On the Action Pane, select **Create loads** to create loads that are based on the source document lines on the **Proposed load lines** FastTab.</span></span>
1. <span data-ttu-id="adf55-140">Fermez la page **Atelier de création de charge**.</span><span class="sxs-lookup"><span data-stu-id="adf55-140">Close the **Load building workbench** page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]