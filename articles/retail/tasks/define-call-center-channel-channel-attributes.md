---
title: Créer des canaux de centre d'appels et définir des attributs de canal
description: Cette procédure décrit la création d'un nouveau canal de vente au détail et la définition des attributs de canal.
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
ms.openlocfilehash: 7ef094535214ecf4c65f95c36a93455446d7e388
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "346753"
---
# <a name="create-call-center-channels-and-define-channel-attributes"></a><span data-ttu-id="c0c09-103">Créer des canaux de centre d'appels et définir des attributs de canal</span><span class="sxs-lookup"><span data-stu-id="c0c09-103">Create call center channels and define channel attributes</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="c0c09-104">Cette procédure décrit la création d'un nouveau canal de vente au détail et la définition des attributs de canal.</span><span class="sxs-lookup"><span data-stu-id="c0c09-104">This procedure walks through creating a new retail channel and defining channel attributes.</span></span> <span data-ttu-id="c0c09-105">La société fictive utilisée pour créer cette tâche est USRT.</span><span class="sxs-lookup"><span data-stu-id="c0c09-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="c0c09-106">Cette procédure est destinée au rôle Informatique au détail.</span><span class="sxs-lookup"><span data-stu-id="c0c09-106">This procedure is intended for the Retail IT role.</span></span>


