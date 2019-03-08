---
title: " Paramétrer les règles et les paramètres pour le cross-docking et le réassort magasin"
description: Cette procédure décrit les étapes pour créer des règles de réapprovisionnement.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailReplenishmentRuleTable, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a22756279ba316a7efd4d09c48c55e8cc98ba29d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "366326"
---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a><span data-ttu-id="d02e6-103"> Paramétrer les règles et les paramètres pour le cross-docking et le réassort magasin</span><span class="sxs-lookup"><span data-stu-id="d02e6-103">Set up rules and parameters for cross docking and buyer's push</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="d02e6-104">Cette procédure décrit les étapes pour créer des règles de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="d02e6-104">This procedure demonstrates the steps to create Replenishment rules.</span></span> <span data-ttu-id="d02e6-105">Les règles de réapprovisionnement permettent de contrôler la distribution des produits dans les magasins lors de l'utilisation des procédures de cross-docking et de réassort magasin.</span><span class="sxs-lookup"><span data-stu-id="d02e6-105">Replenishment rules can be used to control how products are distributed to stores when using Cross-docking and Buyer´s push.</span></span> <span data-ttu-id="d02e6-106">Elles peuvent être paramétrées pour des magasins ou des groupes de magasins.</span><span class="sxs-lookup"><span data-stu-id="d02e6-106">Replenishment rules can be set up for stores or store groups.</span></span> <span data-ttu-id="d02e6-107">Le poids défini pour chaque ligne d'une règle contrôle la manière dont les quantités de produits sont distribuées entre les magasins lors de l'utilisation des règles de réapprovisionnement comme méthode de distribution pour le cross-docking et le réassort magasin.</span><span class="sxs-lookup"><span data-stu-id="d02e6-107">The weight defined for each line in a rule will control how the quantities of products will get distributed between the stores when using Replenishment rules as the distribution method in Cross-docking or Buyer´s push.</span></span> <span data-ttu-id="d02e6-108">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="d02e6-108">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="d02e6-109">Accédez à Règles de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="d02e6-109">Go to Replenishment rules.</span></span>
2. <span data-ttu-id="d02e6-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="d02e6-110">Click New.</span></span>
3. <span data-ttu-id="d02e6-111">Dans le champ Règle de réapprovisionnement, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d02e6-111">In the Replenishment rule field, type a value.</span></span>
4. <span data-ttu-id="d02e6-112">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d02e6-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d02e6-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d02e6-113">Click Save.</span></span>
6. <span data-ttu-id="d02e6-114">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d02e6-114">Click Add.</span></span>
7. <span data-ttu-id="d02e6-115">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d02e6-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d02e6-116">Vous pouvez sélectionner Hiérarchie des réapprovisionnements ou Canal comme type.</span><span class="sxs-lookup"><span data-stu-id="d02e6-116">You can choose Replenishment hierarchy or Channel for the type.</span></span> <span data-ttu-id="d02e6-117">La valeur contrôle si le nom sélectionné est une hiérarchie de canaux ou un canal spécifique.</span><span class="sxs-lookup"><span data-stu-id="d02e6-117">The value controls whether the selection in Name will be a hierarchy of channels or a specific channel.</span></span>  <span data-ttu-id="d02e6-118">Pour cet exemple, utilisez l'option Hiérarchie des réapprovisionnements.</span><span class="sxs-lookup"><span data-stu-id="d02e6-118">For this example, leave it set as Replenishment hierarchy.</span></span>  
8. <span data-ttu-id="d02e6-119">Dans le champ Nom, sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d02e6-119">In the Name field, select a value.</span></span>
    * <span data-ttu-id="d02e6-120">La valeur de poids par défaut est renseignée à partir du poids défini dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d02e6-120">The default weight value is populated from the weight defined on the warehouse.</span></span>  <span data-ttu-id="d02e6-121">Ce poids peut être utilisé pour la règle de réapprovisionnement ou vous pouvez saisir un nouveau poids dans le champ Poids.</span><span class="sxs-lookup"><span data-stu-id="d02e6-121">This weight can be used for the Replenishment rule or you can enter a new weight in the Weight field.</span></span>  
9. <span data-ttu-id="d02e6-122">Dans le champ Poids, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="d02e6-122">In the Weight field, enter a number.</span></span>
10. <span data-ttu-id="d02e6-123">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d02e6-123">Click Add.</span></span>
11. <span data-ttu-id="d02e6-124">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d02e6-124">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="d02e6-125">Dans le champ Type, sélectionnez « Canal ».</span><span class="sxs-lookup"><span data-stu-id="d02e6-125">In the Type field, select 'Channel'.</span></span>
13. <span data-ttu-id="d02e6-126">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d02e6-126">In the Name field, enter or select a value.</span></span>
14. <span data-ttu-id="d02e6-127">Dans le champ Poids, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="d02e6-127">In the Weight field, enter a number.</span></span>
15. <span data-ttu-id="d02e6-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d02e6-128">Click Save.</span></span>

