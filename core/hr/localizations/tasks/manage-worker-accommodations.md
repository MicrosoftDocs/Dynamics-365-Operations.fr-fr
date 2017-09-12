--- 
title: "Gérer les logements des collaborateurs"
description: "Cette procédure décrit le paramétrage des types d'aménagements de l'environnement de travail, tels que les chaises ergonomiques ou les pauses périodiques."
author: ShielaSogge
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
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 10d34d0b2eca95034d1f67931ff72a035be9a6b8
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="manage-worker-accommodations"></a><span data-ttu-id="596bf-103">Gérer les logements des collaborateurs</span><span class="sxs-lookup"><span data-stu-id="596bf-103">Manage worker accommodations</span></span>

[!include[task guide banner](../../../includes/task-guide-banner.md)]

<span data-ttu-id="596bf-104">Cette procédure décrit le paramétrage des types d'aménagements de l'environnement de travail, tels que les chaises ergonomiques ou les pauses périodiques.</span><span class="sxs-lookup"><span data-stu-id="596bf-104">This procedure walks through the steps for setting up work environment accommodation types, such as ergonomic chairs or periodic breaks.</span></span> <span data-ttu-id="596bf-105">Elle indique également la procédure pour affecter ces types d'aménagements à un collaborateur, et pour approuver ou refuser le type d'aménagement.</span><span class="sxs-lookup"><span data-stu-id="596bf-105">It also shows how to assign these accommodation types to a worker, and either approve or deny the accommodation type.</span></span> <span data-ttu-id="596bf-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="596bf-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="setup-accommodations"></a><span data-ttu-id="596bf-107">Configurer des aménagements</span><span class="sxs-lookup"><span data-stu-id="596bf-107">Setup accommodations</span></span>
1. <span data-ttu-id="596bf-108">Accédez à Ressources humaines > Paramétrage > Types d'aménagements.</span><span class="sxs-lookup"><span data-stu-id="596bf-108">Go to Human resources > Setup > Accommodation types.</span></span>
2. <span data-ttu-id="596bf-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="596bf-109">Click New.</span></span>
3. <span data-ttu-id="596bf-110">Dans le champ Type d'aménagement, entrez un nom pour le type d'aménagement.</span><span class="sxs-lookup"><span data-stu-id="596bf-110">In the Accommodation type field, enter a name for the accommodation.</span></span> <span data-ttu-id="596bf-111">Exemple : Clavier.</span><span class="sxs-lookup"><span data-stu-id="596bf-111">Example: Keyboard.</span></span>
4. <span data-ttu-id="596bf-112">Dans le champ Description, entrez une description de l'aménagement.</span><span class="sxs-lookup"><span data-stu-id="596bf-112">In the Description field, enter a description for the accommodation.</span></span> <span data-ttu-id="596bf-113">Exemple : Clavier ergonomique.</span><span class="sxs-lookup"><span data-stu-id="596bf-113">Example: Ergonomic Keyboard.</span></span>
5. <span data-ttu-id="596bf-114">Dans le champ Note, entrez les informations qui vous aident à clarifier l'aménagement.</span><span class="sxs-lookup"><span data-stu-id="596bf-114">In the Note field, enter any information that helps to clarify the accommodation.</span></span>
6. <span data-ttu-id="596bf-115">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="596bf-115">Click Save.</span></span>
7. <span data-ttu-id="596bf-116">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="596bf-116">Close the page.</span></span>

