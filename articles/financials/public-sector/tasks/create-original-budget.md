--- 
title: "Créer un budget d'origine, puis contrepasser les écritures budgétaires préliminaires dans le secteur public"
description: "Lorsque vous créez une écriture budgétaire d'origine et que vous utilisez le modèle de budget et des valeurs de dimension qui contiennent des montants budgétaires préliminaires, ceux-ci peuvent être contrepassés."
author: twheeloc
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2f50cc6bf8ec533db677d290c52dbd711d7a1de8
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-an-original-budget-and-reverse-preliminary-budget-entries-in-the-public-sector"></a><span data-ttu-id="a82a7-103">Créer un budget d'origine, puis contrepasser les écritures budgétaires préliminaires dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="a82a7-103">Create an original budget and reverse preliminary budget entries in the public sector</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a82a7-104">Lorsque vous créez une écriture budgétaire d'origine et que vous utilisez le modèle de budget et des valeurs de dimension qui contiennent des montants budgétaires préliminaires, ceux-ci peuvent être contrepassés.</span><span class="sxs-lookup"><span data-stu-id="a82a7-104">When you create an original budget entry and use the budget model and dimension values that contain preliminary budget amounts, the preliminary budget amounts can be reversed.</span></span> <span data-ttu-id="a82a7-105">Cette procédure a été créée à l'aide des données de la société fictive PSUS dans la partition du secteur public.</span><span class="sxs-lookup"><span data-stu-id="a82a7-105">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="a82a7-106">Accédez à Budgétisation > Écritures de registre budgétaires.</span><span class="sxs-lookup"><span data-stu-id="a82a7-106">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="a82a7-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a82a7-107">Click New.</span></span>
3. <span data-ttu-id="a82a7-108">Dans le champ Modèle de budget, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="a82a7-108">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a82a7-109">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="a82a7-109">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="a82a7-110">Dans le champ Code budgétaire, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="a82a7-110">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="a82a7-111">Dans la liste, cliquez sur Budget d'origine.</span><span class="sxs-lookup"><span data-stu-id="a82a7-111">In the list, click Original budget.</span></span>
7. <span data-ttu-id="a82a7-112">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a82a7-112">Click Save.</span></span>
8. <span data-ttu-id="a82a7-113">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="a82a7-113">Click Add line.</span></span>
9. <span data-ttu-id="a82a7-114">Facultatif : si vous souhaitez modifier la date figurant dans l'en-tête, spécifiez une nouvelle date.</span><span class="sxs-lookup"><span data-stu-id="a82a7-114">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="a82a7-115">Cette date détermine la période fiscale dans laquelle le budget sera enregistré.</span><span class="sxs-lookup"><span data-stu-id="a82a7-115">This date determines the fiscal period that the budget will be recorded to.</span></span>
10. <span data-ttu-id="a82a7-116">Dans le champ Structure de compte, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="a82a7-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="a82a7-117">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="a82a7-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="a82a7-118">Dans le champ Valeurs de dimension, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="a82a7-118">In the Dimension values field, specify the desired values.</span></span>
13. <span data-ttu-id="a82a7-119">Dans le champ Montant, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="a82a7-119">In the Amount field, enter a number.</span></span>
14. <span data-ttu-id="a82a7-120">Dans le champ Devise, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="a82a7-120">In the Currency field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="a82a7-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a82a7-121">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="a82a7-122">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a82a7-122">Click Save.</span></span>
17. <span data-ttu-id="a82a7-123">Cliquez sur Mettre à jour les soldes budgétaires.</span><span class="sxs-lookup"><span data-stu-id="a82a7-123">Click Update budget balances.</span></span>
    * <span data-ttu-id="a82a7-124">Facultatif : vous pouvez sélectionner l'option Contrepasser le budget préliminaire.</span><span class="sxs-lookup"><span data-stu-id="a82a7-124">Optional: You can select the Reverse preliminary budget option.</span></span> <span data-ttu-id="a82a7-125">Notez que vous pouvez contrepasser toutes les écritures budgétaires préliminaires ou seulement celles qui sont dotées du code budget que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="a82a7-125">Note that you can reverse all preliminary budget entries, or only the preliminary budget entries that have the budget code that you specify.</span></span>  
    * <span data-ttu-id="a82a7-126">Pour effectuer des sélections facultatives, cliquez sur l'icône de déverrouillage en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="a82a7-126">To make optional selections, click the Unlock icon at the top of the page.</span></span>  
18. <span data-ttu-id="a82a7-127">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a82a7-127">Click Update.</span></span>


