--- 
title: "Envoyer des produits des centres de distribution aux magasins à l'aide de la procédure de réassort magasin"
description: "Cette procédure décrit les étapes pour créer et traiter un réassort magasin afin de distribuer les produits depuis un emplacement vers un ou plusieurs magasins."
author: rubencdelgado
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: ed47b4f052dab99dec058910e4b8558481b34e59
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="push-products-from-distribution-centers-to-stores-via-buyers-push"></a><span data-ttu-id="6efcf-103">Envoyer des produits des centres de distribution aux magasins à l'aide de la procédure de réassort magasin</span><span class="sxs-lookup"><span data-stu-id="6efcf-103">Push products from distribution centers to stores via buyer's push</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="6efcf-104">Cette procédure décrit les étapes pour créer et traiter un réassort magasin afin de distribuer les produits depuis un emplacement vers un ou plusieurs magasins.</span><span class="sxs-lookup"><span data-stu-id="6efcf-104">This procedure walks through the steps to create and process a Buyer's push to distribute products from one location to one or many stores.</span></span> <span data-ttu-id="6efcf-105">L'utilisateur peut définir plusieurs configurations et laisser le système décider de la distribution des produits, ou saisir manuellement l'emplacement de distribution des produits et la quantité distribuée dans chaque magasin.</span><span class="sxs-lookup"><span data-stu-id="6efcf-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="6efcf-106">Cette procédure n'inclut pas le paramétrage des données pouvant être utilisées dans le réassort magasin, telles que les règles de réapprovisionnement, les hiérarchies organisationnelles et les poids des magasins.</span><span class="sxs-lookup"><span data-stu-id="6efcf-106">This procedure doesn't include setup of data that can be used in the Buyer's push, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="6efcf-107">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="6efcf-107">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="6efcf-108">Accédez à Réassort magasin.</span><span class="sxs-lookup"><span data-stu-id="6efcf-108">Go to Buyer's push.</span></span>
2. <span data-ttu-id="6efcf-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6efcf-109">Click New.</span></span>
3. <span data-ttu-id="6efcf-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6efcf-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="6efcf-111">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="6efcf-111">In the Site field, enter or select a value.</span></span>
5. <span data-ttu-id="6efcf-112">Dans le champ Entrepôt, saisissez ou sélectionnez un entrepôt contenant des produits avec des quantités disponibles.</span><span class="sxs-lookup"><span data-stu-id="6efcf-112">In the Warehouse field, enter or select a warehouse that has products with on-hand quantities.</span></span>
6. <span data-ttu-id="6efcf-113">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="6efcf-113">Click Add.</span></span>
7. <span data-ttu-id="6efcf-114">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6efcf-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="6efcf-115">Dans le champ Numéro d'article, saisissez ou sélectionnez un produit.</span><span class="sxs-lookup"><span data-stu-id="6efcf-115">In the Item number field, enter or select a product.</span></span>
9. <span data-ttu-id="6efcf-116">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="6efcf-116">Click Add.</span></span>
10. <span data-ttu-id="6efcf-117">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6efcf-117">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="6efcf-118">Dans le champ Numéro d'article, saisissez ou sélectionnez une variante de produit.</span><span class="sxs-lookup"><span data-stu-id="6efcf-118">In the Item number field, enter or select a variant product.</span></span>
    * <span data-ttu-id="6efcf-119">Lors de la saisie d'une variante de produit, des lignes sont créées pour chaque variante.</span><span class="sxs-lookup"><span data-stu-id="6efcf-119">When entering a variant product, lines will be created for each variant.</span></span>  
12. <span data-ttu-id="6efcf-120">Dans la liste, marquez une ligne.</span><span class="sxs-lookup"><span data-stu-id="6efcf-120">In the list, mark a row.</span></span>
13. <span data-ttu-id="6efcf-121">Dans le champ Quantité proposée, saisissez la quantité du produit sélectionné que vous souhaitez distribuer.</span><span class="sxs-lookup"><span data-stu-id="6efcf-121">In the Pushed quantity field, type how many of the selected product you want to distribute.</span></span>
14. <span data-ttu-id="6efcf-122">Dans le champ Quantité supplémentaire à proposer, saisissez la quantité des produits ayant une quantité disponible à distribuer.</span><span class="sxs-lookup"><span data-stu-id="6efcf-122">In the Additional quantity to push field, enter the quantity of the products that have available quantity to distribute.</span></span>
15. <span data-ttu-id="6efcf-123">Dans le champ Distribution, saisissez « Priorité de l'entrepôt ».</span><span class="sxs-lookup"><span data-stu-id="6efcf-123">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="6efcf-124">Vous pouvez sélectionner les autres types pour utiliser d'autres règles de distribution.</span><span class="sxs-lookup"><span data-stu-id="6efcf-124">You can select the other types to use other rules for the distribution.</span></span>  
16. <span data-ttu-id="6efcf-125">Dans le champ Hiérarchie des réapprovisionnements, sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6efcf-125">In the Replenishment hierarchy field, select a value.</span></span>
17. <span data-ttu-id="6efcf-126">Sélectionnez Oui dans le champ Respecter les assortiments.</span><span class="sxs-lookup"><span data-stu-id="6efcf-126">Select Yes in the Respect assortments field.</span></span>
18. <span data-ttu-id="6efcf-127">Cliquez sur Calculer les quantités et examinez les quantités ajoutées aux lignes de la section Entrepôt.</span><span class="sxs-lookup"><span data-stu-id="6efcf-127">Click Calculate quantities and review the quantities that are added to the rows in the Warehouse section.</span></span>
19. <span data-ttu-id="6efcf-128">Cliquez sur Créer une commande.</span><span class="sxs-lookup"><span data-stu-id="6efcf-128">Click Create order.</span></span>
20. <span data-ttu-id="6efcf-129">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="6efcf-129">Click Yes.</span></span>


