---
title: Créer un code intérêt avec une plage
description: Vous pouvez paramétrer les codes intérêt de sorte à calculer différents montants d’intérêt en fonction d’une plage de valeurs.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 44b98436d6e0c40f0458dc4744b8b1d96baa8b54
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216567"
---
# <a name="create-an-interest-code-with-a-range"></a><span data-ttu-id="c4c24-103">Créer un code intérêt avec une plage</span><span class="sxs-lookup"><span data-stu-id="c4c24-103">Create an interest code with a range</span></span>

[!include [banner](../../includes/banner.md)]
<span data-ttu-id="c4c24-104">Vous pouvez paramétrer les codes intérêt de sorte à calculer différents montants d’intérêt en fonction d’une plage de valeurs.</span><span class="sxs-lookup"><span data-stu-id="c4c24-104">Interest codes can be set up to calculate different interest amounts based on a range of values.</span></span> <span data-ttu-id="c4c24-105">Cette procédure vous indique comment ajouter un code intérêt et ajouter une plage à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="c4c24-105">This procedure will show you how to add an interest code and add a range to it.</span></span>

1. <span data-ttu-id="c4c24-106">Accédez à Crédit et relances > Intérêts > Paramétrer les codes intérêt.</span><span class="sxs-lookup"><span data-stu-id="c4c24-106">Go to Credit and collections > Interest > Set up interest codes.</span></span>
2. <span data-ttu-id="c4c24-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c4c24-107">Click New.</span></span>
3. <span data-ttu-id="c4c24-108">Dans le champ Code intérêt, entrez le nom du code intérêt.</span><span class="sxs-lookup"><span data-stu-id="c4c24-108">In the Interest code field, enter the name of the interest code.</span></span>
4. <span data-ttu-id="c4c24-109">Dans le champ Description, entrez une description du code intérêt.</span><span class="sxs-lookup"><span data-stu-id="c4c24-109">In the Description field, enter a description for the interest code.</span></span>
5. <span data-ttu-id="c4c24-110">Sélectionnez un mois.</span><span class="sxs-lookup"><span data-stu-id="c4c24-110">Select Month.</span></span>
6. <span data-ttu-id="c4c24-111">Développez la section Bénéfices.</span><span class="sxs-lookup"><span data-stu-id="c4c24-111">Expand the Earnings section.</span></span>
7. <span data-ttu-id="c4c24-112">Développez la section Bénéfices par devise.</span><span class="sxs-lookup"><span data-stu-id="c4c24-112">Expand the Earnings by currency section.</span></span>
8. <span data-ttu-id="c4c24-113">Dans le champ Compte général de validation, indiquez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="c4c24-113">In the Ledger posting account field, specify the desired values.</span></span>
9. <span data-ttu-id="c4c24-114">Dans le champ Intérêts par tranche, sélectionnez « Mois ».</span><span class="sxs-lookup"><span data-stu-id="c4c24-114">In the Interest by range field, select 'Months'.</span></span>
10. <span data-ttu-id="c4c24-115">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="c4c24-115">Click Add.</span></span>
11. <span data-ttu-id="c4c24-116">Dans le champ Description, entrez une description cette devise et cette plage.</span><span class="sxs-lookup"><span data-stu-id="c4c24-116">In the Description field, enter a description for this currency and range.</span></span>
12. <span data-ttu-id="c4c24-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c4c24-117">Click Save.</span></span>
13. <span data-ttu-id="c4c24-118">Cliquez sur Plages.</span><span class="sxs-lookup"><span data-stu-id="c4c24-118">Click Ranges.</span></span>
14. <span data-ttu-id="c4c24-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c4c24-119">Click New.</span></span>
15. <span data-ttu-id="c4c24-120">Spécifiez 0 pour la valeur De, puis entrez le pourcentage d’intérêt par mois qui sera utilisé pour calculer les intérêts.</span><span class="sxs-lookup"><span data-stu-id="c4c24-120">Enter the From value as 0 and then enter the interest percent per month that will be used to calculate the interest.</span></span> <span data-ttu-id="c4c24-121">Dans notre exemple, la valeur est 1,5.</span><span class="sxs-lookup"><span data-stu-id="c4c24-121">For our example, it is 1.5.</span></span>
16. <span data-ttu-id="c4c24-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c4c24-122">Click New.</span></span>
17. <span data-ttu-id="c4c24-123">Spécifiez 4 pour la valeur suivante, ce qui correspond au premier mois où vous calculerez un nouveau montant des intérêts.</span><span class="sxs-lookup"><span data-stu-id="c4c24-123">Enter the next From value as 4, which is the first month that you will be calculating a new interest amount.</span></span>
18. <span data-ttu-id="c4c24-124">Spécifiez le pourcentage d’intérêt par mois qui sera utilisé pour calculer les intérêts à partir du mois 4.</span><span class="sxs-lookup"><span data-stu-id="c4c24-124">Enter the interest percent per month that will be used to calculate the interest starting in month 4.</span></span> <span data-ttu-id="c4c24-125">Dans notre exemple, la valeur est 2,0.</span><span class="sxs-lookup"><span data-stu-id="c4c24-125">For this example, it is 2.0.</span></span>
19. <span data-ttu-id="c4c24-126">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c4c24-126">Click New.</span></span>
20. <span data-ttu-id="c4c24-127">Spécifiez 7 pour la valeur suivante, ce qui correspond au prochain mois où vous calculerez un nouveau montant des intérêts.</span><span class="sxs-lookup"><span data-stu-id="c4c24-127">Enter the next From value as 7, which is the next month that you will be calculating a new interest amount.</span></span>
21. <span data-ttu-id="c4c24-128">Spécifiez le pourcentage d’intérêt par mois qui sera utilisé pour calculer les intérêts à partir du mois 7.</span><span class="sxs-lookup"><span data-stu-id="c4c24-128">Enter the interest percent per month that will be used to calculate the interest starting in month 7.</span></span> <span data-ttu-id="c4c24-129">Dans notre exemple, la valeur est 2,5.</span><span class="sxs-lookup"><span data-stu-id="c4c24-129">For this example, it is 2.5.</span></span>
22. <span data-ttu-id="c4c24-130">Cliquez sur Fermer pour terminer le paramétrage.</span><span class="sxs-lookup"><span data-stu-id="c4c24-130">Click Close to complete the setup.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]