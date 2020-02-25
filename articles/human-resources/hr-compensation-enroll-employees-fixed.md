---
title: Inscrire un employé à un régime de rémunération fixe
description: La gestionnaire de rémunération et avantages peut affecter des employés à des régimes de rémunération fixe pour gérer leur salaire de base.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 843db6bc133382a701d4b25b164794e57df152c7
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009090"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a><span data-ttu-id="22365-103">Inscrire un employé à un régime de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="22365-103">Enroll an employee in a fixed compensation plan</span></span>

<span data-ttu-id="22365-104">La gestionnaire de rémunération et avantages peut affecter des employés à des régimes de rémunération fixe pour gérer leur salaire de base.</span><span class="sxs-lookup"><span data-stu-id="22365-104">The compensation and benefits manager can assign employees to fixed compensation plans to manage their base pay.</span></span> <span data-ttu-id="22365-105">Cette procédure suppose qu'un régime fixe ait été créé et activé, et que des règles d'admissibilité aient été définies pour le régime.</span><span class="sxs-lookup"><span data-stu-id="22365-105">This procedure assumes that a fixed plan has been created and is active, and that eligibility rules have been set for the plan.</span></span> <span data-ttu-id="22365-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="22365-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="22365-107">Pour démarrer le processus, allez dans Ressources humaines > Collaborateurs > Employés > Rémunération > Régime fixe</span><span class="sxs-lookup"><span data-stu-id="22365-107">To begin the procedure, go to Human resources > Workers > Employees > Compensation > Fixed plan</span></span>

1. <span data-ttu-id="22365-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="22365-108">Click New.</span></span>
2. <span data-ttu-id="22365-109">Dans le champ Action, sélectionnez une action de rémunération fixe de type Embaucher/Rembaucher pour décrire la modification en matière de rémunération de l'employé.</span><span class="sxs-lookup"><span data-stu-id="22365-109">In the Action field, select a Fixed compensation action of type Hire/Rehire to describe the change in the employee's compensation.</span></span>
3. <span data-ttu-id="22365-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="22365-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="22365-111">Dans le champ Poste, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="22365-111">In the Position field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="22365-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="22365-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="22365-113">Le niveau qui s'affiche provient du niveau de rémunération de la tâche sur le poste.</span><span class="sxs-lookup"><span data-stu-id="22365-113">The level that's displayed is from the Compensation Level of the Job on the Position.</span></span> <span data-ttu-id="22365-114">Le niveau doit être défini sur cette tâche pour que la rémunération puisse être affectée à l'employé.</span><span class="sxs-lookup"><span data-stu-id="22365-114">The level must be set on the Job before compensation can be assigned to the employee.</span></span>  
6. <span data-ttu-id="22365-115">Dans le champ Régime, sélectionnez le régime de rémunération fixe pour l'employé.</span><span class="sxs-lookup"><span data-stu-id="22365-115">In the Plan field, select the fixed compensation plan for the employee.</span></span> <span data-ttu-id="22365-116">La recherche est filtrée pour afficher uniquement les régimes auxquels l'employé peut prétendre en fonction des règles d'admissibilité.</span><span class="sxs-lookup"><span data-stu-id="22365-116">The Plan lookup is filtered to show only the plans that the employee is eligible for based on the Eligibility rules.</span></span>
7. <span data-ttu-id="22365-117">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="22365-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="22365-118">Les dates d'effet et d'expiration pour la valeur de rémunération sont définies par défaut entre la date de début et de fin de l'affectation de poste du travailleur.</span><span class="sxs-lookup"><span data-stu-id="22365-118">The Effective and Expiration dates for the compensation default from the start and end dates for the worker's position assignment.</span></span> <span data-ttu-id="22365-119">Vous pouvez modifier ces dates si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="22365-119">You can adjust these dates as needed.</span></span>  
    * <span data-ttu-id="22365-120">Si le régime de rémunération fixe est un régime à étapes, sélectionnez l'étape contenant le taux de salaire approprié pour l'employé.</span><span class="sxs-lookup"><span data-stu-id="22365-120">If the Fixed compensation plan is a step plan, select the step containing the correct pay rate for the employee.</span></span> <span data-ttu-id="22365-121">Si le régime de rémunération fixe est un régime de niveau, entrez le taux de salaire approprié pour l'employé.</span><span class="sxs-lookup"><span data-stu-id="22365-121">If the fixed compensation plan is a grade or a band plan, enter the pay rate for the employee.</span></span> <span data-ttu-id="22365-122">Le taux de salaire sera validé par rapport aux paramètres de tolérance pour le plan, et les points de référence minimum et maximum pour le niveau de rémunération de la tâche.</span><span class="sxs-lookup"><span data-stu-id="22365-122">The pay rate will be validated against the tolerance settings for the plan, and the minimum and maximum reference points for the job's compensation level.</span></span>  
8. <span data-ttu-id="22365-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="22365-123">Click OK.</span></span>

