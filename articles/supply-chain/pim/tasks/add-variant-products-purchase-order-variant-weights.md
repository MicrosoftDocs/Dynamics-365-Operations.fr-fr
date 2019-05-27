---
title: Ajouter des variantes de produits à des commandes fournisseur à l'aide des poids des variantes
description: Cette procédure vous guide au long des étapes permettant d'utiliser les poids des variantes pour renseigner automatiquement des lignes de commande fournisseur pour chaque variante d'un produit.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 446260a09bd5177877637ac8a288ad584dfa2b2b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568694"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a><span data-ttu-id="474af-103">Ajouter des variantes de produits à des commandes fournisseur à l'aide des poids des variantes</span><span class="sxs-lookup"><span data-stu-id="474af-103">Add variant products to purchase orders using variant weights</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="474af-104">Cette procédure vous guide au long des étapes permettant d'utiliser les poids des variantes pour renseigner automatiquement des lignes de commande fournisseur pour chaque variante d'un produit.</span><span class="sxs-lookup"><span data-stu-id="474af-104">This procedure walks through the steps for using variant weights to auto populate purchase order lines for each variant of a product.</span></span> <span data-ttu-id="474af-105">Lorsque vous sélectionné la quantité du produit que vous souhaitez acheter, des lignes de commande fournisseur sont créées pour toutes les variantes de produit, avec des quantités suggérées selon les poids configurés dans les variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="474af-105">When you select the quantity of the product you want to purchase, purchase order lines are created for all the variants of the product with suggested quantities based on the weights configured on the product variants.</span></span> <span data-ttu-id="474af-106">Cette procédure n'inclut pas les étapes permettant de configurer les valeurs des poids sur les dimensions de produit et les variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="474af-106">This procedure doesn’t include steps to configure weight values on product dimensions and product variants.</span></span> <span data-ttu-id="474af-107">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="474af-107">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="474af-108">Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="474af-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="474af-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="474af-109">Click New.</span></span>
3. <span data-ttu-id="474af-110">Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="474af-110">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="474af-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="474af-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="474af-112">Activez ou désactivez l'extension de la section Général.</span><span class="sxs-lookup"><span data-stu-id="474af-112">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="474af-113">Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="474af-113">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="474af-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="474af-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="474af-115">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="474af-115">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="474af-116">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="474af-116">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="474af-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="474af-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="474af-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="474af-118">Click OK.</span></span>
12. <span data-ttu-id="474af-119">Activez ou désactivez l'extension de la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="474af-119">Toggle the expansion of the Line details section.</span></span>
13. <span data-ttu-id="474af-120">Cliquez sur l'onglet Variantes.</span><span class="sxs-lookup"><span data-stu-id="474af-120">Click the Variants tab.</span></span>
14. <span data-ttu-id="474af-121">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="474af-121">Click Add line.</span></span>
15. <span data-ttu-id="474af-122">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="474af-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="474af-123">Dans le champ Numéro d'article, tapez « 0140 ».</span><span class="sxs-lookup"><span data-stu-id="474af-123">In the Item number field, type '0140'.</span></span>
17. <span data-ttu-id="474af-124">Définir la Quantité sur « 1000 ».</span><span class="sxs-lookup"><span data-stu-id="474af-124">Set Quantity to '1000'.</span></span>
18. <span data-ttu-id="474af-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="474af-125">Click Save.</span></span>

