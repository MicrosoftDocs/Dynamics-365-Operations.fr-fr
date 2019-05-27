---
title: Réapprovisionnement immédiat
description: Cette rubrique décrit comment utiliser le réapprovisionnement immédiat pour réapprovisionner le stock lorsque une instruction d'emplacement échoue à affecter le stock.
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: ab1f06951d5daceaf002b2cc23236dd818457985
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1543305"
---
# <a name="immediate-replenishment"></a><span data-ttu-id="73235-103">Réapprovisionnement immédiat</span><span class="sxs-lookup"><span data-stu-id="73235-103">Immediate replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="73235-104">Le réapprovisionnement immédiat vous permet de réapprovisionner immédiatement le stock lorsqu'une ligne d'instruction d'emplacement échoue à affecter le stock.</span><span class="sxs-lookup"><span data-stu-id="73235-104">Immediate replenishment lets you replenish inventory immediately after a location directive line fails to allocate inventory.</span></span> <span data-ttu-id="73235-105">Le réapprovisionnement est basé sur une ligne unique dans le paramétrage de l'instruction d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="73235-105">The replenishment is based on a single line in the setup of the location directive.</span></span> <span data-ttu-id="73235-106">Si le stock n'est pas disponible dans l'unité de mesure spécifiée par cette ligne, le réapprovisionnement de cette unité de mesure se produit immédiatement.</span><span class="sxs-lookup"><span data-stu-id="73235-106">If inventory isn't on hand in the unit of measure that is specified by that line, replenishment of that unit of measure occurs immediately.</span></span>

<span data-ttu-id="73235-107">Le réapprovisionnement immédiat fournit une alternative à la méthode où la répartition du stock est basée sur plusieurs lignes de l'instruction d'emplacement, et où la demande est additionnée à la fin de la répartition et réapprovisionnée dans l'unité de mesure spécifiée par la dernière ligne de l'instruction d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="73235-107">Immediate replenishment provides an alternative to the method where the allocation of inventory is based on more lines in the location directive, and where the demand is summed at the end of the allocation and replenished in the unit of measure that is specified by the last line in the location directive.</span></span>

<span data-ttu-id="73235-108">Les avantages à utiliser le réapprovisionnement immédiat sont que le réapprovisionnement peut être limité par des unités spécifiques et la quantité peut être dirigée vers des emplacements spécifiques.</span><span class="sxs-lookup"><span data-stu-id="73235-108">The benefits of using immediate replenishment are that replenishment can be limited by specific units and the quantity can be directed to specific locations.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="73235-109">Scénario d'entreprise</span><span class="sxs-lookup"><span data-stu-id="73235-109">Business scenario</span></span>

<span data-ttu-id="73235-110">Par exemple, vous avez un entrepôt avec des secteurs de prélèvement distincts pour les unités de mesure « caisse » et « chaque ».</span><span class="sxs-lookup"><span data-stu-id="73235-110">For example, you have a warehouse that has separate picking areas for the "box" and "each" units of measure.</span></span> <span data-ttu-id="73235-111">Vous souhaitez optimiser le processus de prélèvement en prélèvement autant de caisses que possible puis en prélevant n'importe quelle quantité restante inférieure à une caisse de « chaque » zone.</span><span class="sxs-lookup"><span data-stu-id="73235-111">You want to optimize the picking process by picking as many boxes as possible and then picking any remaining quantity that is less than a box from the "each" area.</span></span>

