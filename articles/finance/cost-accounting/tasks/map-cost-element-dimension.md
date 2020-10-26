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
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f8d5356e6c7f8aff507d3fa87bb3c30cb38cf36
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3977597"
---
# <a name="map-a-cost-element-dimension"></a><span data-ttu-id="787a8-103">Mapper une dimension d'élément de coût</span><span class="sxs-lookup"><span data-stu-id="787a8-103">Map a cost element dimension</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="787a8-104">Un contrôleur de coûts peut utiliser cette procédure pour mettre en correspondance une dimension d'élément de coût avec une dimension d'élément de coût de l'entité juridique MXMF.</span><span class="sxs-lookup"><span data-stu-id="787a8-104">A cost controller can use this procedure to map a cost element dimension to a cost element dimension in the MXMF legal entity.</span></span> <span data-ttu-id="787a8-105">Cet enregistrement utilise la société fictive USP2.</span><span class="sxs-lookup"><span data-stu-id="787a8-105">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="787a8-106">Accédez à Contrôle de gestion > Dimensions > Dimensions d'éléments de coût.</span><span class="sxs-lookup"><span data-stu-id="787a8-106">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="787a8-107">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="787a8-107">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="787a8-108">Pour cet exemple, sélectionnez Éléments de coût.</span><span class="sxs-lookup"><span data-stu-id="787a8-108">For this example, select Cost elements.</span></span>  
3. <span data-ttu-id="787a8-109">Cliquez sur Mises en correspondance de dimensions.</span><span class="sxs-lookup"><span data-stu-id="787a8-109">Click Dimension mappings.</span></span>
4. <span data-ttu-id="787a8-110">Cliquez sur Configurer les mises en correspondance à partir de cette dimension.</span><span class="sxs-lookup"><span data-stu-id="787a8-110">Click Configure mappings from this dimension.</span></span>
5. <span data-ttu-id="787a8-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="787a8-111">Click New.</span></span>
6. <span data-ttu-id="787a8-112">Dans le champ Dimension cible, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="787a8-112">In the To dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="787a8-113">Pour cet exemple, sélectionnez Éléments de coût MXMF.</span><span class="sxs-lookup"><span data-stu-id="787a8-113">For this example, select MXMF Cost elements.</span></span>  
7. <span data-ttu-id="787a8-114">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="787a8-114">Click New.</span></span>
8. <span data-ttu-id="787a8-115">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="787a8-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="787a8-116">Dans le champ Membre de la dimension de départ, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="787a8-116">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="787a8-117">Pour cet exemple, sélectionnez le membre de dimension 606400 Dépenses de téléphone et de télécopie.</span><span class="sxs-lookup"><span data-stu-id="787a8-117">For this example, select dimension member 606400 Telephone & Fax Expense.</span></span>  
10. <span data-ttu-id="787a8-118">Dans le champ Membre de la dimension de fin, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="787a8-118">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="787a8-119">Pour cet exemple, sélectionnez le membre de dimension 6001004 Telefono.</span><span class="sxs-lookup"><span data-stu-id="787a8-119">For this example, select dimension member 6001004 Telefono.</span></span>  
11. <span data-ttu-id="787a8-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="787a8-120">Click Save.</span></span>

