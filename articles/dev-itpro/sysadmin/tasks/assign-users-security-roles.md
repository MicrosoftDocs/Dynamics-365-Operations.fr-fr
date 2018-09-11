--- 
title: "Affecter des utilisateurs à des rôles de sécurité"
description: "Pour accéder à Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, des rôles de sécurité doivent être affectés aux utilisateurs."
author: maertenm
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: c08c9ee27bef3ec8c51df558766f55d3ea4ac48a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="bf326-103">Affecter des utilisateurs à des rôles de sécurité</span><span class="sxs-lookup"><span data-stu-id="bf326-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bf326-104">Pour accéder à Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, des rôles de sécurité doivent être affectés aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bf326-104">To access Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, users must be assigned to security roles.</span></span> <span data-ttu-id="bf326-105">Cette procédure explique comment les administrateurs système peuvent affecter des utilisateurs aux rôles automatiquement, selon les données commerciales.</span><span class="sxs-lookup"><span data-stu-id="bf326-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="bf326-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="bf326-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="bf326-107">Affecter automatiquement des utilisateurs à des rôles</span><span class="sxs-lookup"><span data-stu-id="bf326-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="bf326-108">Allez dans Administration du système > Sécurité > Affecter des utilisateurs aux rôles.</span><span class="sxs-lookup"><span data-stu-id="bf326-108">Go to System administration > Security > Assign users to roles.</span></span>
2. <span data-ttu-id="bf326-109">Sélectionnez Chef comptable dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="bf326-109">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="bf326-110">Sélectionnez le rôle pour lequel configurer la règle.</span><span class="sxs-lookup"><span data-stu-id="bf326-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="bf326-111">Dans cet exemple, sélectionnez Chef comptable.</span><span class="sxs-lookup"><span data-stu-id="bf326-111">In this example, select Accounting supervisor.</span></span>  
3. <span data-ttu-id="bf326-112">Cliquez sur Ajouter la règle pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bf326-112">Click Add rule to open the drop dialog.</span></span>
4. <span data-ttu-id="bf326-113">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="bf326-113">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="bf326-114">Sélectionnez la requête à utiliser pour cette règle.</span><span class="sxs-lookup"><span data-stu-id="bf326-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="bf326-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bf326-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="bf326-116">Cliquez sur Modifier la demande.</span><span class="sxs-lookup"><span data-stu-id="bf326-116">Click Edit query.</span></span>
    * <span data-ttu-id="bf326-117">Modifiez la requête, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="bf326-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="bf326-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bf326-118">Click OK.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="bf326-119">Exclure des utilisateurs de l'affectation automatique de rôle</span><span class="sxs-lookup"><span data-stu-id="bf326-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="bf326-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bf326-120">Close the page.</span></span>
2. <span data-ttu-id="bf326-121">Allez dans Administration du système > Sécurité > Affecter des utilisateurs aux rôles.</span><span class="sxs-lookup"><span data-stu-id="bf326-121">Go to System administration > Security > Assign users to roles.</span></span>
3. <span data-ttu-id="bf326-122">Sélectionnez Chef comptable dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="bf326-122">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="bf326-123">Permet de sélectionner un rôle.</span><span class="sxs-lookup"><span data-stu-id="bf326-123">Select a role.</span></span> <span data-ttu-id="bf326-124">Pour cet exemple, sélectionnez Chef comptable.</span><span class="sxs-lookup"><span data-stu-id="bf326-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="bf326-125">Cliquez sur Affecter/exclure manuellement des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bf326-125">Click Manually assign / exclude users.</span></span>
5. <span data-ttu-id="bf326-126">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bf326-126">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="bf326-127">Sélectionner un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bf326-127">Select a user.</span></span>  
6. <span data-ttu-id="bf326-128">Cliquez sur Exclure du rôle.</span><span class="sxs-lookup"><span data-stu-id="bf326-128">Click Exclude from role.</span></span>
    * <span data-ttu-id="bf326-129">Cliquez sur Exclure du rôle pour exclure les utilisateurs sélectionnés du rôle.</span><span class="sxs-lookup"><span data-stu-id="bf326-129">Click Exclude from role to exclude the selected users from the role.</span></span> <span data-ttu-id="bf326-130">Pour supprimer des exclusions, sélectionnez les utilisateurs à supprimer des exclusions, puis cliquez sur Redéfinition du statut.</span><span class="sxs-lookup"><span data-stu-id="bf326-130">To remove exclusions, select the users that you want to remove exclusions for, and then click Reset status.</span></span> <span data-ttu-id="bf326-131">Lorsque vous supprimez une exclusion en réinitialisant le statut de l'utilisateur, le rôle d'utilisateur est de nouveau affecté automatiquement.</span><span class="sxs-lookup"><span data-stu-id="bf326-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="bf326-132">Toutefois, l'utilisateur n'est pas immédiatement affecté au rôle ou exclu du rôle lorsque vous réinitialisez le statut.</span><span class="sxs-lookup"><span data-stu-id="bf326-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="bf326-133">Au lieu de cela, l'utilisateur est affecté au rôle ou exclu de celui-ci la prochaine fois que les règles pour l'affectation de rôle automatique sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="bf326-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  


