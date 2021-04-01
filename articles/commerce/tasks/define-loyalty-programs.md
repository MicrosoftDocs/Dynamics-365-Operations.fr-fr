---
title: Définir les programmes de fidélité
description: Cette procédure décrit comment paramétrer un programme de fidélité à deux niveaux de fidélité.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69424cdaae84ffe5ca8157f061ba5876b9eeeff9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256899"
---
# <a name="define-loyalty-programs"></a><span data-ttu-id="29069-103">Définir les programmes de fidélité</span><span class="sxs-lookup"><span data-stu-id="29069-103">Define loyalty programs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="29069-104">Cette procédure décrit comment paramétrer un programme de fidélité à deux niveaux de fidélité.</span><span class="sxs-lookup"><span data-stu-id="29069-104">This procedure shows how to set up a loyalty program with two loyalty tiers.</span></span> <span data-ttu-id="29069-105">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="29069-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="29069-106">Accédez à Commerce et vente au détail > ..</span><span class="sxs-lookup"><span data-stu-id="29069-106">Go to Retail and Commerce > ..</span></span> <span data-ttu-id="29069-107">> Programmes de fidélité.</span><span class="sxs-lookup"><span data-stu-id="29069-107">> Loyalty programs.</span></span>
2. <span data-ttu-id="29069-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="29069-108">Click New.</span></span>
3. <span data-ttu-id="29069-109">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="29069-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="29069-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="29069-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="29069-111">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="29069-111">Click Add line.</span></span>
6. <span data-ttu-id="29069-112">Dans le champ Niveau, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="29069-112">In the Level field, enter a number.</span></span>
7. <span data-ttu-id="29069-113">Dans le champ Niveau, saisissez un nom pour le niveau de fidélité.</span><span class="sxs-lookup"><span data-stu-id="29069-113">In the Tier field, enter a name for the loyalty tier.</span></span>
8. <span data-ttu-id="29069-114">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="29069-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="29069-115">Dans le champ Intervalle de dates, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="29069-115">In the Date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="29069-116">Cet intervalle de dates doit se prolonger dans le futur.</span><span class="sxs-lookup"><span data-stu-id="29069-116">This date interval should extend into the future.</span></span> <span data-ttu-id="29069-117">Par exemple, si l'intervalle de dates sélectionné pour le niveau Or est une période d'un an, tout client qui se qualifie pour le niveau Or peut recevoir les récompenses affectées au niveau Or pendant une année.</span><span class="sxs-lookup"><span data-stu-id="29069-117">For example, if the date interval that is selected for gold tier is a one-year period, any customer who qualifies for the gold tier can receive the rewards that are assigned to the gold tier for one year.</span></span> <span data-ttu-id="29069-118">Si le client se requalifie pour le niveau Or alors qu'il est dans ce niveau, la date d'expiration du niveau est prolongée d'un an, à compter de la date de nouvelle qualification.</span><span class="sxs-lookup"><span data-stu-id="29069-118">If the customer re-qualifies for the gold tier while they are in the tier, the date that the tier expires is extended by another year from the date when they re-qualify.</span></span>  
10. <span data-ttu-id="29069-119">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="29069-119">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="29069-120">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="29069-120">Click Add line.</span></span>
12. <span data-ttu-id="29069-121">Dans le champ Niveau, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="29069-121">In the Level field, enter a number.</span></span>
13. <span data-ttu-id="29069-122">Dans le champ Niveau, saisissez un nom pour le niveau de fidélité.</span><span class="sxs-lookup"><span data-stu-id="29069-122">In the Tier field, enter a name for the loyalty tier.</span></span>
14. <span data-ttu-id="29069-123">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="29069-123">In the Description field, type a value.</span></span>
15. <span data-ttu-id="29069-124">Dans le champ Intervalle de dates, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="29069-124">In the Date interval field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="29069-125">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="29069-125">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="29069-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="29069-126">Click Save.</span></span>
18. <span data-ttu-id="29069-127">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="29069-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="29069-128">Les règles de niveau définissent le nombre minimal de points de récompense à obtenir sur une période pour se qualifier pour le niveau.</span><span class="sxs-lookup"><span data-stu-id="29069-128">Tier rules define the minimum number of a reward point needed to be earned during a time period to qualify for the tier.</span></span>  
19. <span data-ttu-id="29069-129">Activez ou désactivez l'extension de la section Règles de niveau.</span><span class="sxs-lookup"><span data-stu-id="29069-129">Toggle the expansion of the Tier rules section.</span></span>
20. <span data-ttu-id="29069-130">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="29069-130">Click New.</span></span>
    * <span data-ttu-id="29069-131">Il est possible de définir plusieurs règles de niveau par niveau.</span><span class="sxs-lookup"><span data-stu-id="29069-131">You can have more than one tier rule per tier.</span></span> <span data-ttu-id="29069-132">Par exemple, vous pouvez définir trois critères différents pour obtenir un niveau, en dépensant 500€ sur un mois, en dépensant 1000€ sur un an et en effectuant 20 transactions sur une année.</span><span class="sxs-lookup"><span data-stu-id="29069-132">For example, you could have three different criteria to earn a tier; by spending $500 in one month, by spending $1000 over one year, and by having 20 transactions in one year.</span></span> <span data-ttu-id="29069-133">Pour ce faire, vous devez créer trois règles de niveau.</span><span class="sxs-lookup"><span data-stu-id="29069-133">To do this, you would need to create three tier rules.</span></span>  
