---
title: Créer des états de consommation
description: Cette rubrique explique comment créer des états de consommation dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d28acbccc35b3f59f9cca7236dd721a1d9bdead8
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216434"
---
# <a name="create-consumption-reports"></a><span data-ttu-id="50c17-103">Créer des états de consommation</span><span class="sxs-lookup"><span data-stu-id="50c17-103">Create consumption reports</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="50c17-104">Lorsque vous avez créé et validé les enregistrements de consommation sur les ordres de travail dans le module Gestion des actifs, deux états sont disponibles pour afficher les détails de la consommation.</span><span class="sxs-lookup"><span data-stu-id="50c17-104">When you've created and posted consumption registrations on work orders in Asset Management, two reports are available to display consumption details.</span></span>


## <a name="asset-consumption-report"></a><span data-ttu-id="50c17-105">État relatif à la consommation des actifs</span><span class="sxs-lookup"><span data-stu-id="50c17-105">Asset consumption report</span></span>

<span data-ttu-id="50c17-106">Lorsque vous avez validé la consommation sur les ordres de travail, vous pouvez imprimer un état relatif à la consommation des actifs.</span><span class="sxs-lookup"><span data-stu-id="50c17-106">When you have posted consumption on work orders, you can print an asset consumption report.</span></span> <span data-ttu-id="50c17-107">L'état affiche les heures, le coût des heures, le coût des articles, et les dépenses validées sur des actifs.</span><span class="sxs-lookup"><span data-stu-id="50c17-107">The report displays hours, hour costs, item costs, and expenses posted on assets.</span></span>

1. <span data-ttu-id="50c17-108">Cliquez sur **Gestion des actifs** > **États** > **Actifs** > **Consommation d'actifs**.</span><span class="sxs-lookup"><span data-stu-id="50c17-108">Click **Asset management** > **Reports** > **Assets** > **Asset consumption**.</span></span>

2. <span data-ttu-id="50c17-109">Dans la boîte de dialogue **Consommation d'actifs**, sélectionnez les paramètres et le niveau de détail que vous souhaitez afficher en sélectionnant **Oui** sur les boutons bascule appropriés, puis en entrant le niveau du poste technique dans la section **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="50c17-109">In the **Asset consumption** dialog, select the parameters and detail level you want to see by selecting **Yes** on the relevant toggle buttons, and inserting a functional location level in the **Show** section.</span></span>
    - <span data-ttu-id="50c17-110">Vous pouvez utiliser le champ **Niveaux** pour indiquer quel niveau de détail vous souhaitez dans les lignes d'actif en fonction des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="50c17-110">You can use the **Levels** field to indicate how detailed you want the asset lines to be regarding functional locations.</span></span> 
    
        <span data-ttu-id="50c17-111">Par exemple, si vous entrez le chiffre « 1 » dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, tous les actifs pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter une ligne à partir des postes techniques situés à un niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="50c17-111">For example, if you enter the number "1" in the field, and you have a multi-level functional location structure, all assets for a functional location will be shown on the top level, and therefore a line may be added up from functional locations located at a lower level.</span></span> 
        
        <span data-ttu-id="50c17-112">Par exemple, si vous entrez le chiffre « 0 » dans le champ **Niveaux**, un résultat détaillé s'affiche et indique tous les actifs sur tous les niveaux du poste technique auxquels ils sont liés.</span><span class="sxs-lookup"><span data-stu-id="50c17-112">If you enter the number "0" in the **Levels** field, you will see a detailed result showing all assets on all the functional location levels to which they are related.</span></span> 
        
    - <span data-ttu-id="50c17-113">Sélectionnez **Oui** sur le bouton bascule **Somme de tous les sous-actifs** pour afficher les sommes des chaque sous-actif de l'état.</span><span class="sxs-lookup"><span data-stu-id="50c17-113">Select **Yes** on the **Sum on all sub assets** toggle button to see sums for each sub asset in the report.</span></span>

