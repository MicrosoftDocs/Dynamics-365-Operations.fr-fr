---
title: Suspendre et reprendre une transaction dans le point de vente (PDV)
description: Cette rubrique explique comment les utilisateurs peuvent suspendre des transactions en cours et les reprendre ultérieurement ou sur une autre caisse à l'aide de Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f513e2d857908f2b95d27bf48ff1e826724d7cbf
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022572"
---
# <a name="suspend-and-resume-a-transaction-in-the-point-of-sale-pos"></a><span data-ttu-id="f7419-103">Suspendre et reprendre une transaction dans le point de vente (PDV)</span><span class="sxs-lookup"><span data-stu-id="f7419-103">Suspend and resume a transaction in the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="f7419-104">Les utilisateurs du point de vente (PDV) peuvent suspendre des transactions en cours, puis les reprendre plus tard ou sur une autre caisse.</span><span class="sxs-lookup"><span data-stu-id="f7419-104">Point of sale (POS) users can suspend in-progress transactions, and then resume them later or on a different register.</span></span> <span data-ttu-id="f7419-105">Les transactions sont souvent suspendues pour libérer rapidement une caisse pour une autre tâche sans perdre la progression de la transaction en cours.</span><span class="sxs-lookup"><span data-stu-id="f7419-105">Transactions are often suspended to quickly free up a register for a different task without losing any progress on the current transaction.</span></span> <span data-ttu-id="f7419-106">Par exemple, un employé du magasin commence à traiter la transaction d'un client sur un appareil mobile mais doivent la terminer sur une caisse avec un tiroir-caisse.</span><span class="sxs-lookup"><span data-stu-id="f7419-106">For example, a store associate starts to process a customer's transaction on a mobile device but must complete it on a register that has a cash drawer.</span></span> <span data-ttu-id="f7419-107">Dans ce cas, l'employé du magasin peut suspendre la transaction sur l'appareil mobile, puis la rappeler et la reprendre sur une caisse.</span><span class="sxs-lookup"><span data-stu-id="f7419-107">In this case, the store associate can suspend the transaction on the mobile device, and then recall and resume it on a register.</span></span>

## <a name="configure-suspend-and-resume-functionality"></a><span data-ttu-id="f7419-108">Configurer la fonctionnalité Suspendre et reprendre</span><span class="sxs-lookup"><span data-stu-id="f7419-108">Configure suspend and resume functionality</span></span>

### <a name="pos-operations"></a><span data-ttu-id="f7419-109">Opérations PDV</span><span class="sxs-lookup"><span data-stu-id="f7419-109">POS operations</span></span>

<span data-ttu-id="f7419-110">Deux [Opérations PDV](pos-operations.md) permettent au PDV la prise en charge des scénarios Suspendre et reprendre.</span><span class="sxs-lookup"><span data-stu-id="f7419-110">Two [POS operations](pos-operations.md) let the POS support suspend and resume scenarios.</span></span> <span data-ttu-id="f7419-111">Vous pouvez affecter ces opérations au [groupes de boutons](pos-screen-layouts.md) de la page de transaction ou la page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="f7419-111">You can assign these operations to [button grids](pos-screen-layouts.md) on the transaction page or the welcome page.</span></span>

- <span data-ttu-id="f7419-112">503 : Suspendre une transaction</span><span class="sxs-lookup"><span data-stu-id="f7419-112">503: Suspend transaction</span></span>
- <span data-ttu-id="f7419-113">504 : Rappeler une transaction</span><span class="sxs-lookup"><span data-stu-id="f7419-113">504: Recall transaction</span></span>

### <a name="receipt-template"></a><span data-ttu-id="f7419-114">Modèle de ticket de caisse</span><span class="sxs-lookup"><span data-stu-id="f7419-114">Receipt template</span></span>

<span data-ttu-id="f7419-115">Le PDV peut être configuré pour générer un bordereau imprimé lorsqu'une transaction est suspendue.</span><span class="sxs-lookup"><span data-stu-id="f7419-115">The POS can be configured to generate a printed slip when a transaction is suspended.</span></span> <span data-ttu-id="f7419-116">Ce bordereau peut être utilisé pour identifier rapidement et rappeler la transaction ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="f7419-116">That slip can then be used to quickly identify and recall the transaction later.</span></span>

