---
title: Créer un code-barres pour un produit
description: Cette procédure indique comment créer manuellement un code-barres en utilisant le numéro d'article M0001 comme exemple.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, InventItemBarcode, InventItemBarcodeLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ae2765a125045d60566267d01e380069d5d527c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568602"
---
# <a name="create-a-bar-code-for-a-product"></a><span data-ttu-id="10c34-103">Créer un code-barres pour un produit</span><span class="sxs-lookup"><span data-stu-id="10c34-103">Create a bar code for a product</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="10c34-104">Cette procédure indique comment créer manuellement un code-barres en utilisant le numéro d'article M0001 comme exemple.</span><span class="sxs-lookup"><span data-stu-id="10c34-104">This procedure shows how to manually create a bar code using the item number M0001 as an example.</span></span> <span data-ttu-id="10c34-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="10c34-105">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="10c34-106">Cliquez sur Gestion des produits lancés.</span><span class="sxs-lookup"><span data-stu-id="10c34-106">Click Released product maintenance.</span></span>
2. <span data-ttu-id="10c34-107">Cliquez sur Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="10c34-107">Click Released products.</span></span>
3. <span data-ttu-id="10c34-108">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="10c34-108">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="10c34-109">Dans le volet Actions, cliquez sur Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="10c34-109">On the Action Pane, click Manage inventory.</span></span>
5. <span data-ttu-id="10c34-110">Cliquez sur Code-barres.</span><span class="sxs-lookup"><span data-stu-id="10c34-110">Click Bar codes.</span></span>
6. <span data-ttu-id="10c34-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="10c34-111">Click New.</span></span>
7. <span data-ttu-id="10c34-112">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="10c34-112">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="10c34-113">Dans le champ Paramétrage des codes-barres, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="10c34-113">In the Barcode setup field, enter or select a value.</span></span>
9. <span data-ttu-id="10c34-114">Dans le champ Code-barres, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="10c34-114">In the Bar code field, enter or select a value.</span></span>
10. <span data-ttu-id="10c34-115">Dans le champ Code-barres, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="10c34-115">In the Bar code field, type a value.</span></span>
    * <span data-ttu-id="10c34-116">Appuyez sur la touche Tab.</span><span class="sxs-lookup"><span data-stu-id="10c34-116">Press the Tab key.</span></span>  
11. <span data-ttu-id="10c34-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="10c34-117">Close the page.</span></span>
12. <span data-ttu-id="10c34-118">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="10c34-118">In the Quantity field, enter a number.</span></span>
13. <span data-ttu-id="10c34-119">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="10c34-119">Click Save.</span></span>
    * <span data-ttu-id="10c34-120">Lorsque vous cliquez sur Enregistrer, le contrôle de code-barres est exécuté.</span><span class="sxs-lookup"><span data-stu-id="10c34-120">When you click Save, the barcode check is run, and in this case it will display an error stating that the expected check digit is 8, but that 3 was found.</span></span> <span data-ttu-id="10c34-121">Dans ce cas, il affiche une erreur indiquant que le chiffre de contrôle attendu est 8, mais le chiffre affiché est 3. Mettez à jour manuellement le numéro de code-barres afin que le chiffre 8 s'affiche à la fin.</span><span class="sxs-lookup"><span data-stu-id="10c34-121">Manually update the barcode number so that 8 is at the end.</span></span>  
14. <span data-ttu-id="10c34-122">Dans le champ Code-barres, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="10c34-122">In the Bar code field, enter or select a value.</span></span>
15. <span data-ttu-id="10c34-123">Dans le champ Code-barres, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="10c34-123">In the Bar code field, type a value.</span></span>
    * <span data-ttu-id="10c34-124">Appuyez sur la touche Tab.</span><span class="sxs-lookup"><span data-stu-id="10c34-124">Press the Tab key.</span></span>  
16. <span data-ttu-id="10c34-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="10c34-125">Close the page.</span></span>
17. <span data-ttu-id="10c34-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="10c34-126">Click Save.</span></span>
18. <span data-ttu-id="10c34-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="10c34-127">Close the page.</span></span>

