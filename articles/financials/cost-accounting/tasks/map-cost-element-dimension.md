--- 
title: "Mapper une dimension d'élément de coût"
description: "Un contrôleur de coûts peut utiliser cette procédure pour mettre en correspondance une dimension d'élément de coût avec une dimension d'élément de coût de l'entité juridique MXMF."
author: YuyuScheller
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 3ff31db3dbb6da9570bb85bbcaa3b444852d91d7
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="map-a-cost-element-dimension"></a><span data-ttu-id="778d7-103">Mapper une dimension d'élément de coût</span><span class="sxs-lookup"><span data-stu-id="778d7-103">Map a cost element dimension</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="778d7-104">Un contrôleur de coûts peut utiliser cette procédure pour mettre en correspondance une dimension d'élément de coût avec une dimension d'élément de coût de l'entité juridique MXMF.</span><span class="sxs-lookup"><span data-stu-id="778d7-104">A cost controller can use this procedure to map a cost element dimension to a cost element dimension in the MXMF legal entity.</span></span> <span data-ttu-id="778d7-105">Cet enregistrement utilise la société fictive USP2.</span><span class="sxs-lookup"><span data-stu-id="778d7-105">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="778d7-106">Accédez à Contrôle de gestion > Dimensions > Dimensions d'éléments de coût.</span><span class="sxs-lookup"><span data-stu-id="778d7-106">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="778d7-107">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="778d7-107">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="778d7-108">Pour cet exemple, sélectionnez Éléments de coût.</span><span class="sxs-lookup"><span data-stu-id="778d7-108">For this example, select Cost elements.</span></span>  
3. <span data-ttu-id="778d7-109">Cliquez sur Mises en correspondance de dimensions.</span><span class="sxs-lookup"><span data-stu-id="778d7-109">Click Dimension mappings.</span></span>
4. <span data-ttu-id="778d7-110">Cliquez sur Configurer les mises en correspondance à partir de cette dimension.</span><span class="sxs-lookup"><span data-stu-id="778d7-110">Click Configure mappings from this dimension.</span></span>
5. <span data-ttu-id="778d7-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="778d7-111">Click New.</span></span>
6. <span data-ttu-id="778d7-112">Dans le champ Dimension cible, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="778d7-112">In the To dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="778d7-113">Pour cet exemple, sélectionnez Éléments de coût MXMF.</span><span class="sxs-lookup"><span data-stu-id="778d7-113">For this example, select MXMF Cost elements.</span></span>  
7. <span data-ttu-id="778d7-114">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="778d7-114">Click New.</span></span>
8. <span data-ttu-id="778d7-115">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="778d7-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="778d7-116">Dans le champ Membre de la dimension de départ, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="778d7-116">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="778d7-117">Pour cet exemple, sélectionnez le membre de dimension 606400 Dépenses de téléphone et de télécopie.</span><span class="sxs-lookup"><span data-stu-id="778d7-117">For this example, select dimension member 606400 Telephone & Fax Expense.</span></span>  
10. <span data-ttu-id="778d7-118">Dans le champ Membre de la dimension de fin, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="778d7-118">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="778d7-119">Pour cet exemple, sélectionnez le membre de dimension 6001004 Telefono.</span><span class="sxs-lookup"><span data-stu-id="778d7-119">For this example, select dimension member 6001004 Telefono.</span></span>  
11. <span data-ttu-id="778d7-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="778d7-120">Click Save.</span></span>


