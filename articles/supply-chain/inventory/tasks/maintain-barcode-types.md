--- 
title: "Tenir à jour les types de code-barres"
description: "Cette procédure montre comment paramétrer une nouvelle définition de code-barres pouvant être utilisée dans le cadre de l'état de la liste de prélèvements."
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: a0d7092228f078f528ec1cb9ac56d7034c44bccf
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="maintain-barcode-types"></a><span data-ttu-id="435a2-103">Tenir à jour les types de code-barres</span><span class="sxs-lookup"><span data-stu-id="435a2-103">Maintain barcode types</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="435a2-104">Cette procédure montre comment paramétrer une nouvelle définition de code-barres pouvant être utilisée dans le cadre de l'état de la liste de prélèvements.</span><span class="sxs-lookup"><span data-stu-id="435a2-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="435a2-105">Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="435a2-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="435a2-106">Si vous utilisez USMF, vous pouvez utiliser les valeurs des exemples affichées.</span><span class="sxs-lookup"><span data-stu-id="435a2-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="435a2-107">Ces tâches sont généralement effectuées par un responsable de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="435a2-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="435a2-108">Accédez à Codes-barres.</span><span class="sxs-lookup"><span data-stu-id="435a2-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="435a2-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="435a2-109">Click New.</span></span>
3. <span data-ttu-id="435a2-110">Dans le champ Paramétrage des codes-barres, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="435a2-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="435a2-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="435a2-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="435a2-112">Sélectionnez une option dans le champ Type de code-barres.</span><span class="sxs-lookup"><span data-stu-id="435a2-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="435a2-113">Si vous utilisez USMF, vous pouvez sélectionner Code 39.</span><span class="sxs-lookup"><span data-stu-id="435a2-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="435a2-114">Entrez un nombre dans le champ Taille.</span><span class="sxs-lookup"><span data-stu-id="435a2-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="435a2-115">Dans le champ Longueur maximale, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="435a2-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="435a2-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="435a2-116">Click Save.</span></span>
9. <span data-ttu-id="435a2-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="435a2-117">Close the page.</span></span>
10. <span data-ttu-id="435a2-118">Accédez à Paramètres de gestion des stocks et des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="435a2-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="435a2-119">Dans le champ Paramétrage des codes-barres, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="435a2-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="435a2-120">Sélectionnez le paramétrage de code-barres que vous avez créé précédemment, mais gardez à l'esprit que le format de code-barres doit correspondre au format de l'identificateur unique du type d'enregistrement utilisé dans le processus.</span><span class="sxs-lookup"><span data-stu-id="435a2-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="435a2-121">Par exemple, pour les parcours de prélèvement, le format de code-barres doit correspondre au format de la référence du parcours de prélèvement, qui est généralement une souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="435a2-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="435a2-122">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="435a2-122">Click Save.</span></span>
13. <span data-ttu-id="435a2-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="435a2-123">Close the page.</span></span>


