---
title: Créer une version de flux de production
description: Cette procédure est orientée vers la création d'une nouvelle version de flux de production.
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da3b77ed459f42ef91d64066b18b07fece9efc8f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212133"
---
# <a name="create-a-production-flow-version"></a><span data-ttu-id="4c18b-103">Créer une version de flux de production</span><span class="sxs-lookup"><span data-stu-id="4c18b-103">Create a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4c18b-104">Cette procédure est orientée vers la création d'une nouvelle version de flux de production.</span><span class="sxs-lookup"><span data-stu-id="4c18b-104">This procedure focuses on creating a new production flow version.</span></span> <span data-ttu-id="4c18b-105">Pour cette procédure, les paramètres de production pour la lean manufacturing et les unités de mesure du temps des classes doivent être définis.</span><span class="sxs-lookup"><span data-stu-id="4c18b-105">For this procedure, the production parameters for lean manufacturing and the units of measurement for class time must be defined.</span></span> <span data-ttu-id="4c18b-106">Vous devez également définir une chaîne de valeur et un groupe de production.</span><span class="sxs-lookup"><span data-stu-id="4c18b-106">You also need to define a value stream and a production group.</span></span> <span data-ttu-id="4c18b-107">Pour plus d'informations sur les flux de production et des activités en lean manufacturing, consultez les livres blancs sur la Lean manufacturing pour Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="4c18b-107">To learn more about production flows and activities in lean manufacturing, see the white papers on Lean manufacturing for Microsoft Dynamics AX.</span></span> <span data-ttu-id="4c18b-108">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="4c18b-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="4c18b-109">Création d'un flux de production</span><span class="sxs-lookup"><span data-stu-id="4c18b-109">Create a production flow</span></span>
1. <span data-ttu-id="4c18b-110">Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.</span><span class="sxs-lookup"><span data-stu-id="4c18b-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="4c18b-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4c18b-111">Click New.</span></span>
3. <span data-ttu-id="4c18b-112">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="4c18b-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="4c18b-113">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4c18b-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="4c18b-114">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4c18b-114">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="4c18b-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4c18b-115">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4c18b-116">Sélectionnez une unité opérationnelle du type chaîne de valeur.</span><span class="sxs-lookup"><span data-stu-id="4c18b-116">Select an operating unit of type value stream.</span></span> <span data-ttu-id="4c18b-117">Une chaîne de valeur est une unité opérationnelle qui couvre tous les activités et flux de la chaîne de valeur.</span><span class="sxs-lookup"><span data-stu-id="4c18b-117">A value stream is an operating unit that spans all activities and flows of the value stream.</span></span> <span data-ttu-id="4c18b-118">À ce stade, les unités opérationnelles sont limitées à une entité juridique et n'ont aucune fonctionnalité supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="4c18b-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="4c18b-119">Dans le champ Groupe de production, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4c18b-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="4c18b-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4c18b-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4c18b-121">Sélectionnez un groupe de production pour le flux de production.</span><span class="sxs-lookup"><span data-stu-id="4c18b-121">Select a production group for the production flow.</span></span> <span data-ttu-id="4c18b-122">Les groupes de production permettent de définir les matières, le travail, et les comptes de travaux en cours pour un processus de production.</span><span class="sxs-lookup"><span data-stu-id="4c18b-122">Production groups allow the definition of material, labor, and WIP accounts for a production process.</span></span> <span data-ttu-id="4c18b-123">Pour associer le contexte de comptabilité à un flux de production, il convient de créer un groupe de production.</span><span class="sxs-lookup"><span data-stu-id="4c18b-123">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="4c18b-124">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="4c18b-124">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="4c18b-125">Créer une version de flux de production</span><span class="sxs-lookup"><span data-stu-id="4c18b-125">Create a production flow version</span></span>
1. <span data-ttu-id="4c18b-126">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="4c18b-126">Click Add.</span></span>
2. <span data-ttu-id="4c18b-127">Entrez une date et une heure dans le champ Date d'expiration.</span><span class="sxs-lookup"><span data-stu-id="4c18b-127">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="4c18b-128">Si nécessaire, définissez une date d'expiration de la version.</span><span class="sxs-lookup"><span data-stu-id="4c18b-128">If required, define an Expiration date for the version.</span></span> <span data-ttu-id="4c18b-129">Vous pouvez la mettre à jour à tout moment, même pour les versions actives.</span><span class="sxs-lookup"><span data-stu-id="4c18b-129">You can update it at any given time, even for active versions.</span></span> <span data-ttu-id="4c18b-130">Vous pouvez l'utiliser pour planifier l'élimination d'une version.</span><span class="sxs-lookup"><span data-stu-id="4c18b-130">You can use it to plan to phase out a version.</span></span>  
3. <span data-ttu-id="4c18b-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4c18b-131">Click OK.</span></span>
4. <span data-ttu-id="4c18b-132">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4c18b-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="4c18b-133">Dans le champ Unité, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4c18b-133">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="4c18b-134">Résolvez les modifications de l'unité de Takt.</span><span class="sxs-lookup"><span data-stu-id="4c18b-134">ResolveChanges the Takt unit.</span></span>
7. <span data-ttu-id="4c18b-135">Dans le champ Takt time moyen, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="4c18b-135">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="4c18b-136">Définissez le takt time moyen de la version.</span><span class="sxs-lookup"><span data-stu-id="4c18b-136">Define the Average takt time of the version.</span></span> <span data-ttu-id="4c18b-137">Pour le contrôle takt de la version du flux de production, définissez un takt time moyen cible.</span><span class="sxs-lookup"><span data-stu-id="4c18b-137">For the takt control of the production flow version, define a targeted average takt time.</span></span> <span data-ttu-id="4c18b-138">Le takt est défini comme une quantité par période.</span><span class="sxs-lookup"><span data-stu-id="4c18b-138">The takt is defined as quantity per time period.</span></span> <span data-ttu-id="4c18b-139">Dans l'exemple, le takt time est de 0,2 heures par 10 pièces.</span><span class="sxs-lookup"><span data-stu-id="4c18b-139">In the example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="4c18b-140">Pour une durée de travail de 8 heures, cela correspond à une capacité de production journalière de 400 pièces.</span><span class="sxs-lookup"><span data-stu-id="4c18b-140">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="4c18b-141">Entrez un numéro dans le champ Quantité par cycle.</span><span class="sxs-lookup"><span data-stu-id="4c18b-141">In the Quantity per cycle field, enter a number.</span></span>
    * <span data-ttu-id="4c18b-142">Définissez la quantité par cycle liée au takt time moyen.</span><span class="sxs-lookup"><span data-stu-id="4c18b-142">Define the quantity per cycle related to the Average takt time.</span></span>  
