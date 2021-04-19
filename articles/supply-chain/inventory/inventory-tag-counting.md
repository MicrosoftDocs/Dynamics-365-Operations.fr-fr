---
title: Comptage des balises de stock
description: Cette rubrique fournit des informations sur l’inventaire de balises, que vous utilisez pour comparer le contenu réel d’un entrepôt au stock disponible.
author: MarkusFogelberg
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1df4a97dee3dc24856a1b40f3dc8dd095338b614
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825961"
---
# <a name="inventory-tag-counting"></a><span data-ttu-id="5d6d3-103">Comptage des balises de stock</span><span class="sxs-lookup"><span data-stu-id="5d6d3-103">Inventory tag counting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5d6d3-104">Cette rubrique fournit des informations sur l’inventaire de balises, que vous utilisez pour comparer le contenu réel d’un entrepôt au stock disponible.</span><span class="sxs-lookup"><span data-stu-id="5d6d3-104">This topic provides information about tag counting, which you use to compare the actual contents of a warehouse with the on-hand inventory.</span></span>

<span data-ttu-id="5d6d3-105">En créant des lignes dans la page **Comptage des balises**, vous placez un numéro de balise sur chaque article en stock, comme un numéro de 1 à 500.</span><span class="sxs-lookup"><span data-stu-id="5d6d3-105">By creating lines on the **Tag counting** page, you place a tag number on each inventory item, such as a number from 1 to 500.</span></span> <span data-ttu-id="5d6d3-106">Pendant le comptage, entrez le numéro d’article et la quantité sur une balise correspondante.</span><span class="sxs-lookup"><span data-stu-id="5d6d3-106">During the count, you enter the item number and the quantity on a corresponding tag.</span></span> <span data-ttu-id="5d6d3-107">Cette balise peut ensuite être utilisée comme base pour l’entrée dans le journal de comptage des balises.</span><span class="sxs-lookup"><span data-stu-id="5d6d3-107">This tag can then be used as the basis for input in the tag counting journal.</span></span> <span data-ttu-id="5d6d3-108">Après avoir validé le journal de balises, un nouveau journal d’inventaire est créé dans la page **Comptage**.</span><span class="sxs-lookup"><span data-stu-id="5d6d3-108">After you post the tag counting journal, a new counting journal is created on the **Counting** page.</span></span> <span data-ttu-id="5d6d3-109">Ce journal est basé sur les lignes du journal de comptage des balises que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="5d6d3-109">The new journal is based on the tag counting journal lines that you created.</span></span> <span data-ttu-id="5d6d3-110">Pour compter les balises des articles en fonction d’une dimension de stock particulière, sélectionnez la dimension dans la page **Affichage des dimensions** qui s’affiche lorsque vous créez le journal de comptage des balises.</span><span class="sxs-lookup"><span data-stu-id="5d6d3-110">To tag-count items by a specific inventory dimension, select the dimension on the **Display dimension** page that is displayed when you create the tag counting journal.</span></span> <span data-ttu-id="5d6d3-111">Par exemple, pour compter les articles dans un entrepôt particulier, activez la case à cocher **Entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="5d6d3-111">For example, to count items in a specific warehouse, select the **Warehouse** check box.</span></span> <span data-ttu-id="5d6d3-112">Si le curseur **Verrouiller les articles lors du comptage** est sélectionné dans la page **Paramètres de gestion des stocks et des entrepôts**, les articles ne peuvent pas être mis à jour physiquement lors du comptage.</span><span class="sxs-lookup"><span data-stu-id="5d6d3-112">If the **Lock items during count** slider on the **Inventory and warehouse management parameters** page is selected, items can't be physically updated during counting.</span></span> <span data-ttu-id="5d6d3-113">Toutefois, les articles dans les journaux de comptage des balises ne sont pas verrouillés lors du comptage.</span><span class="sxs-lookup"><span data-stu-id="5d6d3-113">However, items in tag counting journals aren't locked during counting.</span></span> <span data-ttu-id="5d6d3-114">Les mouvements de stock ne sont pas créés tant que lorsque les lignes de comptage des balises ne sont pas validées et transférées vers un journal d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="5d6d3-114">Inventory transactions aren't created until the tag counting lines are posted and transferred to a counting journal.</span></span> <span data-ttu-id="5d6d3-115">Si les balises sont introduites dans le désordre et que vous voulez connaître les balises manquantes, cliquez sur l’en-tête de colonne **Balise** pour trier les lignes par balise.</span><span class="sxs-lookup"><span data-stu-id="5d6d3-115">If tags are entered randomly, and you want to identify missing tags, click the **Tag** column header to sort the lines by tag.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5d6d3-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5d6d3-116">Additional resources</span></span>

[<span data-ttu-id="5d6d3-117">Inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="5d6d3-117">Cycle counting</span></span>](../warehousing/cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]