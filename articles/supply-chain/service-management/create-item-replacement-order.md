---
title: Création d'un ordre de remplacement d'article
description: Les ordres de remplacement d'article sont généralement créés après le retour et l'inspection d'un produit.
author: josaw1
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnReplaceItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e63c175d12cac91648cb57a3f41d1769e81d57af
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830097"
---
# <a name="create-an-item-replacement-order"></a><span data-ttu-id="11973-103">Création d'un ordre de remplacement d'article</span><span class="sxs-lookup"><span data-stu-id="11973-103">Create an item replacement order</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="11973-104">Les ordres de remplacement d'article sont généralement créés après le retour et l'inspection d'un produit.</span><span class="sxs-lookup"><span data-stu-id="11973-104">Item replacement orders are usually created after a product is returned and inspected.</span></span> <span data-ttu-id="11973-105">Cependant, lorsqu'un article doit être remplacé avant d'être renvoyé, ou que l'article d'origine ne sera pas renvoyé, vous pouvez créer un ordre de remplacement d'article immédiatement après avoir créé un ordre de retour.</span><span class="sxs-lookup"><span data-stu-id="11973-105">However, when an item must be replaced before it has been returned, or when the original item will not be returned, you can create an item replacement order immediately after you create a return order.</span></span>

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a><span data-ttu-id="11973-106">Créer un ordre de remplacement après avoir reçu un article retourné</span><span class="sxs-lookup"><span data-stu-id="11973-106">Create a replacement order after you receive an item that is returned</span></span>

1.  <span data-ttu-id="11973-107">Cliquez sur **Ventes et marketing** \> **Commun** \> **Ordres de retour** \> **Tous les ordres de retour**.</span><span class="sxs-lookup"><span data-stu-id="11973-107">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="11973-108">Créez un ordre de retour, ou sélectionnez une commande retournée dans la liste pour ouvrir l'écran **Ordre de retour - Numéro de retour marchandises : %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="11973-108">Create a new return order, or select a returned order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="11973-109">Cliquez sur **Ligne de retour**, puis sélectionnez **Article de remplacement**.</span><span class="sxs-lookup"><span data-stu-id="11973-109">Click **Return line**, and then select **Replacement item**.</span></span>

4.  <span data-ttu-id="11973-110">Sélectionnez l'article qui remplace l'article retourné.</span><span class="sxs-lookup"><span data-stu-id="11973-110">Select the item to replace the returned item with.</span></span> <span data-ttu-id="11973-111">Entrez les caractéristiques de l'article, puis cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="11973-111">Enter the item specifications, and then click **Apply**.</span></span>

5.  <span data-ttu-id="11973-112">Cliquez sur **Bon de livraison** pour générer le bon de livraison de l'ordre de retour.</span><span class="sxs-lookup"><span data-stu-id="11973-112">Click **Packing slip** to generate the packing slip for the return order.</span></span> <span data-ttu-id="11973-113">Une commande client est générée pour l'article de remplacement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="11973-113">A sales order is generated for the replacement item that you selected.</span></span>
    
    <span data-ttu-id="11973-114">Une fois la commande client créée pour l'article de remplacement, les contrats de vente sont automatiquement recherchés et, s'il existe un contrat de vente applicable, il est appliqué à la commande client.</span><span class="sxs-lookup"><span data-stu-id="11973-114">After the sales order is created for the replacement item, sales agreements are automatically searched and if there is an applicable sales agreement, it is applied to the sales order.</span></span>

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a><span data-ttu-id="11973-115">Créer un ordre de remplacement avant de recevoir un article retourné</span><span class="sxs-lookup"><span data-stu-id="11973-115">Create a replacement order before you receive an item that will be returned</span></span>

