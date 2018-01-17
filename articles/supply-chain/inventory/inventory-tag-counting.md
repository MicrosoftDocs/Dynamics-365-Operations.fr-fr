---
title: Comptage des balises de stock
description: "Cet article fournit des informations sur l'inventaire de balises, que vous utilisez pour comparer le contenu réel d'un entrepôt au stock disponible."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 8f219b8cde6191dc52300f3b03c930bcd0c71d18
ms.contentlocale: fr-fr
ms.lasthandoff: 01/17/2018

---

# <a name="inventory-tag-counting"></a><span data-ttu-id="74a19-103">Comptage des balises de stock</span><span class="sxs-lookup"><span data-stu-id="74a19-103">Inventory tag counting</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


<span data-ttu-id="74a19-104">Cet article fournit des informations sur l'inventaire de balises, que vous utilisez pour comparer le contenu réel d'un entrepôt au stock disponible.</span><span class="sxs-lookup"><span data-stu-id="74a19-104">This article provides information about tag counting, which you use to compare the actual contents of a warehouse with the on-hand inventory.</span></span>

<span data-ttu-id="74a19-105">En créant des lignes dans la page **Comptage des balises**, vous placez un numéro de balise sur chaque article en stock, comme un numéro de 1 à 500.</span><span class="sxs-lookup"><span data-stu-id="74a19-105">By creating lines on the **Tag counting** page, you place a tag number on each inventory item, such as a number from 1 to 500.</span></span> <span data-ttu-id="74a19-106">Pendant le comptage, entrez le numéro d'article et la quantité sur une balise correspondante.</span><span class="sxs-lookup"><span data-stu-id="74a19-106">During the count, you enter the item number and the quantity on a corresponding tag.</span></span> <span data-ttu-id="74a19-107">Cette balise peut ensuite être utilisée comme base pour l'entrée dans le journal de comptage des balises.</span><span class="sxs-lookup"><span data-stu-id="74a19-107">This tag can then be used as the basis for input in the tag counting journal.</span></span> <span data-ttu-id="74a19-108">Après avoir validé le journal de balises, un nouveau journal d'inventaire est créé dans la page **Comptage**.</span><span class="sxs-lookup"><span data-stu-id="74a19-108">After you post the tag counting journal, a new counting journal is created on the **Counting** page.</span></span> <span data-ttu-id="74a19-109">Ce journal est basé sur les lignes du journal de comptage des balises que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="74a19-109">The new journal is based on the tag counting journal lines that you created.</span></span> <span data-ttu-id="74a19-110">Pour compter les balises des articles en fonction d'une dimension de stock particulière, sélectionnez la dimension dans la page **Affichage des dimensions** qui s'affiche lorsque vous créez le journal de comptage des balises.</span><span class="sxs-lookup"><span data-stu-id="74a19-110">To tag-count items by a specific inventory dimension, select the dimension on the **Display dimension** page that is displayed when you create the tag counting journal.</span></span> <span data-ttu-id="74a19-111">Par exemple, pour compter les articles dans un entrepôt particulier, activez la case à cocher **Entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="74a19-111">For example, to count items in a specific warehouse, select the **Warehouse** check box.</span></span> <span data-ttu-id="74a19-112">Si le curseur **Verrouiller les articles lors du comptage** est sélectionné dans la page **Paramètres de gestion des stocks et des entrepôts**, les articles ne peuvent pas être mis à jour physiquement lors du comptage.</span><span class="sxs-lookup"><span data-stu-id="74a19-112">If the **Lock items during count** slider on the **Inventory and warehouse management parameters** page is selected, items can't be physically updated during counting.</span></span> <span data-ttu-id="74a19-113">Toutefois, les articles dans les journaux de comptage des balises ne sont pas verrouillés lors du comptage.</span><span class="sxs-lookup"><span data-stu-id="74a19-113">However, items in tag counting journals aren't locked during counting.</span></span> <span data-ttu-id="74a19-114">Les mouvements de stock ne sont pas créés tant que lorsque les lignes de comptage des balises ne sont pas validées et transférées vers un journal d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="74a19-114">Inventory transactions aren't created until the tag counting lines are posted and transferred to a counting journal.</span></span> <span data-ttu-id="74a19-115">Si les balises sont introduites dans le désordre et que vous voulez connaître les balises manquantes, cliquez sur l'en-tête de colonne **Balise** pour trier les lignes par balise.</span><span class="sxs-lookup"><span data-stu-id="74a19-115">If tags are entered randomly, and you want to identify missing tags, click the **Tag** column header to sort the lines by tag.</span></span>

<a name="see-also"></a><span data-ttu-id="74a19-116">Voir également :</span><span class="sxs-lookup"><span data-stu-id="74a19-116">See also</span></span>
--------

[<span data-ttu-id="74a19-117">Inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="74a19-117">Cycle counting</span></span>](../warehousing/cycle-counting.md)