<span data-ttu-id="73235-112">Dans ce cas, vous pouvez utiliser le réapprovisionnement immédiat.</span><span class="sxs-lookup"><span data-stu-id="73235-112">In this case, you can use immediate replenishment.</span></span> <span data-ttu-id="73235-113">Dans l'instruction d'emplacement, vous pouvez paramétrer le réapprovisionnement immédiat pour les caisses de sorte que le réapprovisionnement de la demande soit utilisé dès qu'il existe une pénurie de caisses pouvant être prélevées pour la quantité de la demande.</span><span class="sxs-lookup"><span data-stu-id="73235-113">In the location directive, you can set up immediate replenishment for boxes so that demand replenishment is used as soon as there is a shortage of boxes that can be picked for the demand quantity.</span></span> <span data-ttu-id="73235-114">Ainsi, vous optimisez le processus de prélèvement afin que le prélèvement inclue autant de caisses que possible.</span><span class="sxs-lookup"><span data-stu-id="73235-114">In this way, you optimize the picking process so that picking includes as many boxes as possible.</span></span> <span data-ttu-id="73235-115">Le réapprovisionnement immédiat génère le réapprovisionnement des caisses, et la demande ne sera pas transmise afin que les quantités soient prélevées dans « chaque » unité de mesure.</span><span class="sxs-lookup"><span data-stu-id="73235-115">Immediate replenishment will generate replenishment of the boxes, and the demand won't be passed on so that the quantities are picked in the "each" unit of measure.</span></span> <span data-ttu-id="73235-116">En d'autres termes, seules les quantités qui sont destinées être prélevées dans « chaque » unité de mesure (autrement dit, les quantités inférieures à une caisse) sont prélevées dans « chaque » zone.</span><span class="sxs-lookup"><span data-stu-id="73235-116">In other words, only the quantities that are supposed to be picked in the "each" unit of measure (that is, quantities that are less than a box) will be picked from the "each" area.</span></span> <span data-ttu-id="73235-117">Si une pénurie a lieu dans la zone « caisse », vous pouvez prélever autant de caisses que possible de la demande totale.</span><span class="sxs-lookup"><span data-stu-id="73235-117">If a shortage occurs in the "box" area, you can pick as many boxes as possible out of the total demand.</span></span> <span data-ttu-id="73235-118">Les quantités restantes seront alors prélevées dans la zone « chaque ».</span><span class="sxs-lookup"><span data-stu-id="73235-118">The remaining quantities will then be picked from the "each" area.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="73235-119">Dans ce cas</span><span class="sxs-lookup"><span data-stu-id="73235-119">Where it applies</span></span>

<span data-ttu-id="73235-120">Le réapprovisionnement immédiat est utilisé pendant une exécution de vague si l'allocation échoue pour une ligne d'instruction d'emplacement pour laquelle un modèle de réapprovisionnement est défini.</span><span class="sxs-lookup"><span data-stu-id="73235-120">Immediate replenishment is used during wave execution if allocation fails for a location directive line that a replenishment template is set for.</span></span>

## <a name="set-up-immediate-replenishment"></a><span data-ttu-id="73235-121">Paramétrer le réapprovisionnement immédiat</span><span class="sxs-lookup"><span data-stu-id="73235-121">Set up immediate replenishment</span></span>

- <span data-ttu-id="73235-122">Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Instructions d'emplacement**, puis, dans l'onglet **Lignes**, dans la liste **Modèle de réapprovisionnement immédiat**, sélectionnez un modèle de réapprovisionnement pour la demande de vague.</span><span class="sxs-lookup"><span data-stu-id="73235-122">Go to **Warehouse management** \> **Setup** \> **Location directives**, and then, on the **Lines** tab, in the **Immediate replenishment template** list, select a replenishment template for wave demand.</span></span>

<span data-ttu-id="73235-123">Le modèle de réapprovisionnement est appliqué si la ligne d'instruction d'emplacement échoue à affecter une unité de mesure dédiée.</span><span class="sxs-lookup"><span data-stu-id="73235-123">The replenishment template is applied if the location directive line fails to allocate a dedicated unit of measure.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="73235-124">Dépannage</span><span class="sxs-lookup"><span data-stu-id="73235-124">Troubleshooting</span></span>

<span data-ttu-id="73235-125">Si le réapprovisionnement immédiat est sélectionné pour une ligne d'instruction d'emplacement, mais qu'aucun travail de réapprovisionnement n'est généré lorsque vous utilisez des modèles de réapprovisionnement de demande pour cette ligne d'instruction d'emplacement, deux causes principales doivent être étudiées :</span><span class="sxs-lookup"><span data-stu-id="73235-125">If immediate replenishment is selected for a location directive line, but no replenishment work is generated when you use demand replenishment templates for that location directive line, two main causes must be investigated:</span></span>

- <span data-ttu-id="73235-126">Assurez-vous que le modèle de réapprovisionnement de demande appliqué est paramétré pour utiliser les modèles d'emplacement corrects et les modèles de travail de type **Réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="73235-126">Make sure that the demand replenishment template that is applied is set up to use the correct location templates and work templates of the **Replenishment** type.</span></span>
- <span data-ttu-id="73235-127">Assurez-vous que le stock disponible est suffisant aux emplacements où les recherches de modèle de réapprovisionnement de demande de stock disponible pour le réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="73235-127">Make sure that there is enough on-hand inventory at the locations where the demand replenishment template searches for on-hand inventory for replenishment.</span></span>
