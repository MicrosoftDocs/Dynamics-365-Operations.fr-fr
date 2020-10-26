---
title: Méthodologie de la convention d’amortissement semestriel
description: Cette rubrique décrit la méthode utilisée par les immobilisations pour calculer l’amortissement à l’aide de la convention semestrielle, qui calcule six mois d’amortissement au cours de la première et de la dernière année de service d’un actif.
author: moaamer
manager: Ann Beebe
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 55fb03cf08d8ec042aa8fb37fd1fb858d98279b1
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3977237"
---
# <a name="half-year-depreciation-convention-methodology"></a><span data-ttu-id="de9ef-103">Méthodologie de la convention d’amortissement semestriel</span><span class="sxs-lookup"><span data-stu-id="de9ef-103">Half-year depreciation convention methodology</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="de9ef-104">Cette rubrique décrit la méthode utilisée dans les immobilisations pour calculer l’amortissement à l’aide de la convention semestrielle.</span><span class="sxs-lookup"><span data-stu-id="de9ef-104">This topic describes the method that is used in fixed assets to calculate depreciation using the half-year convention.</span></span> <span data-ttu-id="de9ef-105">La convention semestrielle calcule six mois d’amortissement pendant la première et la dernière année de service d’un actif.</span><span class="sxs-lookup"><span data-stu-id="de9ef-105">The half-year convention calculates six months of depreciation during an asset’s first and last year of service.</span></span> <span data-ttu-id="de9ef-106">Pour plus d’informations sur les conventions d’amortissement, voir [Méthodes et conventions d’amortissement](Fixed-asset-depreciation-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="de9ef-106">For more information about depreciation conventions, see [Depreciation methods and conventions](Fixed-asset-depreciation-conventions.md).</span></span> 

<span data-ttu-id="de9ef-107">Lorsque vous utilisez la convention d’amortissement sur six mois, le système utilise l’année d’acquisition ou l’année de mise en service de l’immobilisation, puis calcule cinq années d’amortissement à partir de cette année, puis ajoute six mois.</span><span class="sxs-lookup"><span data-stu-id="de9ef-107">When you use the six-month depreciation convention, the system uses the acquisition year or the year that the asset was placed in service, then calculates five years of depreciation from that year, and then adds six months.</span></span> <span data-ttu-id="de9ef-108">Pour illustrer ce processus, considérons un actif acquis au prix de 50 000 et mis en service en avril 2020.</span><span class="sxs-lookup"><span data-stu-id="de9ef-108">To illustrate this process, consider an asset that was acquired for the price of 50,000, and placed in service in April 2020.</span></span> <span data-ttu-id="de9ef-109">Supposons également que l’actif a une durée de vie de cinq ans.</span><span class="sxs-lookup"><span data-stu-id="de9ef-109">Also assume that the asset has a five-year service life.</span></span>

<span data-ttu-id="de9ef-110">La première année de service se terminera en décembre 2020, ce qui signifie que la fin de la durée de vie de cinq ans de l’actif sera décembre 2024.</span><span class="sxs-lookup"><span data-stu-id="de9ef-110">The first year of service will conclude in December 2020, which means the end of the asset’s five-year service life will be December 2024.</span></span> <span data-ttu-id="de9ef-111">La convention d’amortissement semestrielle ajoutera six mois à la durée de vie de l’actif, ce qui signifie que sa durée de vie se terminera en juin 2025.</span><span class="sxs-lookup"><span data-stu-id="de9ef-111">The half-year depreciation convention will add six months to the asset’s life, which means its service life will end in June 2025.</span></span> 

> <span data-ttu-id="de9ef-112">Amortissement annuel 50 000/5 = 10 000 amortissement mensuel 10 000/12 = 833,33</span><span class="sxs-lookup"><span data-stu-id="de9ef-112">Yearly depreciation 50,000/5 = 10,000 monthly depreciation 10,000/12 = 833.33</span></span> <br>
> <span data-ttu-id="de9ef-113">Amortissement de la première année 10 000/2 = 5 000 et amortissement mensuel suivant 5 000/9 = 555,56</span><span class="sxs-lookup"><span data-stu-id="de9ef-113">First year depreciation 10,000/2 = 5,000  and the subsequent monthly depreciation 5,000/9 = 555.56</span></span>

   <span data-ttu-id="de9ef-114">[![Plan d’amortissement pour la convention d’amortissement semestrielle](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)</span><span class="sxs-lookup"><span data-stu-id="de9ef-114">[![Depreciation schedule for half-year depreciation convention](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)</span></span>

<span data-ttu-id="de9ef-115">Les périodes d’amortissement prolongées ajoutées par la convention semestrielle permettent une répartition plus précise de l’amortissement.</span><span class="sxs-lookup"><span data-stu-id="de9ef-115">The extended depreciation periods that are added by the half-year convention provide more accurate allocation of depreciation.</span></span> <span data-ttu-id="de9ef-116">La convention de six mois représente les dépenses d’amortissement de manière plus égale, ce qui est utile pour la présentation du compte de résultat.</span><span class="sxs-lookup"><span data-stu-id="de9ef-116">The six-month convention represents depreciation expenses more equally, which is useful for reporting on the profit and loss statement.</span></span>
