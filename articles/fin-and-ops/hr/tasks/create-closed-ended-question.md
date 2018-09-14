--- 
title: "Créer une question fermée"
description: "Les questions fermées permettent à la personne interrogée de choisir des options."
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 6b08988a3872cec39b7592732d23862e959aae79
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-closed-ended-question"></a><span data-ttu-id="51fa0-103">Créer une question fermée</span><span class="sxs-lookup"><span data-stu-id="51fa0-103">Create a closed ended question</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="51fa0-104">Les questions fermées permettent à la personne interrogée de choisir des options.</span><span class="sxs-lookup"><span data-stu-id="51fa0-104">Closed-ended questions allow you to provide options for the respondent to choose from.</span></span> <span data-ttu-id="51fa0-105">Vous devez tout d'abord créer le groupe de réponses avec des réponses, puis créer la question qui va utiliser le groupe de réponses.</span><span class="sxs-lookup"><span data-stu-id="51fa0-105">First, you need to create the Answer group with the answers, then create the question that will use the answer group.</span></span> <span data-ttu-id="51fa0-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="51fa0-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-an-answer-group"></a><span data-ttu-id="51fa0-107">Créer un groupe de réponses</span><span class="sxs-lookup"><span data-stu-id="51fa0-107">Create an answer group</span></span>
1. <span data-ttu-id="51fa0-108">Allez dans Questionnaire > Conception > Groupes de réponses.</span><span class="sxs-lookup"><span data-stu-id="51fa0-108">Go to Questionnaire > Design > Answer groups.</span></span>
2. <span data-ttu-id="51fa0-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="51fa0-109">Click New.</span></span>
3. <span data-ttu-id="51fa0-110">Tapez une valeur dans le champ Groupe de réponses.</span><span class="sxs-lookup"><span data-stu-id="51fa0-110">In the Answer group field, type a value.</span></span>
4. <span data-ttu-id="51fa0-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="51fa0-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="51fa0-112">Utilisez la fonctionnalité Aléatoire pour placer de manière aléatoire les réponses dans une commande différente chaque fois que le groupe de réponses est utilisé pour une question.</span><span class="sxs-lookup"><span data-stu-id="51fa0-112">Use the Randomize functionality to randomly place the answers in a different order each time the answer group is used for a question.</span></span>  
5. <span data-ttu-id="51fa0-113">Cliquez sur Réponse.</span><span class="sxs-lookup"><span data-stu-id="51fa0-113">Click Answer.</span></span>
6. <span data-ttu-id="51fa0-114">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="51fa0-114">Click New.</span></span>
    * <span data-ttu-id="51fa0-115">Le numéro de souche contrôle l'ordre dans lequel les réponses sont affichées, sauf si la fonctionnalité Aléatoire est activée pour le groupe de réponses.</span><span class="sxs-lookup"><span data-stu-id="51fa0-115">Sequence number controls the order in which the answers are displayed, unless Randomize is selected for the Answer group.</span></span>  
    * <span data-ttu-id="51fa0-116">Les points peuvent être affectés aux réponses pour être utilisées pour marquer les points le questionnaire.</span><span class="sxs-lookup"><span data-stu-id="51fa0-116">Points can be awarded to answers for use in scoring the questionnaire.</span></span>  
7. <span data-ttu-id="51fa0-117">Entrez un nombre dans le champ Points.</span><span class="sxs-lookup"><span data-stu-id="51fa0-117">In the Points field, enter a number.</span></span>
    * <span data-ttu-id="51fa0-118">La réponse correcte peut être marquée pour indiquer que la réponse sélectionnée est correcte.</span><span class="sxs-lookup"><span data-stu-id="51fa0-118">The correct answer can be marked to indicate that the selected answer is the correct one.</span></span> <span data-ttu-id="51fa0-119">Cette opération peut être utilisée pour marquer les points du questionnaire.</span><span class="sxs-lookup"><span data-stu-id="51fa0-119">This can be used for scoring the questionnaire.</span></span>  
8. <span data-ttu-id="51fa0-120">Tapez une valeur dans le champ Réponse.</span><span class="sxs-lookup"><span data-stu-id="51fa0-120">In the Answer field, type a value.</span></span>
    * <span data-ttu-id="51fa0-121">Continuez à créer des options de sélection de réponse pour le groupe de réponses.</span><span class="sxs-lookup"><span data-stu-id="51fa0-121">Continue to create answer selection options for the answer group.</span></span>  
