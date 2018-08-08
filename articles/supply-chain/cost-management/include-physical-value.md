---
title: Inclure la valeur physique
description: "Vous utilisez la case à cocher Inclure la valeur physique dans l'organisateur Modèle de stock de la page Groupes de modèles d'article pour spécifier si les transactions mises à jour physiquement sont considérées dans le calcul du prix de revient moyen en cours pour un article."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: e96d5e2a658a027d66663868329cf4eedcb1d46f
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="include-physical-value"></a><span data-ttu-id="e2bdc-103">Inclure la valeur physique</span><span class="sxs-lookup"><span data-stu-id="e2bdc-103">Include physical value</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e2bdc-104">Vous utilisez la case à cocher Inclure la valeur physique dans l'organisateur Modèle de stock de la page Groupes de modèles d'article pour spécifier si les transactions mises à jour physiquement sont considérées dans le calcul du prix de revient moyen en cours pour un article.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-104">You use the Include physical value check box on the Inventory model FastTab of the Item model groups page to specify whether physically updated transactions are considered when the running average cost price is calculated for an item.</span></span>

<span data-ttu-id="e2bdc-105">La case à cocher **Inclure la valeur physique** possède les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-105">The **Include physical value** check box has the following values.</span></span>

| <span data-ttu-id="e2bdc-106">Valeur</span><span class="sxs-lookup"><span data-stu-id="e2bdc-106">Value</span></span>    | <span data-ttu-id="e2bdc-107">Résultat</span><span class="sxs-lookup"><span data-stu-id="e2bdc-107">Result</span></span>                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e2bdc-108">Sélectionné</span><span class="sxs-lookup"><span data-stu-id="e2bdc-108">Selected</span></span> | <span data-ttu-id="e2bdc-109">Les transactions mises à jour physiquement et financièrement sont utilisées pour calculer le prix de revient moyen en cours.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-109">Both physically updated transactions and financially updated transactions are used to calculate the running average cost price.</span></span> |
| <span data-ttu-id="e2bdc-110">Désactivé</span><span class="sxs-lookup"><span data-stu-id="e2bdc-110">Cleared</span></span>  | <span data-ttu-id="e2bdc-111">Seules les transactions mises à jour financièrement sont utilisées pour calculer le prix de revient moyen en cours.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-111">Only financially updated transactions are used to calculate the running average cost price.</span></span>                                     |

<span data-ttu-id="e2bdc-112">La case à cocher produit des résultats légèrement différents en fonction du modèle de stock que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-112">The check box has slightly different effects, depending on the inventory model that you use.</span></span>

-   <span data-ttu-id="e2bdc-113">Si vous activez la case à cocher **Inclure la valeur physique** lorsque vous utilisez les modèles de stock par date FIFO (Premier entré, premier sorti), LIFO (Dernier entré, premier sorti), ou LIFO, la clôture de stock engendre également des ajustements sur les transactions mises à jour physiquement.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-113">If you select the **Include physical value** check box when you use the FIFO (First in, first out), LIFO (Last in, first out), or LIFO date inventory model, inventory close also makes adjustments to physically updated transactions.</span></span>
-   <span data-ttu-id="e2bdc-114">Si vous n'activez pas la case à cocher **Inclure la valeur physique** lorsque vous utilisez ces modèles de stock, la clôture de stock engendre des règlements uniquement pour les transactions mises à jour financièrement.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-114">If you don't select the **Include physical value** check box when you use these inventory models, inventory close makes settlements only to financially updated transactions.</span></span>
-   <span data-ttu-id="e2bdc-115">Lorsque vous utilisez les modèles de stock de moyenne pondérée ou de date moyenne pondérée, la clôture de stock règle uniquement les transactions mises à jour financièrement, à moins que vous n'activiez la case à cocher **Inclure la valeur physique**.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-115">When you use the weighted average or weighted average date inventory model, inventory close settles only financially updated transactions, regardless of whether you select the **Include physical value** check box.</span></span>

<span data-ttu-id="e2bdc-116">**Exemple 1** Vous avez activé la case à cocher**Inclure la valeur physique** et vous recevez les commandes fournisseur suivantes :</span><span class="sxs-lookup"><span data-stu-id="e2bdc-116">**Example 1** You've selected the **Include physical value** check box and receive the following purchase orders:</span></span>

-   <span data-ttu-id="e2bdc-117">Une commande fournisseur comportant 2 articles à un prix de revient de 10,00 EUR qui a été mise à jour par bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-117">A purchase order for a quantity of 2 and a cost price of USD 10.00 that has been packing slip–updated</span></span>
-   <span data-ttu-id="e2bdc-118">Une commande fournisseur comportant 3 articles à un prix de revient de 12,00 EUR qui a été mise à jour par une facture.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-118">A purchase order for a quantity of 3 and a cost price of USD 12.00 that has been invoice-updated</span></span>

<span data-ttu-id="e2bdc-119">Dans ce cas, le prix de revient moyen en cours sera de 11,20 EUR car les transactions mises à jour physiquement et financièrement sont utilisées pour calculer le prix de revient.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-119">In this case, the running average cost price will be USD 11.20, because both physically updated transactions and financially updated transactions are used to calculate the cost price.</span></span> <span data-ttu-id="e2bdc-120">**Exemple 2** Vous n'avez pas activé la case à cocher **Inclure la valeur physique** et le prix de revient sur le paramétrage de l'article est de 10,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-120">**Example 2** You haven't selected the **Include physical value** check box, and the cost price on the item setup is USD 10.00.</span></span> <span data-ttu-id="e2bdc-121">Vous recevez une commande fournisseur comportant 20 articles à un prix de revient de 12,00 EUR qui a été mise à jour par bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-121">You receive a purchase order for a quantity of 20 and a cost price of USD 12.00 that has been packing slip–updated.</span></span> <span data-ttu-id="e2bdc-122">Lorsque une commande client est validée, le montant du coût validé est de 10,00 EUR car le prix de revient moyen en cours n'inclut pas les transactions validées physiquement.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-122">When a sales order is posted, the posted cost amount is USD 10.00, because the running average cost price won't include physically posted transactions.</span></span> <span data-ttu-id="e2bdc-123">**Remarque :** À des fins de comparaison, si vous activez la case à cocher **Inclure la valeur physique** pour cet article, lorsqu'une commande client est validée, le montant du coût validé sera de 12,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="e2bdc-123">**Note:** For comparison, if you select the **Include physical value** check box for this item, when a sales order is posted, the posted cost amount will be USD 12.00.</span></span>




