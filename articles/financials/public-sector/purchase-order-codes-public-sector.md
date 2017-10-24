---
title: Codes de commande fournisseur dans le secteur public
description: "Cet article fournit des informations sur les codes et les messages spéciaux pouvant être utilisés lors de la confirmation des commandes fournisseur. Une commande fournisseur de confirmation contourne le processus d'achat habituel."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ConfirmingPOCodes, PurchTableListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 27291
ms.assetid: 65032886-4dc6-4411-98c8-8969287fd7df
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a153b113f198b7bc5b56353a0bfe82ca2fdd7540
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="purchase-order-codes-in-the-public-sector"></a><span data-ttu-id="e7fef-104">Codes de commande fournisseur dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="e7fef-104">Purchase order codes in the public sector</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e7fef-105">Cet article fournit des informations sur les codes et les messages spéciaux pouvant être utilisés lors de la confirmation des commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e7fef-105">This article provides information about the codes and special messages that can be used with confirming purchase orders.</span></span> <span data-ttu-id="e7fef-106">Une commande fournisseur de confirmation contourne le processus d'achat habituel.</span><span class="sxs-lookup"><span data-stu-id="e7fef-106">A confirming purchase order bypasses the typical purchasing process.</span></span>

<span data-ttu-id="e7fef-107">Cet article décrit la fonctionnalité de codes de commande fournisseur disponible pour le secteur public.</span><span class="sxs-lookup"><span data-stu-id="e7fef-107">This article describes the purchase order codes functionality available for the public sector.</span></span> <span data-ttu-id="e7fef-108">Vous devez commencer par déterminer vos codes et messages.</span><span class="sxs-lookup"><span data-stu-id="e7fef-108">You must first determine what your codes and messages will be.</span></span> <span data-ttu-id="e7fef-109">La page **Codes commande fournisseur de confirmation** permet de créer des codes et les messages spéciaux que vous pouvez utiliser avec les commandes fournisseur de confirmation.</span><span class="sxs-lookup"><span data-stu-id="e7fef-109">You can use the **Confirming PO codes** page to create codes and special messages that can be used with confirming purchase orders (POs).</span></span> <span data-ttu-id="e7fef-110">Une commande fournisseur de confirmation contourne le processus d'achat habituel.</span><span class="sxs-lookup"><span data-stu-id="e7fef-110">A confirming purchase order bypasses the typical purchasing process.</span></span> <span data-ttu-id="e7fef-111">Par exemple, vous devez autoriser une commande non planifiée par l'intermédiaire d'un numéro de commande fournisseur au moment d'un achat, plutôt que via un document qui est fourni avant que l'article soit requis.</span><span class="sxs-lookup"><span data-stu-id="e7fef-111">For example, you must authorize an unplanned order by using a PO number at the time of a purchase, instead of by using a document that is provided before the item is required.</span></span> 

<span data-ttu-id="e7fef-112">Après avoir paramétré les codes, vous pouvez les affecter aux commandes fournisseur sur la page **Toutes les commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="e7fef-112">After you set up the codes, you can assign the codes to purchase orders on the **All purchase orders** page.</span></span> 

<span data-ttu-id="e7fef-113">Si vous affectez un code commande fournisseur de confirmation à une commande fournisseur dans l'organisateur **Achats non planifiés** (par exemple, lorsque vous créez une commande fournisseur), le message associé à ce code est imprimé dans la partie supérieure de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e7fef-113">If you assign a confirming PO code to a purchase order on the **Unplanned purchases** FastTab (for example, when you create a new purchase order), the message that is associated with the confirming PO code will be printed at the top of the purchase order.</span></span>

## <a name="tips"></a><span data-ttu-id="e7fef-114">Conseils</span><span class="sxs-lookup"><span data-stu-id="e7fef-114">Tips</span></span>
-   <span data-ttu-id="e7fef-115">Si vous modifiez un code commande fournisseur de confirmation déjà affecté à une commande fournisseur, le nouveau code remplace l'ancien.</span><span class="sxs-lookup"><span data-stu-id="e7fef-115">If you change a confirming PO code that was already assigned to a purchase order, the new code will replace the old code.</span></span> <span data-ttu-id="e7fef-116">Cette modification affecte à la fois les nouvelles commandes fournisseur et les commandes fournisseur qui ont été validées.</span><span class="sxs-lookup"><span data-stu-id="e7fef-116">This change affects both new purchase orders and purchase orders that have been posted.</span></span> <span data-ttu-id="e7fef-117">Par exemple, une commande fournisseur avait un code de confirmation de commande fournisseur **Confirmation** lorsqu'elle a été validée, mais ce code a été modifié ultérieurement pour devenir **Urgence**.</span><span class="sxs-lookup"><span data-stu-id="e7fef-117">For example, a purchase order had a confirming PO code of **Confirming** when it was posted, but that code is later changed to **Emergency**.</span></span> <span data-ttu-id="e7fef-118">Dans ce cas, chaque commande fournisseur dotée du code **Confirmation**sera désormais dotée du code **Urgence**.</span><span class="sxs-lookup"><span data-stu-id="e7fef-118">In this case, every purchase order that had the **Confirming** code will now have the **Emergency** code instead.</span></span>
-   <span data-ttu-id="e7fef-119">Vous pouvez créer des messages dans différentes langues.</span><span class="sxs-lookup"><span data-stu-id="e7fef-119">You can create messages in different languages.</span></span> <span data-ttu-id="e7fef-120">Cette fonctionnalité s'avère utile lorsque vous effectuez des achats auprès de fournisseurs implantés dans d'autres pays ou régions.</span><span class="sxs-lookup"><span data-stu-id="e7fef-120">This feature is helpful when you are purchasing from merchants in other countries or regions.</span></span> <span data-ttu-id="e7fef-121">Par exemple, votre organisation est implantée dans un pays ou une région anglophone et vous souhaitez créer un message en espagnol pour les commandes fournisseur de confirmation ayant **Confirmation** pour code de commande fournisseur de confirmation.</span><span class="sxs-lookup"><span data-stu-id="e7fef-121">For example, your organization is located in an English-speaking country or region, and you want to create a Spanish message for confirming purchase orders that have a confirming PO code **Confirming**.</span></span>

 




