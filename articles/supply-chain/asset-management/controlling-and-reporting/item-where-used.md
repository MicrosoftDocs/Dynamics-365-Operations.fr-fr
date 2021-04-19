---
title: Cas d’emploi d’article
description: Cette rubrique explique comment obtenir une vue d’ensemble de l’emplacement d’utilisation d’un article dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemWhereUsed, EntAssetItemWhereUsedCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 262a5a9d83767599f6e15183d6afcacf4b5901fe
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808638"
---
# <a name="item-where-used"></a><span data-ttu-id="c5b56-103">Cas d’emploi d’article</span><span class="sxs-lookup"><span data-stu-id="c5b56-103">Item where used</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="c5b56-104">Vous pouvez effectuer un calcul pour un article spécifique pour obtenir une vue d’ensemble de son emplacement d’utilisation dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="c5b56-104">You can make a calculation for a specific item to get an overview of where in Asset Management the item has been used.</span></span> <span data-ttu-id="c5b56-105">Les résultats indiquent le contexte dans lequel l’article était utilisé pendant toute sa durée de vie.</span><span class="sxs-lookup"><span data-stu-id="c5b56-105">The results show the context in which the item has been used during its lifetime.</span></span> <span data-ttu-id="c5b56-106">La page **Cas d’emploi d’article** peut être ouverte à partir du menu principal Gestion des actifs, et elle est également accessible à partir des pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="c5b56-106">The **Item where used** page can be opened from the main Asset Management menu, and it can also be accessed from the following pages:</span></span>

- [<span data-ttu-id="c5b56-107">Nomenclatures d’actif</span><span class="sxs-lookup"><span data-stu-id="c5b56-107">Asset BOMs</span></span>](../objects/object-BOM.md)

- [<span data-ttu-id="c5b56-108">Pièces détachées sur Valeurs par défaut du type d’actif</span><span class="sxs-lookup"><span data-stu-id="c5b56-108">Spare parts on asset type defaults</span></span>](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [<span data-ttu-id="c5b56-109">Catégories de type de tâche de maintenance et types de tâches de maintenance, variantes de type de tâche de maintenance, opérations de tâches de maintenance et listes de contrôle de maintenance</span><span class="sxs-lookup"><span data-stu-id="c5b56-109">Maintenance job type categories and maintenance job types, maintenance job type variants, maintenance job trades, and maintenance checklists</span></span>](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [<span data-ttu-id="c5b56-110">Prévision en matière de maintenance</span><span class="sxs-lookup"><span data-stu-id="c5b56-110">Maintenance forecast</span></span>](../work-orders/maintenance-forecasts.md)

- [<span data-ttu-id="c5b56-111">Approvisionnement</span><span class="sxs-lookup"><span data-stu-id="c5b56-111">Procurement</span></span>](../work-orders/procurement.md)

- [<span data-ttu-id="c5b56-112">Achats de l’ordre de travail</span><span class="sxs-lookup"><span data-stu-id="c5b56-112">Work order purchase</span></span>](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a><span data-ttu-id="c5b56-113">Effectuer un calcul de cas d’emploi d’article</span><span class="sxs-lookup"><span data-stu-id="c5b56-113">Make an item-where-used calculation</span></span>

1. <span data-ttu-id="c5b56-114">Cliquez sur **Gestion des actifs** > **Recherches** > **Cas d’emploi d’article** ou cliquez sur le bouton **Cas d’emploi d’article** sur l’une des pages mentionnées ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="c5b56-114">Click **Asset management** > **Inquiries** > **Item where used**, or select the **Item where used** button on one of the pages mentioned above.</span></span>

2. <span data-ttu-id="c5b56-115">Dans la boîte de dialogue **Cas d’emploi d’article**, sélectionnez l’article pour lequel vous souhaitez effectuer le calcul dans le champ **Numéro d’article**.</span><span class="sxs-lookup"><span data-stu-id="c5b56-115">In the **Item where used** dialog, select the item for which you want to make the calculation in the **Item number** field.</span></span>

3. <span data-ttu-id="c5b56-116">Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes d’article en fonction des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="c5b56-116">You can use the **Level** field to indicate how detailed you want the item lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="c5b56-117">Par exemple, si vous insérez le chiffre « 1 » dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes d’article pour un poste technique s’affichent dans le niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="c5b56-117">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all item lines for a functional location will be shown on the top level.</span></span> <span data-ttu-id="c5b56-118">Par conséquent, la relation/quantité d’une ligne peut être ajoutée à partir des emplacements fonctionnels situés à un niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="c5b56-118">Therefore, relation/quantity on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="c5b56-119">Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s’affiche et indique toutes les lignes d’article sur tous les niveaux du poste technique auxquels ils sont liés.</span><span class="sxs-lookup"><span data-stu-id="c5b56-119">If you insert the number "0" in the **Level** field, you will see a detailed result showing all item lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="c5b56-120">Dans la section **Inclure**, sélectionnez « Oui » sur les boutons bascule à inclure dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="c5b56-120">In the **Include** section, select "Yes" on the toggle buttons that you want to include in the calculation.</span></span>

5. <span data-ttu-id="c5b56-121">Cliquez sur **OK** pour démarrer le calcul.</span><span class="sxs-lookup"><span data-stu-id="c5b56-121">Click **OK** to start the calculation.</span></span>

6. <span data-ttu-id="c5b56-122">Dans l’onglet **Cas d’emploi d’article**, sélectionnez les boutons **Grouper par** pour afficher le niveau requis de détail du calcul.</span><span class="sxs-lookup"><span data-stu-id="c5b56-122">On the **Item where used** tab, select the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="c5b56-123">Les boutons **Grouper par** sélectionnés sont mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="c5b56-123">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="c5b56-124">Cliquez sur un bouton pour l’activer ou le désactiver.</span><span class="sxs-lookup"><span data-stu-id="c5b56-124">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="c5b56-125">Si vous souhaitez afficher d’autres dimensions associées à l’article, cliquez sur **Afficher les dimensions**, puis sélectionnez les dimensions à afficher.</span><span class="sxs-lookup"><span data-stu-id="c5b56-125">If you want to show dimensions related to the item, click **Display dimensions**, and select the dimensions to be shown.</span></span>

## <a name="example"></a><span data-ttu-id="c5b56-126">Exemple</span><span class="sxs-lookup"><span data-stu-id="c5b56-126">Example</span></span>

<span data-ttu-id="c5b56-127">Dans la capture d’écran ci-dessous, vous verrez un exemple de calcul de cas d’emploi d’article pour le numéro d’article « 1000 ».</span><span class="sxs-lookup"><span data-stu-id="c5b56-127">In the screenshot below, you see an example of an item-where-used calculation for item number "1000".</span></span>

![Exemple de calcul de cas d’emploi d’article](media/12-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]