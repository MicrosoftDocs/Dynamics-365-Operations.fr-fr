---
title: Affecter des utilisateurs à des rôles de sécurité
description: Pour accéder aux applications Finance and Operations, les utilisateurs doivent être affectés à des rôles de sécurité.
author: ChrisGarty
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0744f45ac91dfb9b5aae35091e3675202c9144f9
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143541"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="e7123-103">Affecter des utilisateurs à des rôles de sécurité</span><span class="sxs-lookup"><span data-stu-id="e7123-103">Assign users to security roles</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e7123-104">Pour utiliser autre chose que les fonctionnalités courantes, des rôles de sécurité doivent être attribués aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e7123-104">To use anything other than common capabilities, users must be assigned to security roles.</span></span> <span data-ttu-id="e7123-105">Cette procédure explique comment les administrateurs système peuvent affecter automatiquement des utilisateurs aux rôles, selon les données commerciales.</span><span class="sxs-lookup"><span data-stu-id="e7123-105">This procedure explains how system administrators can automatically assign users to roles, based on business data.</span></span> 

## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="e7123-106">Affecter automatiquement des utilisateurs à des rôles</span><span class="sxs-lookup"><span data-stu-id="e7123-106">Automatically assign users to roles</span></span>
1. <span data-ttu-id="e7123-107">Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Affecter des utilisateurs aux rôles**.</span><span class="sxs-lookup"><span data-stu-id="e7123-107">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="e7123-108">Sélectionnez Chef comptable dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="e7123-108">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="e7123-109">Sélectionnez le rôle pour lequel configurer la règle.</span><span class="sxs-lookup"><span data-stu-id="e7123-109">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="e7123-110">Dans cet exemple, sélectionnez Chef comptable.</span><span class="sxs-lookup"><span data-stu-id="e7123-110">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="e7123-111">Cliquez sur **Ajouter la règle** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e7123-111">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="e7123-112">Dans la liste **Sélectionner une requête**, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e7123-112">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="e7123-113">Sélectionnez la requête à utiliser pour cette règle.</span><span class="sxs-lookup"><span data-stu-id="e7123-113">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="e7123-114">Dans la liste **Nom de la règle d'appartenance**, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e7123-114">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e7123-115">Cliquez sur **Modifier la requête.**</span><span class="sxs-lookup"><span data-stu-id="e7123-115">Click **Edit query**.</span></span> <span data-ttu-id="e7123-116">Modifiez la requête, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="e7123-116">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="e7123-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7123-117">Click **OK**.</span></span>
8. <span data-ttu-id="e7123-118">Cliquez sur **Exécuter l'affectation automatique de rôle**.</span><span class="sxs-lookup"><span data-stu-id="e7123-118">Click **Run automatic role assignment**.</span></span>
9. <span data-ttu-id="e7123-119">Accédez à **Volet Navigation > Modules > Administration système > Utilisateurs > Utilisateurs** (idéalement dans un onglet distinct du navigateur).</span><span class="sxs-lookup"><span data-stu-id="e7123-119">Go to **Navigation pane > Modules > System administration > Users > Users** (ideally in a separate browser tab).</span></span>
10. <span data-ttu-id="e7123-120">Examinez les rôles affectés à différents utilisateurs pour confirmer que la requête d'affectation du rôle était correcte.</span><span class="sxs-lookup"><span data-stu-id="e7123-120">Review the roles assigned to various users to confirm that the role assignment query was correct.</span></span> <span data-ttu-id="e7123-121">Ajustez et réexécutez si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e7123-121">Adjust and re-run if needed.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="e7123-122">Exclure des utilisateurs de l'affectation automatique de rôle</span><span class="sxs-lookup"><span data-stu-id="e7123-122">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="e7123-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e7123-123">Close the page.</span></span>
2. <span data-ttu-id="e7123-124">Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Affecter des utilisateurs aux rôles**.</span><span class="sxs-lookup"><span data-stu-id="e7123-124">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="e7123-125">Sélectionnez Chef comptable dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="e7123-125">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="e7123-126">Permet de sélectionner un rôle.</span><span class="sxs-lookup"><span data-stu-id="e7123-126">Select a role.</span></span> <span data-ttu-id="e7123-127">Pour cet exemple, sélectionnez Chef comptable.</span><span class="sxs-lookup"><span data-stu-id="e7123-127">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="e7123-128">Dans le menu **Utilisateurs attribués au rôle**, sélectionnez **Affecter/exclure manuellement des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="e7123-128">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="e7123-129">Dans la liste **Affecter des utilisateurs au rôle ou exclure des utilisateurs du rôle**, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e7123-129">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="e7123-130">Sélectionner un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e7123-130">Select a user.</span></span>  
6. <span data-ttu-id="e7123-131">Sous le **volet Actions**, sélectionnez **Exclure du rôle**.</span><span class="sxs-lookup"><span data-stu-id="e7123-131">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="e7123-132">Cliquez sur **Exclure du rôle** pour exclure les utilisateurs sélectionnés du rôle.</span><span class="sxs-lookup"><span data-stu-id="e7123-132">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="e7123-133">Pour supprimer des exclusions, sélectionnez les utilisateurs à supprimer des exclusions, puis cliquez sur **Redéfinition du statut**.</span><span class="sxs-lookup"><span data-stu-id="e7123-133">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="e7123-134">Lorsque vous supprimez une exclusion en réinitialisant le statut de l'utilisateur, le rôle d'utilisateur est de nouveau affecté automatiquement.</span><span class="sxs-lookup"><span data-stu-id="e7123-134">When you remove an exclusion by resetting the user's status, the user's role is again assigned automatically.</span></span> <span data-ttu-id="e7123-135">Toutefois, l'utilisateur n'est pas immédiatement affecté au rôle ou exclu du rôle lorsque vous réinitialisez le statut.</span><span class="sxs-lookup"><span data-stu-id="e7123-135">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="e7123-136">Au lieu de cela, l'utilisateur est affecté au rôle ou exclu de celui-ci la prochaine fois que les règles pour l'affectation de rôle automatique sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="e7123-136">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
