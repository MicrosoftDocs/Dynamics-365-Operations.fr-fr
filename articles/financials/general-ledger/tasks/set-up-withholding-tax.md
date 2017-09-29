--- 
title: "Paramétrer la retenue à la source"
description: "La retenue à la source est une taxe sur les fournisseurs qui ne crée pas de transaction de taxe."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: dc4c0745235052cb4145bc7083fef1a88c8bb5c9
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="da6da-103">Paramétrer la retenue à la source</span><span class="sxs-lookup"><span data-stu-id="da6da-103">Set up withholding tax</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="da6da-104">La retenue à la source est une taxe sur les fournisseurs qui ne crée pas de transaction de taxe.</span><span class="sxs-lookup"><span data-stu-id="da6da-104">Withholding tax is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="da6da-105">La retenue à la source calculée sur les paiements des fournisseurs fait partie du passif.</span><span class="sxs-lookup"><span data-stu-id="da6da-105">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="da6da-106">Par conséquent, seuls les comptes de passif ou de bilan sont utilisés pour la validation de la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="da6da-106">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="da6da-107">Ce guide de tâche décrit comment paramétrer la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="da6da-107">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="da6da-108">Accédez à Taxe > Taxes indirectes >Retenue à la source > Codes de retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="da6da-108">Go to Tax > Indirect taxes > Withholding tax > Withholding tax codes.</span></span>
2. <span data-ttu-id="da6da-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="da6da-109">Click New.</span></span>
3. <span data-ttu-id="da6da-110">Tapez une valeur dans le champ Code de retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="da6da-110">In the Withholding tax code field, type a value.</span></span>
4. <span data-ttu-id="da6da-111">Dans le champ Nom de retenue à la source, entrez le nom du code retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="da6da-111">In the Withholding tax name field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="da6da-112">Dans le champ Compte principal, sélectionnez le compte principal pour la validation de l'assujettissement de la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="da6da-112">In the Main account field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="da6da-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="da6da-113">Click Save.</span></span>
7. <span data-ttu-id="da6da-114">Cliquez sur Valeurs.</span><span class="sxs-lookup"><span data-stu-id="da6da-114">Click Values.</span></span>
8. <span data-ttu-id="da6da-115">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="da6da-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="da6da-116">Dans le champ Valeur, entrez un pourcentage utilisé pour le calcul de la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="da6da-116">In the Value field, enter a percentage used for the calculation of the withholding tax.</span></span>
10. <span data-ttu-id="da6da-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="da6da-117">Click Save.</span></span>
11. <span data-ttu-id="da6da-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="da6da-118">Close the page.</span></span>
12. <span data-ttu-id="da6da-119">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="da6da-119">Click Save.</span></span>
13. <span data-ttu-id="da6da-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="da6da-120">Close the page.</span></span>
14. <span data-ttu-id="da6da-121">Accédez à Taxe > Taxes indirectes > Retenue à la source > Groupes de retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="da6da-121">Go to Tax > Indirect taxes > Withholding tax > Withholding tax groups.</span></span>
15. <span data-ttu-id="da6da-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="da6da-122">Click New.</span></span>
16. <span data-ttu-id="da6da-123">Dans le champ Groupe de retenue à la source, entrez l'identificateur du groupe de retenues à la source.</span><span class="sxs-lookup"><span data-stu-id="da6da-123">In the Withholding tax group field, enter the identifier of the withholding tax group.</span></span>
17. <span data-ttu-id="da6da-124">Dans le champ Description, entrez le nom du groupe de retenues à la source.</span><span class="sxs-lookup"><span data-stu-id="da6da-124">In the Description field, enter the name of the withholding tax group.</span></span>
18. <span data-ttu-id="da6da-125">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="da6da-125">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="da6da-126">Sélectionnez le code de retenue à la source dans le champ Code de retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="da6da-126">In the Withholding tax code field, select the withholding tax code.</span></span>
20. <span data-ttu-id="da6da-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="da6da-127">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="da6da-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="da6da-128">Click Save.</span></span>


