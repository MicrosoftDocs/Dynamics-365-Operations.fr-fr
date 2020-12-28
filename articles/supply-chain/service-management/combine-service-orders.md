---
title: Combiner les commandes de service
description: Vous pouvez combiner les commandes de service.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 17fbed59b1fe7bec80f25f74451872efd61bed62
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427676"
---
# <a name="combine-service-orders"></a><span data-ttu-id="2ce78-103">Combiner les commandes de service</span><span class="sxs-lookup"><span data-stu-id="2ce78-103">Combine service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="2ce78-104">Lorsque vous créez des lignes de commande automatiquement dans l'écran **Accords de service**, vous avez le choix entre les options suivantes pour spécifier la manière selon laquelle vous souhaitez les regrouper.</span><span class="sxs-lookup"><span data-stu-id="2ce78-104">When you create service order lines automatically in the **Service agreements** form, you can choose one of the following options to specify how you want to group them:</span></span>

  - <span data-ttu-id="2ce78-105">**Par accord de service**</span><span class="sxs-lookup"><span data-stu-id="2ce78-105">**By service agreement**</span></span>

  - <span data-ttu-id="2ce78-106">**Par tâche de service**</span><span class="sxs-lookup"><span data-stu-id="2ce78-106">**By service task**</span></span>

  - <span data-ttu-id="2ce78-107">**Par employé**</span><span class="sxs-lookup"><span data-stu-id="2ce78-107">**By employee**</span></span>

  - <span data-ttu-id="2ce78-108">**Par objet de service**</span><span class="sxs-lookup"><span data-stu-id="2ce78-108">**By service object**</span></span>

## <a name="example"></a><span data-ttu-id="2ce78-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="2ce78-109">Example</span></span>

<span data-ttu-id="2ce78-110">Créez un accord de service pour lequel la date de début est le 31-03-2007.</span><span class="sxs-lookup"><span data-stu-id="2ce78-110">You create a service agreement that has a start date on 03-31-2007.</span></span> <span data-ttu-id="2ce78-111">Dans le champ **Combiner les commandes de service**, spécifiez **Par objet de service**.</span><span class="sxs-lookup"><span data-stu-id="2ce78-111">In the **Combine service orders** field, you specify **By service object**.</span></span> <span data-ttu-id="2ce78-112">Créez ensuite les lignes d'accord de service suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ce78-112">You then create the following service agreement lines:</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2ce78-113">Numéro de ligne d'accord</span><span class="sxs-lookup"><span data-stu-id="2ce78-113">Agreement line number</span></span></p></th>
<th><p><span data-ttu-id="2ce78-114">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="2ce78-114">Transaction type</span></span></p></th>
<th><p><span data-ttu-id="2ce78-115">Description</span><span class="sxs-lookup"><span data-stu-id="2ce78-115">Description</span></span></p></th>
<th><p><span data-ttu-id="2ce78-116">Intervalle</span><span class="sxs-lookup"><span data-stu-id="2ce78-116">Interval</span></span></p></th>
<th><p><span data-ttu-id="2ce78-117">Objet du service</span><span class="sxs-lookup"><span data-stu-id="2ce78-117">Service object</span></span></p></th>
<th><p><span data-ttu-id="2ce78-118">Date de début</span><span class="sxs-lookup"><span data-stu-id="2ce78-118">Start date</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ce78-119">1</span><span class="sxs-lookup"><span data-stu-id="2ce78-119">1</span></span></p></td>
<td><p><span data-ttu-id="2ce78-120"><strong>Heure</strong></span><span class="sxs-lookup"><span data-stu-id="2ce78-120"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="2ce78-121">LAS1</span><span class="sxs-lookup"><span data-stu-id="2ce78-121">SAL1</span></span></p></td>
<td><p><span data-ttu-id="2ce78-122">Hebdomadairement</span><span class="sxs-lookup"><span data-stu-id="2ce78-122">Weekly</span></span></p></td>
<td><p><span data-ttu-id="2ce78-123">X-1</span><span class="sxs-lookup"><span data-stu-id="2ce78-123">X-1</span></span></p></td>
<td><p><span data-ttu-id="2ce78-124">01-04-2007</span><span class="sxs-lookup"><span data-stu-id="2ce78-124">04-01-2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ce78-125">2</span><span class="sxs-lookup"><span data-stu-id="2ce78-125">2</span></span></p></td>
<td><p><span data-ttu-id="2ce78-126"><strong>Heure</strong></span><span class="sxs-lookup"><span data-stu-id="2ce78-126"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="2ce78-127">LAS2</span><span class="sxs-lookup"><span data-stu-id="2ce78-127">SAL2</span></span></p></td>
<td><p><span data-ttu-id="2ce78-128">Bimensuel</span><span class="sxs-lookup"><span data-stu-id="2ce78-128">Biweekly</span></span></p></td>
<td><p><span data-ttu-id="2ce78-129">X-2</span><span class="sxs-lookup"><span data-stu-id="2ce78-129">X-2</span></span></p></td>
<td><p><span data-ttu-id="2ce78-130">01-04-2007</span><span class="sxs-lookup"><span data-stu-id="2ce78-130">04-01-2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ce78-131">3</span><span class="sxs-lookup"><span data-stu-id="2ce78-131">3</span></span></p></td>
<td><p><span data-ttu-id="2ce78-132"><strong>Heure</strong></span><span class="sxs-lookup"><span data-stu-id="2ce78-132"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="2ce78-133">LAS3</span><span class="sxs-lookup"><span data-stu-id="2ce78-133">SAL3</span></span></p></td>
<td><p><span data-ttu-id="2ce78-134">Hebdomadairement</span><span class="sxs-lookup"><span data-stu-id="2ce78-134">Weekly</span></span></p></td>
<td><p><span data-ttu-id="2ce78-135">X-2</span><span class="sxs-lookup"><span data-stu-id="2ce78-135">X-2</span></span></p></td>
<td><p><span data-ttu-id="2ce78-136">01-04-2007</span><span class="sxs-lookup"><span data-stu-id="2ce78-136">04-01-2007</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2ce78-137">Vous ne devez pas spécifier de fenêtre Délai pour les lignes d'accord de service.</span><span class="sxs-lookup"><span data-stu-id="2ce78-137">You do not specify time windows for any of the service agreement lines.</span></span> <span data-ttu-id="2ce78-138">Par conséquent, les lignes de commande de service ne bougent plus à partir du jour d'échéance calculé.</span><span class="sxs-lookup"><span data-stu-id="2ce78-138">Therefore, the service order lines will not move from the calculated day on which they fall.</span></span>

