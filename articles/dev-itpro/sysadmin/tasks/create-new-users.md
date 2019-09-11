---
title: Création de nouveaux utilisateurs
description: Les utilisateurs sont des employés internes de votre organisation, ou des clients et fournisseurs externes, qui doivent avoir accès au système pour effectuer leurs tâches.
author: maertenm
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a542ece226750330262e0c44427e5654fa4f6369
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916482"
---
# <a name="create-new-users"></a><span data-ttu-id="9564f-103">Création de nouveaux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9564f-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9564f-104">Les utilisateurs sont des employés internes de votre organisation, ou des clients et fournisseurs externes, qui doivent avoir accès au système pour effectuer leurs tâches.</span><span class="sxs-lookup"><span data-stu-id="9564f-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="9564f-105">Les administrateurs système peuvent exécuter cette procédure pour ajouter des utilisateurs au système.</span><span class="sxs-lookup"><span data-stu-id="9564f-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="9564f-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="9564f-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="9564f-107">Ajout d'un nouvel utilisateur</span><span class="sxs-lookup"><span data-stu-id="9564f-107">Add a new user</span></span>
1. <span data-ttu-id="9564f-108">Accédez à **Volet de navigation > Modules > Administration système > Utilisateurs > Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="9564f-108">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="9564f-109">Dans le **volet Actions**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9564f-109">On the **Action pane**, click **New**.</span></span>
3. <span data-ttu-id="9564f-110">Dans le champ **ID utilisateur**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9564f-110">In the **User ID** field, type a value.</span></span> <span data-ttu-id="9564f-111">Entrez un identificateur unique pour l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9564f-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="9564f-112">Un ID utilisateur est requis.</span><span class="sxs-lookup"><span data-stu-id="9564f-112">A user ID is required.</span></span>  
4. <span data-ttu-id="9564f-113">Dans le champ **Nom d'utilisateur**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9564f-113">In the **User name** field, type a value.</span></span> <span data-ttu-id="9564f-114">Entrez le nom de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9564f-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="9564f-115">Dans le champ **Domaine**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9564f-115">In the **Domain** field, type a value.</span></span> <span data-ttu-id="9564f-116">Entrez le domaine de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9564f-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="9564f-117">Dans le champ **Alias**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9564f-117">In the **Alias** field, type a value.</span></span> <span data-ttu-id="9564f-118">Entrez l'alias de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9564f-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="9564f-119">Dans le champ **Société**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9564f-119">In the **Company** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="9564f-120">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9564f-120">In the list, find and select the desired record.</span></span> 
9. <span data-ttu-id="9564f-121">Dans la section **Rôle de l'utilisateur**, cliquez sur **Affecter des rôles**.</span><span class="sxs-lookup"><span data-stu-id="9564f-121">In the **User's roles** section, click **Assign roles**.</span></span>
10. <span data-ttu-id="9564f-122">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9564f-122">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="9564f-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9564f-123">Click **OK**.</span></span>
12. <span data-ttu-id="9564f-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9564f-124">Click **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="9564f-125">Importer des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9564f-125">Import users</span></span>
1. <span data-ttu-id="9564f-126">Dans le volet  **Actions**, cliquez sur **Importer des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="9564f-126">On the **Action pane**, click **Import users**.</span></span>
2. <span data-ttu-id="9564f-127">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9564f-127">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="9564f-128">Cliquez sur **Importer des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="9564f-128">Click **Import users**.</span></span>
4. <span data-ttu-id="9564f-129">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="9564f-129">Click **Close**.</span></span>

