---
title: Relations d'objets de service
description: "Vous pouvez créer des relations d'objets de service entre un objet de service et un accord de service ou une commande de service."
author: YuyuScheller
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceObjectRelation
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
ms.openlocfilehash: 90c16653dee0614beaad8e4693c012b67a54b297
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="service-object-relations"></a><span data-ttu-id="9d7fb-103">Relations d'objets de service</span><span class="sxs-lookup"><span data-stu-id="9d7fb-103">Service object relations</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d7fb-104">Vous pouvez créer des relations d'objets de service entre un objet de service et un accord de service ou une commande de service.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-104">You can create service object relations between a service object and a service agreement or service order.</span></span> <span data-ttu-id="9d7fb-105">Lorsque vous créez une relation, vous associez l'objet de service à l'accord de service ou la commande de service.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-105">When you create a relation, you attach the service object to the service agreement or service order.</span></span>

<span data-ttu-id="9d7fb-106">Une fois la relation créée, vous pouvez associer l'objet de service à n'importe quelle ligne de l'accord de service ou de la commande de service.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-106">After the relation is created, you can attach the service object to any lines on the service agreement or service order.</span></span>

## <a name="template-boms"></a><span data-ttu-id="9d7fb-107">Nomenclatures des modèles</span><span class="sxs-lookup"><span data-stu-id="9d7fb-107">Template BOMs</span></span>

<span data-ttu-id="9d7fb-108">Vous pouvez également spécifier une nomenclature des modèles pour une relation d'objets.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-108">You can also specify a template BOM for the object relation.</span></span> <span data-ttu-id="9d7fb-109">La nomenclature des modèles est une nomenclature pour l'objet associé au service.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-109">The template BOM is a bill of materials for the object on which you perform service.</span></span> <span data-ttu-id="9d7fb-110">Si vous remplacez un composant de l'objet de service au cours d'une visite de service, vous pouvez enregistrer cette modification dans la nomenclature des services à l'aide de l'écran Objets du service.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-110">If you replace a component part of the service object during a service visit, you can register this change in the service BOM by using the Service objects form.</span></span>

## <a name="example"></a><span data-ttu-id="9d7fb-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="9d7fb-111">Example</span></span>

<span data-ttu-id="9d7fb-112">Vous créez un accord de service pour la prise en charge de deux ascenseurs sur le site d'un client.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-112">You create a service agreement for servicing two elevators at a customer site.</span></span>
<span data-ttu-id="9d7fb-113">L'accord de service est doté de l'ID d'identification SAL-001.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-113">The service agreement has the identifier ID SAL-001.</span></span>

<span data-ttu-id="9d7fb-114">Les ascenseurs sont paramétrés comme objets du service EL-S/1000 et EL-L/1000 dans l'écran .</span><span class="sxs-lookup"><span data-stu-id="9d7fb-114">The elevators are set up in the Service objects form as objects, EL-S/1000 and EL-L/1000.</span></span>

<span data-ttu-id="9d7fb-115">Vous associez les objets de service EL-S/1000 et EL-L/1000 à l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-115">You attach the service objects, EL-S/1000 and EL-L/1000, to the service agreement.</span></span>

<span data-ttu-id="9d7fb-116">Vous souhaitez enregistrer des modifications dans la nomenclature pour l'objet de service en raison du remplacement de composants de l'objet. Vous associez donc une nomenclature des services à la relation d'objets de service, comme indiqué dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-116">You want to register changes in the BOM for the service object as you replace component parts of the object, so you attach a service BOM to the service object relation, as described in the following table.</span></span>

| <span data-ttu-id="9d7fb-117">Objet de service</span><span class="sxs-lookup"><span data-stu-id="9d7fb-117">Service object</span></span> | <span data-ttu-id="9d7fb-118">Relation – Accord de service</span><span class="sxs-lookup"><span data-stu-id="9d7fb-118">Relation – Service agreement</span></span> | <span data-ttu-id="9d7fb-119">Nomenclature des services</span><span class="sxs-lookup"><span data-stu-id="9d7fb-119">Service BOM</span></span>   |
|----------------|------------------------------|---------------|
| <span data-ttu-id="9d7fb-120">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="9d7fb-120">EL-S/1000</span></span>      | <span data-ttu-id="9d7fb-121">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="9d7fb-121">ID SAL-001</span></span>                   | <span data-ttu-id="9d7fb-122">BOM-EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="9d7fb-122">BOM-EL-S/1000</span></span> |
| <span data-ttu-id="9d7fb-123">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="9d7fb-123">EL-L/1000</span></span>      | <span data-ttu-id="9d7fb-124">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="9d7fb-124">ID SAL-001</span></span>                   | <span data-ttu-id="9d7fb-125">BOM-EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="9d7fb-125">BOM-EL-L/1000</span></span> |

<span data-ttu-id="9d7fb-126">Comme l'accord inclut des relations d'objets de service, vous pouvez créer des lignes d'accord de service avec ces objets, comme indiqué dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-126">Because there are service object relations for the agreement, you can now create service agreement lines with these objects, as shown in the following table.</span></span>

