---
title: Créer des canaux de centre d'appels et définir les attributs de canal
description: Cette procédure décrit la création d'un canal et la définition des attributs de canal.
author: mugunthanm
manager: AnnBe
ms.date: 05/22/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a2f99029195a8b783f0d12990d4e8bab0bb348d7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412314"
---
# <a name="create-call-center-channels-and-define-channel-attributes"></a><span data-ttu-id="9a539-103">Créer des canaux de centre d'appels et définir les attributs de canal</span><span class="sxs-lookup"><span data-stu-id="9a539-103">Create call center channels and define channel attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a539-104">Cette procédure décrit la création d'un nouveau canal de Commerce et la définition des attributs de canal.</span><span class="sxs-lookup"><span data-stu-id="9a539-104">This procedure walks through creating a new commerce channel and defining channel attributes.</span></span> <span data-ttu-id="9a539-105">La société fictive utilisée pour créer cette tâche est USRT.</span><span class="sxs-lookup"><span data-stu-id="9a539-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="9a539-106">Cette procédure est destinée au rôle Informatique Commerce.</span><span class="sxs-lookup"><span data-stu-id="9a539-106">This procedure is intended for the Commerce IT role.</span></span>


## <a name="create-new-store"></a><span data-ttu-id="9a539-107">Créer un nouveau magasin</span><span class="sxs-lookup"><span data-stu-id="9a539-107">Create new store</span></span>
1. <span data-ttu-id="9a539-108">Accédez à Tous les espaces de travail > Déploiement de canal.</span><span class="sxs-lookup"><span data-stu-id="9a539-108">Go to All workspaces > Channel deployment.</span></span>
2. <span data-ttu-id="9a539-109">Cliquez sur Nouveau canal.</span><span class="sxs-lookup"><span data-stu-id="9a539-109">Click New channel.</span></span>
3. <span data-ttu-id="9a539-110">Cliquez sur Magasin.</span><span class="sxs-lookup"><span data-stu-id="9a539-110">Click Store.</span></span>
4. <span data-ttu-id="9a539-111">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="9a539-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="9a539-112">Dans le champ Numéro de magasin, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9a539-112">In the Store number field, type a value.</span></span>
6. <span data-ttu-id="9a539-113">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a539-113">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="9a539-114">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9a539-114">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="9a539-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a539-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="9a539-116">Dans le champ Fuseau horaire du magasin, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="9a539-116">In the Store time zone field, select an option.</span></span>
10. <span data-ttu-id="9a539-117">Dans le champ Profil du canal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a539-117">In the Channel profile field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="9a539-118">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a539-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="9a539-119">Dans le champ Langue, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a539-119">In the Language field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="9a539-120">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9a539-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="9a539-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a539-121">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="9a539-122">Dans le champ Groupe de taxe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a539-122">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="9a539-123">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9a539-123">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="9a539-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a539-124">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="9a539-125">Dans le champ Carnet d'adresses du client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a539-125">In the Customer address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9a539-126">Sélectionnez le carnet d'adresses utilisé pour lier des clients à ce magasin.</span><span class="sxs-lookup"><span data-stu-id="9a539-126">Select the address book used to link customers to this store.</span></span>  
19. <span data-ttu-id="9a539-127">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9a539-127">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="9a539-128">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a539-128">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="9a539-129">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="9a539-129">Click Select.</span></span>
22. <span data-ttu-id="9a539-130">Dans le champ Carnet d'adresses de l'employé, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a539-130">In the Employee address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9a539-131">Sélectionnez le carnet d'adresses utilisé pour lier des caissiers à ce canal.</span><span class="sxs-lookup"><span data-stu-id="9a539-131">Select the address book used to link cashiers to this channel.</span></span>  
23. <span data-ttu-id="9a539-132">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9a539-132">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="9a539-133">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a539-133">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="9a539-134">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="9a539-134">Click Select.</span></span>
26. <span data-ttu-id="9a539-135">Dans le champ Client par défaut, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a539-135">In the Default customer field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="9a539-136">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a539-136">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="9a539-137">Développez ou réduisez la section Mise en page de l'écran.</span><span class="sxs-lookup"><span data-stu-id="9a539-137">Expand or collapse the Screen layout section.</span></span>
29. <span data-ttu-id="9a539-138">Dans le champ ID mise en page de l'écran, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a539-138">In the Screen layout ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9a539-139">Sélectionnez la mis en page de l'écran PDV par défaut pour ce magasin.</span><span class="sxs-lookup"><span data-stu-id="9a539-139">Select the default POS screen layout for this store.</span></span>  
30. <span data-ttu-id="9a539-140">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9a539-140">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="9a539-141">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a539-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="9a539-142">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="9a539-142">On the Action Pane, click Set up.</span></span>
33. <span data-ttu-id="9a539-143">Cliquez sur Attributs de canal.</span><span class="sxs-lookup"><span data-stu-id="9a539-143">Click Channel attributes.</span></span>
34. <span data-ttu-id="9a539-144">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9a539-144">Click New.</span></span>
35. <span data-ttu-id="9a539-145">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a539-145">In the Name field, click the drop-down button to open the lookup.</span></span>
36. <span data-ttu-id="9a539-146">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9a539-146">In the list, find and select the desired record.</span></span>
37. <span data-ttu-id="9a539-147">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a539-147">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="9a539-148">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9a539-148">Click Save.</span></span>
39. <span data-ttu-id="9a539-149">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9a539-149">Close the page.</span></span>
40. <span data-ttu-id="9a539-150">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="9a539-150">On the Action Pane, click Set up.</span></span>
41. <span data-ttu-id="9a539-151">Cliquez sur Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="9a539-151">Click Payment methods.</span></span>
42. <span data-ttu-id="9a539-152">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9a539-152">Click New.</span></span>
43. <span data-ttu-id="9a539-153">Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a539-153">In the Payment method field, click the drop-down button to open the lookup.</span></span>
44. <span data-ttu-id="9a539-154">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a539-154">In the list, click the link in the selected row.</span></span>
45. <span data-ttu-id="9a539-155">Développez ou réduisez la section Validation.</span><span class="sxs-lookup"><span data-stu-id="9a539-155">Expand or collapse the Posting section.</span></span>
46. <span data-ttu-id="9a539-156">Dans le champ Numéro de compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="9a539-156">In the Account number field, specify the desired values.</span></span>
47. <span data-ttu-id="9a539-157">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9a539-157">Click Save.</span></span>
48. <span data-ttu-id="9a539-158">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9a539-158">Close the page.</span></span>
49. <span data-ttu-id="9a539-159">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="9a539-159">On the Action Pane, click Set up.</span></span>
50. <span data-ttu-id="9a539-160">Cliquez sur Déclaration des montants en caisse.</span><span class="sxs-lookup"><span data-stu-id="9a539-160">Click Cash declaration.</span></span>
51. <span data-ttu-id="9a539-161">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9a539-161">Click New.</span></span>
52. <span data-ttu-id="9a539-162">Dans le champ Montant dans la devise de transaction, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9a539-162">In the Amount in transaction currency field, enter a number.</span></span>
53. <span data-ttu-id="9a539-163">Dans le champ Devise, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a539-163">In the Currency field, click the drop-down button to open the lookup.</span></span>
54. <span data-ttu-id="9a539-164">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9a539-164">In the list, find and select the desired record.</span></span>
55. <span data-ttu-id="9a539-165">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a539-165">In the list, click the link in the selected row.</span></span>
56. <span data-ttu-id="9a539-166">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9a539-166">Click Save.</span></span>
57. <span data-ttu-id="9a539-167">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9a539-167">Close the page.</span></span>
58. <span data-ttu-id="9a539-168">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="9a539-168">On the Action Pane, click Set up.</span></span>
59. <span data-ttu-id="9a539-169">Cliquez sur Affectation de groupe de localisateurs de magasin.</span><span class="sxs-lookup"><span data-stu-id="9a539-169">Click Store locator group assignment.</span></span>
60. <span data-ttu-id="9a539-170">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9a539-170">Click New.</span></span>
61. <span data-ttu-id="9a539-171">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a539-171">In the list, mark the selected row.</span></span>
62. <span data-ttu-id="9a539-172">Dans le champ Groupe de localisateurs, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a539-172">In the Locator group field, click the drop-down button to open the lookup.</span></span>
63. <span data-ttu-id="9a539-173">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9a539-173">In the list, find and select the desired record.</span></span>
64. <span data-ttu-id="9a539-174">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a539-174">In the list, click the link in the selected row.</span></span>
65. <span data-ttu-id="9a539-175">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9a539-175">Click Save.</span></span>
66. <span data-ttu-id="9a539-176">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9a539-176">Close the page.</span></span>

