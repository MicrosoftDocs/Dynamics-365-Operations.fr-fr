---
title: Relations d'objets de service
description: Vous pouvez créer des relations d'objets de service entre un objet de service et un accord de service ou une commande de service.
author: ShylaThompson
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 03047b3eccf3c90d4cf7426ddaec83f10dbea1b0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "314369"
---
# <a name="service-object-relations"></a><span data-ttu-id="b1477-103">Relations d'objets de service</span><span class="sxs-lookup"><span data-stu-id="b1477-103">Service object relations</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b1477-104">Vous pouvez créer des relations d'objets de service entre un objet de service et un accord de service ou une commande de service.</span><span class="sxs-lookup"><span data-stu-id="b1477-104">You can create service object relations between a service object and a service agreement or service order.</span></span> <span data-ttu-id="b1477-105">Lorsque vous créez une relation, vous associez l'objet de service à l'accord de service ou la commande de service.</span><span class="sxs-lookup"><span data-stu-id="b1477-105">When you create a relation, you attach the service object to the service agreement or service order.</span></span>

<span data-ttu-id="b1477-106">Une fois la relation créée, vous pouvez associer l'objet de service à n'importe quelle ligne de l'accord de service ou de la commande de service.</span><span class="sxs-lookup"><span data-stu-id="b1477-106">After the relation is created, you can attach the service object to any lines on the service agreement or service order.</span></span>

## <a name="template-boms"></a><span data-ttu-id="b1477-107">Nomenclatures des modèles</span><span class="sxs-lookup"><span data-stu-id="b1477-107">Template BOMs</span></span>

<span data-ttu-id="b1477-108">Vous pouvez également spécifier une nomenclature des modèles pour une relation d'objets.</span><span class="sxs-lookup"><span data-stu-id="b1477-108">You can also specify a template BOM for the object relation.</span></span> <span data-ttu-id="b1477-109">La nomenclature des modèles est une nomenclature pour l'objet associé au service.</span><span class="sxs-lookup"><span data-stu-id="b1477-109">The template BOM is a bill of materials for the object on which you perform service.</span></span> <span data-ttu-id="b1477-110">Si vous remplacez un composant de l'objet de service au cours d'une visite de service, vous pouvez enregistrer cette modification dans la nomenclature des services à l'aide de l'écran Objets du service.</span><span class="sxs-lookup"><span data-stu-id="b1477-110">If you replace a component part of the service object during a service visit, you can register this change in the service BOM by using the Service objects form.</span></span>

## <a name="example"></a><span data-ttu-id="b1477-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="b1477-111">Example</span></span>

<span data-ttu-id="b1477-112">Vous créez un accord de service pour la prise en charge de deux ascenseurs sur le site d'un client.</span><span class="sxs-lookup"><span data-stu-id="b1477-112">You create a service agreement for servicing two elevators at a customer site.</span></span>
<span data-ttu-id="b1477-113">L'accord de service est doté de l'ID d'identification SAL-001.</span><span class="sxs-lookup"><span data-stu-id="b1477-113">The service agreement has the identifier ID SAL-001.</span></span>

<span data-ttu-id="b1477-114">Les ascenseurs sont paramétrés comme objets du service EL-S/1000 et EL-L/1000 dans l'écran .</span><span class="sxs-lookup"><span data-stu-id="b1477-114">The elevators are set up in the Service objects form as objects, EL-S/1000 and EL-L/1000.</span></span>

<span data-ttu-id="b1477-115">Vous associez les objets de service EL-S/1000 et EL-L/1000 à l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="b1477-115">You attach the service objects, EL-S/1000 and EL-L/1000, to the service agreement.</span></span>

<span data-ttu-id="b1477-116">Vous souhaitez enregistrer des modifications dans la nomenclature pour l'objet de service en raison du remplacement de composants de l'objet. Vous associez donc une nomenclature des services à la relation d'objets de service, comme indiqué dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="b1477-116">You want to register changes in the BOM for the service object as you replace component parts of the object, so you attach a service BOM to the service object relation, as described in the following table.</span></span>

| <span data-ttu-id="b1477-117">Objet de service</span><span class="sxs-lookup"><span data-stu-id="b1477-117">Service object</span></span> | <span data-ttu-id="b1477-118">Relation – Accord de service</span><span class="sxs-lookup"><span data-stu-id="b1477-118">Relation – Service agreement</span></span> | <span data-ttu-id="b1477-119">Nomenclature des services</span><span class="sxs-lookup"><span data-stu-id="b1477-119">Service BOM</span></span>   |
|----------------|------------------------------|---------------|
| <span data-ttu-id="b1477-120">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="b1477-120">EL-S/1000</span></span>      | <span data-ttu-id="b1477-121">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="b1477-121">ID SAL-001</span></span>                   | <span data-ttu-id="b1477-122">BOM-EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="b1477-122">BOM-EL-S/1000</span></span> |
| <span data-ttu-id="b1477-123">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="b1477-123">EL-L/1000</span></span>      | <span data-ttu-id="b1477-124">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="b1477-124">ID SAL-001</span></span>                   | <span data-ttu-id="b1477-125">BOM-EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="b1477-125">BOM-EL-L/1000</span></span> |

<span data-ttu-id="b1477-126">Comme l'accord inclut des relations d'objets de service, vous pouvez créer des lignes d'accord de service avec ces objets, comme indiqué dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="b1477-126">Because there are service object relations for the agreement, you can now create service agreement lines with these objects, as shown in the following table.</span></span>

