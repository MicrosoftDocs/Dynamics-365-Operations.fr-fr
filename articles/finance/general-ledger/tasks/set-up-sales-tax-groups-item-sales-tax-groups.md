---
title: Paramétrer des groupes de taxe et groupes de taxe d’article
description: Cet enregistrement de tâche décrit le paramétrage des groupes Taxe et Taxe d’article.
author: twheeloc
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxGroup,  TaxItemGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e97766be1207fb66b38f25b1e423fb21cec9e726
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222165"
---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="6a93c-103">Paramétrer des groupes de taxe et groupes de taxe d’article</span><span class="sxs-lookup"><span data-stu-id="6a93c-103">Set up sales tax groups and item sales tax groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6a93c-104">Cet enregistrement de tâche décrit le paramétrage des groupes Taxe et Taxe d’article.</span><span class="sxs-lookup"><span data-stu-id="6a93c-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="6a93c-105">Les groupes de taxe sont des groupes de codes taxe associés aux clients et aux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="6a93c-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="6a93c-106">Ils sont également associés aux comptes généraux pour les transactions non validées pour un fournisseur ou client spécifique.</span><span class="sxs-lookup"><span data-stu-id="6a93c-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="6a93c-107">Les groupes Taxe d’article sont des groupes de codes taxe associés aux ressources comme des produits.</span><span class="sxs-lookup"><span data-stu-id="6a93c-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="6a93c-108">Les taxes qui s’appliquent à une transaction donnée sont déterminées par les codes taxe inclus dans le groupe de taxe et le groupe de taxe d’article de la transaction.</span><span class="sxs-lookup"><span data-stu-id="6a93c-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="6a93c-109">Le calcul de la taxe requiert la sélection d’un groupe de taxe et d’un groupe de taxe d’article pour chaque transaction pour laquelle la taxe doit être calculée ou enregistrée.</span><span class="sxs-lookup"><span data-stu-id="6a93c-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="6a93c-110">Accédez à **Volet de navigation > Modules > Taxes > Taxes indirectes > Taxe > Groupes de taxe**.</span><span class="sxs-lookup"><span data-stu-id="6a93c-110">Go to **Navigation pane > Modules > Tax > Indirect taxes > Sales tax > Sales tax groups**.</span></span>
2. <span data-ttu-id="6a93c-111">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6a93c-111">Click **New**.</span></span>
3. <span data-ttu-id="6a93c-112">Dans le champ **Groupe de taxe**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6a93c-112">In the **Sales tax group** field, type a value.</span></span>
4. <span data-ttu-id="6a93c-113">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="6a93c-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="6a93c-114">Activez ou désactivez l’extension de la section **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="6a93c-114">Toggle the expansion of the **Setup** section.</span></span>
6. <span data-ttu-id="6a93c-115">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6a93c-115">Click **Add**.</span></span>
7. <span data-ttu-id="6a93c-116">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a93c-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="6a93c-117">Dans le champ **Code taxe**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a93c-117">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="6a93c-118">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a93c-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="6a93c-119">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6a93c-119">Click **Save**.</span></span>
11. <span data-ttu-id="6a93c-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6a93c-120">Close the page.</span></span>
12. <span data-ttu-id="6a93c-121">Accédez à **Taxe > Taxes indirectes > Taxe > Groupes de taxe d’article**.</span><span class="sxs-lookup"><span data-stu-id="6a93c-121">Go to **Tax > Indirect taxes > Sales tax > Item sales tax groups**.</span></span>
13. <span data-ttu-id="6a93c-122">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6a93c-122">Click **New**.</span></span>
14. <span data-ttu-id="6a93c-123">Tapez une valeur dans le champ **Groupe de taxe d’article**.</span><span class="sxs-lookup"><span data-stu-id="6a93c-123">In the **Item sales tax group** field, type a value.</span></span>
15. <span data-ttu-id="6a93c-124">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="6a93c-124">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="6a93c-125">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6a93c-125">Click **Add**.</span></span>
17. <span data-ttu-id="6a93c-126">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a93c-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="6a93c-127">Dans le champ **Code taxe**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a93c-127">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="6a93c-128">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a93c-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="6a93c-129">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6a93c-129">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]