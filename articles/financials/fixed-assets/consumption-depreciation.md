---
title: Amortissement de consommation
description: "Cet article donne une vue d'ensemble de la méthode de consommation de l'amortissement."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 653c7de18d8227d639d0138201a9ec395b484d2f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="consumption-depreciation"></a><span data-ttu-id="dcc74-103">Amortissement de consommation</span><span class="sxs-lookup"><span data-stu-id="dcc74-103">Consumption depreciation</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="dcc74-104">Cet article donne une vue d'ensemble de la méthode de consommation de l'amortissement.</span><span class="sxs-lookup"><span data-stu-id="dcc74-104">This article gives an overview of the Consumption method of depreciation.</span></span>

<span data-ttu-id="dcc74-105">Si vous paramétrez un profil d'amortissement pour des immobilisations et que vous sélectionnez **Consommation** dans le champ **Méthode** de la page **Profils d'amortissement**, les immobilisations affectées au profil d'amortissement sont basées sur leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="dcc74-105">If you set up a depreciation profile for fixed assets and select **Consumption** in the **Method** field on the **Depreciation profiles** page, fixed assets are assigned to the depreciation profile based on their usage.</span></span> <span data-ttu-id="dcc74-106">Vous n'êtes pas obligé de paramétrer des pourcentages et des intervalles sur la page **Profils d'amortissement**.</span><span class="sxs-lookup"><span data-stu-id="dcc74-106">You don't have to set up percentages and intervals on the **Depreciation profiles** page.</span></span> <span data-ttu-id="dcc74-107">Après avoir créé un profil d'amortissement qui utilise la méthode Consommation, vous pouvez paramétrer la méthode de plusieurs manières.</span><span class="sxs-lookup"><span data-stu-id="dcc74-107">After you create a depreciation profile that uses the Consumption method, you can set up the method in various ways.</span></span>