9. <span data-ttu-id="51fa0-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="51fa0-122">Click New.</span></span>
10. <span data-ttu-id="51fa0-123">Entrez un nombre dans le champ Points.</span><span class="sxs-lookup"><span data-stu-id="51fa0-123">In the Points field, enter a number.</span></span>
11. <span data-ttu-id="51fa0-124">Tapez une valeur dans le champ Réponse.</span><span class="sxs-lookup"><span data-stu-id="51fa0-124">In the Answer field, type a value.</span></span>
12. <span data-ttu-id="51fa0-125">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="51fa0-125">Click New.</span></span>
13. <span data-ttu-id="51fa0-126">Entrez un nombre dans le champ Points.</span><span class="sxs-lookup"><span data-stu-id="51fa0-126">In the Points field, enter a number.</span></span>
14. <span data-ttu-id="51fa0-127">Tapez une valeur dans le champ Réponse.</span><span class="sxs-lookup"><span data-stu-id="51fa0-127">In the Answer field, type a value.</span></span>
15. <span data-ttu-id="51fa0-128">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="51fa0-128">Click New.</span></span>
16. <span data-ttu-id="51fa0-129">Entrez un nombre dans le champ Points.</span><span class="sxs-lookup"><span data-stu-id="51fa0-129">In the Points field, enter a number.</span></span>
17. <span data-ttu-id="51fa0-130">Tapez une valeur dans le champ Réponse.</span><span class="sxs-lookup"><span data-stu-id="51fa0-130">In the Answer field, type a value.</span></span>
18. <span data-ttu-id="51fa0-131">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="51fa0-131">Click New.</span></span>
19. <span data-ttu-id="51fa0-132">Entrez un nombre dans le champ Points.</span><span class="sxs-lookup"><span data-stu-id="51fa0-132">In the Points field, enter a number.</span></span>
20. <span data-ttu-id="51fa0-133">Tapez une valeur dans le champ Réponse.</span><span class="sxs-lookup"><span data-stu-id="51fa0-133">In the Answer field, type a value.</span></span>
21. <span data-ttu-id="51fa0-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51fa0-134">Close the page.</span></span>
22. <span data-ttu-id="51fa0-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51fa0-135">Close the page.</span></span>

## <a name="create-the-question"></a><span data-ttu-id="51fa0-136">Créer la question</span><span class="sxs-lookup"><span data-stu-id="51fa0-136">Create the question</span></span>
1. <span data-ttu-id="51fa0-137">Accédez à Questionnaire > Conception > Questions.</span><span class="sxs-lookup"><span data-stu-id="51fa0-137">Go to Questionnaire > Design > Questions.</span></span>
2. <span data-ttu-id="51fa0-138">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="51fa0-138">Click New.</span></span>
3. <span data-ttu-id="51fa0-139">Utilisez le champ Type pour regrouper les questions associées.</span><span class="sxs-lookup"><span data-stu-id="51fa0-139">Use the Type field to group related questions together.</span></span>
    * <span data-ttu-id="51fa0-140">Vous pouvez utiliser les types d'entrée Case à cocher, bouton Autre ou Zone de liste modifiable pour des questions fermées.</span><span class="sxs-lookup"><span data-stu-id="51fa0-140">You can use input types of Check box, Alternative button, or Combo box for closed-ended questions.</span></span>  
4. <span data-ttu-id="51fa0-141">Sélectionnez une option dans le champ Type de saisie.</span><span class="sxs-lookup"><span data-stu-id="51fa0-141">In the Input type field, select an option.</span></span>
5. <span data-ttu-id="51fa0-142">Saisissez ou sélectionnez une valeur dans le champ Groupe de réponses.</span><span class="sxs-lookup"><span data-stu-id="51fa0-142">In the Answer group field, enter or select a value.</span></span>
6. <span data-ttu-id="51fa0-143">Tapez une valeur dans le champ Texte.</span><span class="sxs-lookup"><span data-stu-id="51fa0-143">In the Text field, type a value.</span></span>


