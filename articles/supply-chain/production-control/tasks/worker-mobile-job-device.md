--- 
title: "Configurer un collaborateur à l'aide du périphérique de travail mobile"
description: "Cette procédure vous indique comment affecter des rôles corrects au compte utilisateur d'un collaborateur, puis autoriser ce collaborateur à effectuer des enregistrements d'atelier."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 5322d77af470c25f0849cbbfbbfbc4a50a7e859b
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="7a773-103">Configurer un collaborateur à l'aide du périphérique de travail mobile</span><span class="sxs-lookup"><span data-stu-id="7a773-103">Configure a worker using the mobile job device</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7a773-104">Cette procédure vous indique comment affecter des rôles corrects au compte utilisateur d'un collaborateur, puis autoriser ce collaborateur à effectuer des enregistrements d'atelier.</span><span class="sxs-lookup"><span data-stu-id="7a773-104">This procedure shows you how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>


## <a name="assign-roles-to-user-account"></a><span data-ttu-id="7a773-105">Affecter des rôles au compte utilisateur</span><span class="sxs-lookup"><span data-stu-id="7a773-105">Assign roles to user account</span></span>
1. <span data-ttu-id="7a773-106">Accédez à Administration système > Utilisateurs > Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7a773-106">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="7a773-107">Utilisez le filtre rapide pour filtrer sur le nom d'un collaborateur pour lequel le compte utilisateur est associé au rôle d'opérateur.</span><span class="sxs-lookup"><span data-stu-id="7a773-107">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="7a773-108">Dans les données d'exemple, le nom est Shannon.</span><span class="sxs-lookup"><span data-stu-id="7a773-108">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="7a773-109">Mettre en surbrillance l'enregistrement du compte utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7a773-109">Highlight the user account record.</span></span>
4. <span data-ttu-id="7a773-110">Dans la liste, cliquez sur le lien « Nom » de la ligne sélectionnée pour afficher les détails du compte utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7a773-110">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="7a773-111">Dans l'arborescence, sélectionnez « Rôles\opérateur ».</span><span class="sxs-lookup"><span data-stu-id="7a773-111">In the tree, select 'Roles\Machine operator'.</span></span>
6. <span data-ttu-id="7a773-112">Fermez la page des détails du compte utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7a773-112">Close the user account details page.</span></span>
7. <span data-ttu-id="7a773-113">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7a773-113">Close the page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="7a773-114">Paramétrez le compte du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="7a773-114">Configure worker account.</span></span>
1. <span data-ttu-id="7a773-115">Accédez à Ressources humaines > Collaborateurs > Collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="7a773-115">Go to Human resources > Workers > Workers.</span></span>
2. <span data-ttu-id="7a773-116">Utilisez le filtre rapide pour filtrer sur le nom d'un collaborateur pour lequel le compte utilisateur est associé au rôle d'opérateur.</span><span class="sxs-lookup"><span data-stu-id="7a773-116">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="7a773-117">Dans les données d'exemple, le nom est Shannon.</span><span class="sxs-lookup"><span data-stu-id="7a773-117">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="7a773-118">Mettre en surbrillance l'enregistrement du compte utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7a773-118">Highlight the user account record.</span></span>
4. <span data-ttu-id="7a773-119">Dans la liste, cliquez sur le lien « Nom » de la ligne sélectionnée pour afficher les détails du compte utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7a773-119">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="7a773-120">Cliquez sur l'onglet Emploi.</span><span class="sxs-lookup"><span data-stu-id="7a773-120">Click the Employment tab.</span></span>
6. <span data-ttu-id="7a773-121">Développez l'organisateur Enregistrement du temps et cliquez sur Activer sur les terminaux d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="7a773-121">Expand the Time registration FastTab and click Activate on registration terminals.</span></span>
7. <span data-ttu-id="7a773-122">Cliquez sur Activer sur les terminaux d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="7a773-122">Click Activate on registration terminals.</span></span>
8. <span data-ttu-id="7a773-123">Dans le champ Groupe de calcul, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7a773-123">In the Calculation group field, enter or select a value.</span></span>
9. <span data-ttu-id="7a773-124">Dans le champ Groupe de calcul par défaut, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7a773-124">In the Default calculation group field, enter or select a value.</span></span>
10. <span data-ttu-id="7a773-125">Dans le champ Groupe d'approbation, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7a773-125">In the Approval group field, enter or select a value.</span></span>
11. <span data-ttu-id="7a773-126">Dans le champ Profil standard, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7a773-126">In the Standard profile field, enter or select a value.</span></span>
12. <span data-ttu-id="7a773-127">Dans le champ Groupe de profils, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7a773-127">In the Profile group field, enter or select a value.</span></span>
13. <span data-ttu-id="7a773-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7a773-128">Click OK.</span></span>
14. <span data-ttu-id="7a773-129">Cliquez sur Modifier pour saisir un numéro de badge pour le nouveau collaborateur qualifié pour l'enregistrement des heures.</span><span class="sxs-lookup"><span data-stu-id="7a773-129">Click Edit to enter a badge number for the new time registration worker.</span></span>
15. <span data-ttu-id="7a773-130">Dans le champ ID badge, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7a773-130">In the Badge ID field, type a value.</span></span>
16. <span data-ttu-id="7a773-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7a773-131">Click Save.</span></span>
17. <span data-ttu-id="7a773-132">Utilisez le raccourci SaveRecord.</span><span class="sxs-lookup"><span data-stu-id="7a773-132">Use the SaveRecord shortcut.</span></span>
18. <span data-ttu-id="7a773-133">Fermez la page des détails du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="7a773-133">Close the worker details page.</span></span>
19. <span data-ttu-id="7a773-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7a773-134">Close the page.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="7a773-135">Affectez le collaborateur au groupe de périphériques.</span><span class="sxs-lookup"><span data-stu-id="7a773-135">Assign worker to device group.</span></span>
1. <span data-ttu-id="7a773-136">Accédez à Contrôle de la production > Paramétrage > Contrôle et suivi de la production > Configurer le bon de travail pour les périphériques.</span><span class="sxs-lookup"><span data-stu-id="7a773-136">Go to Production control > Setup > Manufacturing execution > Configure job card for devices.</span></span>
2. <span data-ttu-id="7a773-137">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="7a773-137">Click Add.</span></span>
3. <span data-ttu-id="7a773-138">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7a773-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="7a773-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7a773-139">Click OK.</span></span>
5. <span data-ttu-id="7a773-140">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="7a773-140">Click Edit.</span></span>
6. <span data-ttu-id="7a773-141">Dans le champ Unité de production, vous pouvez définir le filtre par défaut pour le collaborateur.</span><span class="sxs-lookup"><span data-stu-id="7a773-141">In the Production unit field, you can set the default filter for the worker.</span></span> <span data-ttu-id="7a773-142">Cela garantit que seules les tâches de production pour l'unité de production sélectionnée sont affichées lorsque le collaborateur se connecte au périphérique.</span><span class="sxs-lookup"><span data-stu-id="7a773-142">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span>
7. <span data-ttu-id="7a773-143">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7a773-143">Close the page.</span></span>

