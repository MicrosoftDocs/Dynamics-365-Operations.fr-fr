---
title: "Mettre à jour des bons de livraison pour les retours"
description: "Pour pouvoir recevoir des retours marchandises dans le stock, il faut mettre à jour le bon de livraison relatif à la commande dont les articles font partie."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 7532c5b1debdb498c2d6bab129208a412387c8fa
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="packing-slip-updates-for-returns"></a><span data-ttu-id="ccb24-103">Mettre à jour des bons de livraison pour les retours</span><span class="sxs-lookup"><span data-stu-id="ccb24-103">Packing slip updates for returns</span></span>  

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ccb24-104">Pour pouvoir recevoir des retours marchandises dans le stock, il faut mettre à jour le bon de livraison relatif à la commande dont les articles font partie.</span><span class="sxs-lookup"><span data-stu-id="ccb24-104">Before returned items can be received into inventory, the packing slip for the order to which they belong must be updated.</span></span> <span data-ttu-id="ccb24-105">Toute comme le processus de mise à jour de facture consiste à mettre à jour la transaction financière, le processus de mise à jour de bon de livraison consiste à mettre à jour physiquement l'enregistrement de stock, ce qui signifie qu'il valide les modifications apportées au stock.</span><span class="sxs-lookup"><span data-stu-id="ccb24-105">Just as the invoice update process is the update to the financial transaction, the packing slip update process is the physical update of the inventory record, which means that it commits the changes to inventory.</span></span> <span data-ttu-id="ccb24-106">En cas de retour, les opérations affectées à l'action de disposition sont exécutées durant la mise à jour du bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="ccb24-106">In the case of returns, the steps that are assigned to the disposition action are implemented during the packing slip update.</span></span>

<span data-ttu-id="ccb24-107">Il est possible de traiter la mise à jour du bon de livraison dans le journal des arrivées d'articles ou l'ordre de retour.</span><span class="sxs-lookup"><span data-stu-id="ccb24-107">The packing slip update can be processed in either the item arrival journal or the return order.</span></span>

<span data-ttu-id="ccb24-108">Dans le cadre du traitement de validation des bons de livraison, il est possible d'associer le numéro de référence du bon de livraison figurant sur les documents d'expédition du client aux lignes de commande.</span><span class="sxs-lookup"><span data-stu-id="ccb24-108">As part of the process for posting packing slips, the packing slip reference number from the customer’s shipping documents can be associated with the order lines.</span></span> <span data-ttu-id="ccb24-109">Cette association est purement indicative.</span><span class="sxs-lookup"><span data-stu-id="ccb24-109">This association is optional and for reference only.</span></span> <span data-ttu-id="ccb24-110">Elle n'entraîne pas de mises à jour de transactions.</span><span class="sxs-lookup"><span data-stu-id="ccb24-110">It does not create any transactional updates.</span></span>

<span data-ttu-id="ccb24-111">Si les retours marchandises ne sont pas tous arrivés, incluez uniquement la quantité reçue dans la mise à jour du bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="ccb24-111">If not all of the expected return items have arrived, you should include only the quantity that has been received in the packing slip update.</span></span> <span data-ttu-id="ccb24-112">Laissez les autres articles sur la commande jusqu'à ce que le reste de l'expédition de retour arrive.</span><span class="sxs-lookup"><span data-stu-id="ccb24-112">Leave the remaining items on the order until the rest of the return shipment has arrived.</span></span>

<span data-ttu-id="ccb24-113">Si un article est retourné par le contrôle au département d'expédition et de réception, par exemple, si le contrôleur ne sait pas où placer l'article dans le stock, il convient de mettre à jour le bon de livraison correspondant pour enregistrer et traiter correctement le code disposition spécifié comme résultat du contrôle.</span><span class="sxs-lookup"><span data-stu-id="ccb24-113">If an item is sent back from quarantine to the Shipping and Receiving department, such as when the quarantine inspector does not know where to store the item in inventory, the corresponding packing slip must be updated to correctly register and act on the disposition code that is specified as a result of the quarantine.</span></span>

<span data-ttu-id="ccb24-114">Lorsque vous mettez à jour un bon de livraison pour un article retourné dans le cadre d'un contrat de vente, l'engagement de contrat de vente pour cet article est automatiquement mis à jour pour refléter les modifications de quantité ou de montant.</span><span class="sxs-lookup"><span data-stu-id="ccb24-114">When you update a packing slip for a returned item that is from a sales agreement, the sales agreement commitment for that item is automatically updated to reflect the change in the quantity or the amount.</span></span> 

## <a name="see-also"></a><span data-ttu-id="ccb24-115">Voir également :</span><span class="sxs-lookup"><span data-stu-id="ccb24-115">See also</span></span>

[<span data-ttu-id="ccb24-116">Exécution de mises à jour de factures pour les retours</span><span class="sxs-lookup"><span data-stu-id="ccb24-116">Perform invoice updates for returns</span></span>](perform-invoice-updates-for-returns.md)

  