<span data-ttu-id="f7419-117">Pour permettre au POS d'imprimer un bordereau, vous devez ajouter le format du ticket de caisse **Transaction suspendue** au profil de ticket de caisse du magasin.</span><span class="sxs-lookup"><span data-stu-id="f7419-117">To enable the POS to print a slip, you must add the **Suspended transaction** receipt format to the store's receipt profile.</span></span> <span data-ttu-id="f7419-118">Vous pouvez concevoir le format du ticket de caisse afin qu'il inclue ou exclue des détails spécifiques sur la transaction.</span><span class="sxs-lookup"><span data-stu-id="f7419-118">You can design the receipt format so that it includes or excludes specific details about the transaction.</span></span> <span data-ttu-id="f7419-119">Par exemple, le format peut inclure un code-barres pour prendre en charge la lecture.</span><span class="sxs-lookup"><span data-stu-id="f7419-119">For example, the format can include a barcode to support scanning.</span></span>

### <a name="receipt-numbering"></a><span data-ttu-id="f7419-120">Numérotation des tickets de caisse</span><span class="sxs-lookup"><span data-stu-id="f7419-120">Receipt numbering</span></span>

<span data-ttu-id="f7419-121">Quant aux autres types de transactions de PDV qui génèrent un ticket de caisse imprimé, vous pouvez définir une souche de numéros pour les transactions suspendues dans la section **Numérotation des tickets de caisse** du profil de fonctionnalité du magasin.</span><span class="sxs-lookup"><span data-stu-id="f7419-121">As for other POS transaction types that generate a printed receipt, you can define a number sequence for suspended transactions in the **Receipt numbering** section of the store's functionality profile.</span></span>

### <a name="void-when-closing-shift"></a><span data-ttu-id="f7419-122">Annuler lors de la clôture de l'équipe</span><span class="sxs-lookup"><span data-stu-id="f7419-122">Void when closing shift</span></span>

<span data-ttu-id="f7419-123">Vous pouvez utiliser l'option **Annuler lors de la clôture de l'équipe** pour obliger les utilisateurs à terminer ou à annuler les transactions suspendues avant de clôturer leur équipe.</span><span class="sxs-lookup"><span data-stu-id="f7419-123">You can use the **Void when closing shift** option to require that users either complete or void any suspended transactions before they close their shift.</span></span> <span data-ttu-id="f7419-124">Lors de l'opération **Clôturer l'équipe**, le PDV invite les utilisateurs à afficher ou annuler les transactions suspendues en attente.</span><span class="sxs-lookup"><span data-stu-id="f7419-124">During the **Close shift** operation, the POS will prompt users to either view or void any outstanding suspended transactions.</span></span>

## <a name="suspend-and-resume-a-transaction"></a><span data-ttu-id="f7419-125">Suspendre et reprendre une transaction</span><span class="sxs-lookup"><span data-stu-id="f7419-125">Suspend and resume a transaction</span></span>

### <a name="suspend-a-transaction"></a><span data-ttu-id="f7419-126">Suspendre une transaction</span><span class="sxs-lookup"><span data-stu-id="f7419-126">Suspend a transaction</span></span>

<span data-ttu-id="f7419-127">Les utilisateurs disposant des autorisations nécessaires, et dont la mise en page de l'écran comprend l'opération **Suspendre une transaction**, peuvent suspendre une transaction afin qu'elle soit rappelée plus tard ou sur une autre caisse.</span><span class="sxs-lookup"><span data-stu-id="f7419-127">Users who have sufficient privileges, and who have a screen layout that includes the **Suspend transaction** operation, can suspend a transaction so that it can be recalled later or on a different register.</span></span>

<span data-ttu-id="f7419-128">Les transactions peuvent être suspendues uniquement si elles ne contiennent **pas** les types de lignes suivants :</span><span class="sxs-lookup"><span data-stu-id="f7419-128">Transactions can be suspended only if they do **not** contain the following types of lines:</span></span>

- <span data-ttu-id="f7419-129">Lignes de paiement actives</span><span class="sxs-lookup"><span data-stu-id="f7419-129">Active payment lines</span></span>
- <span data-ttu-id="f7419-130">Lignes de carte cadeau (pour émettre une carte cadeau ou ajouter au solde de la carte cadeau)</span><span class="sxs-lookup"><span data-stu-id="f7419-130">Gift card lines (either to issue a gift card or to add to the gift card balance)</span></span>

<span data-ttu-id="f7419-131">Une transaction suspendue n'affecte pas les informations de vente ou les informations de disponibilité de stock du magasin.</span><span class="sxs-lookup"><span data-stu-id="f7419-131">A suspended transaction doesn't affect sales information or inventory availability information for the store.</span></span>

