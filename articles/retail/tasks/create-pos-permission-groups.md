--- 
title: " Créer des groupes d'autorisations de PDV"
description: "Cette procédure indique comment créer un groupe d'autorisations de PDV."
author: scott-tucker
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 985cce1f1848408517ce71b36575162960c3d84e
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="61bf0-103"> Créer des groupes d'autorisations de PDV</span><span class="sxs-lookup"><span data-stu-id="61bf0-103">Create POS permission groups</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="61bf0-104">Cette procédure indique comment créer un groupe d'autorisations de PDV.</span><span class="sxs-lookup"><span data-stu-id="61bf0-104">This procedure will show how to create a POS permission group.</span></span> <span data-ttu-id="61bf0-105">La société fictive utilisée pour créer cette tâche est USRT.</span><span class="sxs-lookup"><span data-stu-id="61bf0-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="61bf0-106">Cette tâche est destinée au rôle Gestionnaire des opérations de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="61bf0-106">This task is intended for the Retail operations manager role.</span></span>

1. <span data-ttu-id="61bf0-107">Accédez à Groupes d'autorisations.</span><span class="sxs-lookup"><span data-stu-id="61bf0-107">Go to Permission groups.</span></span>
2. <span data-ttu-id="61bf0-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="61bf0-108">Click New.</span></span>
3. <span data-ttu-id="61bf0-109">Dans le champ ID groupe d'autorisations du PDV, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="61bf0-109">In the POS permission group ID field, type a value.</span></span>
4. <span data-ttu-id="61bf0-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="61bf0-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="61bf0-111">Sélectionnez Oui dans le champ Afficher les entrées de l'horloge de pointage.</span><span class="sxs-lookup"><span data-stu-id="61bf0-111">Select Yes in the View time clock entries field.</span></span>
    * <span data-ttu-id="61bf0-112">Vous pouvez maintenant activer ou désactiver diverses autorisations pour votre groupe d'autorisations PDV.</span><span class="sxs-lookup"><span data-stu-id="61bf0-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="61bf0-113">Pour certaines autorisations, vous pouvez définir une valeur qui sera utilisée pour évaluer si l'utilisateur PDV peut effectuer l'action.</span><span class="sxs-lookup"><span data-stu-id="61bf0-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span>  <span data-ttu-id="61bf0-114">Ce guide de tâches active quelques autorisations qui peuvent être accordées à un caissier.</span><span class="sxs-lookup"><span data-stu-id="61bf0-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="61bf0-115">Sélectionnez Oui dans le champ Autoriser la création de commandes.</span><span class="sxs-lookup"><span data-stu-id="61bf0-115">Select Yes in the Allow create order field.</span></span>
7. <span data-ttu-id="61bf0-116">Sélectionnez Oui dans le champ Autoriser la modification de commandes.</span><span class="sxs-lookup"><span data-stu-id="61bf0-116">Select Yes in the Allow edit order field.</span></span>
8. <span data-ttu-id="61bf0-117">Sélectionnez Oui dans le champ Autoriser la récupération de commandes.</span><span class="sxs-lookup"><span data-stu-id="61bf0-117">Select Yes in the Allow retrieve order field.</span></span>
9. <span data-ttu-id="61bf0-118">Sélectionnez Oui dans le champ Autoriser la modification du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="61bf0-118">Select Yes in the Allow password change field.</span></span>
10. <span data-ttu-id="61bf0-119">Sélectionnez Oui dans le champ Autoriser la clôture en aveugle.</span><span class="sxs-lookup"><span data-stu-id="61bf0-119">Select Yes in the Allow blind close field.</span></span>
11. <span data-ttu-id="61bf0-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="61bf0-120">Click Save.</span></span>
    * <span data-ttu-id="61bf0-121">Une fois vos modifications enregistrées, vous devez exécuter le programme de répartition du personnel pour que les modifications soient appliquées aux canaux de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="61bf0-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  
12. <span data-ttu-id="61bf0-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="61bf0-122">Close the page.</span></span>
13. <span data-ttu-id="61bf0-123">Accédez à Tâches.</span><span class="sxs-lookup"><span data-stu-id="61bf0-123">Go to Jobs.</span></span>
    * <span data-ttu-id="61bf0-124">Nous allons ensuite affecter le groupe d'autorisations PDV à une tâche.</span><span class="sxs-lookup"><span data-stu-id="61bf0-124">Next we will assign the POS permission group to a Job.</span></span>  
14. <span data-ttu-id="61bf0-125">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="61bf0-125">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="61bf0-126">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="61bf0-126">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="61bf0-127">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="61bf0-127">Click Edit.</span></span>
17. <span data-ttu-id="61bf0-128">Développez la section Classification des tâches.</span><span class="sxs-lookup"><span data-stu-id="61bf0-128">Expand the Job classification section.</span></span>
18. <span data-ttu-id="61bf0-129">Dans le champ Groupe d'autorisations du PDV, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="61bf0-129">In the POS permission group field, enter or select a value.</span></span>
    * <span data-ttu-id="61bf0-130">Tous les collaborateurs affectés à des postes pour cette tâche utilisent les paramètres de ce groupe d'autorisations PDV sauf si les autorisations de PDV des collaborateurs ont été remplacées au niveau de leur poste.</span><span class="sxs-lookup"><span data-stu-id="61bf0-130">All Workers in Positions for this Job will use this POS permission group’s settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
19. <span data-ttu-id="61bf0-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="61bf0-131">Click Save.</span></span>
    * <span data-ttu-id="61bf0-132">Une fois vos modifications enregistrées, vous devez exécuter le programme de répartition du personnel pour que les modifications soient appliquées aux canaux de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="61bf0-132">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  