## <a name="set-up-and-use-consumption-depreciation"></a><span data-ttu-id="dcc74-108">Paramétrage et utilisation de l'amortissement par consommation</span><span class="sxs-lookup"><span data-stu-id="dcc74-108">Set up and use consumption depreciation</span></span>
1.  <span data-ttu-id="dcc74-109">Sur la page **Profils d'amortissement**, créez le profil d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="dcc74-109">On the **Depreciation profiles** page, create the depreciation profile.</span></span> <span data-ttu-id="dcc74-110">Pour les calculs de consommation, le profil d'amortissement doit être doté d'un ID et d'un nom, et vous devez sélectionner **Consommation** dans le champ **Méthode**.</span><span class="sxs-lookup"><span data-stu-id="dcc74-110">For consumption calculations, the depreciation profile must have an ID and a name, and **Consumption** must be selected in the **Method** field.</span></span>
2.  <span data-ttu-id="dcc74-111">Sur la page **Facteurs de consommation**, paramétrez les facteurs de consommation.</span><span class="sxs-lookup"><span data-stu-id="dcc74-111">On the **Consumption factors** page, set up consumption factors.</span></span> <span data-ttu-id="dcc74-112">Chaque facteur de consommation doit être doté d'un ID et d'un nom, ainsi que d'un facteur de consommation spécifié en tant que quantité ou pourcentage.</span><span class="sxs-lookup"><span data-stu-id="dcc74-112">Each consumption factor must have an ID and a name, and a consumption factor that is specified as either a quantity or a percentage.</span></span>
3.  <span data-ttu-id="dcc74-113">Sur la page **Unités de consommation**, paramétrez les unités de consommation.</span><span class="sxs-lookup"><span data-stu-id="dcc74-113">On the **Consumption units** page, set up consumption units.</span></span> <span data-ttu-id="dcc74-114">Chaque unité de consommation doit avoir un ID et un nom.</span><span class="sxs-lookup"><span data-stu-id="dcc74-114">Each consumption unit must have an ID and a name.</span></span> <span data-ttu-id="dcc74-115">Les unités d'amortissement permettent de calculer l'amortissement par consommation sur la page **Amortissement de consommation**.</span><span class="sxs-lookup"><span data-stu-id="dcc74-115">Depreciation units are used to calculate consumption depreciation on the **Consumption depreciation** page.</span></span> <span data-ttu-id="dcc74-116">Exemples d'unités : un kilomètre (km), un kilogramme (kg) ou une heure.</span><span class="sxs-lookup"><span data-stu-id="dcc74-116">Examples of units are kilometer (km), kilogram (kg), and hour.</span></span>
4.  <span data-ttu-id="dcc74-117">Sur la page **Immobilisations**, paramétrez les immobilisations individuelles.</span><span class="sxs-lookup"><span data-stu-id="dcc74-117">On the **Fixed assets** page, set up individual fixed assets.</span></span> <span data-ttu-id="dcc74-118">Pour chaque immobilisation, sélectionnez des modèles de valeurs et des registres des amortissements associés à des profils d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="dcc74-118">For each fixed asset, select value models and depreciation books that have depreciation profiles.</span></span> <span data-ttu-id="dcc74-119">Vous devez paramétrer des modèles de valeur ou des registres des amortissements pour l'amortissement par consommation, si une de vos immobilisations utilise des profils d'amortissement basés sur la méthode Consommation.</span><span class="sxs-lookup"><span data-stu-id="dcc74-119">You must set up value models or depreciation books for consumption depreciation if any of your fixed assets use depreciation profiles that are based on the Consumption method.</span></span> <span data-ttu-id="dcc74-120">Ce paramétrage est effectué soit sous l'onglet **Amortissement** de la page **Modèles de valeur**, soit dans l'organisateur **Général** de la page **Profil d'amortissement**.</span><span class="sxs-lookup"><span data-stu-id="dcc74-120">This setup is done either on the **Depreciation** tab of the **Value models** page or on the **General** FastTab of the **Depreciation profile** page.</span></span> <span data-ttu-id="dcc74-121">Vous pouvez utiliser le même modèle de valeur pour plusieurs immobilisations.</span><span class="sxs-lookup"><span data-stu-id="dcc74-121">You can use the same value model for multiple fixed assets.</span></span> <span data-ttu-id="dcc74-122">Les profils d'amortissement font partie du modèle de valeur ou du registre des amortissements sélectionnés pour chaque immobilisation.</span><span class="sxs-lookup"><span data-stu-id="dcc74-122">Depreciation profiles are part of the value model or depreciation book that you select for each fixed asset.</span></span> <span data-ttu-id="dcc74-123">Vous ne pouvez pas ajouter ni modifier de profils d'amortissement directement sur la page **Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="dcc74-123">You can't add or modify depreciation profiles directly on the **Fixed assets** page.</span></span> <span data-ttu-id="dcc74-124">Vous pouvez modifier les profils d'amortissement uniquement sur la page **Registres des amortissements**.</span><span class="sxs-lookup"><span data-stu-id="dcc74-124">You can modify depreciation profiles only on the **Depreciation books** page.</span></span>
5.  <span data-ttu-id="dcc74-125">Sur la page **Modèles de valeur** ou la page **Registres des amortissements**, dans le groupe de champs **Amortissement de consommation**, renseignez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="dcc74-125">On the **Value models** page or the **Depreciation books** page, in the **Consumption depreciation** field group, enter information in the following fields:</span></span>
    -   <span data-ttu-id="dcc74-126">Facteur de consommation</span><span class="sxs-lookup"><span data-stu-id="dcc74-126">Consumption factor</span></span>
    -   <span data-ttu-id="dcc74-127">Unité</span><span class="sxs-lookup"><span data-stu-id="dcc74-127">Unit</span></span>
    -   <span data-ttu-id="dcc74-128">Amortissement à l'unité</span><span class="sxs-lookup"><span data-stu-id="dcc74-128">Unit depreciation</span></span>
    -   <span data-ttu-id="dcc74-129">Consommation estimée</span><span class="sxs-lookup"><span data-stu-id="dcc74-129">Estimated consumption</span></span>

    <span data-ttu-id="dcc74-130">Le champ**Consommation validée** indique l'amortissement par consommation, en unités, qui a déjà été validé soit pour la combinaison de l'immobilisation et du modèle de valeur, soit pour le registre des amortissements.</span><span class="sxs-lookup"><span data-stu-id="dcc74-130">The **Posted consumption** field shows the consumption depreciation, in units, that has already been posted either for the combination of the fixed asset and value model, or for the depreciation book.</span></span> <span data-ttu-id="dcc74-131">Vous ne pouvez pas mettre à jour manuellement la valeur de ce champ.</span><span class="sxs-lookup"><span data-stu-id="dcc74-131">You can't manually update the value in this field.</span></span>