| <span data-ttu-id="b1477-127">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="b1477-127">Transaction type</span></span> | <span data-ttu-id="b1477-128">catégorie ;</span><span class="sxs-lookup"><span data-stu-id="b1477-128">Category</span></span>           | <span data-ttu-id="b1477-129">Objet de service</span><span class="sxs-lookup"><span data-stu-id="b1477-129">Service object</span></span> |
|------------------|--------------------|----------------|
| <span data-ttu-id="b1477-130">Heure</span><span class="sxs-lookup"><span data-stu-id="b1477-130">Hour</span></span>             | <span data-ttu-id="b1477-131">Inspection</span><span class="sxs-lookup"><span data-stu-id="b1477-131">Inspection</span></span>         | <span data-ttu-id="b1477-132">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="b1477-132">EL-S/1000</span></span>      |
| <span data-ttu-id="b1477-133">Heure</span><span class="sxs-lookup"><span data-stu-id="b1477-133">Hour</span></span>             | <span data-ttu-id="b1477-134">Nettoyage du système d'engrenages</span><span class="sxs-lookup"><span data-stu-id="b1477-134">Gear box cleaning</span></span>  | <span data-ttu-id="b1477-135">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="b1477-135">EL-S/1000</span></span>      |
| <span data-ttu-id="b1477-136">Article</span><span class="sxs-lookup"><span data-stu-id="b1477-136">Item</span></span>             | <span data-ttu-id="b1477-137">Matériaux de nettoyage</span><span class="sxs-lookup"><span data-stu-id="b1477-137">Cleaning materials</span></span> | <span data-ttu-id="b1477-138">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="b1477-138">EL-S/1000</span></span>      |
| <span data-ttu-id="b1477-139">Heure</span><span class="sxs-lookup"><span data-stu-id="b1477-139">Hour</span></span>             | <span data-ttu-id="b1477-140">Inspection</span><span class="sxs-lookup"><span data-stu-id="b1477-140">Inspection</span></span>         | <span data-ttu-id="b1477-141">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="b1477-141">EL-L/1000</span></span>      |
| <span data-ttu-id="b1477-142">Heure</span><span class="sxs-lookup"><span data-stu-id="b1477-142">Hour</span></span>             | <span data-ttu-id="b1477-143">Nettoyage du système d'engrenages</span><span class="sxs-lookup"><span data-stu-id="b1477-143">Gearbox cleaning</span></span>   | <span data-ttu-id="b1477-144">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="b1477-144">EL-L/1000</span></span>      |
| <span data-ttu-id="b1477-145">Article</span><span class="sxs-lookup"><span data-stu-id="b1477-145">Item</span></span>             | <span data-ttu-id="b1477-146">Matériaux de nettoyage</span><span class="sxs-lookup"><span data-stu-id="b1477-146">Cleaning materials</span></span> | <span data-ttu-id="b1477-147">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="b1477-147">EL-L/1000</span></span>      |

<span data-ttu-id="b1477-148">Au cours d'une visite de service, vous devez remplacer le système d'engrenages de l'ascenseur EL-S/1000.</span><span class="sxs-lookup"><span data-stu-id="b1477-148">On a service visit, you have to replace the gearbox for elevator EL-S/1000.</span></span> <span data-ttu-id="b1477-149">Pour remplacer le composant de l'objet, vous pouvez accéder au Concepteur de nomenclatures à l'aide de la relation d'objets de service paramétrée pour l'accord de service en cours.</span><span class="sxs-lookup"><span data-stu-id="b1477-149">To replace a component part of the object, you can access the BOM Designer by using the service object relation that you set up for the current service agreement.</span></span>

<span data-ttu-id="b1477-150">Accès au Concepteur de nomenclatures à l'aide de la relation d'objets de service</span><span class="sxs-lookup"><span data-stu-id="b1477-150">Access the BOM Designer by using a service object relation</span></span>

1. <span data-ttu-id="b1477-151">Accords de service</span><span class="sxs-lookup"><span data-stu-id="b1477-151">Service agreements</span></span>
2. <span data-ttu-id="b1477-152">Double-cliquez sur un accord de service, ou cliquez sur Accord de service pour créer un accord de service.</span><span class="sxs-lookup"><span data-stu-id="b1477-152">Double-click a service agreement, or click Service agreement to create a service agreement.</span></span>
3. <span data-ttu-id="b1477-153">Cliquez sur l'onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="b1477-153">Click the Setup tab.</span></span>
4. <span data-ttu-id="b1477-154">Cliquez sur Objets du service pour lier une nomenclature des modèles à l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="b1477-154">Click Service objects to attach a template BOM to the service agreement.</span></span>
5. <span data-ttu-id="b1477-155">Dans l'écran d'objets du service, cliquez sur Concepteur pour ouvrir l'écran Concepteur et modifier la nomenclature des modèles.</span><span class="sxs-lookup"><span data-stu-id="b1477-155">In the Service objects form, click Designer to open the Designer form to modify the template BOM.</span></span>

## <a name="automatically-created-service-orders"></a><span data-ttu-id="b1477-156">Commandes de service créées automatiquement</span><span class="sxs-lookup"><span data-stu-id="b1477-156">Automatically created service orders</span></span>

<span data-ttu-id="b1477-157">Si vous créez automatiquement des commandes de service pour un accord de service, les relations d'objets de service dans l'accord sont également créées dans les commandes de service.</span><span class="sxs-lookup"><span data-stu-id="b1477-157">If you automatically create service orders for a service agreement, the service object relations in the agreement are also created in the service orders.</span></span>

