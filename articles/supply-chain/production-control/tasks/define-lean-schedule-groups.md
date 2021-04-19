---
title: Définir les groupes de calendriers de production au plus juste
description: Les groupes de calendriers de production au plus juste sont définis pour regrouper et distinguer les produits dans le calendrier kanban.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanScheduleGroup, GanttColorTableLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 647e721a0616ceae387322517f2955d75c06bfd2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828752"
---
# <a name="define-lean-schedule-groups"></a><span data-ttu-id="ca8ed-103">Définir les groupes de calendriers de production au plus juste</span><span class="sxs-lookup"><span data-stu-id="ca8ed-103">Define lean schedule groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ca8ed-104">Les groupes de calendriers de production au plus juste sont définis pour regrouper et distinguer les produits dans le calendrier kanban.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-104">Lean schedule groups are defined to group and distinguish products in kanban scheduling.</span></span> <span data-ttu-id="ca8ed-105">Le regroupement peut être effectuée comme l’association générique par société ou être spécifique à une cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-105">The grouping can be done as generic association per company or specific to a work cell.</span></span> <span data-ttu-id="ca8ed-106">Chaque groupe est doté d’un code couleur pour l’indication visuelle dans la page de liste de calendrier kanban.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-106">Each group has a color code assigned for visual indication in the kanban scheduling listpage.</span></span> <span data-ttu-id="ca8ed-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="define-lean-scheduling-group"></a><span data-ttu-id="ca8ed-108">Définir un groupe de calendriers de production au plus juste</span><span class="sxs-lookup"><span data-stu-id="ca8ed-108">Define lean scheduling group</span></span>
1. <span data-ttu-id="ca8ed-109">Accédez à Gestion des informations sur les produits > Lean Manufacturing > Groupes de calendriers de production au plus juste.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-109">Go to Product information management > Lean manufacturing > Lean schedule groups.</span></span>
2. <span data-ttu-id="ca8ed-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-110">Click New.</span></span>
3. <span data-ttu-id="ca8ed-111">Dans le champ Groupe de programmes, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-111">In the Schedule group field, type a value.</span></span>
    * <span data-ttu-id="ca8ed-112">Un groupe de calendriers de production peut être défini comme un groupe global ou spécifique à une cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-112">A schedule group can be defined as global group or specific to a work cell.</span></span> <span data-ttu-id="ca8ed-113">Dans cet exemple simple, nous définissons un groupe global, et la cellule de travail demeure vide.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-113">In this simple example, we define a global group, and the work cell is kept empty.</span></span> <span data-ttu-id="ca8ed-114">Les paramètres de ce groupe s’appliquent à toutes les cellules de travail qui n’ont pas de groupes de calendriers de production spécifiques.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-114">The settings of this group apply to all work cells that do not have specific schedule groups.</span></span>  
4. <span data-ttu-id="ca8ed-115">Sélectionnez une couleur de la sélection des couleurs.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-115">Select a color from the color selection.</span></span>
    * <span data-ttu-id="ca8ed-116">Les couleurs permettent de mettre en surbrillance les tâches de la page de liste du programme kanban ou du tableau de traitement kanban.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-116">The colors are used to highlight the jobs on the kanban schedule list page or the kanban process board.</span></span>  
5. <span data-ttu-id="ca8ed-117">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="ca8ed-118">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-118">In the list, click the link in the selected row.</span></span>

## <a name="associate-product"></a><span data-ttu-id="ca8ed-119">Associer un produit</span><span class="sxs-lookup"><span data-stu-id="ca8ed-119">Associate product</span></span>
1. <span data-ttu-id="ca8ed-120">Associer un produit spécifique</span><span class="sxs-lookup"><span data-stu-id="ca8ed-120">Associate a specific product</span></span>
    * <span data-ttu-id="ca8ed-121">Il existe deux manières d’associer des produits aux groupes de calendriers de production au plus juste, comme produit spécifique (Type de relation d’article = Article) ou dans le cadre d’une clé de répartition par article (Type de relation d’article = groupe).</span><span class="sxs-lookup"><span data-stu-id="ca8ed-121">There are two ways to associate products to lean schedule groups, either as a specific product (Item relation type = Item) or as part of an item allocation key (item relation type = group).</span></span>    
2. <span data-ttu-id="ca8ed-122">Dans le champ Type de relation d’article, sélectionnez Article</span><span class="sxs-lookup"><span data-stu-id="ca8ed-122">In the Item relation type field, select Item</span></span>
3. <span data-ttu-id="ca8ed-123">Tapez une valeur dans le champ Numéro d’article.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-123">In the Item number field, type a value.</span></span>
4. <span data-ttu-id="ca8ed-124">Dans le champ Taux de débit, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-124">In the Throughput ratio field, enter a number.</span></span>
    * <span data-ttu-id="ca8ed-125">Le taux par défaut de débit est 1, ce qui signifie que les produits associés consomment précisément la capacité spécifiée dans les activités de processus des flux de production.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-125">The default Throughput ratio is 1, which means that the related products consume exactly the capacity specified in the process activites of the production flows.</span></span> <span data-ttu-id="ca8ed-126">Taux de débit > 1 définit une consommation de ressource plus élevée, Taux de débit < 1 définit une consommation de ressource plus faible.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-126">Throughput ratio > 1 defines a higher resource consumption, Throughput ratio < 1 defines a lower resource consumption.</span></span> <span data-ttu-id="ca8ed-127">Le taux est utilisé dans le calcul des coûts et dans le calcul de la consommation de la tâche de kanban.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-127">The ratio is used in the cost calculation and in the calculation of the kanban job consumption.</span></span>  

## <a name="associate-item-allocation-key"></a><span data-ttu-id="ca8ed-128">Associer une clé de répartition par article</span><span class="sxs-lookup"><span data-stu-id="ca8ed-128">Associate item allocation key</span></span>
1. <span data-ttu-id="ca8ed-129">Associer une clé de répartition par article</span><span class="sxs-lookup"><span data-stu-id="ca8ed-129">Associate an item allocation key</span></span>
    * <span data-ttu-id="ca8ed-130">Ajoutez une association à une clé de répartition par article à l’aide du groupe Type de relation d’article.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-130">Add an association to an item allocation key by using the Item relation type Group.</span></span>   <span data-ttu-id="ca8ed-131">Notez que pour ce processus, vous devez la clé de répartition par article prévue doit être définie dans vos données.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-131">Note that for this process, you need a forecast item alllocation key defined in your data.</span></span>  
2. <span data-ttu-id="ca8ed-132">Dans le champ Type de relation d’article, sélectionnez Groupe</span><span class="sxs-lookup"><span data-stu-id="ca8ed-132">In the Item relation type field, select Group</span></span>
3. <span data-ttu-id="ca8ed-133">Dans le champ Clé de répartition par article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-133">In the Item allocation key field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ca8ed-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ca8ed-134">In the list, click the link in the selected row.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]