21. <span data-ttu-id="29069-134">Dans le champ Point de récompense, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="29069-134">In the Reward point field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="29069-135">Il doit s'agir d'un point de récompense de fidélité non remboursable.</span><span class="sxs-lookup"><span data-stu-id="29069-135">This should be a non-redeemable loyalty reward point.</span></span>  
22. <span data-ttu-id="29069-136">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="29069-136">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="29069-137">Dans le champ Nombre minimal de points émis, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="29069-137">In the Minimum issued points field, enter a number.</span></span>
    * <span data-ttu-id="29069-138">Pour le niveau le plus bas, si tous les clients se qualifient en participant simplement au programme, saisissez « 0 ».</span><span class="sxs-lookup"><span data-stu-id="29069-138">For the lowest level tier, if all customers qualify simply by participating in the program, enter '0'.</span></span>  
24. <span data-ttu-id="29069-139">Dans le champ Intervalle de dates de l'évaluation, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="29069-139">In the Evaluation date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="29069-140">Cet intervalle de dates doit se prolonger dans le passé.</span><span class="sxs-lookup"><span data-stu-id="29069-140">This date interval should extend into the past.</span></span> <span data-ttu-id="29069-141">Seuls les points obtenus durant cet intervalle de dates sont comptabilisés pour atteindre la valeur minimale de points émis.</span><span class="sxs-lookup"><span data-stu-id="29069-141">Only points earned during this date interval will be counted towards reaching the minimum issued points value.</span></span>  
25. <span data-ttu-id="29069-142">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="29069-142">In the list, click the link in the selected row.</span></span>
26. <span data-ttu-id="29069-143">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="29069-143">Click Save.</span></span>
27. <span data-ttu-id="29069-144">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="29069-144">In the list, find and select the desired record.</span></span>
28. <span data-ttu-id="29069-145">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="29069-145">Click New.</span></span>
29. <span data-ttu-id="29069-146">Dans le champ Point de récompense, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="29069-146">In the Reward point field, click the drop-down button to open the lookup.</span></span>
30. <span data-ttu-id="29069-147">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="29069-147">In the list, click the link in the selected row.</span></span>
31. <span data-ttu-id="29069-148">Dans le champ Nombre minimal de points émis, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="29069-148">In the Minimum issued points field, enter a number.</span></span>
32. <span data-ttu-id="29069-149">Dans le champ Intervalle de dates de l'évaluation, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="29069-149">In the Evaluation date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="29069-150">Cet intervalle de dates doit se prolonger dans le passé.</span><span class="sxs-lookup"><span data-stu-id="29069-150">This date interval should extend into the past.</span></span>  
33. <span data-ttu-id="29069-151">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="29069-151">In the list, click the link in the selected row.</span></span>
34. <span data-ttu-id="29069-152">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="29069-152">Click Save.</span></span>
35. <span data-ttu-id="29069-153">Cliquez sur Groupes de prix.</span><span class="sxs-lookup"><span data-stu-id="29069-153">Click Price groups.</span></span>
    * <span data-ttu-id="29069-154">Si vous souhaitez accorder des remises aux clients du programme de fidélité,</span><span class="sxs-lookup"><span data-stu-id="29069-154">If you want to give loyalty customers discounts.</span></span> <span data-ttu-id="29069-155">vous devez affecter un ou plusieurs groupes de prix au programme de fidélité et affecter les groupes de prix aux remises.</span><span class="sxs-lookup"><span data-stu-id="29069-155">you'll need to assign one or more price groups to the loyalty program and assign the price groups to discounts.</span></span> <span data-ttu-id="29069-156">Il est recommandé de ne pas combiner des groupes de prix dans différents types d'entités de remise.</span><span class="sxs-lookup"><span data-stu-id="29069-156">It is a best practice to not mix price groups across different types of discounting entities.</span></span>  <span data-ttu-id="29069-157">Par exemple, n'utilisez pas le même groupe de prix pour une remise de fidélité et une remise de canal.</span><span class="sxs-lookup"><span data-stu-id="29069-157">For example, don't use the same price group for a loyalty discount and a channel discount.</span></span>  
36. <span data-ttu-id="29069-158">Dans le champ Groupe de prix, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="29069-158">In the Price group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="29069-159">Le lien Groupes de prix en haut de la page s'applique au programme de fidélité.</span><span class="sxs-lookup"><span data-stu-id="29069-159">The Price groups link at the top of the page is for the loyalty program.</span></span> <span data-ttu-id="29069-160">Le lien Groupes de prix de l'organisateur Niveaux de programme ne s'applique qu'à un niveau de fidélité spécifique.</span><span class="sxs-lookup"><span data-stu-id="29069-160">The Price groups link in the Program tiers FastTab is for a specific loyalty tier only.</span></span>  
37. <span data-ttu-id="29069-161">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="29069-161">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="29069-162">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="29069-162">Click Save.</span></span>
39. <span data-ttu-id="29069-163">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="29069-163">Close the page.</span></span>
40. <span data-ttu-id="29069-164">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="29069-164">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]