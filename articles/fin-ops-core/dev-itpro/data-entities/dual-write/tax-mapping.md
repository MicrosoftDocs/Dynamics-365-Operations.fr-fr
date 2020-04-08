---
title: Taxe intégrée
description: Cette rubrique décrit l'intégration des données de taxe entre les applications Finance and Operations et Common Data Service.
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
ms.openlocfilehash: a4da37d45698290b40f6c72148f1500bef72127a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173083"
---
# <a name="integrated-tax"></a><span data-ttu-id="fa222-103">Taxe intégrée</span><span class="sxs-lookup"><span data-stu-id="fa222-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="fa222-104">Les données de paramétrage de la taxe définissent le paramétrage pour les taxes indirectes (TVA, GST, taxe) et la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="fa222-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="fa222-105">Elles décrivent la règle de calcul de taxe, le taux de taxe, la comptabilité des taxes, le règlement et d'autres concepts.</span><span class="sxs-lookup"><span data-stu-id="fa222-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="fa222-106">Modèles</span><span class="sxs-lookup"><span data-stu-id="fa222-106">Templates</span></span>

<span data-ttu-id="fa222-107">Les données de taxe comprennent un ensemble de mappages d'entités qui fonctionnent ensemble pendant l'interaction des données client, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="fa222-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="fa222-108">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fa222-108">Finance and Operations apps</span></span> | <span data-ttu-id="fa222-109">Applications pilotées par modèle dans Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="fa222-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="fa222-110">Description </span><span class="sxs-lookup"><span data-stu-id="fa222-110">Description</span></span> |
-------------------------|---------------------------------
<span data-ttu-id="fa222-111">Codes taxe</span><span class="sxs-lookup"><span data-stu-id="fa222-111">Tax codes</span></span>                   | <span data-ttu-id="fa222-112">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="fa222-112">msdyn\_taxcodes.md</span></span> | 
<span data-ttu-id="fa222-113">Groupes de taxe</span><span class="sxs-lookup"><span data-stu-id="fa222-113">Tax groups</span></span>                 | <span data-ttu-id="fa222-114">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="fa222-114">msdyn\_taxgroups.md</span></span> | 
<span data-ttu-id="fa222-115">Groupes de taxe d'article</span><span class="sxs-lookup"><span data-stu-id="fa222-115">Tax item groups</span></span>             | <span data-ttu-id="fa222-116">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="fa222-116">msdyn\_taxitemgroups.md</span></span> | 
<span data-ttu-id="fa222-117">Exemptions de taxe</span><span class="sxs-lookup"><span data-stu-id="fa222-117">Tax Exemptions</span></span>             | <span data-ttu-id="fa222-118">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="fa222-118">msdyn\_taxexemptcodes.md</span></span> | 
<span data-ttu-id="fa222-119">Administrations fiscales</span><span class="sxs-lookup"><span data-stu-id="fa222-119">Tax Authorities</span></span>             | <span data-ttu-id="fa222-120">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="fa222-120">msdyn\_taxauthorities.md</span></span> | 
<span data-ttu-id="fa222-121">Codes de retenue à la source</span><span class="sxs-lookup"><span data-stu-id="fa222-121">Withholding tax codes</span></span>       | <span data-ttu-id="fa222-122">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="fa222-122">msdyn\_withholdingtaxcodes.md</span></span> | 
<span data-ttu-id="fa222-123">Groupes de retenue à la source</span><span class="sxs-lookup"><span data-stu-id="fa222-123">Withholding tax groups</span></span>     | <span data-ttu-id="fa222-124">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="fa222-124">msdyn\_withholdingtaxgroups.md</span></span> | 
<span data-ttu-id="fa222-125">Groupe de compte général de taxe</span><span class="sxs-lookup"><span data-stu-id="fa222-125">Tax Ledger Account Group</span></span> | <span data-ttu-id="fa222-126">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="fa222-126">msdyn\_taxpostinggroups</span></span>     | 

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

