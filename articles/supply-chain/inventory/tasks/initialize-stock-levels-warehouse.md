---
title: Initialiser les niveaux des stocks dans l’entrepôt
description: Cette procédure décrit la manière dont vous obtenez le stock disponible mis à jour manuellement à l’aide du journal des mouvements de stock.
author: perlynne
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0746b799c701c569f0ae5c657ac3302ab6626287
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823479"
---
# <a name="initialize-stock-levels-in-the-warehouse"></a><span data-ttu-id="07de2-103">Initialiser les niveaux des stocks dans l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="07de2-103">Initialize stock levels in the warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="07de2-104">Cette procédure décrit la manière dont vous obtenez le stock disponible mis à jour manuellement à l’aide du journal des mouvements de stock.</span><span class="sxs-lookup"><span data-stu-id="07de2-104">This procedure shows you how to get the on-hand inventory updated manually using an Inventory movement journal.</span></span> <span data-ttu-id="07de2-105">(Il est également possible de mettre à jour le stock disponible en important les transactions dans des entités de données.) Vous pouvez exécuter ce guide avec les données de démonstration de la société USMF dans lesquelles toutes les conditions préalables, comme le nom de journal, le paramétrage des articles, les profils de validation et les comptes sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="07de2-105">(It's also possible to update on-hand inventory by importing transactions in data entities.) You can run this guide in demo data company USMF where all the prerequisites like journal name, item setup, posting profiles, and accounts are available.</span></span> <span data-ttu-id="07de2-106">Le guide propose des valeurs spécifiques pour l’article et les dimensions utilisés.</span><span class="sxs-lookup"><span data-stu-id="07de2-106">The guide suggests specific values for the item and dimensions that are used.</span></span> <span data-ttu-id="07de2-107">Si vous sélectionnez un article différent, vous devrez peut-être entrer des valeurs pour des dimensions différentes.</span><span class="sxs-lookup"><span data-stu-id="07de2-107">If you choose a different item, you may need to enter values for different dimensions.</span></span>

1. <span data-ttu-id="07de2-108">Accédez à Gestion des stocks > Entrées de journal > Articles > Mouvement.</span><span class="sxs-lookup"><span data-stu-id="07de2-108">Go to Inventory management > Journal entries > Items > Movement.</span></span>
2. <span data-ttu-id="07de2-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="07de2-109">Click New.</span></span>
3. <span data-ttu-id="07de2-110">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="07de2-110">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="07de2-111">Sélectionnez IMov.</span><span class="sxs-lookup"><span data-stu-id="07de2-111">Select IMov.</span></span>
    * <span data-ttu-id="07de2-112">Il est judicieux d’utiliser différents modèles de nom de journal pour les différents objectifs de l’activité.</span><span class="sxs-lookup"><span data-stu-id="07de2-112">It's a good practice to use different journal name templates for the different business purposes.</span></span>  
5. <span data-ttu-id="07de2-113">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="07de2-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="07de2-114">Spécifiez les valeurs ’140200’ dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="07de2-114">In the Offset account field, specify the values '140200'.</span></span>
    * <span data-ttu-id="07de2-115">Il s’agit du compte de contrepartie qui sera le compte par défaut dans les lignes de journal.</span><span class="sxs-lookup"><span data-stu-id="07de2-115">This is the offset account that will be the default account on the journal lines.</span></span> <span data-ttu-id="07de2-116">Il est possible de remplacer la valeur par défaut pour affecter différents comptes de contrepartie par ligne.</span><span class="sxs-lookup"><span data-stu-id="07de2-116">It's possible to override the default to assign different offset accounts per line.</span></span>  
7. <span data-ttu-id="07de2-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="07de2-117">Click OK.</span></span>
8. <span data-ttu-id="07de2-118">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="07de2-118">Click New.</span></span>
9. <span data-ttu-id="07de2-119">Dans le champ Numéro d’article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="07de2-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="07de2-120">Sélectionner l’article A0001.</span><span class="sxs-lookup"><span data-stu-id="07de2-120">Select item A0001.</span></span>
11. <span data-ttu-id="07de2-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="07de2-121">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="07de2-122">Cliquez sur l’onglet Dimensions de stock.</span><span class="sxs-lookup"><span data-stu-id="07de2-122">Click the Inventory dimensions tab.</span></span>
13. <span data-ttu-id="07de2-123">Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="07de2-123">In the Site field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="07de2-124">Sélectionner le site 1.</span><span class="sxs-lookup"><span data-stu-id="07de2-124">Select site 1.</span></span>
15. <span data-ttu-id="07de2-125">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="07de2-125">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="07de2-126">Sélectionner l’entrepôt 13.</span><span class="sxs-lookup"><span data-stu-id="07de2-126">Select warehouse 13.</span></span>
17. <span data-ttu-id="07de2-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="07de2-127">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="07de2-128">Dans le champ Emplacement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="07de2-128">In the Location field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="07de2-129">Sélectionner l’emplacement 13.</span><span class="sxs-lookup"><span data-stu-id="07de2-129">Select location 13.</span></span>
20. <span data-ttu-id="07de2-130">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="07de2-130">In the Quantity field, enter a number.</span></span>
21. <span data-ttu-id="07de2-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="07de2-131">Click Save.</span></span>
22. <span data-ttu-id="07de2-132">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="07de2-132">Click Post.</span></span>
23. <span data-ttu-id="07de2-133">Activez ou désactivez la case à cocher Transférer toutes les erreurs de validation vers un nouveau journal.</span><span class="sxs-lookup"><span data-stu-id="07de2-133">Check or uncheck the Transfer all posting errors to a new journal check box.</span></span>
    * <span data-ttu-id="07de2-134">Si vous activez cette option, toutes les lignes non validées seront copiées dans un nouveau journal.</span><span class="sxs-lookup"><span data-stu-id="07de2-134">If you enable this option, any lines that fail to post will be copied to a new journal.</span></span> <span data-ttu-id="07de2-135">Vous pouvez utiliser les informations contenues dans le journal pour corriger les problèmes puis revalider les lignes.</span><span class="sxs-lookup"><span data-stu-id="07de2-135">You can use the information in the log to correct the issues and then re-post the lines.</span></span>  
24. <span data-ttu-id="07de2-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="07de2-136">Click OK.</span></span>
25. <span data-ttu-id="07de2-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="07de2-137">Close the page.</span></span>
26. <span data-ttu-id="07de2-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="07de2-138">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]