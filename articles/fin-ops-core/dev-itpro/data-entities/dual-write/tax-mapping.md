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
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 68461f375c6d5b04f224331dc192c921cf3c4d04
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979327"
---
# <a name="integrated-tax"></a><span data-ttu-id="0f04c-103">Taxe intégrée</span><span class="sxs-lookup"><span data-stu-id="0f04c-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="0f04c-104">Les données de paramétrage de la taxe définissent le paramétrage pour les taxes indirectes (TVA, GST, taxe) et la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="0f04c-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="0f04c-105">Elles décrivent la règle de calcul de taxe, le taux de taxe, la comptabilité des taxes, le règlement et d'autres concepts.</span><span class="sxs-lookup"><span data-stu-id="0f04c-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="0f04c-106">Modèles</span><span class="sxs-lookup"><span data-stu-id="0f04c-106">Templates</span></span>

<span data-ttu-id="0f04c-107">Les données de taxe comprennent un ensemble de mappages d'entités qui fonctionnent ensemble pendant l'interaction des données client, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="0f04c-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="0f04c-108">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0f04c-108">Finance and Operations apps</span></span> | <span data-ttu-id="0f04c-109">Applications pilotées par modèle dans Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0f04c-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="0f04c-110">Description</span><span class="sxs-lookup"><span data-stu-id="0f04c-110">Description</span></span> |
-------------------------|---------------------------------|----|
<span data-ttu-id="0f04c-111">Groupe de taxe d'article</span><span class="sxs-lookup"><span data-stu-id="0f04c-111">Item sales tax group</span></span> | <span data-ttu-id="0f04c-112">msdyn_taxitemgroups</span><span class="sxs-lookup"><span data-stu-id="0f04c-112">msdyn_taxitemgroups</span></span> |
<span data-ttu-id="0f04c-113">Administrations fiscales</span><span class="sxs-lookup"><span data-stu-id="0f04c-113">Sales tax authorities</span></span> | <span data-ttu-id="0f04c-114">msdyn_taxauthorities</span><span class="sxs-lookup"><span data-stu-id="0f04c-114">msdyn_taxauthorities</span></span> |
<span data-ttu-id="0f04c-115">Entité Code d'exonération fiscale pour CDS</span><span class="sxs-lookup"><span data-stu-id="0f04c-115">Sales tax exempt code entity CDS</span></span> | <span data-ttu-id="0f04c-116">msdyn_taxexemptcodes</span><span class="sxs-lookup"><span data-stu-id="0f04c-116">msdyn_taxexemptcodes</span></span> |
<span data-ttu-id="0f04c-117">Groupes de taxe</span><span class="sxs-lookup"><span data-stu-id="0f04c-117">Sales tax groups</span></span> | <span data-ttu-id="0f04c-118">msdyn_taxgroups</span><span class="sxs-lookup"><span data-stu-id="0f04c-118">msdyn_taxgroups</span></span> |
<span data-ttu-id="0f04c-119">Groupes de validation dans la comptabilité des taxes V2</span><span class="sxs-lookup"><span data-stu-id="0f04c-119">Sales tax ledger posting groups V2</span></span> | <span data-ttu-id="0f04c-120">msdyn_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="0f04c-120">msdyn_taxpostinggroups</span></span> |
<span data-ttu-id="0f04c-121">Codes de retenue à la source</span><span class="sxs-lookup"><span data-stu-id="0f04c-121">Withholding tax codes</span></span> | <span data-ttu-id="0f04c-122">msdyn_withholdingtaxcodes</span><span class="sxs-lookup"><span data-stu-id="0f04c-122">msdyn_withholdingtaxcodes</span></span> |
<span data-ttu-id="0f04c-123">Groupes de retenue à la source</span><span class="sxs-lookup"><span data-stu-id="0f04c-123">Withholding tax groups</span></span> | <span data-ttu-id="0f04c-124">msdyn_withholdingtaxgroups</span><span class="sxs-lookup"><span data-stu-id="0f04c-124">msdyn_withholdingtaxgroups</span></span> | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