3. <span data-ttu-id="50c17-114">Sélectionnez un intervalle de dates dans la section **Dates**.</span><span class="sxs-lookup"><span data-stu-id="50c17-114">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="50c17-115">Dans l'organisateur **Destination**, indiquez si vous souhaitez afficher l'état à l'écran, l'imprimer ou l'enregistrer en tant que fichier ou e-mail.</span><span class="sxs-lookup"><span data-stu-id="50c17-115">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="50c17-116">Si nécessaire, vous pouvez sélectionner des actifs spécifiques à afficher dans l'état.</span><span class="sxs-lookup"><span data-stu-id="50c17-116">If required, you can select specific assets to be displayed in the report.</span></span> <span data-ttu-id="50c17-117">Dans l'organisateur **Enregistrements à inclure**, cliquez sur **Filtre**, puis ajoutez des actifs à inclure dans l'état.</span><span class="sxs-lookup"><span data-stu-id="50c17-117">On the **Records to include** FastTab, click **Filter**, and add the assets you want to include in the report.</span></span>

6. <span data-ttu-id="50c17-118">Cliquez sur **OK** pour générer l'état.</span><span class="sxs-lookup"><span data-stu-id="50c17-118">Click **OK** to generate the report.</span></span>


## <a name="work-order-consumption-report"></a><span data-ttu-id="50c17-119">État de consommation de l'ordre de travail</span><span class="sxs-lookup"><span data-stu-id="50c17-119">Work order consumption report</span></span>

<span data-ttu-id="50c17-120">Lorsque vous avez validé la consommation sur les ordres de travail, vous pouvez imprimer un état relatif à cette consommation.</span><span class="sxs-lookup"><span data-stu-id="50c17-120">When you have posted consumption on work orders, you can print a work order consumption report.</span></span> <span data-ttu-id="50c17-121">L'état affiche les heures, le coût des heures, le coût des articles, et les dépenses validées sur des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="50c17-121">The report displays hours, hour costs, item costs, and expenses posted on work orders.</span></span>

1. <span data-ttu-id="50c17-122">Cliquez sur **Gestion des actifs** > **États** > **Ordres de travail** > **Consommation de l'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="50c17-122">Click **Asset management** > **Reports** > **Work orders** > **Work order consumption**.</span></span>

2. <span data-ttu-id="50c17-123">Dans la boîte de dialogue **Consommation de l'ordre de travail**, sélectionnez les paramètres que vous souhaitez inclure dans l'état en sélectionnant **Oui** sur les boutons à bascule dans la section **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="50c17-123">In the **Work order consumption** dialog, select the parameters you want to include in the report by selecting **Yes** on the relevant toggle buttons in the **Show** section.</span></span>

3. <span data-ttu-id="50c17-124">Sélectionnez un intervalle de dates dans la section **Dates**.</span><span class="sxs-lookup"><span data-stu-id="50c17-124">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="50c17-125">Dans l'organisateur **Destination**, indiquez si vous souhaitez afficher l'état à l'écran, l'imprimer ou l'enregistrer en tant que fichier ou e-mail.</span><span class="sxs-lookup"><span data-stu-id="50c17-125">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="50c17-126">Si nécessaire, vous pouvez sélectionner des ordres de travail spécifiques à afficher dans l'état.</span><span class="sxs-lookup"><span data-stu-id="50c17-126">If required, you can select specific work orders to be displayed in the report.</span></span> <span data-ttu-id="50c17-127">Dans l'organisateur **Enregistrements à inclure**, cliquez sur **Filtre**, puis ajoutez des ordres de travail à inclure dans l'état.</span><span class="sxs-lookup"><span data-stu-id="50c17-127">On the **Records to include** FastTab, click **Filter**, and add the work orders you want to include in the report.</span></span>

6. <span data-ttu-id="50c17-128">Cliquez sur **OK** pour générer l'état.</span><span class="sxs-lookup"><span data-stu-id="50c17-128">Click **OK** to generate the report.</span></span>


>[!NOTE]
><span data-ttu-id="50c17-129">Vous pouvez également générer un [état d'ordre de travail](../work-orders/work-order-report.md), qui contient plus de détails sur les ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="50c17-129">You can also generate a [work order report](../work-orders/work-order-report.md), which contains more work order details.</span></span>

