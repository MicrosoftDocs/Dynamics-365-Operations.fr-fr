--- 
title: " Paramétrer les règles et les paramètres pour le cross-docking et le réassort magasin"
description: "Cette procédure décrit les étapes pour créer des règles de réapprovisionnement."
author: josaw1
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: f3a20b7bf476cae854c7f7c86d89d73e44b6749b
ms.contentlocale: fr-fr
ms.lasthandoff: 02/07/2018

---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a><span data-ttu-id="bd4a7-103"> Paramétrer les règles et les paramètres pour le cross-docking et le réassort magasin</span><span class="sxs-lookup"><span data-stu-id="bd4a7-103">Set up rules and parameters for cross docking and buyer's push</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="bd4a7-104">Cette procédure décrit les étapes pour créer des règles de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-104">This procedure demonstrates the steps to create Replenishment rules.</span></span> <span data-ttu-id="bd4a7-105">Les règles de réapprovisionnement permettent de contrôler la distribution des produits dans les magasins lors de l'utilisation des procédures de cross-docking et de réassort magasin.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-105">Replenishment rules can be used to control how products are distributed to stores when using Cross-docking and Buyer´s push.</span></span> <span data-ttu-id="bd4a7-106">Elles peuvent être paramétrées pour des magasins ou des groupes de magasins.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-106">Replenishment rules can be set up for stores or store groups.</span></span> <span data-ttu-id="bd4a7-107">Le poids défini pour chaque ligne d'une règle contrôle la manière dont les quantités de produits sont distribuées entre les magasins lors de l'utilisation des règles de réapprovisionnement comme méthode de distribution pour le cross-docking et le réassort magasin.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-107">The weight defined for each line in a rule will control how the quantities of products will get distributed between the stores when using Replenishment rules as the distribution method in Cross-docking or Buyer´s push.</span></span> <span data-ttu-id="bd4a7-108">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-108">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="bd4a7-109">Accédez à Règles de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-109">Go to Replenishment rules.</span></span>
2. <span data-ttu-id="bd4a7-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-110">Click New.</span></span>
3. <span data-ttu-id="bd4a7-111">Dans le champ Règle de réapprovisionnement, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-111">In the Replenishment rule field, type a value.</span></span>
4. <span data-ttu-id="bd4a7-112">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="bd4a7-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-113">Click Save.</span></span>
6. <span data-ttu-id="bd4a7-114">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-114">Click Add.</span></span>
7. <span data-ttu-id="bd4a7-115">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="bd4a7-116">Vous pouvez sélectionner Hiérarchie des réapprovisionnements ou Canal comme type.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-116">You can choose Replenishment hierarchy or Channel for the type.</span></span> <span data-ttu-id="bd4a7-117">La valeur contrôle si le nom sélectionné est une hiérarchie de canaux ou un canal spécifique.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-117">The value controls whether the selection in Name will be a hierarchy of channels or a specific channel.</span></span>  <span data-ttu-id="bd4a7-118">Pour cet exemple, utilisez l'option Hiérarchie des réapprovisionnements.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-118">For this example, leave it set as Replenishment hierarchy.</span></span>  
8. <span data-ttu-id="bd4a7-119">Dans le champ Nom, sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-119">In the Name field, select a value.</span></span>
    * <span data-ttu-id="bd4a7-120">La valeur de poids par défaut est renseignée à partir du poids défini dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-120">The default weight value is populated from the weight defined on the warehouse.</span></span>  <span data-ttu-id="bd4a7-121">Ce poids peut être utilisé pour la règle de réapprovisionnement ou vous pouvez saisir un nouveau poids dans le champ Poids.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-121">This weight can be used for the Replenishment rule or you can enter a new weight in the Weight field.</span></span>  
9. <span data-ttu-id="bd4a7-122">Dans le champ Poids, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-122">In the Weight field, enter a number.</span></span>
10. <span data-ttu-id="bd4a7-123">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-123">Click Add.</span></span>
11. <span data-ttu-id="bd4a7-124">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-124">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="bd4a7-125">Dans le champ Type, sélectionnez « Canal ».</span><span class="sxs-lookup"><span data-stu-id="bd4a7-125">In the Type field, select 'Channel'.</span></span>
13. <span data-ttu-id="bd4a7-126">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-126">In the Name field, enter or select a value.</span></span>
14. <span data-ttu-id="bd4a7-127">Dans le champ Poids, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-127">In the Weight field, enter a number.</span></span>
15. <span data-ttu-id="bd4a7-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bd4a7-128">Click Save.</span></span>