## <a name="create-new-store"></a><span data-ttu-id="c0c09-107">Créer un nouveau magasin</span><span class="sxs-lookup"><span data-stu-id="c0c09-107">Create new store</span></span>
1. <span data-ttu-id="c0c09-108">Accédez à Tous les espaces de travail > Déploiement de canal.</span><span class="sxs-lookup"><span data-stu-id="c0c09-108">Go to All workspaces > Channel deployment.</span></span>
2. <span data-ttu-id="c0c09-109">Cliquez sur Nouveau canal.</span><span class="sxs-lookup"><span data-stu-id="c0c09-109">Click New channel.</span></span>
3. <span data-ttu-id="c0c09-110">Cliquez sur Magasin.</span><span class="sxs-lookup"><span data-stu-id="c0c09-110">Click Store.</span></span>
4. <span data-ttu-id="c0c09-111">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="c0c09-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="c0c09-112">Dans le champ Numéro de magasin, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c0c09-112">In the Store number field, type a value.</span></span>
6. <span data-ttu-id="c0c09-113">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c0c09-113">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="c0c09-114">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c0c09-114">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="c0c09-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c0c09-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="c0c09-116">Dans le champ Fuseau horaire du magasin, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="c0c09-116">In the Store time zone field, select an option.</span></span>
10. <span data-ttu-id="c0c09-117">Dans le champ Profil du canal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c0c09-117">In the Channel profile field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="c0c09-118">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c0c09-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="c0c09-119">Dans le champ Langue, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c0c09-119">In the Language field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="c0c09-120">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c0c09-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="c0c09-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c0c09-121">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="c0c09-122">Dans le champ Groupe de taxe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c0c09-122">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="c0c09-123">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c0c09-123">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="c0c09-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c0c09-124">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="c0c09-125">Dans le champ Carnet d'adresses du client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c0c09-125">In the Customer address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c0c09-126">Sélectionnez le carnet d'adresses utilisé pour lier des clients à ce magasin.</span><span class="sxs-lookup"><span data-stu-id="c0c09-126">Select the address book used to link customers to this store.</span></span>  
19. <span data-ttu-id="c0c09-127">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c0c09-127">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="c0c09-128">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c0c09-128">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="c0c09-129">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="c0c09-129">Click Select.</span></span>
22. <span data-ttu-id="c0c09-130">Dans le champ Carnet d'adresses de l'employé, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c0c09-130">In the Employee address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c0c09-131">Sélectionnez le carnet d'adresses utilisé pour lier des caissiers à ce canal.</span><span class="sxs-lookup"><span data-stu-id="c0c09-131">Select the address book used to link cashiers to this channel.</span></span>  
23. <span data-ttu-id="c0c09-132">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c0c09-132">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="c0c09-133">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c0c09-133">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="c0c09-134">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="c0c09-134">Click Select.</span></span>
26. <span data-ttu-id="c0c09-135">Dans le champ Client par défaut, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c0c09-135">In the Default customer field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="c0c09-136">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c0c09-136">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="c0c09-137">Développez ou réduisez la section Mise en page de l'écran.</span><span class="sxs-lookup"><span data-stu-id="c0c09-137">Expand or collapse the Screen layout section.</span></span>
29. <span data-ttu-id="c0c09-138">Dans le champ ID mise en page de l'écran, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c0c09-138">In the Screen layout ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c0c09-139">Sélectionnez la mis en page de l'écran PDV par défaut pour ce magasin.</span><span class="sxs-lookup"><span data-stu-id="c0c09-139">Select the default POS screen layout for this store.</span></span>  
30. <span data-ttu-id="c0c09-140">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c0c09-140">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="c0c09-141">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c0c09-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="c0c09-142">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="c0c09-142">On the Action Pane, click Set up.</span></span>
33. <span data-ttu-id="c0c09-143">Cliquez sur Attributs de canal.</span><span class="sxs-lookup"><span data-stu-id="c0c09-143">Click Channel attributes.</span></span>
34. <span data-ttu-id="c0c09-144">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c0c09-144">Click New.</span></span>
35. <span data-ttu-id="c0c09-145">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c0c09-145">In the Name field, click the drop-down button to open the lookup.</span></span>
36. <span data-ttu-id="c0c09-146">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c0c09-146">In the list, find and select the desired record.</span></span>
37. <span data-ttu-id="c0c09-147">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c0c09-147">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="c0c09-148">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c0c09-148">Click Save.</span></span>
39. <span data-ttu-id="c0c09-149">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c0c09-149">Close the page.</span></span>
40. <span data-ttu-id="c0c09-150">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="c0c09-150">On the Action Pane, click Set up.</span></span>
41. <span data-ttu-id="c0c09-151">Cliquez sur Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="c0c09-151">Click Payment methods.</span></span>
42. <span data-ttu-id="c0c09-152">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c0c09-152">Click New.</span></span>
43. <span data-ttu-id="c0c09-153">Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c0c09-153">In the Payment method field, click the drop-down button to open the lookup.</span></span>
44. <span data-ttu-id="c0c09-154">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c0c09-154">In the list, click the link in the selected row.</span></span>
45. <span data-ttu-id="c0c09-155">Développez ou réduisez la section Validation.</span><span class="sxs-lookup"><span data-stu-id="c0c09-155">Expand or collapse the Posting section.</span></span>
46. <span data-ttu-id="c0c09-156">Dans le champ Numéro de compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="c0c09-156">In the Account number field, specify the desired values.</span></span>
47. <span data-ttu-id="c0c09-157">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c0c09-157">Click Save.</span></span>
48. <span data-ttu-id="c0c09-158">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c0c09-158">Close the page.</span></span>
49. <span data-ttu-id="c0c09-159">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="c0c09-159">On the Action Pane, click Set up.</span></span>
50. <span data-ttu-id="c0c09-160">Cliquez sur Déclaration des montants en caisse.</span><span class="sxs-lookup"><span data-stu-id="c0c09-160">Click Cash declaration.</span></span>
51. <span data-ttu-id="c0c09-161">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c0c09-161">Click New.</span></span>
52. <span data-ttu-id="c0c09-162">Dans le champ Montant dans la devise de transaction, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c0c09-162">In the Amount in transaction currency field, enter a number.</span></span>
53. <span data-ttu-id="c0c09-163">Dans le champ Devise, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c0c09-163">In the Currency field, click the drop-down button to open the lookup.</span></span>
54. <span data-ttu-id="c0c09-164">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c0c09-164">In the list, find and select the desired record.</span></span>
55. <span data-ttu-id="c0c09-165">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c0c09-165">In the list, click the link in the selected row.</span></span>
56. <span data-ttu-id="c0c09-166">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c0c09-166">Click Save.</span></span>
57. <span data-ttu-id="c0c09-167">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c0c09-167">Close the page.</span></span>
58. <span data-ttu-id="c0c09-168">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="c0c09-168">On the Action Pane, click Set up.</span></span>
59. <span data-ttu-id="c0c09-169">Cliquez sur Affectation de groupe de localisateurs de magasin.</span><span class="sxs-lookup"><span data-stu-id="c0c09-169">Click Store locator group assignment.</span></span>
60. <span data-ttu-id="c0c09-170">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c0c09-170">Click New.</span></span>
61. <span data-ttu-id="c0c09-171">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c0c09-171">In the list, mark the selected row.</span></span>
62. <span data-ttu-id="c0c09-172">Dans le champ Groupe de localisateurs, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c0c09-172">In the Locator group field, click the drop-down button to open the lookup.</span></span>
63. <span data-ttu-id="c0c09-173">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c0c09-173">In the list, find and select the desired record.</span></span>
64. <span data-ttu-id="c0c09-174">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c0c09-174">In the list, click the link in the selected row.</span></span>
65. <span data-ttu-id="c0c09-175">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c0c09-175">Click Save.</span></span>
66. <span data-ttu-id="c0c09-176">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c0c09-176">Close the page.</span></span>