| <span data-ttu-id="9d7fb-127">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="9d7fb-127">Transaction type</span></span> | <span data-ttu-id="9d7fb-128">catégorie ;</span><span class="sxs-lookup"><span data-stu-id="9d7fb-128">Category</span></span>           | <span data-ttu-id="9d7fb-129">Objet de service</span><span class="sxs-lookup"><span data-stu-id="9d7fb-129">Service object</span></span> |
|------------------|--------------------|----------------|
| <span data-ttu-id="9d7fb-130">Heure</span><span class="sxs-lookup"><span data-stu-id="9d7fb-130">Hour</span></span>             | <span data-ttu-id="9d7fb-131">Inspection</span><span class="sxs-lookup"><span data-stu-id="9d7fb-131">Inspection</span></span>         | <span data-ttu-id="9d7fb-132">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="9d7fb-132">EL-S/1000</span></span>      |
| <span data-ttu-id="9d7fb-133">Heure</span><span class="sxs-lookup"><span data-stu-id="9d7fb-133">Hour</span></span>             | <span data-ttu-id="9d7fb-134">Nettoyage du système d'engrenages</span><span class="sxs-lookup"><span data-stu-id="9d7fb-134">Gear box cleaning</span></span>  | <span data-ttu-id="9d7fb-135">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="9d7fb-135">EL-S/1000</span></span>      |
| <span data-ttu-id="9d7fb-136">Article</span><span class="sxs-lookup"><span data-stu-id="9d7fb-136">Item</span></span>             | <span data-ttu-id="9d7fb-137">Matériaux de nettoyage</span><span class="sxs-lookup"><span data-stu-id="9d7fb-137">Cleaning materials</span></span> | <span data-ttu-id="9d7fb-138">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="9d7fb-138">EL-S/1000</span></span>      |
| <span data-ttu-id="9d7fb-139">Heure</span><span class="sxs-lookup"><span data-stu-id="9d7fb-139">Hour</span></span>             | <span data-ttu-id="9d7fb-140">Inspection</span><span class="sxs-lookup"><span data-stu-id="9d7fb-140">Inspection</span></span>         | <span data-ttu-id="9d7fb-141">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="9d7fb-141">EL-L/1000</span></span>      |
| <span data-ttu-id="9d7fb-142">Heure</span><span class="sxs-lookup"><span data-stu-id="9d7fb-142">Hour</span></span>             | <span data-ttu-id="9d7fb-143">Nettoyage du système d'engrenages</span><span class="sxs-lookup"><span data-stu-id="9d7fb-143">Gearbox cleaning</span></span>   | <span data-ttu-id="9d7fb-144">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="9d7fb-144">EL-L/1000</span></span>      |
| <span data-ttu-id="9d7fb-145">Article</span><span class="sxs-lookup"><span data-stu-id="9d7fb-145">Item</span></span>             | <span data-ttu-id="9d7fb-146">Matériaux de nettoyage</span><span class="sxs-lookup"><span data-stu-id="9d7fb-146">Cleaning materials</span></span> | <span data-ttu-id="9d7fb-147">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="9d7fb-147">EL-L/1000</span></span>      |

<span data-ttu-id="9d7fb-148">Au cours d'une visite de service, vous devez remplacer le système d'engrenages de l'ascenseur EL-S/1000.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-148">On a service visit, you have to replace the gearbox for elevator EL-S/1000.</span></span> <span data-ttu-id="9d7fb-149">Pour remplacer le composant de l'objet, vous pouvez accéder au Concepteur de nomenclatures à l'aide de la relation d'objets de service paramétrée pour l'accord de service en cours.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-149">To replace a component part of the object, you can access the BOM Designer by using the service object relation that you set up for the current service agreement.</span></span>

<span data-ttu-id="9d7fb-150">Accès au Concepteur de nomenclatures à l'aide de la relation d'objets de service</span><span class="sxs-lookup"><span data-stu-id="9d7fb-150">Access the BOM Designer by using a service object relation</span></span>

1. <span data-ttu-id="9d7fb-151">Accords de service</span><span class="sxs-lookup"><span data-stu-id="9d7fb-151">Service agreements</span></span>
2. <span data-ttu-id="9d7fb-152">Double-cliquez sur un accord de service, ou cliquez sur Accord de service pour créer un accord de service.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-152">Double-click a service agreement, or click Service agreement to create a service agreement.</span></span>
3. <span data-ttu-id="9d7fb-153">Cliquez sur l'onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-153">Click the Setup tab.</span></span>
4. <span data-ttu-id="9d7fb-154">Cliquez sur Objets du service pour lier une nomenclature des modèles à l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-154">Click Service objects to attach a template BOM to the service agreement.</span></span>
5. <span data-ttu-id="9d7fb-155">Dans l'écran d'objets du service, cliquez sur Concepteur pour ouvrir l'écran Concepteur et modifier la nomenclature des modèles.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-155">In the Service objects form, click Designer to open the Designer form to modify the template BOM.</span></span>

## <a name="automatically-created-service-orders"></a><span data-ttu-id="9d7fb-156">Commandes de service créées automatiquement</span><span class="sxs-lookup"><span data-stu-id="9d7fb-156">Automatically created service orders</span></span>

<span data-ttu-id="9d7fb-157">Si vous créez automatiquement des commandes de service pour un accord de service, les relations d'objets de service dans l'accord sont également créées dans les commandes de service.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-157">If you automatically create service orders for a service agreement, the service object relations in the agreement are also created in the service orders.</span></span>


