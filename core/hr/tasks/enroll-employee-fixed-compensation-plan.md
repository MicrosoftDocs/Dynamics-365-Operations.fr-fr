--- 
title: "Inscrire un employé à un régime de rémunération fixe"
description: "La gestionnaire de rémunération et avantages peut affecter des employés à des régimes de rémunération fixe pour gérer leur salaire de base."
author: kherr75
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 88630311a4326508fa69a8938fa216f1a45ba089
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a><span data-ttu-id="46ec5-103">Inscrire un employé à un régime de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="46ec5-103">Enroll an employee in a fixed compensation plan</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="46ec5-104">La gestionnaire de rémunération et avantages peut affecter des employés à des régimes de rémunération fixe pour gérer leur salaire de base.</span><span class="sxs-lookup"><span data-stu-id="46ec5-104">The compensation and benefits manager can assign employees to fixed compensation plans to manage their base pay.</span></span> <span data-ttu-id="46ec5-105">Cette procédure suppose qu'un régime fixe ait été créé et activé, et que des règles d'admissibilité aient été définies pour le régime.</span><span class="sxs-lookup"><span data-stu-id="46ec5-105">This procedure assumes that a fixed plan has been created and is active, and that eligibility rules have been set for the plan.</span></span> <span data-ttu-id="46ec5-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="46ec5-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="46ec5-107">Pour démarrer le processus, allez dans Ressources humaines > Collaborateurs > Employés > Rémunération > Régime fixe</span><span class="sxs-lookup"><span data-stu-id="46ec5-107">To begin the procedure, go to Human resources > Workers > Employees > Compensation > Fixed plan</span></span>

1. <span data-ttu-id="46ec5-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="46ec5-108">Click New.</span></span>
2. <span data-ttu-id="46ec5-109">Dans le champ Action, sélectionnez une action de rémunération fixe de type Embaucher/Rembaucher pour décrire la modification en matière de rémunération de l'employé.</span><span class="sxs-lookup"><span data-stu-id="46ec5-109">In the Action field, select a Fixed compensation action of type Hire/Rehire to describe the change in the employee's compensation.</span></span>
3. <span data-ttu-id="46ec5-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="46ec5-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="46ec5-111">Dans le champ Poste, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="46ec5-111">In the Position field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="46ec5-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="46ec5-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="46ec5-113">Le niveau qui s'affiche provient du niveau de rémunération de la tâche sur le poste.</span><span class="sxs-lookup"><span data-stu-id="46ec5-113">The level that's displayed is from the Compensation Level of the Job on the Position.</span></span> <span data-ttu-id="46ec5-114">Le niveau doit être défini sur cette tâche pour que la rémunération puisse être affectée à l'employé.</span><span class="sxs-lookup"><span data-stu-id="46ec5-114">The level must be set on the Job before compensation can be assigned to the employee.</span></span>  
6. <span data-ttu-id="46ec5-115">Dans le champ Régime, sélectionnez le régime de rémunération fixe pour l'employé.</span><span class="sxs-lookup"><span data-stu-id="46ec5-115">In the Plan field, select the fixed compensation plan for the employee.</span></span> <span data-ttu-id="46ec5-116">La recherche est filtrée pour afficher uniquement les régimes auxquels l'employé peut prétendre en fonction des règles d'admissibilité.</span><span class="sxs-lookup"><span data-stu-id="46ec5-116">The Plan lookup is filtered to show only the plans that the employee is eligible for based on the Eligibility rules.</span></span>
7. <span data-ttu-id="46ec5-117">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="46ec5-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="46ec5-118">Les dates d'effet et d'expiration pour la valeur de rémunération sont définies par défaut entre la date de début et de fin de l'affectation de poste du travailleur.</span><span class="sxs-lookup"><span data-stu-id="46ec5-118">The Effective and Expiration dates for the compensation default from the start and end dates for the worker's position assignment.</span></span> <span data-ttu-id="46ec5-119">Vous pouvez modifier ces dates si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="46ec5-119">You can adjust these dates as needed.</span></span>  
    * <span data-ttu-id="46ec5-120">Si le régime de rémunération fixe est un régime à étapes, sélectionnez l'étape contenant le taux de salaire approprié pour l'employé.</span><span class="sxs-lookup"><span data-stu-id="46ec5-120">If the Fixed compensation plan is a step plan, select the step containing the correct pay rate for the employee.</span></span> <span data-ttu-id="46ec5-121">Si le régime de rémunération fixe est un régime de niveau, entrez le taux de salaire approprié pour l'employé.</span><span class="sxs-lookup"><span data-stu-id="46ec5-121">If the fixed compensation plan is a grade or a band plan, enter the pay rate for the employee.</span></span> <span data-ttu-id="46ec5-122">Le taux de salaire sera validé par rapport aux paramètres de tolérance pour le plan, et les points de référence minimum et maximum pour le niveau de rémunération de la tâche.</span><span class="sxs-lookup"><span data-stu-id="46ec5-122">The pay rate will be validated against the tolerance settings for the plan, and the minimum and maximum reference points for the job's compensation level.</span></span>  
8. <span data-ttu-id="46ec5-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="46ec5-123">Click OK.</span></span>


