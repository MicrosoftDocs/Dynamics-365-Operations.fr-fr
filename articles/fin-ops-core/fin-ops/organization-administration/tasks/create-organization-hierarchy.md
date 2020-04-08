---
title: Créer une hiérarchie d'organisation
description: Procédez comme suit pour créer une hiérarchie organisationnelle.
author: sericks007
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMHierarchyManager, OMHierarchyPurposeAssociation, OMHierarchySelection, HierarchyDesigner
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dde06f758be57fb646696c861218565476abcadc
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140557"
---
# <a name="create-an-organization-hierarchy"></a><span data-ttu-id="3ec73-103">Créer une hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="3ec73-103">Create an organization hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3ec73-104">Procédez comme suit pour créer une hiérarchie organisationnelle.</span><span class="sxs-lookup"><span data-stu-id="3ec73-104">Use the following procedure to create an organizational hierarchy.</span></span> <span data-ttu-id="3ec73-105">Les hiérarchies organisationnelles vous permettent d'afficher et de créer des états relatifs à votre entreprise à partir de perspectives différentes.</span><span class="sxs-lookup"><span data-stu-id="3ec73-105">You can use organizational hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="3ec73-106">Par exemple, vous pouvez paramétrer une hiérarchie pour les déclarations légales ou fiscales.</span><span class="sxs-lookup"><span data-stu-id="3ec73-106">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="3ec73-107">Vous pouvez ensuite paramétrer une autre hiérarchie pour déclarer des informations financières qui ne sont pas requises par la loi, mais qui sont utilisées à des fins de déclaration interne.</span><span class="sxs-lookup"><span data-stu-id="3ec73-107">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span> 

<span data-ttu-id="3ec73-108">Vous devez créer une hiérarchie organisationnelle avant de créer des organisations.</span><span class="sxs-lookup"><span data-stu-id="3ec73-108">Before you create an organizational hierarchy, you must create organizations.</span></span> <span data-ttu-id="3ec73-109">Pour plus d'informations, voir les tâches « Créer une entité juridique » ou « Créer une unité opérationnelle ».</span><span class="sxs-lookup"><span data-stu-id="3ec73-109">For more information, see the "Create a legal entity" or "Create an operating unit" tasks.</span></span> <span data-ttu-id="3ec73-110">Vous pouvez également créer des départements et des équipes.</span><span class="sxs-lookup"><span data-stu-id="3ec73-110">You can also create departments and teams.</span></span> 

<span data-ttu-id="3ec73-111">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="3ec73-111">The demo data company used to create this procedure is USMF.</span></span>

## <a name="create-a-hierarchy"></a><span data-ttu-id="3ec73-112">Créer une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="3ec73-112">Create a hierarchy</span></span>
1. <span data-ttu-id="3ec73-113">Accédez au **volet de navigation > Modules > Administration d'organisation > Organisations > Hiérarchies de l'organisation**.</span><span class="sxs-lookup"><span data-stu-id="3ec73-113">Go to **Navigation pane > Modules > Organization administration > Organizations > Organization hierarchies**.</span></span>
2. <span data-ttu-id="3ec73-114">Dans le **volet Actions**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="3ec73-114">On the **Action pane**, click **New**.</span></span>
3. <span data-ttu-id="3ec73-115">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="3ec73-115">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="3ec73-116">Dans la section **Objectif**, cliquez sur **Affecter un objectif**.</span><span class="sxs-lookup"><span data-stu-id="3ec73-116">In the **Purpose** section, click **Assign purpose**.</span></span>
5. <span data-ttu-id="3ec73-117">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3ec73-117">In the list, find and select the desired record.</span></span> <span data-ttu-id="3ec73-118">Sélectionnez un objet à affecter à la hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="3ec73-118">Select a purpose to assign to your organization hierarchy.</span></span>  
6. <span data-ttu-id="3ec73-119">Dans le section **Hiérarchies affectées**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="3ec73-119">In the **Assigned hierarchies** sectiom, click **Add**.</span></span>
7. <span data-ttu-id="3ec73-120">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3ec73-120">In the list, mark the selected row.</span></span> <span data-ttu-id="3ec73-121">Recherchez la hiérarchie que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="3ec73-121">Find the hierarchy you just created.</span></span>  
8. <span data-ttu-id="3ec73-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ec73-122">Click **OK**.</span></span>

## <a name="add-organizations-to-the-hierarchy"></a><span data-ttu-id="3ec73-123">Ajout d'organisations à la hiérarchie</span><span class="sxs-lookup"><span data-stu-id="3ec73-123">Add organizations to the hierarchy</span></span>
1. <span data-ttu-id="3ec73-124">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3ec73-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="3ec73-125">Sélectionnez votre hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="3ec73-125">Select your hierarchy.</span></span>  
2. <span data-ttu-id="3ec73-126">Dans la section **Hiérarchies affectées**, cliquez sur **Afficher la hiérarchie**.</span><span class="sxs-lookup"><span data-stu-id="3ec73-126">In the **Assigned hierarchies** section, click **View hierarchy**.</span></span>
    - <span data-ttu-id="3ec73-127">Ajoutez des organisations, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="3ec73-127">Add organizations, as necessary.</span></span>  
    - <span data-ttu-id="3ec73-128">Pour ajouter une organisation, cliquez sur **Modifier**, puis **Insérer** pour ajouter l'organisation.</span><span class="sxs-lookup"><span data-stu-id="3ec73-128">To add an organization, click **Edit** and then **Insert** to add the organization.</span></span> <span data-ttu-id="3ec73-129">Lorsque vous avez apporté les modifications, vous pouvez **enregistrer** un brouillon et/ou **publier** les modifications.</span><span class="sxs-lookup"><span data-stu-id="3ec73-129">When you are done making changes you can **Save** a draft and/or **Publish** the changes.</span></span>  

