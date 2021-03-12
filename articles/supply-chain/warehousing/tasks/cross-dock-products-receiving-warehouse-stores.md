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
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac93806bc85be92840548e160ddf803e63adbbc4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977186"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a><span data-ttu-id="f5c7b-103">Produits croisés entre l'entrepôt de réception et les magasins</span><span class="sxs-lookup"><span data-stu-id="f5c7b-103">Cross-dock products from receiving warehouse to stores</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f5c7b-104">Cette procédure décrit les étapes pour créer et traiter un cross-docking afin de distribuer les produits depuis l'emplacement de réception d'une commande fournisseur vers un ou plusieurs magasins.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-104">This procedure walks through the steps to create and process a Cross-dock to distribute products from the receiving location of a purchase order to one or many stores.</span></span> <span data-ttu-id="f5c7b-105">L'utilisateur peut définir plusieurs configurations et laisser le système décider de la distribution des produits, ou saisir manuellement l'emplacement de distribution des produits et la quantité distribuée dans chaque magasin.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="f5c7b-106">La procédure n'inclut pas le paramétrage des données pouvant être utilisées dans le cross-docking, telles que les règles de réapprovisionnement, les hiérarchies organisationnelles et les poids des magasins.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-106">The procedure doesn't include setup of data that can be used in the Cross-dock, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="f5c7b-107">La société fictive USRT sert d'exemple dans la procédure.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-107">The procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="f5c7b-108">Allez dans Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-108">Go to All purchase orders.</span></span>
2. <span data-ttu-id="f5c7b-109">Sélectionnez une commande fournisseur dans la liste et cliquez sur le lien pour ouvrir la commande.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-109">Select a purchase order in the list and click the link to open the order.</span></span>
3. <span data-ttu-id="f5c7b-110">Dans le volet Actions, cliquez sur Commerce et vente au détail.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-110">On the Action Pane, click Retail and Commerce.</span></span>
4. <span data-ttu-id="f5c7b-111">Cliquez sur Cross-docking.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-111">Click Cross docking.</span></span>
5. <span data-ttu-id="f5c7b-112">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-112">Click Edit.</span></span>
    * <span data-ttu-id="f5c7b-113">La catégorie peut être utilisée pour filtrer les articles de la section Lignes.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-113">The category can be used to filter the items in the Lines section.</span></span>  
6. <span data-ttu-id="f5c7b-114">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="f5c7b-115">Dans le champ Quantité de cross-docking, entrez une valeur pour spécifier quelle proportion de la quantité achetée du produit sélectionné doit être distribuée.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-115">In the Cross docking quantity field, type a value to specify how much of the quantity being purchased of the selected product should be distributed.</span></span>
8. <span data-ttu-id="f5c7b-116">Dans le champ Quantité de cross-docking supplémentaire, saisissez une valeur pour spécifier les quantités à distribuer pour les produits disponibles achetés.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-116">In the Additional cross docking quantity field, enter a value to specify the quantities to distribute for the available products being purchased</span></span>
9. <span data-ttu-id="f5c7b-117">Dans le champ Distribution, saisissez « Priorité de l'entrepôt ».</span><span class="sxs-lookup"><span data-stu-id="f5c7b-117">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="f5c7b-118">Vous pouvez sélectionner les autres types pour utiliser différentes règles de distribution.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-118">You can select the other types to use different rules for the distribution.</span></span>  
10. <span data-ttu-id="f5c7b-119">Dans le champ Hiérarchie des réapprovisionnements, sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-119">In the Replenishment hierarchy field, select a value.</span></span>
11. <span data-ttu-id="f5c7b-120">Sélectionnez Oui dans le champ Respecter les assortiments.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-120">Select Yes in the Respect assortments field.</span></span>
12. <span data-ttu-id="f5c7b-121">Cliquez sur Calculer les quantités.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-121">Click Calculate quantities.</span></span>
13. <span data-ttu-id="f5c7b-122">Cliquez sur Créer une commande.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-122">Click Create order.</span></span>
14. <span data-ttu-id="f5c7b-123">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="f5c7b-123">Click Yes.</span></span>
15. <span data-ttu-id="f5c7b-124">Dans la liste, recherchez et sélectionnez un entrepôt qui a reçu des produits</span><span class="sxs-lookup"><span data-stu-id="f5c7b-124">In the list, find and select a warehouse that received products</span></span>
16. <span data-ttu-id="f5c7b-125">Cliquez sur Commande pour afficher les commandes créées pour l'entrepôt sélectionné</span><span class="sxs-lookup"><span data-stu-id="f5c7b-125">Click Order to view the orders that got created for the selected warehouse</span></span>