## <a name="examples"></a><span data-ttu-id="dcc74-132">Exemples</span><span class="sxs-lookup"><span data-stu-id="dcc74-132">Examples</span></span>
### <a name="example-1"></a><span data-ttu-id="dcc74-133">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="dcc74-133">Example 1</span></span>

<span data-ttu-id="dcc74-134">Le facteur de consommation suivant est paramétré pour le 31 janvier :</span><span class="sxs-lookup"><span data-stu-id="dcc74-134">The following consumption factor is set up for January 31:</span></span>

-   <span data-ttu-id="dcc74-135">La quantité est de 1 000.</span><span class="sxs-lookup"><span data-stu-id="dcc74-135">The quantity is 1,000.</span></span>
-   <span data-ttu-id="dcc74-136">Le prix d'amortissement à l'unité spécifié est de 1,5.</span><span class="sxs-lookup"><span data-stu-id="dcc74-136">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>

<span data-ttu-id="dcc74-137">La proposition d'amortissement du 31 janvier est la suivante : Quantité × Amortissement à l'unité 1 000 × 1,5 = 1 500 Si le facteur spécifié pour l'immobilisation est un facteur de pourcentage, la quantité qui est estimée dans le champ **Consommation estimée** pour le modèle de valeur de l'immobilisation est multiplié par le pourcentage paramétré pour la date de fin sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="dcc74-137">The depreciation proposal on January 31 is as follows: Quantity × Unit depreciation 1,000 × 1.5 = 1,500 If the factor that is specified for the fixed asset is a percentage factor, the quantity that is estimated in the **Estimated consumption** field for the value model of the fixed asset is multiplied by the percentage that is set up for the selected end date.</span></span> <span data-ttu-id="dcc74-138">La quantité qui en résulte est ensuite suggérée comme quantité d'amortissement pour la période.</span><span class="sxs-lookup"><span data-stu-id="dcc74-138">The resulting quantity is then suggested as the depreciation quantity for the period.</span></span>

### <a name="example-2"></a><span data-ttu-id="dcc74-139">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="dcc74-139">Example 2</span></span>

<span data-ttu-id="dcc74-140">Le facteur suivant pour l'amortissement par consommation est paramétré pour le 31 janvier :</span><span class="sxs-lookup"><span data-stu-id="dcc74-140">The following factor for consumption depreciation is set up for January 31:</span></span>

-   <span data-ttu-id="dcc74-141">La pourcentage est de 10 pour cent.</span><span class="sxs-lookup"><span data-stu-id="dcc74-141">The percentage is 10 percent.</span></span>
-   <span data-ttu-id="dcc74-142">Le prix d'amortissement à l'unité spécifié est de 1,5.</span><span class="sxs-lookup"><span data-stu-id="dcc74-142">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>
-   <span data-ttu-id="dcc74-143">La quantité estimée de l'immobilisation est de 2 000.</span><span class="sxs-lookup"><span data-stu-id="dcc74-143">The estimated quantity of the fixed asset is 2,000.</span></span>

<span data-ttu-id="dcc74-144">La proposition d'amortissement du 31 janvier est la suivante : Quantité estimée × Pourcentage x Amortissement à l'unité 2 000 × 0,10 × 1,5 = 300</span><span class="sxs-lookup"><span data-stu-id="dcc74-144">The depreciation proposal on January 31 is as follows: Estimated quantity × Percentage × Unit depreciation 2,000 × .10 × 1.5 = 300</span></span>




