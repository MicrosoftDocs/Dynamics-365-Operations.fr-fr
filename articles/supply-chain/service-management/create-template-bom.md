---
title: "Création d'une nomenclature des modèles"
description: "Vous pouvez créer une nomenclature des modèles à l'aide de différentes méthodes."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a80cf596a3e7c7f08d493a0fb7350fad62d38c3e
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="create-a-template-bom"></a><span data-ttu-id="7e7f0-103">Création d'une nomenclature des modèles</span><span class="sxs-lookup"><span data-stu-id="7e7f0-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="7e7f0-104">Vous pouvez créer une nomenclature des modèles à l'aide des méthodes suivantes.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="7e7f0-105">Pour toutes les méthodes, les champs **Date de début** et **Date de fin** sont facultatifs et à but informatif uniquement.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="7e7f0-106">Création manuelle d'une nomenclature des modèles</span><span class="sxs-lookup"><span data-stu-id="7e7f0-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="7e7f0-107">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Objets du service** \> **Nomenclatures des modèles**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-107">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="7e7f0-108">Appuyez sur Ctrl+N pour ouvrir l'écran **Créer une nomenclature des modèles**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-108">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="7e7f0-109">Sous **Copier les lignes de nomenclature de la référence**, sélectionnez l'option **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="7e7f0-110">Dans le champ **Numéro d'article**, entrez un article du type **Nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="7e7f0-111">Dans le champ **Nom**, entrez un nom pour le modèle.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="7e7f0-112">Dans les champs **Date de début** et **Date de fin**, entrez un intervalle de dates dans lequel la nomenclature des modèles est active.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="7e7f0-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-113">Click **OK**.</span></span>

<span data-ttu-id="7e7f0-114">Un nouveau modèle de nomenclature vide est créé.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="7e7f0-115">Création d'une nomenclature des modèles basée sur une autre nomenclature des modèles</span><span class="sxs-lookup"><span data-stu-id="7e7f0-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="7e7f0-116">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Objets du service** \> **Nomenclatures des modèles**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-116">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="7e7f0-117">Appuyez sur Ctrl+N pour ouvrir l'écran **Créer une nomenclature des modèles**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-117">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="7e7f0-118">Sous **Copier les lignes de nomenclature de la référence**, sélectionnez l'option **Nomenclature des modèles**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="7e7f0-119">Dans le champ **Numéro de référence**, sélectionnez une nomenclature des modèles existante à copier vers votre nouvelle nomenclature des modèles.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="7e7f0-120">Dans le champ **Nom**, entrez un nom pour le modèle.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="7e7f0-121">Dans les champs **Date de début** et **Date de fin**, entrez un intervalle de dates dans lequel la nomenclature des modèles est active.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="7e7f0-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-122">Click **OK**.</span></span>

<span data-ttu-id="7e7f0-123">Un nouveau modèle de nomenclature contenant des lignes correspondant aux lignes du modèle de nomenclature d'origine est créé.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="7e7f0-124">Création d'une nomenclature des modèles basée sur un article de nomenclature</span><span class="sxs-lookup"><span data-stu-id="7e7f0-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="7e7f0-125">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Objets du service** \> **Nomenclatures des modèles**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-125">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="7e7f0-126">Appuyez sur Ctrl+N pour ouvrir l'écran **Créer une nomenclature des modèles**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-126">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="7e7f0-127">Sous **Copier les lignes de nomenclature de la référence**, sélectionnez **Nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="7e7f0-128">Dans le champ **Numéro de référence**, sélectionnez une version de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="7e7f0-129">Un article du type Nomenclature est copié vers le **Numéro d'article**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="7e7f0-130">Dans le champ **Nom**, entrez un nom pour le modèle.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="7e7f0-131">Dans les champs **Date de début** et **Date de fin**, entrez un intervalle de dates dans lequel la nomenclature des modèles est active.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="7e7f0-132">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-132">Click **OK**.</span></span>

<span data-ttu-id="7e7f0-133">Un nouvelle nomenclature des modèles est créée à l'aide de lignes correspondant à celles de la nomenclature indiquée dans **Nomenclatures**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="7e7f0-134">Création d'une nomenclature des modèles basée sur une nomenclature de production</span><span class="sxs-lookup"><span data-stu-id="7e7f0-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="7e7f0-135">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Objets du service** \> **Nomenclatures des modèles**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-135">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="7e7f0-136">Appuyez sur Ctrl+N pour ouvrir l'écran **Créer une nomenclature des modèles**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-136">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="7e7f0-137">Sous **Copier les lignes de nomenclature de la référence**, sélectionnez **Production**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="7e7f0-138">Dans le champ **Numéro de référence**, sélectionnez une nomenclature de production.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="7e7f0-139">Dans le champ **Nom**, entrez un nom pour le modèle.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="7e7f0-140">Dans les champs **Date de début** et **Date de fin**, entrez un intervalle de dates dans lequel la nomenclature des modèles est active.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="7e7f0-141">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-141">Click **OK**.</span></span>

<span data-ttu-id="7e7f0-142">Une nouvelle nomenclature des modèles est créée à l'aide de lignes correspondant à celles de la nomenclature indiquée dans **Nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="7e7f0-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e7f0-143">Voir également :</span><span class="sxs-lookup"><span data-stu-id="7e7f0-143">See also</span></span>

[<span data-ttu-id="7e7f0-144">Nomenclatures des modèles</span><span class="sxs-lookup"><span data-stu-id="7e7f0-144">Template BOMs</span></span>](template-boms.md)

  



