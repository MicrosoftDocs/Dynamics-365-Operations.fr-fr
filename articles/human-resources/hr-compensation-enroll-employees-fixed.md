---
title: Inscrire un employé à un régime de rémunération fixe
description: La gestionnaire de rémunération et avantages peut affecter des employés à des régimes de rémunération fixe pour gérer leur salaire de base.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc8373a4a39a1a212ab445b2b300fbddfe0e4a39
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112531"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a><span data-ttu-id="3e6bb-103">Inscrire un employé à un régime de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="3e6bb-103">Enroll an employee in a fixed compensation plan</span></span>

<span data-ttu-id="3e6bb-104">La gestionnaire de rémunération et avantages peut affecter des employés à des régimes de rémunération fixe pour gérer leur salaire de base.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-104">The compensation and benefits manager can assign employees to fixed compensation plans to manage their base pay.</span></span> <span data-ttu-id="3e6bb-105">Cette procédure suppose qu'un régime fixe ait été créé et activé, et que des règles d'admissibilité aient été définies pour le régime.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-105">This procedure assumes that a fixed plan has been created and is active, and that eligibility rules have been set for the plan.</span></span> <span data-ttu-id="3e6bb-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="3e6bb-107">Pour démarrer le processus, allez dans Ressources humaines > Collaborateurs > Employés > Rémunération > Régime fixe</span><span class="sxs-lookup"><span data-stu-id="3e6bb-107">To begin the procedure, go to Human resources > Workers > Employees > Compensation > Fixed plan</span></span>

1. <span data-ttu-id="3e6bb-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-108">Click New.</span></span>
2. <span data-ttu-id="3e6bb-109">Dans le champ Action, sélectionnez une action de rémunération fixe de type Embaucher/Rembaucher pour décrire la modification en matière de rémunération de l'employé.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-109">In the Action field, select a Fixed compensation action of type Hire/Rehire to describe the change in the employee's compensation.</span></span>
3. <span data-ttu-id="3e6bb-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="3e6bb-111">Dans le champ Poste, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-111">In the Position field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="3e6bb-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3e6bb-113">Le niveau qui s'affiche provient du niveau de rémunération de la tâche sur le poste.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-113">The level that's displayed is from the Compensation Level of the Job on the Position.</span></span> <span data-ttu-id="3e6bb-114">Le niveau doit être défini sur cette tâche pour que la rémunération puisse être affectée à l'employé.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-114">The level must be set on the Job before compensation can be assigned to the employee.</span></span>  
6. <span data-ttu-id="3e6bb-115">Dans le champ Régime, sélectionnez le régime de rémunération fixe pour l'employé.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-115">In the Plan field, select the fixed compensation plan for the employee.</span></span> <span data-ttu-id="3e6bb-116">La recherche est filtrée pour afficher uniquement les régimes auxquels l'employé peut prétendre en fonction des règles d'admissibilité.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-116">The Plan lookup is filtered to show only the plans that the employee is eligible for based on the Eligibility rules.</span></span>
7. <span data-ttu-id="3e6bb-117">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3e6bb-118">Les dates d'effet et d'expiration pour la valeur de rémunération sont définies par défaut entre la date de début et de fin de l'affectation de poste du travailleur.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-118">The Effective and Expiration dates for the compensation default from the start and end dates for the worker's position assignment.</span></span> <span data-ttu-id="3e6bb-119">Vous pouvez modifier ces dates si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-119">You can adjust these dates as needed.</span></span>  
    * <span data-ttu-id="3e6bb-120">Si le régime de rémunération fixe est un régime à étapes, sélectionnez l'étape contenant le taux de salaire approprié pour l'employé.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-120">If the Fixed compensation plan is a step plan, select the step containing the correct pay rate for the employee.</span></span> <span data-ttu-id="3e6bb-121">Si le régime de rémunération fixe est un régime de niveau, entrez le taux de salaire approprié pour l'employé.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-121">If the fixed compensation plan is a grade or a band plan, enter the pay rate for the employee.</span></span> <span data-ttu-id="3e6bb-122">Le taux de salaire sera validé par rapport aux paramètres de tolérance pour le plan, et les points de référence minimum et maximum pour le niveau de rémunération de la tâche.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-122">The pay rate will be validated against the tolerance settings for the plan, and the minimum and maximum reference points for the job's compensation level.</span></span>  
8. <span data-ttu-id="3e6bb-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3e6bb-123">Click OK.</span></span>

