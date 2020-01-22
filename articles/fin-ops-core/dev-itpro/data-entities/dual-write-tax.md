---
title: Taxe intégrée
description: Cette rubrique décrit l'intégration des données de taxe entre Finance and Operations et Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 86e74086a5a74c7af5f2572d1a653a1658d729c0
ms.sourcegitcommit: d0322d1ed6c798301058e44dae76227a0e1f49ac
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2019
ms.locfileid: "2853857"
---
# <a name="integrated-tax"></a><span data-ttu-id="a010b-103">Taxe intégrée</span><span class="sxs-lookup"><span data-stu-id="a010b-103">Integrated tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a010b-104">Les données de paramétrage de la taxe définissent le paramétrage pour les taxes indirectes (TVA, GST, taxe) et la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="a010b-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="a010b-105">Elles décrivent la règle de calcul de taxe, le taux de taxe, la comptabilité des taxes, le règlement et d'autres concepts.</span><span class="sxs-lookup"><span data-stu-id="a010b-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="a010b-106">Modèles</span><span class="sxs-lookup"><span data-stu-id="a010b-106">Templates</span></span>

<span data-ttu-id="a010b-107">Les données de taxe comprennent un ensemble de mappages d'entités qui fonctionnent ensemble pendant l'interaction des données client, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a010b-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="a010b-108">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a010b-108">Finance and Operations</span></span>   | <span data-ttu-id="a010b-109">Autres applications Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a010b-109">Other Dynamics 365 apps</span></span>
-------------------------|---------------------------------
<span data-ttu-id="a010b-110">Codes taxe</span><span class="sxs-lookup"><span data-stu-id="a010b-110">Tax codes</span></span>                  | <span data-ttu-id="a010b-111">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="a010b-111">msdyn\_taxcodes.md</span></span>
<span data-ttu-id="a010b-112">Groupes de taxe</span><span class="sxs-lookup"><span data-stu-id="a010b-112">Tax groups</span></span>               | <span data-ttu-id="a010b-113">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="a010b-113">msdyn\_taxgroups.md</span></span>
<span data-ttu-id="a010b-114">Groupes de taxe d'article</span><span class="sxs-lookup"><span data-stu-id="a010b-114">Tax item groups</span></span>          | <span data-ttu-id="a010b-115">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="a010b-115">msdyn\_taxitemgroups.md</span></span>
<span data-ttu-id="a010b-116">Exemptions de taxe</span><span class="sxs-lookup"><span data-stu-id="a010b-116">Tax Exemptions</span></span>           | <span data-ttu-id="a010b-117">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="a010b-117">msdyn\_taxexemptcodes.md</span></span>
<span data-ttu-id="a010b-118">Administrations fiscales</span><span class="sxs-lookup"><span data-stu-id="a010b-118">Tax Authorities</span></span>          | <span data-ttu-id="a010b-119">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="a010b-119">msdyn\_taxauthorities.md</span></span>
<span data-ttu-id="a010b-120">Codes de retenue à la source</span><span class="sxs-lookup"><span data-stu-id="a010b-120">Withholding tax codes</span></span>      | <span data-ttu-id="a010b-121">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="a010b-121">msdyn\_withholdingtaxcodes.md</span></span>
<span data-ttu-id="a010b-122">Groupes de retenue à la source</span><span class="sxs-lookup"><span data-stu-id="a010b-122">Withholding tax groups</span></span>   | <span data-ttu-id="a010b-123">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="a010b-123">msdyn\_withholdingtaxgroups.md</span></span>
<span data-ttu-id="a010b-124">Groupe de compte général de taxe</span><span class="sxs-lookup"><span data-stu-id="a010b-124">Tax Ledger Account Group</span></span> | <span data-ttu-id="a010b-125">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="a010b-125">msdyn\_taxpostinggroups</span></span>  

[!include [banner](../includes/dual-write-symbols.md)]

[!include [Tax groups](dual-write/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](dual-write/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](dual-write/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](dual-write/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](dual-write/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](dual-write/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](dual-write/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]
