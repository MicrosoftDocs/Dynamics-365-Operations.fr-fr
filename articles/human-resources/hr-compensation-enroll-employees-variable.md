---
title: Inscription d'un employé à un régime de rémunération variable
description: La gestionnaire de rémunération et avantages peut inscrire des employés dans des régimes de rémunération variable pour calculer des primes en espèces ou non pour les employés.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a7a173403e79212be5e4aac36d99f349da159e08
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112530"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a><span data-ttu-id="e9757-103">Inscription d'un employé à un régime de rémunération variable</span><span class="sxs-lookup"><span data-stu-id="e9757-103">Enroll an employee in a variable compensation plan</span></span>

<span data-ttu-id="e9757-104">La gestionnaire de rémunération et avantages peut inscrire des employés dans des régimes de rémunération variable pour calculer des primes en espèces ou non pour les employés.</span><span class="sxs-lookup"><span data-stu-id="e9757-104">The Compensation and Benefits manager can enroll employees in variable compensation plans to calculate cash and non-cash awards for employees.</span></span> <span data-ttu-id="e9757-105">Cette procédure suppose qu'un régime de rémunération variable a été créé avec le champ Activer l'inscription défini sur Oui, et que des règles d'admissibilité ont été créées pour ce régime de rémunération variable.</span><span class="sxs-lookup"><span data-stu-id="e9757-105">This procedure assumes that a variable compensation plan has been created with the Enable enrolment field set to Yes, and that eligibility rules have been created for that variable compensation plan.</span></span> <span data-ttu-id="e9757-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="e9757-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="e9757-107">Pour démarrer cette procédure, accédez à Ressources humaines > Collaborateurs > Employés > Rémunération > Inscription au régime variable</span><span class="sxs-lookup"><span data-stu-id="e9757-107">To begin this procedure, go to Human resources > Workers > Employees > Compensation > Variable plan enrolment</span></span>

1. <span data-ttu-id="e9757-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e9757-108">Click New.</span></span>
2. <span data-ttu-id="e9757-109">Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e9757-109">In the Plan field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e9757-110">La recherche est filtrée pour afficher uniquement les régimes de rémunération variable auxquels l'employé peut prétendre en fonction des règles d'admissibilité.</span><span class="sxs-lookup"><span data-stu-id="e9757-110">The plan lookup will be filtered to only show the variable compensation plans that the employee is eligible for based on the eligibility rules.</span></span>  
3. <span data-ttu-id="e9757-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e9757-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="e9757-112">Activez ou désactivez l'extension de la section Général.</span><span class="sxs-lookup"><span data-stu-id="e9757-112">Toggle the expansion of the General section.</span></span>
5. <span data-ttu-id="e9757-113">Entrez une date dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="e9757-113">In the Effective date field, enter a date.</span></span>
6. <span data-ttu-id="e9757-114">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e9757-114">Click Save.</span></span>
7. <span data-ttu-id="e9757-115">Activez ou désactivez l'extension de la section Remplacements.</span><span class="sxs-lookup"><span data-stu-id="e9757-115">Toggle the expansion of the Overrides section.</span></span>
    * <span data-ttu-id="e9757-116">Le cas échéant, une date de règle d'embauche peut être définie pour remplacer la date d'embauche d'un employé lorsque la règle d'embauche spécifiée pour le régime de rémunération variable sélectionné est Pourcentage.</span><span class="sxs-lookup"><span data-stu-id="e9757-116">Optionally, a hire rule date can be set to override the hire date for an employee when the hire rule specified for the selected variable plan is Percent.</span></span>  
    * <span data-ttu-id="e9757-117">Si le régime variable est un pourcentage du régime de base, le pourcentage de prime peut être remplacé pour l'employé.</span><span class="sxs-lookup"><span data-stu-id="e9757-117">If the variable plan is a percent of basis plan, the award percentage can be overridden for the employee.</span></span> <span data-ttu-id="e9757-118">Si le régime de rémunération variable est un nombre d'unités du régime, le nombre d'unités peut être remplacé pour l'employé.</span><span class="sxs-lookup"><span data-stu-id="e9757-118">If the variable compensation plan is a number of units plan, the number of units can be overridden for the employee.</span></span>  
    * <span data-ttu-id="e9757-119">Si un montant fixe doit être octroyé à l'employé pour sa prime, ce montant peut être défini ici.</span><span class="sxs-lookup"><span data-stu-id="e9757-119">If the employee should be given a flat amount for their award, the amount can be set here.</span></span>  
8. <span data-ttu-id="e9757-120">Activez ou désactivez l'extension de la section Remplacements organisationnels.</span><span class="sxs-lookup"><span data-stu-id="e9757-120">Toggle the expansion of the Organizational overrides section.</span></span>
    * <span data-ttu-id="e9757-121">Si les performances de l'employé doivent prendre en compte les performances de différents départements ou d'un département autre que celui affecté au poste de l'employé, le département peut être remplacé.</span><span class="sxs-lookup"><span data-stu-id="e9757-121">If the employee's performance should take into consideration, the performance of different departments, or a department other than the one assigned on the employee's position, the department can be overridden.</span></span> <span data-ttu-id="e9757-122">La colonne de pourcentage doit être égale à 100.</span><span class="sxs-lookup"><span data-stu-id="e9757-122">The Percent column should total 100.</span></span>  

