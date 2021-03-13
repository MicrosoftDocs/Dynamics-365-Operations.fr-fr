---
title: Paramétrage d'une hiérarchie des catégories d'approvisionnement
description: Cette procédure vous indique comment créer de nouveaux nœuds dans une hiérarchie des catégories d'approvisionnement et comment configurer une catégorie d'approvisionnement à utiliser dans processus d'approvisionnement.
author: RichardLuan
manager: tfehr
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eb37b2761708770b82f23cfbed86248d30a59410
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017315"
---
# <a name="set-up-a-procurement-category-hierarchy"></a><span data-ttu-id="9600c-103">Paramétrage d'une hiérarchie des catégories d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="9600c-103">Set up a procurement category hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9600c-104">Cette procédure vous indique comment créer de nouveaux nœuds dans une hiérarchie des catégories d'approvisionnement et comment configurer une catégorie d'approvisionnement à utiliser dans processus d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="9600c-104">This procedure shows you how to create new nodes in a procurement category hierarchy and how to configure a procurement category to be used in a procurement process.</span></span> <span data-ttu-id="9600c-105">Ces tâches sont généralement effectuées par un responsable des achats.</span><span class="sxs-lookup"><span data-stu-id="9600c-105">These tasks would typically be carried out by a Purchasing manager.</span></span> <span data-ttu-id="9600c-106">Avant de démarrer cette procédure, il doit y avoir une hiérarchie de catégories de type Approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="9600c-106">Before you can start this procedure, there must be a category hierarchy of type Procurement.</span></span> <span data-ttu-id="9600c-107">Si vous utilisez une société de données de démonstration, vous pouvez exécuter cette procédure à l'aide de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="9600c-107">If you're using a demo data company, you can run this procedure in the USMF company.</span></span>


## <a name="add-a-new-procurement-category"></a><span data-ttu-id="9600c-108">Ajouter une catégorie d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="9600c-108">Add a new procurement category</span></span>
1. <span data-ttu-id="9600c-109">Accédez au **Volet de navigation > Modules > Approvisionnements > Consignation > Catégories d'approvisionnement**.</span><span class="sxs-lookup"><span data-stu-id="9600c-109">Go to **Navigation pane > Modules > Procurement and sourcing > Consignment > Procurement categories**.</span></span>
2. <span data-ttu-id="9600c-110">Sélectionnez **Modifier la hiérarchie de catégories** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="9600c-110">On the Action Pane, select **Edit category hierarchy**.</span></span> <span data-ttu-id="9600c-111">La hiérarchie des catégories d'approvisionnement actuelle s'affiche à la gauche de la page.</span><span class="sxs-lookup"><span data-stu-id="9600c-111">The current procurement category hierarchy is displayed in the left side of the page.</span></span> <span data-ttu-id="9600c-112">Vous êtes sur le point de modifier la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="9600c-112">You  are about to modify the hierarchy.</span></span>  
3. <span data-ttu-id="9600c-113">Sélectionnez **Nouveau nœud de catégories** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="9600c-113">On the Action Pane, select **New category node**.</span></span> <span data-ttu-id="9600c-114">Le système sélectionne le nœud supérieur par défaut.</span><span class="sxs-lookup"><span data-stu-id="9600c-114">The system selects the top node by default.</span></span> <span data-ttu-id="9600c-115">Si vous exécutez cette procédure en tant que guide des tâches, vous pouvez cliquer sur le bouton Déverrouiller et sélectionner un autre nœud parent dans lequel insérer votre nouveau nœud.</span><span class="sxs-lookup"><span data-stu-id="9600c-115">If you are running this procedure as a task guide, you can click the Unlock button and select another parent node to insert your new node into.</span></span> <span data-ttu-id="9600c-116">Une fois que c'est fait, verrouillez à nouveau le guide de tâches, puis cliquez sur Nouveau nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="9600c-116">Once that is done, lock the task guide again and then click New category node.</span></span>  
4. <span data-ttu-id="9600c-117">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="9600c-117">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="9600c-118">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="9600c-118">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="9600c-119">Dans le champ **Nom convivial**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9600c-119">In the **Friendly name** field, type a value.</span></span> <span data-ttu-id="9600c-120">Le nom convivial est facultatif.</span><span class="sxs-lookup"><span data-stu-id="9600c-120">The friendly name is optional.</span></span> <span data-ttu-id="9600c-121">Il sera affiché dans les recherches de catégories avec le nom de la catégorie.</span><span class="sxs-lookup"><span data-stu-id="9600c-121">It will be displayed in category lookups together with the category name.</span></span>  
7. <span data-ttu-id="9600c-122">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9600c-122">Select **Save**.</span></span>

## <a name="add-products-to-your-new-procurement-category"></a><span data-ttu-id="9600c-123">Ajouter des produits à une nouvelle catégorie d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="9600c-123">Add products to your new procurement category</span></span>
1. <span data-ttu-id="9600c-124">Accédez à **Approvisionnements > Consignation > Catégories d'approvisionnement**.</span><span class="sxs-lookup"><span data-stu-id="9600c-124">Go to **Procurement and sourcing > Consignment > Procurement categories**.</span></span> <span data-ttu-id="9600c-125">Sélectionnez le nœud que vous venez d'ajouter.</span><span class="sxs-lookup"><span data-stu-id="9600c-125">Select the node you just added.</span></span> <span data-ttu-id="9600c-126">Si vous exécutez cette procédure en tant que guide des tâches, vous devrez peut-être déverrouiller le guide des tâches pour sélectionner le nœud.</span><span class="sxs-lookup"><span data-stu-id="9600c-126">If you're running this procedure as a task guide you might need to unlock the task guide to select the node.</span></span>  
2. <span data-ttu-id="9600c-127">Activez ou désactivez l'extension de la section **Produits**.</span><span class="sxs-lookup"><span data-stu-id="9600c-127">Toggle the expansion of the **Products** section.</span></span>
3. <span data-ttu-id="9600c-128">Sélectionnez **Ajouter** pour associer des produits à la catégorie d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="9600c-128">Select **Add** to associate products with the procurement category.</span></span>
4. <span data-ttu-id="9600c-129">Sélectionnez les produits à ajouter à la catégorie d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="9600c-129">Select the products you want to add to the procurement category.</span></span>
5. <span data-ttu-id="9600c-130">Sélectionnez la flèche pour ajouter les produits à la table **Sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="9600c-130">Select the arrow to add the products to the **Selected** table.</span></span>
6. <span data-ttu-id="9600c-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9600c-131">Select **OK**.</span></span>
