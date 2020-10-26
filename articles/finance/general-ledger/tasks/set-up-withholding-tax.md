---
title: Paramétrer la retenue à la source
description: Cette rubrique explique comment paramétrer la retenue à la source.
author: twheeloc
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bfa1b9e43a5745eb5b5c442998597319f196f23f
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976743"
---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="9ab7f-103">Paramétrer la retenue à la source</span><span class="sxs-lookup"><span data-stu-id="9ab7f-103">Set up withholding tax</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9ab7f-104">Cette rubrique explique comment paramétrer la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-104">This topic explains how to set up withholding tax.</span></span> <span data-ttu-id="9ab7f-105">La *retenue à la source* est une taxe sur les fournisseurs qui ne crée pas de transaction de taxe.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-105">*Withholding tax* is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="9ab7f-106">La retenue à la source calculée sur les paiements des fournisseurs fait partie du passif.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-106">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="9ab7f-107">Par conséquent, seuls les comptes de passif ou de bilan sont utilisés pour la validation de la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-107">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="9ab7f-108">Ce guide de tâche décrit comment paramétrer la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-108">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="9ab7f-109">Allez dans **Volet de navigation > Modules > Taxes > Taxes indirectes > Retenue à la source > Codes de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-109">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax codes**.</span></span>
2. <span data-ttu-id="9ab7f-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-110">Select **New**.</span></span>
3. <span data-ttu-id="9ab7f-111">Tapez une valeur dans le champ **Code de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-111">In the **Withholding tax code** field, type a value.</span></span>
4. <span data-ttu-id="9ab7f-112">Dans le champ **Nom de retenue à la source**, entrez le nom du code retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-112">In the **Withholding tax name** field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="9ab7f-113">Dans le champ **Compte principal**, sélectionnez le compte principal pour la validation de l'assujettissement de la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-113">In the **Main account** field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="9ab7f-114">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-114">Select **Save**.</span></span>
7. <span data-ttu-id="9ab7f-115">Sélectionnez **Valeurs** et marquez l'enregistrement souhaité dans la liste.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-115">Select **Values** and mark the desired record in the list.</span></span>
8. <span data-ttu-id="9ab7f-116">Dans le champ **Valeur**, entrez un pourcentage utilisé pour le calcul de la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-116">In the **Value** field, enter a percentage used for the calculation of the withholding tax.</span></span>
9. <span data-ttu-id="9ab7f-117">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-117">Select **Save**.</span></span>
10. <span data-ttu-id="9ab7f-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-118">Close the page.</span></span>
11. <span data-ttu-id="9ab7f-119">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-119">Select **Save**.</span></span>
12. <span data-ttu-id="9ab7f-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-120">Close the page.</span></span>
13. <span data-ttu-id="9ab7f-121">Allez dans **Volet de navigation > Modules > Taxes > Taxes indirectes > Retenue à la source > Groupes de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-121">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax groups**.</span></span>
14. <span data-ttu-id="9ab7f-122">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-122">Select **New**.</span></span>
15. <span data-ttu-id="9ab7f-123">Dans le champ **Groupe de retenue à la source**, entrez l'identificateur du groupe de retenues à la source.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-123">In the **Withholding tax group** field, enter the identifier of the withholding tax group.</span></span>
16. <span data-ttu-id="9ab7f-124">Dans le champ **Description**, entrez le nom du groupe de retenues à la source.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-124">In the **Description** field, enter the name of the withholding tax group.</span></span>
17. <span data-ttu-id="9ab7f-125">Sélectionnez le code de retenue à la source dans le champ **Code de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-125">In the **Withholding tax code** field, select the withholding tax code.</span></span>
18. <span data-ttu-id="9ab7f-126">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-126">Select **Save**.</span></span>
19. <span data-ttu-id="9ab7f-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9ab7f-127">Close the page.</span></span>

