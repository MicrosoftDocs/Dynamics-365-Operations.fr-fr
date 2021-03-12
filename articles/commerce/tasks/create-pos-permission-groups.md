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
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ac03e1bfb7a2463b31feca0a4303c182a00ad259
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964818"
---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="6a9b0-103">Créer des groupes d'autorisations PDV</span><span class="sxs-lookup"><span data-stu-id="6a9b0-103">Create POS permission groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6a9b0-104">Cette rubrique illustre la création d'un groupe d'autorisations du PDV.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-104">This topic explains how to create a POS permission group.</span></span> <span data-ttu-id="6a9b0-105">La société fictive utilisée pour créer cette tâche est USRT.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="6a9b0-106">Cette tâche est destinée au rôle Gestionnaire des opérations Commerce.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-106">This task is intended for the Commerce operations manager role.</span></span>

1. <span data-ttu-id="6a9b0-107">Dans le volet de navigation, accédez à **Modules > Commerce et vente au détail > Employés > Groupes d'autorisations**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-107">In the navigation pane, go to **Modules > Retail and Commerce > Employees > Permission groups**.</span></span>
2. <span data-ttu-id="6a9b0-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-108">Select **New**.</span></span>
3. <span data-ttu-id="6a9b0-109">Entrez une valeur dans le champ **ID groupe d'autorisations du PDV**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-109">In the **POS permission group ID** field, type a value.</span></span>
4. <span data-ttu-id="6a9b0-110">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="6a9b0-111">Sélectionnez **Oui** dans le champ **Afficher les entrées de l'horloge de pointage**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-111">Select **Yes** in the **View time clock entries** field.</span></span> <span data-ttu-id="6a9b0-112">Vous pouvez maintenant activer ou désactiver diverses autorisations pour votre groupe d'autorisations PDV.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="6a9b0-113">Pour certaines autorisations, vous pouvez définir une valeur qui sera utilisée pour évaluer si l'utilisateur PDV peut effectuer l'action.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span> <span data-ttu-id="6a9b0-114">Ce guide de tâches active quelques autorisations qui peuvent être accordées à un caissier.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="6a9b0-115">Sélectionnez **Oui** dans le champ **Autoriser la création de commandes**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-115">Select **Yes** in the **Allow create order** field.</span></span>
7. <span data-ttu-id="6a9b0-116">Sélectionnez **Oui** dans le champ **Autoriser la modification de commandes**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-116">Select **Yes** in the **Allow edit order** field.</span></span>
8. <span data-ttu-id="6a9b0-117">Sélectionnez **Oui** dans le champ **Autoriser la récupération de commandes**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-117">Select **Yes** in the **Allow retrieve order** field.</span></span>
9. <span data-ttu-id="6a9b0-118">Sélectionnez **Oui** dans le champ **Autoriser la modification du mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-118">Select **Yes** in the **Allow password change** field.</span></span>
10. <span data-ttu-id="6a9b0-119">Sélectionnez **Oui** dans le champ **Autoriser la clôture en aveugle**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-119">Select **Yes** in the **Allow blind close** field.</span></span>
11. <span data-ttu-id="6a9b0-120">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-120">Select **Save**.</span></span> <span data-ttu-id="6a9b0-121">Une fois vos modifications enregistrées, vous devez exécuter le programme de répartition du personnel pour que les modifications soient appliquées aux canaux Commerce.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to commerce channels.</span></span> 
12. <span data-ttu-id="6a9b0-122">Dans le volet de navigation, allez dans **Modules > Ressources humaines > Tâches > Tâches**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-122">In the navigation pane, go to **Modules > Human resources > Jobs > Jobs**.</span></span>
13. <span data-ttu-id="6a9b0-123">Nous allons ensuite affecter le groupe d'autorisations PDV à une tâche.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-123">Next we will assign the POS permission group to a Job.</span></span> <span data-ttu-id="6a9b0-124">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-124">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="6a9b0-125">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-125">Select **Edit**.</span></span>
15. <span data-ttu-id="6a9b0-126">Développez la section **Classification des tâches**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-126">Expand the **Job classification** section.</span></span>
16. <span data-ttu-id="6a9b0-127">Dans le champ Groupe d'autorisations du PDV, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-127">In the POS permission group field, enter or select a value.</span></span> <span data-ttu-id="6a9b0-128">Tous les collaborateurs affectés à des postes pour cette tâche utilisent les paramètres de ce groupe d'autorisations PDV sauf si les autorisations de PDV des collaborateurs ont été remplacées au niveau de leur poste.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-128">All Workers in Positions for this Job will use this POS permission group's settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
17. <span data-ttu-id="6a9b0-129">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-129">Select **Save**.</span></span> <span data-ttu-id="6a9b0-130">Une fois vos modifications enregistrées, vous devez exécuter le programme de répartition du personnel pour que les modifications soient appliquées aux canaux.</span><span class="sxs-lookup"><span data-stu-id="6a9b0-130">After your changes are saved you need to run the Staff distribution schedule to push the changes to channels.</span></span>  

