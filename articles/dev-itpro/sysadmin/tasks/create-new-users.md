---
title: Création de nouveaux utilisateurs
description: Les utilisateurs sont des employés internes de votre organisation, ou des clients et fournisseurs externes, qui doivent avoir accès au système pour effectuer leurs tâches.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 12cf223d262c4e0f2a195e95c83a00fc1a3f07e5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558709"
---
# <a name="create-new-users"></a><span data-ttu-id="94fcc-103">Création de nouveaux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="94fcc-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="94fcc-104">Les utilisateurs sont des employés internes de votre organisation, ou des clients et fournisseurs externes, qui doivent avoir accès au système pour effectuer leurs tâches.</span><span class="sxs-lookup"><span data-stu-id="94fcc-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="94fcc-105">Les administrateurs système peuvent exécuter cette procédure pour ajouter des utilisateurs au système.</span><span class="sxs-lookup"><span data-stu-id="94fcc-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="94fcc-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="94fcc-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="94fcc-107">Ajout d'un nouvel utilisateur</span><span class="sxs-lookup"><span data-stu-id="94fcc-107">Add a new user</span></span>
1. <span data-ttu-id="94fcc-108">Accédez à Administration système > Utilisateurs > Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="94fcc-108">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="94fcc-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="94fcc-109">Click New.</span></span>
3. <span data-ttu-id="94fcc-110">Dans le champ ID utilisateur, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="94fcc-110">In the User ID field, type a value.</span></span>
    * <span data-ttu-id="94fcc-111">Entrez un identificateur unique pour l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94fcc-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="94fcc-112">Un ID utilisateur est requis.</span><span class="sxs-lookup"><span data-stu-id="94fcc-112">A user ID is required.</span></span>  
4. <span data-ttu-id="94fcc-113">Dans le champ Nom de l'utilisateur, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="94fcc-113">In the User name field, type a value.</span></span>
    * <span data-ttu-id="94fcc-114">Entrez le nom de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94fcc-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="94fcc-115">Dans le champ Domaine, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="94fcc-115">In the Domain field, type a value.</span></span>
    * <span data-ttu-id="94fcc-116">Entrez le domaine de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94fcc-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="94fcc-117">Dans le champ Alias, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="94fcc-117">In the Alias field, type a value.</span></span>
    * <span data-ttu-id="94fcc-118">Entrez l'alias de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94fcc-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="94fcc-119">Dans le champ Société, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="94fcc-119">In the Company field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="94fcc-120">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="94fcc-120">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="94fcc-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="94fcc-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="94fcc-122">Sélectionnez la société de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94fcc-122">Select the user's company</span></span>  
10. <span data-ttu-id="94fcc-123">Cliquez sur Affecter des rôles.</span><span class="sxs-lookup"><span data-stu-id="94fcc-123">Click Assign roles.</span></span>
11. <span data-ttu-id="94fcc-124">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="94fcc-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="94fcc-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="94fcc-125">Click OK.</span></span>
13. <span data-ttu-id="94fcc-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="94fcc-126">Click Save.</span></span>

## <a name="import-users"></a><span data-ttu-id="94fcc-127">Importer des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="94fcc-127">Import users</span></span>
1. <span data-ttu-id="94fcc-128">Cliquez sur Importer des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="94fcc-128">Click Import users.</span></span>
2. <span data-ttu-id="94fcc-129">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="94fcc-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="94fcc-130">Cliquez sur Importer des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="94fcc-130">Click Import users.</span></span>
4. <span data-ttu-id="94fcc-131">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="94fcc-131">Click Close.</span></span>

