---
title: Définir un modèle de travail pour les commandes fournisseur
description: Cette procédure consiste à réaliser le paramétrage d'un modèle de travail simple à utiliser pour le rangement des articles reçus.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d737f9dfd1888602266a87853e54407618ae2781
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558317"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a><span data-ttu-id="f9470-103">Définir un modèle de travail pour les commandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="f9470-103">Set up a work template for purchase orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f9470-104">Cette procédure consiste à réaliser le paramétrage d'un modèle de travail simple à utiliser pour le rangement des articles reçus.</span><span class="sxs-lookup"><span data-stu-id="f9470-104">This procedure focuses on the set up of a simple work template to be used when putting away received items.</span></span> <span data-ttu-id="f9470-105">Les modèles de travail déterminent l'ensemble des instructions fournies à l'employé de l'entrepôt sur un appareil mobile lorsqu'il déplace des articles à partir de la zone de réception.</span><span class="sxs-lookup"><span data-stu-id="f9470-105">Work templates determine the set of instructions presented to the warehouse worker on a mobile device when moving items from the receiving area.</span></span> <span data-ttu-id="f9470-106">Vous pouvez utiliser cette procédure avec les données fournies avec la société fictive de démonstration USMF.</span><span class="sxs-lookup"><span data-stu-id="f9470-106">You can use this procedure with the data mentioned in demo data company USMF.</span></span> <span data-ttu-id="f9470-107">Avant de lancer ce guide, créez un ID de pool de travail.</span><span class="sxs-lookup"><span data-stu-id="f9470-107">Before you start this guide, create a work pool ID.</span></span> <span data-ttu-id="f9470-108">Dans cet exemple, on utilise un ID de pool de travail appelé Entrant.</span><span class="sxs-lookup"><span data-stu-id="f9470-108">In this example, a work pool ID called in Inbound is used.</span></span> <span data-ttu-id="f9470-109">Cette procédure est destinée au gestionnaire d'entrepôts.</span><span class="sxs-lookup"><span data-stu-id="f9470-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="f9470-110">Accédez à Gestion des entrepôts > Configuration > Travail > Modèles de travail.</span><span class="sxs-lookup"><span data-stu-id="f9470-110">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="f9470-111">Dans le champ Type d'ordre de travail, sélectionnez « Commandes fournisseurs ».</span><span class="sxs-lookup"><span data-stu-id="f9470-111">In the Work order type field, select 'Purchase orders'.</span></span>

## <a name="create-a-work-template-header"></a><span data-ttu-id="f9470-112">Créer un en-tête de modèle de travail</span><span class="sxs-lookup"><span data-stu-id="f9470-112">Create a work template header</span></span>
1. <span data-ttu-id="f9470-113">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f9470-113">Click New.</span></span>
2. <span data-ttu-id="f9470-114">Entrez un nombre dans le champ Numéro de souche.</span><span class="sxs-lookup"><span data-stu-id="f9470-114">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="f9470-115">Il s'agit de l'ordre dans lequel les modèles de travail sont évalués.</span><span class="sxs-lookup"><span data-stu-id="f9470-115">This is the sequence in which the work templates are evaluated.</span></span> <span data-ttu-id="f9470-116">Vous pouvez modifier la séquence, au besoin.</span><span class="sxs-lookup"><span data-stu-id="f9470-116">You can modify the sequence, if needed.</span></span>  
3. <span data-ttu-id="f9470-117">Dans le champ Modèle de travail, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f9470-117">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="f9470-118">Il s'agit de l'identificateur unique pour ce modèle.</span><span class="sxs-lookup"><span data-stu-id="f9470-118">This is the unique identifier for this template.</span></span>  
4. <span data-ttu-id="f9470-119">Dans le champ Description du modèle de travail, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f9470-119">In the Work template description field, type a value.</span></span>
    * <span data-ttu-id="f9470-120">L'option Valide ne sera pas activée tant que vous n'aurez pas renseigné toutes les informations nécessaires au modèle et n'aurez pas cliqué sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f9470-120">The Valid option will not be checked until you’ve completed all the information that's needed by the template and have then clicked Save.</span></span>  
    * <span data-ttu-id="f9470-121">Un ordre d'exécution du type Commande fournisseur ne peut pas être traité automatiquement, alors laissez l'option Traiter automatiquement sur Non.</span><span class="sxs-lookup"><span data-stu-id="f9470-121">A work order of type Purchase order cannot be automatically processed, so leave the  Automatically process option set to No.</span></span>  
5. <span data-ttu-id="f9470-122">Tapez une valeur dans le champ ID de pool de travail.</span><span class="sxs-lookup"><span data-stu-id="f9470-122">In the Work pool ID field, type a value.</span></span>
    * <span data-ttu-id="f9470-123">Les ID de pool de travail vous permettent d'organiser le travail en groupes.</span><span class="sxs-lookup"><span data-stu-id="f9470-123">Work pool IDs allow you to organize work into groups.</span></span> <span data-ttu-id="f9470-124">La valeur que vous définissez ici sera la valeur par défaut pour tout travail créé à l'aide de ce modèle.</span><span class="sxs-lookup"><span data-stu-id="f9470-124">The value that you set here will be the default value for any work that’s created using this template.</span></span>  