### <a name="resume-a-suspended-transaction"></a><span data-ttu-id="f7419-132">Reprendre une transaction suspendue</span><span class="sxs-lookup"><span data-stu-id="f7419-132">Resume a suspended transaction</span></span>

<span data-ttu-id="f7419-133">Les transactions suspendues peuvent être rappelées et reprises dans le même magasin par n'importe quel utilisateur disposant d'autorisations nécessaires, et ayant également une mise en page incluant l'opération **Rappeler une transaction**.</span><span class="sxs-lookup"><span data-stu-id="f7419-133">Suspended transactions can be recalled and resumed in the same store by any user who has sufficient privileges, and who also has a layout that includes the **Recall transaction** operation.</span></span>

<span data-ttu-id="f7419-134">Pour rappeler rapidement et facilement une transaction suspendue, lisez le code-barres sur le bordereau imprimé tout en affichant la liste des transactions de l'opération **Rappeler une transaction**.</span><span class="sxs-lookup"><span data-stu-id="f7419-134">To quickly and easily recall a suspended transaction, scan the barcode on the printed slip while you're viewing the list of transactions from the **Recall transaction** operation.</span></span>

### <a name="considerations-for-offline-mode"></a><span data-ttu-id="f7419-135">Considérations relatives au mode hors connexion</span><span class="sxs-lookup"><span data-stu-id="f7419-135">Considerations for offline mode</span></span>

- <span data-ttu-id="f7419-136">Toute transaction suspendue alors que le PDV est en mode en ligne ne peut être reprise en mode hors ligne, car les données ne sont pas synchronisées à la base de données hors ligne.</span><span class="sxs-lookup"><span data-stu-id="f7419-136">Any transaction that is suspended while the POS is in online mode can't be resumed in offline mode, because the data isn't synced to the offline database.</span></span>
- <span data-ttu-id="f7419-137">Si vous suspendez une transaction alors que le PDV est en mode hors ligne, vous pouvez la rappeler en mode hors ligne, à condition que le PDV n'ait pas été basculé vers le mode en ligne entre-temps depuis que vous avez suspendu la transaction.</span><span class="sxs-lookup"><span data-stu-id="f7419-137">If you suspend a transaction while the POS is in offline mode, you can recall it in offline mode, provided that the POS wasn't switched back to online mode at any time since you suspended the transaction.</span></span> <span data-ttu-id="f7419-138">Lorsque le PDV est basculé vers le mode en ligne, les données sur les transactions suspendues sont déplacées vers la base de données en ligne et supprimées de la base de données hors ligne.</span><span class="sxs-lookup"><span data-stu-id="f7419-138">When the POS is switched back to online mode, data about suspended transactions is moved to the online database and removed from the offline database.</span></span> <span data-ttu-id="f7419-139">Par conséquent, les transactions peuvent être reprises uniquement en mode en ligne.</span><span class="sxs-lookup"><span data-stu-id="f7419-139">Therefore, the transactions can be resumed only in online mode.</span></span> <span data-ttu-id="f7419-140">Si vous basculez le PDV vers le mode hors ligne, vous ne pourrez pas reprendre les transaction suspendues, car elles ont déjà été supprimées de la base de données hors ligne.</span><span class="sxs-lookup"><span data-stu-id="f7419-140">If you switch the POS back to offline mode, you won't be able to resume those suspended transaction, because they have already been removed from the offline database.</span></span>

### <a name="void-a-suspended-transaction"></a><span data-ttu-id="f7419-141">Annuler une transaction suspendue</span><span class="sxs-lookup"><span data-stu-id="f7419-141">Void a suspended transaction</span></span>

<span data-ttu-id="f7419-142">Vous pouvez annuler des transactions suspendues en rappelant la transaction puis en effectuant l'opération **Annuler la transaction**, ou en sélectionnant la transaction dans la liste **Rappeler la transaction** et en sélectionnant **Annuler** sur la barre d'application.</span><span class="sxs-lookup"><span data-stu-id="f7419-142">You can void suspended transactions either by recalling the transaction and then performing the **Void transaction** operation, or by selecting the transaction in the **Recall transaction** list and selecting **Void** on the app bar.</span></span> <span data-ttu-id="f7419-143">Sinon, le magasin peut être configuré pour inviter les utilisateurs à annuler les transactions suspendues lorsqu'ils clôturent leur équipe.</span><span class="sxs-lookup"><span data-stu-id="f7419-143">Alternatively, the store can be configured to prompt users to void suspended transactions when they close their shift.</span></span>
