---
title: Paramétrer des codes taxe
description: Cette rubrique explique comment paramétrer des codes taxe dans Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 594e8f0595ecace748a70860c1ccacaf90b7d279
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222189"
---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="09dec-103">Paramétrer des codes taxe</span><span class="sxs-lookup"><span data-stu-id="09dec-103">Set up sales tax codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="09dec-104">Cette rubrique explique comment paramétrer des codes taxe.</span><span class="sxs-lookup"><span data-stu-id="09dec-104">This topic explains how to set up sales tax codes.</span></span> <span data-ttu-id="09dec-105">Les codes taxe sont créés pour chaque taxe indirecte ou responsabilité que l’entité juridique est obligée de calculer, de collecter et de payer à l’administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="09dec-105">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="09dec-106">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="09dec-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="09dec-107">Allez dans **Volet de navigation > Taxes > Taxes indirectes > Taxe > Codes taxe**.</span><span class="sxs-lookup"><span data-stu-id="09dec-107">Go to **Navigation pane > Tax > Indirect taxes > Sales tax > Sales tax codes**.</span></span>
2. <span data-ttu-id="09dec-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="09dec-108">Select **New**.</span></span>
3. <span data-ttu-id="09dec-109">Tapez une valeur dans le champ **Code taxe**.</span><span class="sxs-lookup"><span data-stu-id="09dec-109">In the **Sales tax code** field, type a value.</span></span>
4. <span data-ttu-id="09dec-110">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="09dec-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="09dec-111">Sélectionnez une **Période de règlement** en ouvrant la liste déroulante pour spécifier l’administration fiscale et les intervalles auxquels cette taxe doit être déclarée et payée.</span><span class="sxs-lookup"><span data-stu-id="09dec-111">Select a **Settlement period** by opening the pull-down list to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="09dec-112">Sélectionnez un **Groupe de validation dans la comptabilité** pour spécifier les comptes principaux pour valider la taxe dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="09dec-112">Select a **Ledger posting group** to specify the main accounts to post sales tax to the general ledger.</span></span>
7. <span data-ttu-id="09dec-113">Développez le raccourci **Calcul**.</span><span class="sxs-lookup"><span data-stu-id="09dec-113">Expand the **Calculation** FastTab.</span></span> <span data-ttu-id="09dec-114">Plusieurs champs contrôlent la manière dont les montants de taxe sont calculés.</span><span class="sxs-lookup"><span data-stu-id="09dec-114">This includes multiple fields that control how sales tax amounts will be calculated.</span></span> <span data-ttu-id="09dec-115">Renseignez ces champs si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="09dec-115">Fill these fields out as needed.</span></span>  
8. <span data-ttu-id="09dec-116">Dans le **Volet Actions** en haut de l’interface, sélectionnez **Code taxe**.</span><span class="sxs-lookup"><span data-stu-id="09dec-116">On the **Action Pane** at the top of the interface, select **Sales tax code**.</span></span>
9. <span data-ttu-id="09dec-117">Sélectionnez **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="09dec-117">Select **Values**.</span></span>
10. <span data-ttu-id="09dec-118">Entrez la valeur pour ce code taxe dans la colonne **valeur**.</span><span class="sxs-lookup"><span data-stu-id="09dec-118">Enter the value for this tax code in the **value** column.</span></span>
    - <span data-ttu-id="09dec-119">Dans le raccourci **Calcul**, dans le champ Origine, si Montant par unité est sélectionné, la valeur sera multipliée par la quantité de la transaction pour calculer le montant de la taxe.</span><span class="sxs-lookup"><span data-stu-id="09dec-119">On the **Calculation** FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="09dec-120">Si le code taxe n’est pas une taxe basée sur des unités, la valeur est un pourcentage appliqué sur le code d’origine pour cette taxe pour calculer le montant de la taxe.</span><span class="sxs-lookup"><span data-stu-id="09dec-120">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
11. <span data-ttu-id="09dec-121">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="09dec-121">Select **Save**.</span></span>
12. <span data-ttu-id="09dec-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="09dec-122">Close the page.</span></span>
13. <span data-ttu-id="09dec-123">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="09dec-123">Select **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]