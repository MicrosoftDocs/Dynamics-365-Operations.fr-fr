---
title: Montant arrondi pour les calculs d'amortissement
description: "Cet article présente le champ Arrondir l'amortissement qui est indiqué dans les pages de paramétrage du registre."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 7721e46a72e0f8133ed67c597a066a97ffd61669
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="round-off-amount-for-depreciation-calculations"></a><span data-ttu-id="0c677-103">Montant arrondi pour les calculs d'amortissement</span><span class="sxs-lookup"><span data-stu-id="0c677-103">Round-off amount for depreciation calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0c677-104">Cet article présente le champ Arrondir l'amortissement qui est indiqué dans les pages de paramétrage du registre.</span><span class="sxs-lookup"><span data-stu-id="0c677-104">This article discusses the Round-off depreciation field that is found on the Book setup pages.</span></span>

<span data-ttu-id="0c677-105">Les montants d'amortissement arrondis sont définis pour chaque registre.</span><span class="sxs-lookup"><span data-stu-id="0c677-105">Round-off depreciation amounts are set for each book.</span></span> <span data-ttu-id="0c677-106">Les montants d'amortissement arrondis sont utilisés dans le profil d'amortissement des immobilisations qui indique le prochain amortissement et la valeur de l'immobilisation, ainsi que dans les propositions d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="0c677-106">Round-off depreciation amounts are used in the fixed asset depreciation profile that shows the future depreciation and value of the fixed asset, and also in depreciation proposals.</span></span> <span data-ttu-id="0c677-107">Entrez le montant minimal de l'amortissement autorisé pour le registre.</span><span class="sxs-lookup"><span data-stu-id="0c677-107">Enter the lowest depreciation amount that is allowed for the book.</span></span> 

<span data-ttu-id="0c677-108">Indépendamment de l'arrondi paramétré, le montant d'amortissement de la dernière période d'amortissement n'est pas arrondi.</span><span class="sxs-lookup"><span data-stu-id="0c677-108">Regardless of the rounding that is set up, the depreciation amount in the last depreciation period isn't rounded.</span></span> <span data-ttu-id="0c677-109">À la fin de la dernière période d'amortissement, la valeur de l'immobilisation doit être nulle ou égale à la valeur de mise au rebut, si cette valeur est utilisée.</span><span class="sxs-lookup"><span data-stu-id="0c677-109">At the end of the last depreciation period, the value of the fixed asset must be 0 (zero) or the scrap value, if scrap value is used.</span></span>

### <a name="example"></a><span data-ttu-id="0c677-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="0c677-110">Example</span></span>

<span data-ttu-id="0c677-111">Un amortissement sans arrondi est calculé comme égal à 2 444,44.</span><span class="sxs-lookup"><span data-stu-id="0c677-111">Depreciation without rounding is calculated as 2,444.44.</span></span> <span data-ttu-id="0c677-112">Selon la manière dont l'arrondi est paramétré, différents montants sont suggérés, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="0c677-112">As the following table shows, the amounts that are suggested vary, depending on how rounding is set up.</span></span>

| <span data-ttu-id="0c677-113">Méthode d'arrondi</span><span class="sxs-lookup"><span data-stu-id="0c677-113">Rounding method</span></span> | <span data-ttu-id="0c677-114">Montant d'amortissement</span><span class="sxs-lookup"><span data-stu-id="0c677-114">Depreciation amount</span></span> |
|-----------------|---------------------|
| <span data-ttu-id="0c677-115">Arrondi 0,1</span><span class="sxs-lookup"><span data-stu-id="0c677-115">Rounding 0.1</span></span>    | <span data-ttu-id="0c677-116">2 444,40</span><span class="sxs-lookup"><span data-stu-id="0c677-116">2,444.40</span></span>            |
| <span data-ttu-id="0c677-117">Arrondi 1,00</span><span class="sxs-lookup"><span data-stu-id="0c677-117">Rounding 1.00</span></span>   | <span data-ttu-id="0c677-118">2 444,00</span><span class="sxs-lookup"><span data-stu-id="0c677-118">2,444.00</span></span>            |
| <span data-ttu-id="0c677-119">Arrondi 10,00</span><span class="sxs-lookup"><span data-stu-id="0c677-119">Rounding 10.00</span></span>  | <span data-ttu-id="0c677-120">2 440,00</span><span class="sxs-lookup"><span data-stu-id="0c677-120">2,440.00</span></span>            |
| <span data-ttu-id="0c677-121">Arrondi 100,00</span><span class="sxs-lookup"><span data-stu-id="0c677-121">Rounding 100.00</span></span> | <span data-ttu-id="0c677-122">2 400,00</span><span class="sxs-lookup"><span data-stu-id="0c677-122">2,400.00</span></span>            |