6. <span data-ttu-id="f9470-125">Dans le champ Priorité du travail, entrez 1.</span><span class="sxs-lookup"><span data-stu-id="f9470-125">In the Work priority field, enter '1'.</span></span>
    * <span data-ttu-id="f9470-126">Cela indique l'importance du travail, et la valeur que vous définissez ici sera la valeur par défaut pour tout travail créé à l'aide de ce modèle.</span><span class="sxs-lookup"><span data-stu-id="f9470-126">This indicates the importance of the work, and the value that you set here will be the default for any work created using this template.</span></span>  
7. <span data-ttu-id="f9470-127">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f9470-127">Click Save.</span></span>
    * <span data-ttu-id="f9470-128">Vous devez enregistrer l'en-tête du modèle de travail avant que le bouton Modifier la requête devienne disponible.</span><span class="sxs-lookup"><span data-stu-id="f9470-128">You must save the work template header before the Edit Query button becomes available.</span></span>  

## <a name="set-up-the-query-for-the-work-template"></a><span data-ttu-id="f9470-129">Définissez la requête utilisée pour le modèle de travail.</span><span class="sxs-lookup"><span data-stu-id="f9470-129">Set up the query for the work template</span></span>
1. <span data-ttu-id="f9470-130">Cliquez sur Modifier la demande.</span><span class="sxs-lookup"><span data-stu-id="f9470-130">Click Edit query.</span></span>
    * <span data-ttu-id="f9470-131">Nous définirons une limitation spécifiant que le modèle ne peut être utilisé que dans un entrepôt particulier.</span><span class="sxs-lookup"><span data-stu-id="f9470-131">We’ll set a limitation that the template can only be used within a specific warehouse.</span></span>  
2. <span data-ttu-id="f9470-132">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="f9470-132">Click Add.</span></span>
3. <span data-ttu-id="f9470-133">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f9470-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="f9470-134">Dans le champ Champ, tapez « Entrepôt ».</span><span class="sxs-lookup"><span data-stu-id="f9470-134">In the Field field, type 'warehouse'.</span></span>
5. <span data-ttu-id="f9470-135">Tapez une valeur dans le champ Critères.</span><span class="sxs-lookup"><span data-stu-id="f9470-135">In the Criteria field, type a value.</span></span>
6. <span data-ttu-id="f9470-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f9470-136">Click OK.</span></span>
7. <span data-ttu-id="f9470-137">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="f9470-137">Click Yes.</span></span>

## <a name="set-work-template-details"></a><span data-ttu-id="f9470-138">Définissez les détails du modèle de travail</span><span class="sxs-lookup"><span data-stu-id="f9470-138">Set work template details</span></span>
1. <span data-ttu-id="f9470-139">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f9470-139">Click New.</span></span>
2. <span data-ttu-id="f9470-140">Dans le champ Type de travail, sélectionnez « Prélever ».</span><span class="sxs-lookup"><span data-stu-id="f9470-140">In the Work type field, select 'Pick'.</span></span>
3. <span data-ttu-id="f9470-141">Tapez « Achat » dans le champ ID classe de travail.</span><span class="sxs-lookup"><span data-stu-id="f9470-141">In the Work class ID field, type 'purchase'.</span></span>
    * <span data-ttu-id="f9470-142">La classe de travail que vous définissez ici sera la valeur par défaut sur toutes les lignes de travail de type Prélèvement créées à l'aide de ce modèle.</span><span class="sxs-lookup"><span data-stu-id="f9470-142">The work class that you set here will be the default on all work lines of type Pick that are created using this template.</span></span> <span data-ttu-id="f9470-143">La classe de travail ne peut pas être remplacée à partir des lignes d'ordre d'exécution.</span><span class="sxs-lookup"><span data-stu-id="f9470-143">The work class cannot be overridden from the work order lines.</span></span> <span data-ttu-id="f9470-144">Les classes de travail sont utilisées pour diriger et/ou limiter le type de lignes de commande de travail qu'un employé de l'entrepôt peut traiter sur un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="f9470-144">Work classes are used to direct and/or limit the type of work order lines a warehouse worker can process on a mobile device.</span></span>  
4. <span data-ttu-id="f9470-145">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f9470-145">Click New.</span></span>
5. <span data-ttu-id="f9470-146">Dans le champ Type de travail, sélectionnez « Put ».</span><span class="sxs-lookup"><span data-stu-id="f9470-146">In the Work type field, select 'Put'.</span></span>
6. <span data-ttu-id="f9470-147">Tapez une valeur dans le champ ID classe de travail.</span><span class="sxs-lookup"><span data-stu-id="f9470-147">In the Work class ID field, type a value.</span></span>
    * <span data-ttu-id="f9470-148">Les instructions de prélèvement et de placement sont un ensemble.</span><span class="sxs-lookup"><span data-stu-id="f9470-148">The pick and put instructions are a set.</span></span> <span data-ttu-id="f9470-149">Chaque ensemble prélever/placer doit avoir la même classe de travail.</span><span class="sxs-lookup"><span data-stu-id="f9470-149">Each pick/put set must have the same work class.</span></span> <span data-ttu-id="f9470-150">Utilisez la même classe de travail que vous avez fournie pour l'instruction de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="f9470-150">Use the same work class that you provided for the pick instruction.</span></span>  
7. <span data-ttu-id="f9470-151">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f9470-151">Click Save.</span></span>
    * <span data-ttu-id="f9470-152">Notez que la case à cocher Valide est maintenant activée.</span><span class="sxs-lookup"><span data-stu-id="f9470-152">Note that the Valid checkbox is now checked.</span></span>  

