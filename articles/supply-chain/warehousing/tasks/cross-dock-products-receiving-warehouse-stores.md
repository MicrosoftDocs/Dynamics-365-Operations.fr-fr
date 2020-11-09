---
title: Produits croisés entre l'entrepôt de réception et les magasins
description: Cette procédure décrit les étapes pour créer et traiter un cross-docking afin de distribuer les produits depuis l'emplacement de réception d'une commande fournisseur vers un ou plusieurs magasins.
author: ShylaThompson
manager: tfehr
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailBuyersPushPerPackage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 033d4f72b626130c144faff30fe0d35349b26c6d
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4015870"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a><span data-ttu-id="5b068-103">Produits croisés entre l'entrepôt de réception et les magasins</span><span class="sxs-lookup"><span data-stu-id="5b068-103">Cross-dock products from receiving warehouse to stores</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5b068-104">Cette procédure décrit les étapes pour créer et traiter un cross-docking afin de distribuer les produits depuis l'emplacement de réception d'une commande fournisseur vers un ou plusieurs magasins.</span><span class="sxs-lookup"><span data-stu-id="5b068-104">This procedure walks through the steps to create and process a Cross-dock to distribute products from the receiving location of a purchase order to one or many stores.</span></span> <span data-ttu-id="5b068-105">L'utilisateur peut définir plusieurs configurations et laisser le système décider de la distribution des produits, ou saisir manuellement l'emplacement de distribution des produits et la quantité distribuée dans chaque magasin.</span><span class="sxs-lookup"><span data-stu-id="5b068-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="5b068-106">La procédure n'inclut pas le paramétrage des données pouvant être utilisées dans le cross-docking, telles que les règles de réapprovisionnement, les hiérarchies organisationnelles et les poids des magasins.</span><span class="sxs-lookup"><span data-stu-id="5b068-106">The procedure doesn't include setup of data that can be used in the Cross-dock, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="5b068-107">La société fictive USRT sert d'exemple dans la procédure.</span><span class="sxs-lookup"><span data-stu-id="5b068-107">The procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="5b068-108">Allez dans Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="5b068-108">Go to All purchase orders.</span></span>
2. <span data-ttu-id="5b068-109">Sélectionnez une commande fournisseur dans la liste et cliquez sur le lien pour ouvrir la commande.</span><span class="sxs-lookup"><span data-stu-id="5b068-109">Select a purchase order in the list and click the link to open the order.</span></span>
3. <span data-ttu-id="5b068-110">Dans le volet Actions, cliquez sur Commerce et vente au détail.</span><span class="sxs-lookup"><span data-stu-id="5b068-110">On the Action Pane, click Retail and Commerce.</span></span>
4. <span data-ttu-id="5b068-111">Cliquez sur Cross-docking.</span><span class="sxs-lookup"><span data-stu-id="5b068-111">Click Cross docking.</span></span>
5. <span data-ttu-id="5b068-112">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="5b068-112">Click Edit.</span></span>
    * <span data-ttu-id="5b068-113">La catégorie peut être utilisée pour filtrer les articles de la section Lignes.</span><span class="sxs-lookup"><span data-stu-id="5b068-113">The category can be used to filter the items in the Lines section.</span></span>  
6. <span data-ttu-id="5b068-114">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="5b068-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="5b068-115">Dans le champ Quantité de cross-docking, entrez une valeur pour spécifier quelle proportion de la quantité achetée du produit sélectionné doit être distribuée.</span><span class="sxs-lookup"><span data-stu-id="5b068-115">In the Cross docking quantity field, type a value to specify how much of the quantity being purchased of the selected product should be distributed.</span></span>
8. <span data-ttu-id="5b068-116">Dans le champ Quantité de cross-docking supplémentaire, saisissez une valeur pour spécifier les quantités à distribuer pour les produits disponibles achetés.</span><span class="sxs-lookup"><span data-stu-id="5b068-116">In the Additional cross docking quantity field, enter a value to specify the quantities to distribute for the available products being purchased</span></span>
9. <span data-ttu-id="5b068-117">Dans le champ Distribution, saisissez « Priorité de l'entrepôt ».</span><span class="sxs-lookup"><span data-stu-id="5b068-117">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="5b068-118">Vous pouvez sélectionner les autres types pour utiliser différentes règles de distribution.</span><span class="sxs-lookup"><span data-stu-id="5b068-118">You can select the other types to use different rules for the distribution.</span></span>  
10. <span data-ttu-id="5b068-119">Dans le champ Hiérarchie des réapprovisionnements, sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5b068-119">In the Replenishment hierarchy field, select a value.</span></span>
11. <span data-ttu-id="5b068-120">Sélectionnez Oui dans le champ Respecter les assortiments.</span><span class="sxs-lookup"><span data-stu-id="5b068-120">Select Yes in the Respect assortments field.</span></span>
12. <span data-ttu-id="5b068-121">Cliquez sur Calculer les quantités.</span><span class="sxs-lookup"><span data-stu-id="5b068-121">Click Calculate quantities.</span></span>
13. <span data-ttu-id="5b068-122">Cliquez sur Créer une commande.</span><span class="sxs-lookup"><span data-stu-id="5b068-122">Click Create order.</span></span>
14. <span data-ttu-id="5b068-123">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="5b068-123">Click Yes.</span></span>
15. <span data-ttu-id="5b068-124">Dans la liste, recherchez et sélectionnez un entrepôt qui a reçu des produits</span><span class="sxs-lookup"><span data-stu-id="5b068-124">In the list, find and select a warehouse that received products</span></span>
16. <span data-ttu-id="5b068-125">Cliquez sur Commande pour afficher les commandes créées pour l'entrepôt sélectionné</span><span class="sxs-lookup"><span data-stu-id="5b068-125">Click Order to view the orders that got created for the selected warehouse</span></span>

