---
title: Créer des modules de produit pour les commandes fournisseur
description: Cette procédure vous guide lors de la création d'un ensemble de produits et de son utilisation sur une commande fournisseur.
author: josaw1
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d16c5c576ce6b35687fb7edab835d52f6f58e6a0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256971"
---
# <a name="create-product-packages-for-purchase-orders"></a><span data-ttu-id="89d64-103">Créer des modules de produit pour les commandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="89d64-103">Create product packages for purchase orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89d64-104">Cette procédure vous guide lors de la création d'un ensemble de produits et de son utilisation sur une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="89d64-104">This procedure walks through creating a product package and using it on a purchase order.</span></span> <span data-ttu-id="89d64-105">La commande fournisseur sera utilisée pour créer une commande pour un ensemble prédéfini de produits.</span><span class="sxs-lookup"><span data-stu-id="89d64-105">The purchase order will be used to create an order for a pre-defined set of products.</span></span> <span data-ttu-id="89d64-106">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="89d64-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-product-package"></a><span data-ttu-id="89d64-107">Créer un ensemble de produits</span><span class="sxs-lookup"><span data-stu-id="89d64-107">Create a product package</span></span>
1. <span data-ttu-id="89d64-108">Accédez à Commerce et vente au détail > Gestion des stocks > Réapprovisionnement > Ensembles de produits.</span><span class="sxs-lookup"><span data-stu-id="89d64-108">Go to Retail and Commerce > Inventory management > Replenishment > Product packages.</span></span>
2. <span data-ttu-id="89d64-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="89d64-109">Click New.</span></span>
3. <span data-ttu-id="89d64-110">Dans le champ Numéro d'ensemble, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="89d64-110">In the Package number field, type a value.</span></span>
4. <span data-ttu-id="89d64-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="89d64-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="89d64-112">Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="89d64-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="89d64-113">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89d64-113">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="89d64-114">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="89d64-114">Click Add.</span></span>
8. <span data-ttu-id="89d64-115">Dans le champ Numéro d'article, tapez « 0160 ».</span><span class="sxs-lookup"><span data-stu-id="89d64-115">In the Item number field, type '0160'.</span></span>
9. <span data-ttu-id="89d64-116">Dans le champ Taille, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="89d64-116">In the Size field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="89d64-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89d64-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="89d64-118">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="89d64-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="89d64-119">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="89d64-119">Click Add.</span></span>
13. <span data-ttu-id="89d64-120">Dans le champ Numéro d'article, tapez « 0160 ».</span><span class="sxs-lookup"><span data-stu-id="89d64-120">In the Item number field, type '0160'.</span></span>
14. <span data-ttu-id="89d64-121">Dans le champ Numéro de variante, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="89d64-121">In the Variant number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="89d64-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89d64-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="89d64-123">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="89d64-123">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="89d64-124">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="89d64-124">Click Add.</span></span>
18. <span data-ttu-id="89d64-125">Dans le champ Numéro d'article, tapez « 0175 ».</span><span class="sxs-lookup"><span data-stu-id="89d64-125">In the Item number field, type '0175'.</span></span>
19. <span data-ttu-id="89d64-126">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="89d64-126">In the Quantity field, enter a number.</span></span>
20. <span data-ttu-id="89d64-127">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="89d64-127">Click Save.</span></span>
21. <span data-ttu-id="89d64-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="89d64-128">Close the page.</span></span>

## <a name="add-package-to-purchase-order"></a><span data-ttu-id="89d64-129">Ajouter un ensemble à une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="89d64-129">Add package to purchase order</span></span>
1. <span data-ttu-id="89d64-130">Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="89d64-130">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="89d64-131">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="89d64-131">Click New.</span></span>
3. <span data-ttu-id="89d64-132">Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="89d64-132">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="89d64-133">Dans la liste, sélectionnez le même fournisseur pour lequel l'ensemble de produits a été précédemment créé, si un fournisseur a été sélectionné.</span><span class="sxs-lookup"><span data-stu-id="89d64-133">In the list, select the same vendor that the product package was previously created for, if a vendor was selected.</span></span>
5. <span data-ttu-id="89d64-134">Activez ou désactivez l'extension de la section Général.</span><span class="sxs-lookup"><span data-stu-id="89d64-134">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="89d64-135">Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="89d64-135">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="89d64-136">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89d64-136">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="89d64-137">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="89d64-137">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="89d64-138">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89d64-138">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="89d64-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="89d64-139">Click OK.</span></span>
11. <span data-ttu-id="89d64-140">Activez ou désactivez l'extension de la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="89d64-140">Toggle the expansion of the Line details section.</span></span>
12. <span data-ttu-id="89d64-141">Cliquez sur l'onglet Ensembles de produits.</span><span class="sxs-lookup"><span data-stu-id="89d64-141">Click the Product packages tab.</span></span>
13. <span data-ttu-id="89d64-142">Cliquez sur Ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="89d64-142">Click Purchase order line.</span></span>
14. <span data-ttu-id="89d64-143">Cliquez sur Créer des lignes à partir de l'ensemble.</span><span class="sxs-lookup"><span data-stu-id="89d64-143">Click Create lines from package.</span></span>
15. <span data-ttu-id="89d64-144">Dans la liste, recherchez et sélectionnez l'ensemble de produits créé à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="89d64-144">In the list, find and select the product package created in previous step.</span></span>
16. <span data-ttu-id="89d64-145">Entrez un numéro dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="89d64-145">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="89d64-146">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="89d64-146">Click Create.</span></span>
18. <span data-ttu-id="89d64-147">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="89d64-147">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]