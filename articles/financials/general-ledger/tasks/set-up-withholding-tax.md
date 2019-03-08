---
title: Paramétrer la retenue à la source
description: La retenue à la source est une taxe sur les fournisseurs qui ne crée pas de transaction de taxe.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 382b6332665af2491563960a75d498a4f007aba8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "337231"
---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="89b0b-103">Paramétrer la retenue à la source</span><span class="sxs-lookup"><span data-stu-id="89b0b-103">Set up withholding tax</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="89b0b-104">La retenue à la source est une taxe sur les fournisseurs qui ne crée pas de transaction de taxe.</span><span class="sxs-lookup"><span data-stu-id="89b0b-104">Withholding tax is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="89b0b-105">La retenue à la source calculée sur les paiements des fournisseurs fait partie du passif.</span><span class="sxs-lookup"><span data-stu-id="89b0b-105">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="89b0b-106">Par conséquent, seuls les comptes de passif ou de bilan sont utilisés pour la validation de la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="89b0b-106">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="89b0b-107">Ce guide de tâche décrit comment paramétrer la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="89b0b-107">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="89b0b-108">Accédez à Taxe > Taxes indirectes >Retenue à la source > Codes de retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="89b0b-108">Go to Tax > Indirect taxes > Withholding tax > Withholding tax codes.</span></span>
2. <span data-ttu-id="89b0b-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="89b0b-109">Click New.</span></span>
3. <span data-ttu-id="89b0b-110">Tapez une valeur dans le champ Code de retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="89b0b-110">In the Withholding tax code field, type a value.</span></span>
4. <span data-ttu-id="89b0b-111">Dans le champ Nom de retenue à la source, entrez le nom du code retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="89b0b-111">In the Withholding tax name field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="89b0b-112">Dans le champ Compte principal, sélectionnez le compte principal pour la validation de l'assujettissement de la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="89b0b-112">In the Main account field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="89b0b-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="89b0b-113">Click Save.</span></span>
7. <span data-ttu-id="89b0b-114">Cliquez sur Valeurs.</span><span class="sxs-lookup"><span data-stu-id="89b0b-114">Click Values.</span></span>
8. <span data-ttu-id="89b0b-115">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89b0b-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="89b0b-116">Dans le champ Valeur, entrez un pourcentage utilisé pour le calcul de la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="89b0b-116">In the Value field, enter a percentage used for the calculation of the withholding tax.</span></span>
10. <span data-ttu-id="89b0b-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="89b0b-117">Click Save.</span></span>
11. <span data-ttu-id="89b0b-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="89b0b-118">Close the page.</span></span>
12. <span data-ttu-id="89b0b-119">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="89b0b-119">Click Save.</span></span>
13. <span data-ttu-id="89b0b-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="89b0b-120">Close the page.</span></span>
14. <span data-ttu-id="89b0b-121">Accédez à Taxe > Taxes indirectes > Retenue à la source > Groupes de retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="89b0b-121">Go to Tax > Indirect taxes > Withholding tax > Withholding tax groups.</span></span>
15. <span data-ttu-id="89b0b-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="89b0b-122">Click New.</span></span>
16. <span data-ttu-id="89b0b-123">Dans le champ Groupe de retenue à la source, entrez l'identificateur du groupe de retenues à la source.</span><span class="sxs-lookup"><span data-stu-id="89b0b-123">In the Withholding tax group field, enter the identifier of the withholding tax group.</span></span>
17. <span data-ttu-id="89b0b-124">Dans le champ Description, entrez le nom du groupe de retenues à la source.</span><span class="sxs-lookup"><span data-stu-id="89b0b-124">In the Description field, enter the name of the withholding tax group.</span></span>
18. <span data-ttu-id="89b0b-125">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89b0b-125">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="89b0b-126">Sélectionnez le code de retenue à la source dans le champ Code de retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="89b0b-126">In the Withholding tax code field, select the withholding tax code.</span></span>
20. <span data-ttu-id="89b0b-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89b0b-127">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="89b0b-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="89b0b-128">Click Save.</span></span>