## <a name="assign-accommodations"></a><span data-ttu-id="596bf-117">Attribuer des aménagements</span><span class="sxs-lookup"><span data-stu-id="596bf-117">Assign accommodations</span></span>
1. <span data-ttu-id="596bf-118">Accédez à Ressources humaines > Collaborateurs > Employés.</span><span class="sxs-lookup"><span data-stu-id="596bf-118">Go to Human resources > Workers > Employees.</span></span>
2. <span data-ttu-id="596bf-119">Dans la liste, sélectionnez un employé.</span><span class="sxs-lookup"><span data-stu-id="596bf-119">From the list, select an employee.</span></span>
3. <span data-ttu-id="596bf-120">Cliquez sur le nom d'un employé pour afficher les détails de l'employé qui demande les aménagements.</span><span class="sxs-lookup"><span data-stu-id="596bf-120">Click the employee's name to view details about the employee who is requesting the accommodation.</span></span>
4. <span data-ttu-id="596bf-121">Développez Organisateur des informations personnelles.</span><span class="sxs-lookup"><span data-stu-id="596bf-121">Expand the Personal information FastTab.</span></span>
5. <span data-ttu-id="596bf-122">Cliquez sur Aménagements.</span><span class="sxs-lookup"><span data-stu-id="596bf-122">Click Accommodations.</span></span>
6. <span data-ttu-id="596bf-123">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="596bf-123">Click New.</span></span>
7. <span data-ttu-id="596bf-124">Dans le champ Type d'aménagement, sélectionnez l'aménagement approprié.</span><span class="sxs-lookup"><span data-stu-id="596bf-124">In the Accommodation type field, select the appropriate accommodation.</span></span> <span data-ttu-id="596bf-125">Exemple : Clavier</span><span class="sxs-lookup"><span data-stu-id="596bf-125">Example: Keyboard</span></span>
8. <span data-ttu-id="596bf-126">Dans le champ Tâche, entrez la tâche qui nécessite l'aménagement.</span><span class="sxs-lookup"><span data-stu-id="596bf-126">In the Job task field, enter the work task that requires the accommodation.</span></span>
9. <span data-ttu-id="596bf-127">Dans le champ Statut, entrez le statut approprié.</span><span class="sxs-lookup"><span data-stu-id="596bf-127">In the Status field, enter the appropriate status.</span></span> <span data-ttu-id="596bf-128">Exemple : Raisonnable</span><span class="sxs-lookup"><span data-stu-id="596bf-128">Example: Reasonable</span></span>
    * <span data-ttu-id="596bf-129">Les statuts suivants sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="596bf-129">The following statuses are available.</span></span> <span data-ttu-id="596bf-130">Demandé indique que la demande d'aménagement a été créée mais pas encore été examinée.</span><span class="sxs-lookup"><span data-stu-id="596bf-130">Requested indicates that the accommodation has been created but not yet reviewed.</span></span> <span data-ttu-id="596bf-131">Raisonnable indique que l'aménagement est raisonnable et sera accordé.</span><span class="sxs-lookup"><span data-stu-id="596bf-131">Reasonable indicates that the accommodation is reasonable and will be granted.</span></span> <span data-ttu-id="596bf-132">Difficultés anormale indique que l'aménagement entraînera des frais déraisonnables pour l'employeur et qu'il a été refusé.</span><span class="sxs-lookup"><span data-stu-id="596bf-132">Undue hardship indicates that the accommodation will place an unreasonable burden on the employer, and has been denied.</span></span> <span data-ttu-id="596bf-133">Dans cet exemple, la demande a été approuvée immédiatement, car la demande d'aménagement était minimale.</span><span class="sxs-lookup"><span data-stu-id="596bf-133">In this example, the request was approved immediately because the accommodation request was minimal.</span></span>  
10. <span data-ttu-id="596bf-134">Dans le champ Accepté, sélectionnez la personne qui a accepté la demande d'aménagement.</span><span class="sxs-lookup"><span data-stu-id="596bf-134">In the Accepted field, select the person who accepted the accommodation request.</span></span>
11. <span data-ttu-id="596bf-135">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="596bf-135">Click Select.</span></span>
12. <span data-ttu-id="596bf-136">Dans le champ Date acceptée, entrez la date et l'heure auxquelles la demande d'aménagement a été acceptée.</span><span class="sxs-lookup"><span data-stu-id="596bf-136">In the Accepted date field, enter the date and time when the accommodation request was accepted.</span></span>
13. <span data-ttu-id="596bf-137">Développez la section Note.</span><span class="sxs-lookup"><span data-stu-id="596bf-137">Expand the Note section.</span></span>
14. <span data-ttu-id="596bf-138">Dans le champ Financier, entrez les coûts d'informations ou de ressources qui permettent de clarifier l'impact de l'aménagement.</span><span class="sxs-lookup"><span data-stu-id="596bf-138">In the Financial field, enter any information or resource costs that helps to clarify the impact of the accommodation.</span></span>
    * <span data-ttu-id="596bf-139">Si l'aménagement a été refusé, le champ Réponse peut être utilisé pour indiquer la raison du refus.</span><span class="sxs-lookup"><span data-stu-id="596bf-139">If the accommodation has been denied, the Reply field can be used to indicate why a request was denied.</span></span>  
15. <span data-ttu-id="596bf-140">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="596bf-140">Click Save.</span></span>