1.  <span data-ttu-id="11973-116">Cliquez sur **Ventes et marketing** \> **Commun** \> **Ordres de retour** \> **Tous les ordres de retour**.</span><span class="sxs-lookup"><span data-stu-id="11973-116">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="11973-117">Créez un ordre de retour, ou sélectionnez une commande retournée dans la liste pour ouvrir l'écran **Ordre de retour - Numéro de retour marchandises : %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="11973-117">Create a new return order, or select a return order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="11973-118">Cliquez sur **Rechercher une commande client** si vous souhaitez identifier la commande client correspondante à l'article retourné.</span><span class="sxs-lookup"><span data-stu-id="11973-118">Click **Find sales order** if you want to identify the sales order for the returned item.</span></span> <span data-ttu-id="11973-119">Renseignez l'écran **Rechercher une commande client**, puis cliquez sur **OK** pour fermer l'écran et revenir à l'écran **Ordre de retour - Numéro de retour marchandises : %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="11973-119">Complete the **Find sales order** form and then click **OK** to close the form and return to the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="11973-120">La ligne de la commande client pour l'article retourné est copiée dans l'ordre de retour.</span><span class="sxs-lookup"><span data-stu-id="11973-120">The sales order line for the returned item is copied to the return order.</span></span>

4.  <span data-ttu-id="11973-121">Cliquez sur **Ordre de remplacement** pour ouvrir l'écran **Créer une commande client**.</span><span class="sxs-lookup"><span data-stu-id="11973-121">Click **Replacement order** to open the **Create sales order** form.</span></span>

5.  <span data-ttu-id="11973-122">Activez la case à cocher **Copier des lignes d'ordre de retour** pour transférer les détails de l'ordre de retour sélectionné dans l'écran **Numéro de retour marchandises : %1, %2** vers cette commande client.</span><span class="sxs-lookup"><span data-stu-id="11973-122">Select the **Copy return order lines** check box to transfer details from the return order you selected on the **Return order - RMA number: %1, %2** form to this sales order.</span></span>

6.  <span data-ttu-id="11973-123">Entrez ou modifiez les détails, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="11973-123">Enter or modify details, as required.</span></span>
    
    <span data-ttu-id="11973-124">Si vous avez identifié la commande client à l'étape 3, et si la ligne de la commande client pour l'article retourné est liée à un contrat de vente, l'identificateur du contrat de vente applicable pour l'ordre de remplacement d'article est automatiquement affiché dans le champ **ID contrat de vente**.</span><span class="sxs-lookup"><span data-stu-id="11973-124">If you identified the sales order in step 3, and if the sales order line for the returned item is linked to a sales agreement, the identifier of the applicable sales agreement for the item replacement order will be automatically displayed in the **Sales agreement ID** field.</span></span>

7.  <span data-ttu-id="11973-125">Cliquez sur **OK** pour fermer l'écran **Créer une commande client** et ouvrir l'écran **Commande client**, où vous pouvez continuer à entrer des informations pour la commande client.</span><span class="sxs-lookup"><span data-stu-id="11973-125">Click **OK** to close the **Create sales order** form and open the **Sales order** form, where you can continue to enter information for the new sales order.</span></span> <span data-ttu-id="11973-126">Toutes les lignes de l'ordre de retour applicables sont copiées dans la commande client.</span><span class="sxs-lookup"><span data-stu-id="11973-126">Any applicable return order lines will be copied to the new sales order.</span></span> 
    
    <span data-ttu-id="11973-127">Si l'identificateur du contrat de vente est automatiquement affiché dans le champ **ID contrat de vente**, le contrat de vente a été lié à l'en-tête de la commande client pour l'ordre de remplacement d'article.</span><span class="sxs-lookup"><span data-stu-id="11973-127">If the identifier of the sales agreement is automatically displayed in the **Sales agreement ID** field, then the sales agreement has been linked to the sales order header for the item replacement order.</span></span> <span data-ttu-id="11973-128">S'il existe un engagement applicable dans le contrat de vente qui n'a pas été respecté, et la commande client est créée avant que le contrat de vente expire, un lien est établi entre la ligne du contrat de vente et la ligne de la commande client.</span><span class="sxs-lookup"><span data-stu-id="11973-128">If there is an applicable commitment in the sales agreement that has not been fulfilled yet, and the sales order is created before the sales agreement expires, a link is established between the sales agreement line and the sales order line.</span></span> <span data-ttu-id="11973-129">Par conséquent, les informations du contrat de vente, telles que le prix de l'article, sont copiées vers la nouvelle ligne de la commande client.</span><span class="sxs-lookup"><span data-stu-id="11973-129">Therefore, information from the sales agreement, such as item price, is copied to the new sales order line.</span></span> 
  


