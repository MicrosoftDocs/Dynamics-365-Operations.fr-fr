---
title: Créer des groupes d'autorisations PDV
description: Cette rubrique illustre la création d'un groupe d'autorisations du PDV.
author: scott-tucker
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e6782c60aa659523775cc6c4eb1694430a4bf4f
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914793"
---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="a7ac3-103">Créer des groupes d'autorisations PDV</span><span class="sxs-lookup"><span data-stu-id="a7ac3-103">Create POS permission groups</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="a7ac3-104">Cette rubrique illustre la création d'un groupe d'autorisations du PDV.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-104">This topic explains how to create a POS permission group.</span></span> <span data-ttu-id="a7ac3-105">La société fictive utilisée pour créer cette tâche est USRT.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="a7ac3-106">Cette tâche est destinée au rôle Gestionnaire des opérations de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-106">This task is intended for the Retail operations manager role.</span></span>

1. <span data-ttu-id="a7ac3-107">Dans le volet de navigation, accédez à **Modules > Retail > Employés > Groupes d'autorisations**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-107">In the navigation pane, go to **Modules > Retail > Employees > Permission groups**.</span></span>
2. <span data-ttu-id="a7ac3-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-108">Select **New**.</span></span>
3. <span data-ttu-id="a7ac3-109">Entrez une valeur dans le champ **ID groupe d'autorisations du PDV**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-109">In the **POS permission group ID** field, type a value.</span></span>
4. <span data-ttu-id="a7ac3-110">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="a7ac3-111">Sélectionnez **Oui** dans le champ **Afficher les entrées de l'horloge de pointage**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-111">Select **Yes** in the **View time clock entries** field.</span></span> <span data-ttu-id="a7ac3-112">Vous pouvez maintenant activer ou désactiver diverses autorisations pour votre groupe d'autorisations PDV.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="a7ac3-113">Pour certaines autorisations, vous pouvez définir une valeur qui sera utilisée pour évaluer si l'utilisateur PDV peut effectuer l'action.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span> <span data-ttu-id="a7ac3-114">Ce guide de tâches active quelques autorisations qui peuvent être accordées à un caissier.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="a7ac3-115">Sélectionnez **Oui** dans le champ **Autoriser la création de commandes**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-115">Select **Yes** in the **Allow create order** field.</span></span>
7. <span data-ttu-id="a7ac3-116">Sélectionnez **Oui** dans le champ **Autoriser la modification de commandes**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-116">Select **Yes** in the **Allow edit order** field.</span></span>
8. <span data-ttu-id="a7ac3-117">Sélectionnez **Oui** dans le champ **Autoriser la récupération de commandes**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-117">Select **Yes** in the **Allow retrieve order** field.</span></span>
9. <span data-ttu-id="a7ac3-118">Sélectionnez **Oui** dans le champ **Autoriser la modification du mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-118">Select **Yes** in the **Allow password change** field.</span></span>
10. <span data-ttu-id="a7ac3-119">Sélectionnez **Oui** dans le champ **Autoriser la clôture en aveugle**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-119">Select **Yes** in the **Allow blind close** field.</span></span>
11. <span data-ttu-id="a7ac3-120">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-120">Select **Save**.</span></span> <span data-ttu-id="a7ac3-121">Une fois vos modifications enregistrées, vous devez exécuter le programme de répartition du personnel pour que les modifications soient appliquées aux canaux de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span> 
12. <span data-ttu-id="a7ac3-122">Dans le volet de navigation, allez dans **Modules > Ressources humaines > Tâches > Tâches**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-122">In the navigation pane, go to **Modules > Human resources > Jobs > Jobs**.</span></span>
13. <span data-ttu-id="a7ac3-123">Nous allons ensuite affecter le groupe d'autorisations PDV à une tâche.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-123">Next we will assign the POS permission group to a Job.</span></span> <span data-ttu-id="a7ac3-124">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-124">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="a7ac3-125">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-125">Select **Edit**.</span></span>
15. <span data-ttu-id="a7ac3-126">Développez la section **Classification des tâches**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-126">Expand the **Job classification** section.</span></span>
16. <span data-ttu-id="a7ac3-127">Dans le champ Groupe d'autorisations du PDV, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-127">In the POS permission group field, enter or select a value.</span></span> <span data-ttu-id="a7ac3-128">Tous les collaborateurs affectés à des postes pour cette tâche utilisent les paramètres de ce groupe d'autorisations PDV sauf si les autorisations de PDV des collaborateurs ont été remplacées au niveau de leur poste.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-128">All Workers in Positions for this Job will use this POS permission group’s settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
17. <span data-ttu-id="a7ac3-129">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-129">Select **Save**.</span></span> <span data-ttu-id="a7ac3-130">Une fois vos modifications enregistrées, vous devez exécuter le programme de répartition du personnel pour que les modifications soient appliquées aux canaux de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="a7ac3-130">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  