<span data-ttu-id="2ce78-139">Ensuite, vous devez générer des lignes de commande de service à partir de l'écran **Créer des commandes de service** du 01-04-2007 au 30-04-2007.</span><span class="sxs-lookup"><span data-stu-id="2ce78-139">Next, you generate service order lines from the **Create service orders** form from 04-01-2007 until 04-30-2007.</span></span>

<span data-ttu-id="2ce78-140">En tout, dix commandes de service sont créées.</span><span class="sxs-lookup"><span data-stu-id="2ce78-140">In total, 10 service orders are created.</span></span> <span data-ttu-id="2ce78-141">Étant donné que le paramétrage combiné que vous avez sélectionné était **Par objet de service**, toutes les commandes de service créées ne possèdent que des lignes de commande de service avec un objet de service spécifique.</span><span class="sxs-lookup"><span data-stu-id="2ce78-141">Because the combined setting that you selected was **By service object**, all service orders that are created have only service order lines with one specific service object.</span></span> <span data-ttu-id="2ce78-142">Les lignes de commande de service générées à partir de l'accord de service et présentant la même date de service et le même objet sont combinées dans la même commande de service.</span><span class="sxs-lookup"><span data-stu-id="2ce78-142">Service order lines that are generated from the service agreement and have the same service date and object are combined on the same service order.</span></span>


> [!NOTE]
> <P><span data-ttu-id="2ce78-143">Dans cet exemple, le calendrier spécifié dans l'écran <STRONG>Paramètres de gestion des services</STRONG> ne contient pas de jours clôturés.</span><span class="sxs-lookup"><span data-stu-id="2ce78-143">In this example, the calendar that is specified in the <STRONG>Service management parameters</STRONG> form has no closed days.</span></span></P>



<span data-ttu-id="2ce78-144">Un regroupement supplémentaire de lignes de commande de service en commandes de service a lieu avec toutes les fenêtres Délai spécifiées dans les lignes de l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="2ce78-144">Additional grouping of service order lines into service orders occurs according to any time window that you specify on the service agreement lines.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ce78-145">Voir également :</span><span class="sxs-lookup"><span data-stu-id="2ce78-145">See also</span></span>

[<span data-ttu-id="2ce78-146">Création de commandes de service automatiquement</span><span class="sxs-lookup"><span data-stu-id="2ce78-146">Create service orders automatically</span></span>](create-service-orders-automatically.md)

  


