---
title: Affecter des utilisateurs à des rôles de sécurité
description: Pour accéder aux applications Finance and Operations, des rôles de sécurité doivent être affectés aux utilisateurs.
author: ChrisGarty
manager: AnnBe
ms.date: 09/16/2019
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
ms.openlocfilehash: a4daecc1acd589cd1656402244e5325382a407e7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180965"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="ad021-103">Affecter des utilisateurs à des rôles de sécurité</span><span class="sxs-lookup"><span data-stu-id="ad021-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ad021-104">Pour utiliser autre chose que les fonctionnalités courantes, des rôles de sécurité doivent être attribués aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ad021-104">To use anything other than common capabilities, users must be assigned to security roles.</span></span> <span data-ttu-id="ad021-105">Cette procédure explique comment les administrateurs système peuvent affecter automatiquement des utilisateurs aux rôles, selon les données commerciales.</span><span class="sxs-lookup"><span data-stu-id="ad021-105">This procedure explains how system administrators can automatically assign users to roles, based on business data.</span></span> 

## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="ad021-106">Affecter automatiquement des utilisateurs à des rôles</span><span class="sxs-lookup"><span data-stu-id="ad021-106">Automatically assign users to roles</span></span>
1. <span data-ttu-id="ad021-107">Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Affecter des utilisateurs aux rôles**.</span><span class="sxs-lookup"><span data-stu-id="ad021-107">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="ad021-108">Sélectionnez Chef comptable dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="ad021-108">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="ad021-109">Sélectionnez le rôle pour lequel configurer la règle.</span><span class="sxs-lookup"><span data-stu-id="ad021-109">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="ad021-110">Dans cet exemple, sélectionnez Chef comptable.</span><span class="sxs-lookup"><span data-stu-id="ad021-110">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="ad021-111">Cliquez sur **Ajouter la règle** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ad021-111">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="ad021-112">Dans la liste **Sélectionner une requête**, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ad021-112">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="ad021-113">Sélectionnez la requête à utiliser pour cette règle.</span><span class="sxs-lookup"><span data-stu-id="ad021-113">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="ad021-114">Dans la liste **Nom de la règle d'appartenance**, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ad021-114">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="ad021-115">Cliquez sur **Modifier la requête.**</span><span class="sxs-lookup"><span data-stu-id="ad021-115">Click **Edit query**.</span></span> <span data-ttu-id="ad021-116">Modifiez la requête, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="ad021-116">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="ad021-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad021-117">Click **OK**.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="ad021-118">Exclure des utilisateurs de l'affectation automatique de rôle</span><span class="sxs-lookup"><span data-stu-id="ad021-118">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="ad021-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ad021-119">Close the page.</span></span>
2. <span data-ttu-id="ad021-120">Accédez à **Volet de navigation > Modules > Administration système > Sécurité > Affecter des utilisateurs aux rôles**.</span><span class="sxs-lookup"><span data-stu-id="ad021-120">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="ad021-121">Sélectionnez Chef comptable dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="ad021-121">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="ad021-122">Permet de sélectionner un rôle.</span><span class="sxs-lookup"><span data-stu-id="ad021-122">Select a role.</span></span> <span data-ttu-id="ad021-123">Pour cet exemple, sélectionnez Chef comptable.</span><span class="sxs-lookup"><span data-stu-id="ad021-123">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="ad021-124">Dans le menu **Utilisateurs attribués au rôle**, sélectionnez **Affecter/exclure manuellement des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="ad021-124">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="ad021-125">Dans la liste **Affecter des utilisateurs au rôle ou exclure des utilisateurs du rôle**, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ad021-125">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="ad021-126">Sélectionner un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ad021-126">Select a user.</span></span>  
6. <span data-ttu-id="ad021-127">Sous le **volet Actions**, sélectionnez **Exclure du rôle**.</span><span class="sxs-lookup"><span data-stu-id="ad021-127">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="ad021-128">Cliquez sur **Exclure du rôle** pour exclure les utilisateurs sélectionnés du rôle.</span><span class="sxs-lookup"><span data-stu-id="ad021-128">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="ad021-129">Pour supprimer des exclusions, sélectionnez les utilisateurs à supprimer des exclusions, puis cliquez sur **Redéfinition du statut**.</span><span class="sxs-lookup"><span data-stu-id="ad021-129">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="ad021-130">Lorsque vous supprimez une exclusion en réinitialisant le statut de l'utilisateur, le rôle d'utilisateur est de nouveau affecté automatiquement.</span><span class="sxs-lookup"><span data-stu-id="ad021-130">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="ad021-131">Toutefois, l'utilisateur n'est pas immédiatement affecté au rôle ou exclu du rôle lorsque vous réinitialisez le statut.</span><span class="sxs-lookup"><span data-stu-id="ad021-131">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="ad021-132">Au lieu de cela, l'utilisateur est affecté au rôle ou exclu de celui-ci la prochaine fois que les règles pour l'affectation de rôle automatique sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="ad021-132">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
