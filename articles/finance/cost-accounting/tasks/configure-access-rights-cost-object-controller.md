---
title: Configurer les droits d'accès d'un contrôleur d'objet de coût
description: Utilisez cette procédure pour configurer les droits d'accès d'un contrôleur d'objet de coût.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a931980add70ddc003d8a7c1a78f451bacbf57d4
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144494"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a><span data-ttu-id="f7908-103">Configurer les droits d'accès d'un contrôleur d'objet de coût</span><span class="sxs-lookup"><span data-stu-id="f7908-103">Configure access rights for a cost object controller</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f7908-104">Utilisez cette procédure pour configurer les droits d'accès d'un contrôleur d'objet de coût.</span><span class="sxs-lookup"><span data-stu-id="f7908-104">Use this procedure to configure access rights for a cost object controller.</span></span> <span data-ttu-id="f7908-105">Cet enregistrement utilise la société fictive USP2.</span><span class="sxs-lookup"><span data-stu-id="f7908-105">This recording uses the USP2 demo data company.</span></span>


## <a name="assign-the-cost-object-controller-role"></a><span data-ttu-id="f7908-106">Affecter le rôle Contrôleur d'objet de coût</span><span class="sxs-lookup"><span data-stu-id="f7908-106">Assign the cost object controller role</span></span>
1. <span data-ttu-id="f7908-107">Accédez à Administration système > Utilisateurs > Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f7908-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="f7908-108">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="f7908-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="f7908-109">Par exemple, filtrez le champ Nom d'utilisateur avec la valeur « alicia ».</span><span class="sxs-lookup"><span data-stu-id="f7908-109">For example, filter on the User name field with a value of 'alicia'.</span></span>
3. <span data-ttu-id="f7908-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f7908-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="f7908-111">Cliquez sur Affecter des rôles.</span><span class="sxs-lookup"><span data-stu-id="f7908-111">Click Assign roles.</span></span>
5. <span data-ttu-id="f7908-112">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="f7908-112">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="f7908-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f7908-113">Click OK.</span></span>

## <a name="enable-access-list-security"></a><span data-ttu-id="f7908-114">Activer la sécurité de la liste d'accès</span><span class="sxs-lookup"><span data-stu-id="f7908-114">Enable access list security</span></span>
1. <span data-ttu-id="f7908-115">Accédez à Contrôle de gestion > Dimensions > Hiérarchies des dimensions.</span><span class="sxs-lookup"><span data-stu-id="f7908-115">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="f7908-116">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="f7908-116">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f7908-117">Sélectionnez Organisation.</span><span class="sxs-lookup"><span data-stu-id="f7908-117">Select Organization.</span></span>  
3. <span data-ttu-id="f7908-118">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="f7908-118">Click Edit.</span></span>
4. <span data-ttu-id="f7908-119">Sélectionnez Oui dans le champ Hiérarchie de la liste d'accès.</span><span class="sxs-lookup"><span data-stu-id="f7908-119">Select Yes in the Access list hierarchy field.</span></span>
5. <span data-ttu-id="f7908-120">Cliquez sur Afficher la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="f7908-120">Click View hierarchy.</span></span>

## <a name="assign-access-rights-to-user"></a><span data-ttu-id="f7908-121">Affecter des droits d'accès à l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="f7908-121">Assign access rights to user</span></span>
1. <span data-ttu-id="f7908-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f7908-122">Click New.</span></span>
2. <span data-ttu-id="f7908-123">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f7908-123">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="f7908-124">Saisissez ou sélectionnez une valeur dans le champ ID utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f7908-124">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="f7908-125">Sélectionnez Administrateur.</span><span class="sxs-lookup"><span data-stu-id="f7908-125">Select Admin.</span></span>  
4. <span data-ttu-id="f7908-126">Dans l'arborescence, sélectionnez « Organisation\PDG\Directeur financier\FIM ».</span><span class="sxs-lookup"><span data-stu-id="f7908-126">In the tree, select 'Organization\CEO\CFO\FIM'.</span></span>
5. <span data-ttu-id="f7908-127">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f7908-127">Click New.</span></span>
6. <span data-ttu-id="f7908-128">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f7908-128">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="f7908-129">Saisissez ou sélectionnez une valeur dans le champ ID utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f7908-129">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="f7908-130">Sélectionnez Alicia.</span><span class="sxs-lookup"><span data-stu-id="f7908-130">Select Alicia.</span></span>  
8. <span data-ttu-id="f7908-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f7908-131">Click Save.</span></span>

## <a name="enable-access-rights-in-cost-accounting"></a><span data-ttu-id="f7908-132">Activer les droits d'accès dans Contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="f7908-132">Enable access rights in Cost accounting</span></span>
1. <span data-ttu-id="f7908-133">Accédez à Contrôle de gestion > Paramétrage > Paramètres.</span><span class="sxs-lookup"><span data-stu-id="f7908-133">Go to Cost accounting > Setup > Parameters.</span></span>
2. <span data-ttu-id="f7908-134">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="f7908-134">Click the General tab.</span></span>
3. <span data-ttu-id="f7908-135">Sélectionnez Oui dans le champ Activer l'affichage pour les membres de dimension d'objet de coût.</span><span class="sxs-lookup"><span data-stu-id="f7908-135">Select Yes in the Enable view access for cost object dimension members field.</span></span>
4. <span data-ttu-id="f7908-136">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f7908-136">Click Save.</span></span>
5. <span data-ttu-id="f7908-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f7908-137">Close the page.</span></span>
6. <span data-ttu-id="f7908-138">Accédez à Contrôle de gestion > Paramétrage > Configuration de l'espace de travail de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="f7908-138">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
7. <span data-ttu-id="f7908-139">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="f7908-139">Click Edit.</span></span>
8. <span data-ttu-id="f7908-140">Sélectionnez Oui dans le champ Publié.</span><span class="sxs-lookup"><span data-stu-id="f7908-140">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="f7908-141">Si vous sélectionnez Oui, un utilisateur affecté à l'un des quatre rôles suivants peut afficher les états dans l'espace de travail Contrôle des coûts : gestionnaire de contrôle de gestion, comptable, commis contrôleur de gestion et contrôleur d'objet de coût.</span><span class="sxs-lookup"><span data-stu-id="f7908-141">If you select Yes, a user who is assigned one of the following four roles can see the reports in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, and cost object controller.</span></span> <span data-ttu-id="f7908-142">Si vous sélectionnez Non, seul un utilisateur affecté à l'un des rôles suivants peut afficher les états : gestionnaire de contrôle de gestion, comptable et commis contrôleur de gestion.</span><span class="sxs-lookup"><span data-stu-id="f7908-142">If you select No, only a user who is assigned one of the following roles can see the reports: cost accounting manager, cost accountant, and cost accountant clerk.</span></span>    
9. <span data-ttu-id="f7908-143">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f7908-143">Click Save.</span></span>

