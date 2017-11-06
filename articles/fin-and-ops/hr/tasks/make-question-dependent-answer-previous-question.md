--- 
title: "Rendre une question dépendante de la réponse à la question précédente"
description: "Les questions conditionnelles permettent de spécifier la question de suivi qui est présentée à la personne interrogée, selon la réponse à la question précédente."
author: twheeloc
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 05f7af94813934c1d77d6a509587280395f0e8bd
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a><span data-ttu-id="3d28f-103">Rendre une question dépendante de la réponse à la question précédente</span><span class="sxs-lookup"><span data-stu-id="3d28f-103">Make a question dependent on the answer of the previous question</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3d28f-104">Les questions conditionnelles permettent de spécifier la question de suivi qui est présentée à la personne interrogée, selon la réponse à la question précédente.</span><span class="sxs-lookup"><span data-stu-id="3d28f-104">Conditional questions allow you to specify what follow-up question will be presented to a respondent, based on the answer to the preceding question.</span></span> <span data-ttu-id="3d28f-105">Par exemple, si vous demandez « Vous préférez le café ou le thé ? », une question de suivi logique peut être déterminée selon que la personne interrogée sélectionne le café ou le thé en tant que réponse.</span><span class="sxs-lookup"><span data-stu-id="3d28f-105">For example, if you ask "Do you prefer coffee or tea," a logical follow-up question can be determined depending on whether the respondent selects coffee or tea as their answer.</span></span> <span data-ttu-id="3d28f-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="3d28f-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="find-the-existing-questionnaire"></a><span data-ttu-id="3d28f-107">Rechercher le questionnaire existant</span><span class="sxs-lookup"><span data-stu-id="3d28f-107">Find the existing questionnaire</span></span>
1. <span data-ttu-id="3d28f-108">Accédez à Questionnaire > Conception > Questionnaires.</span><span class="sxs-lookup"><span data-stu-id="3d28f-108">Go to Questionnaire > Design > Questionnaires.</span></span>
2. <span data-ttu-id="3d28f-109">Sélectionnez le questionnaire WorkFH dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3d28f-109">In the list, select the WorkFH questionnaire.</span></span>

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a><span data-ttu-id="3d28f-110">Ajouter toutes les questions et les sous-questions au questionnaire</span><span class="sxs-lookup"><span data-stu-id="3d28f-110">Add all questions and sub-questions to the Questionnaire</span></span>
1. <span data-ttu-id="3d28f-111">Cliquez sur Questions.</span><span class="sxs-lookup"><span data-stu-id="3d28f-111">Click Questions.</span></span>
2. <span data-ttu-id="3d28f-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3d28f-112">Click New.</span></span>
3. <span data-ttu-id="3d28f-113">Dans le champ Question, sélectionnez la question 00016.</span><span class="sxs-lookup"><span data-stu-id="3d28f-113">In the Question field, select question number 00016.</span></span>
4. <span data-ttu-id="3d28f-114">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3d28f-114">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="3d28f-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3d28f-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="3d28f-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3d28f-116">Click Save.</span></span>
7. <span data-ttu-id="3d28f-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3d28f-117">Close the page.</span></span>

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a><span data-ttu-id="3d28f-118">Définir l'ordre du questionnaire sur Conditionnel et rendre la question dépendante de la question appropriée</span><span class="sxs-lookup"><span data-stu-id="3d28f-118">Set the Questionnaire Sequence to Conditional and make the question dependent on the appropriate question</span></span>
1. <span data-ttu-id="3d28f-119">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="3d28f-119">Click Edit.</span></span>
2. <span data-ttu-id="3d28f-120">Développez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="3d28f-120">Expand the Setup section.</span></span>
3. <span data-ttu-id="3d28f-121">Dans le champ Ordre des questions, sélectionnez « Conditionnelle ».</span><span class="sxs-lookup"><span data-stu-id="3d28f-121">In the Question order field, select 'Conditional'.</span></span>
4. <span data-ttu-id="3d28f-122">Cliquez sur Question conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="3d28f-122">Click Conditional question.</span></span>
5. <span data-ttu-id="3d28f-123">Dans l'arborescence, sélectionnez « Questions\Expliquez pourquoi vous avez répondu cela à la question précédente ? ».</span><span class="sxs-lookup"><span data-stu-id="3d28f-123">In the tree, select 'Questions\Explain why you answered the previous question the way you did?'.</span></span>
6. <span data-ttu-id="3d28f-124">Dans le champ Question principale, sélectionnez la question 00009.</span><span class="sxs-lookup"><span data-stu-id="3d28f-124">In the Primary question field, select question 00009</span></span>
7. <span data-ttu-id="3d28f-125">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3d28f-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="3d28f-126">Dans le champ Réponse, entrez l'ID de séquence de réponse de l'option de réponse dont doit dépendre la question.</span><span class="sxs-lookup"><span data-stu-id="3d28f-126">In the Answer field, enter the answer sequence ID of the answer option you want to make the question dependent on.</span></span> <span data-ttu-id="3d28f-127">Par exemple, entrez 1 pour la première option de réponse.</span><span class="sxs-lookup"><span data-stu-id="3d28f-127">For example, enter 1 for the first answer option.</span></span>
9. <span data-ttu-id="3d28f-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3d28f-128">Click Save.</span></span>
10. <span data-ttu-id="3d28f-129">Dans l'arborescence, sélectionnez « Questions\Je suis assez payé pour mon travail ».</span><span class="sxs-lookup"><span data-stu-id="3d28f-129">In the tree, select 'Questions\I am paid fairly for the work I do.'.</span></span>
    * <span data-ttu-id="3d28f-130">Notez que l'arborescence de questions est mise à jour pour indiquer la dépendance.</span><span class="sxs-lookup"><span data-stu-id="3d28f-130">Note that the question tree updated to show the dependency.</span></span>  


