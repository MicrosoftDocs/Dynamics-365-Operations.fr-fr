---
title: Mapper une dimension d'élément de coût
description: Un contrôleur de coûts peut utiliser cette procédure pour mettre en correspondance une dimension d'élément de coût avec une dimension d'élément de coût de l'entité juridique MXMF.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 346c64ffb19e320d0babf886c15f1b46959b4f32
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841151"
---
# <a name="map-a-cost-element-dimension"></a><span data-ttu-id="49448-103">Mapper une dimension d'élément de coût</span><span class="sxs-lookup"><span data-stu-id="49448-103">Map a cost element dimension</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="49448-104">Un contrôleur de coûts peut utiliser cette procédure pour mettre en correspondance une dimension d'élément de coût avec une dimension d'élément de coût de l'entité juridique MXMF.</span><span class="sxs-lookup"><span data-stu-id="49448-104">A cost controller can use this procedure to map a cost element dimension to a cost element dimension in the MXMF legal entity.</span></span> <span data-ttu-id="49448-105">Cet enregistrement utilise la société fictive USP2.</span><span class="sxs-lookup"><span data-stu-id="49448-105">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="49448-106">Accédez à Contrôle de gestion > Dimensions > Dimensions d'éléments de coût.</span><span class="sxs-lookup"><span data-stu-id="49448-106">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="49448-107">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="49448-107">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="49448-108">Pour cet exemple, sélectionnez Éléments de coût.</span><span class="sxs-lookup"><span data-stu-id="49448-108">For this example, select Cost elements.</span></span>  
3. <span data-ttu-id="49448-109">Cliquez sur Mises en correspondance de dimensions.</span><span class="sxs-lookup"><span data-stu-id="49448-109">Click Dimension mappings.</span></span>
4. <span data-ttu-id="49448-110">Cliquez sur Configurer les mises en correspondance à partir de cette dimension.</span><span class="sxs-lookup"><span data-stu-id="49448-110">Click Configure mappings from this dimension.</span></span>
5. <span data-ttu-id="49448-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="49448-111">Click New.</span></span>
6. <span data-ttu-id="49448-112">Dans le champ Dimension cible, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="49448-112">In the To dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="49448-113">Pour cet exemple, sélectionnez Éléments de coût MXMF.</span><span class="sxs-lookup"><span data-stu-id="49448-113">For this example, select MXMF Cost elements.</span></span>  
7. <span data-ttu-id="49448-114">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="49448-114">Click New.</span></span>
8. <span data-ttu-id="49448-115">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="49448-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="49448-116">Dans le champ Membre de la dimension de départ, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="49448-116">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="49448-117">Pour cet exemple, sélectionnez le membre de dimension 606400 Dépenses de téléphone et de télécopie.</span><span class="sxs-lookup"><span data-stu-id="49448-117">For this example, select dimension member 606400 Telephone & Fax Expense.</span></span>  
10. <span data-ttu-id="49448-118">Dans le champ Membre de la dimension de fin, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="49448-118">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="49448-119">Pour cet exemple, sélectionnez le membre de dimension 6001004 Telefono.</span><span class="sxs-lookup"><span data-stu-id="49448-119">For this example, select dimension member 6001004 Telefono.</span></span>  
11. <span data-ttu-id="49448-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="49448-120">Click Save.</span></span>

