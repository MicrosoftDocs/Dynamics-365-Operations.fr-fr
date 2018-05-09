--- 
title: "Paramétrer des codes taxe"
description: "Les codes taxe sont créés pour chaque taxe indirecte ou responsabilité que l'entité juridique est obligée de calculer, de collecter et de payer à l'administration fiscale."
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 20033cef966a643b7735d488bc354136dc55d6b0
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="43b5a-103">Paramétrer des codes taxe</span><span class="sxs-lookup"><span data-stu-id="43b5a-103">Set up sales tax codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="43b5a-104">Les codes taxe sont créés pour chaque taxe indirecte ou responsabilité que l'entité juridique est obligée de calculer, de collecter et de payer à l'administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="43b5a-104">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="43b5a-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="43b5a-105">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="43b5a-106">Accédez à Taxes > Taxes indirectes > Taxe > Codes taxe.</span><span class="sxs-lookup"><span data-stu-id="43b5a-106">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="43b5a-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="43b5a-107">Click New.</span></span>
3. <span data-ttu-id="43b5a-108">Tapez une valeur dans le champ Code taxe.</span><span class="sxs-lookup"><span data-stu-id="43b5a-108">In the Sales tax code field, type a value.</span></span>
4. <span data-ttu-id="43b5a-109">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="43b5a-109">In the Name field, type a value.</span></span>
5. <span data-ttu-id="43b5a-110">Sélectionnez une période de règlement pour spécifier l'administration fiscale et les intervalles auxquels cette taxe doit être déclarée et payée.</span><span class="sxs-lookup"><span data-stu-id="43b5a-110">Select a Settlement period to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="43b5a-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="43b5a-111">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="43b5a-112">Sélectionnez un groupe de validation dans la comptabilité pour spécifier les comptes principaux pour valider la taxe dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="43b5a-112">Select a Ledger posting group to specify the main accounts to post sales tax to the general ledger.</span></span>
8. <span data-ttu-id="43b5a-113">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="43b5a-113">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="43b5a-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="43b5a-114">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="43b5a-115">Développez l'organisateur Calcul.</span><span class="sxs-lookup"><span data-stu-id="43b5a-115">Expand the Calculation FastTab.</span></span>
    * <span data-ttu-id="43b5a-116">L'organisateur Calcul a plusieurs champs qui contrôlent la manière dont les montants de taxe sont calculés.</span><span class="sxs-lookup"><span data-stu-id="43b5a-116">The Calculation FastTab has multiple fields that control how sales tax amounts will be calculated.</span></span>  
11. <span data-ttu-id="43b5a-117">Dans le volet Actions, cliquez sur le code Taxe.</span><span class="sxs-lookup"><span data-stu-id="43b5a-117">On the Action Pane, click Sales tax code.</span></span>
12. <span data-ttu-id="43b5a-118">Cliquez sur Valeurs.</span><span class="sxs-lookup"><span data-stu-id="43b5a-118">Click Values.</span></span>
13. <span data-ttu-id="43b5a-119">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="43b5a-119">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="43b5a-120">Entrez la valeur de ce code taxe.</span><span class="sxs-lookup"><span data-stu-id="43b5a-120">Enter the value for this tax code.</span></span>
    * <span data-ttu-id="43b5a-121">Dans l'organisateur Calcul, dans le champ Origine, si Montant par unité est sélectionné, la valeur sera multipliée par la quantité de la transaction pour calculer le montant de la taxe.</span><span class="sxs-lookup"><span data-stu-id="43b5a-121">On the Calculation FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="43b5a-122">Si le code taxe n'est pas une taxe basée sur des unités, la valeur est un pourcentage appliqué sur le code d'origine pour cette taxe pour calculer le montant de la taxe.</span><span class="sxs-lookup"><span data-stu-id="43b5a-122">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
15. <span data-ttu-id="43b5a-123">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="43b5a-123">Click Save.</span></span>
16. <span data-ttu-id="43b5a-124">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="43b5a-124">Close the page.</span></span>
17. <span data-ttu-id="43b5a-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="43b5a-125">Click Save.</span></span>