9. <span data-ttu-id="4c18b-143">Activez ou désactivez l'extension de la section Détails de la version.</span><span class="sxs-lookup"><span data-stu-id="4c18b-143">Toggle the expansion of the Version details section.</span></span>
10. <span data-ttu-id="4c18b-144">Dans le champ Takt time minimal, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="4c18b-144">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="4c18b-145">Définissez le takt time minimal.</span><span class="sxs-lookup"><span data-stu-id="4c18b-145">Define the minimum takt time.</span></span> <span data-ttu-id="4c18b-146">Le takt time minimal doit être inférieur ou égal au takt time moyen.</span><span class="sxs-lookup"><span data-stu-id="4c18b-146">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="4c18b-147">Dans le champ Takt time maximal, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="4c18b-147">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="4c18b-148">Le takt time maximal doit être supérieur ou égal au takt time moyen.</span><span class="sxs-lookup"><span data-stu-id="4c18b-148">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="4c18b-149">Entrez un nombre dans le champ Période pour la durée de cycle réelle (jours).</span><span class="sxs-lookup"><span data-stu-id="4c18b-149">In the Period for actual cycle time (days) field, enter a number.</span></span>
    * <span data-ttu-id="4c18b-150">Entrez le nombre de jours dans la période pour la durée de cycle réelle.</span><span class="sxs-lookup"><span data-stu-id="4c18b-150">Enter the number of days in the Period for actual cycle time.</span></span> <span data-ttu-id="4c18b-151">La période pour la durée de cycle réelle est le nombre de jours pendant lesquels les tâches sont regroupées à rebours à partir de la minute actuelle pour calculer la durée de cycle réelle.</span><span class="sxs-lookup"><span data-stu-id="4c18b-151">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="4c18b-152">Cette valeur peut être modifiée à tout moment et n'est utilisée que pour le calcul des durées de cycle réelles.</span><span class="sxs-lookup"><span data-stu-id="4c18b-152">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="4c18b-153">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="4c18b-153">Click Save.</span></span>

