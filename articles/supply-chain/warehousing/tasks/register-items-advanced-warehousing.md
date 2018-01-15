--- 
title: "Enregistrer des articles pour un article activé pour l'entreposage avancé à l'aide d'un journal des arrivées d'articles"
description: "Cette procédure décrit la manière dont vous enregistrez des articles à l'aide des journaux d'arrivée des articles lorsque vous utilisez les processus de la gestion avancée des entrepôts."
author: BibiSp
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 050d1fcbc59d9bb3253bfed2433987285423b334
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="3f6b9-103">Enregistrer des articles pour un article activé pour l'entreposage avancé à l'aide d'un journal des arrivées d'articles</span><span class="sxs-lookup"><span data-stu-id="3f6b9-103">Register items for an advanced warehousing enabled item using an item arrival journal</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3f6b9-104">Cette procédure décrit la manière dont vous enregistrez des articles à l'aide des journaux d'arrivée des articles lorsque vous utilisez les processus de la gestion avancée des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-104">This procedure shows you how to register items using the item arrival journal when you are using advanced warehouse management processes.</span></span> <span data-ttu-id="3f6b9-105">Cette opération est généralement effectuée par la personne qui s'occupe de la réception.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-105">This would usually be done by a receiving clerk.</span></span> 

<span data-ttu-id="3f6b9-106">Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-106">You can run this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="3f6b9-107">Vous devez avoir une commande fournisseur confirmée avec une ligne de commande fournisseur en cours avant de lancer ce guide.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-107">You need to have a confirmed purchase order with an open purchase order line before you start this guide.</span></span> <span data-ttu-id="3f6b9-108">L'article de la ligne doit être stocké et il ne doit ni utiliser les variantes de produit ni avoir des dimensions de suivi.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-108">The item on the line must be stocked, and it must not use product variants, and must not have tracking dimensions.</span></span> <span data-ttu-id="3f6b9-109">Et l'article doit être associé à un groupe de dimensions de stockage compatible avec les processus de gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-109">And the item needs to be associated with a warehouse management process enabled storage dimension group.</span></span> <span data-ttu-id="3f6b9-110">L'entrepôt utilisé doit être activé pour les processus de gestion des entrepôts et l'emplacement que vous utilisez pour la réception doit être contrôlé par un contenant.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-110">The warehouse that’s used must be enabled for warehouse management processes and the location that you use for receiving must be license plate controlled.</span></span> <span data-ttu-id="3f6b9-111">Si vous utilisez USMF, vous pouvez utiliser le Compte société 1001, l'entrepôt 51 et l'article M9200 pour créer la CF.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-111">If you’re using USMF, you can use company account 1001, Warehouse 51, and item M9200 to create your PO.</span></span> 

<span data-ttu-id="3f6b9-112">Notez le numéro de la commande fournisseur que vous créez, et notez également le numéro d'article et le site que vous avez utilisé pour la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-112">Make a note of the number of the purchase order that you create, and also note the item number and the site that you used for your purchase order line.</span></span>


## <a name="create-an-item-arrival-journal-header"></a><span data-ttu-id="3f6b9-113">Créer un en-tête du journal des arrivées d'articles</span><span class="sxs-lookup"><span data-stu-id="3f6b9-113">Create an item arrival journal header</span></span>
1. <span data-ttu-id="3f6b9-114">Accédez à Arrivée d'articles.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-114">Go to Item arrival.</span></span>
2. <span data-ttu-id="3f6b9-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-115">Click New.</span></span>
3. <span data-ttu-id="3f6b9-116">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-116">In the Name field, type a value.</span></span>
    * <span data-ttu-id="3f6b9-117">Si vous utilisez USMF, vous pouvez taper WHS.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-117">If you are using USMF, you can type WHS.</span></span> <span data-ttu-id="3f6b9-118">Si vous utilisez d'autres données, le journal dont vous choisissez le nom doit avoir les propriétés suivantes : Vérifier l'emplacement de prélèvement doit être définie sur Non et Gestion des contrôles doit être définie sur Non.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-118">If you’re using other data, the journal whose name you choose has to have the following properties: Check picking location must be set to No, and Quarantine management must be set to No.</span></span>  
4. <span data-ttu-id="3f6b9-119">Tapez une valeur dans le champ Nombre.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-119">In the Number field, type a value.</span></span>
5. <span data-ttu-id="3f6b9-120">Tapez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-120">In the Site field, type a value.</span></span>
    * <span data-ttu-id="3f6b9-121">Sélectionnez le site que vous avez utilisé pour votre ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-121">Select the site that you used for your purchase order line.</span></span> <span data-ttu-id="3f6b9-122">Il servira de valeur par défaut, qui sera la valeur par défaut de toutes les lignes du journal.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-122">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="3f6b9-123">Si vous avez utilisé l'entrepôt 51 dans USMF, choisissez le site 5.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-123">If you used warehouse 51 in USMF, choose site 5.</span></span>  
6. <span data-ttu-id="3f6b9-124">Tapez une valeur dans le champ Entrepôts.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-124">In the Warehouse field, type a value.</span></span>
    * <span data-ttu-id="3f6b9-125">Sélectionnez un entrepôt valide pour le site sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-125">Select a valid warehouse for the site that you’ve selected.</span></span> <span data-ttu-id="3f6b9-126">Il servira de valeur par défaut, qui sera la valeur par défaut de toutes les lignes du journal.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-126">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="3f6b9-127">Si vous utilisez les valeurs d'exemple de USMF, sélectionnez 51.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-127">If you’re using the example values in USMF, select 51.</span></span>  
7. <span data-ttu-id="3f6b9-128">Dans le champ Emplacement, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-128">In the Location field, type a value.</span></span>
    * <span data-ttu-id="3f6b9-129">Sélectionnez un emplacement valide dans l'entrepôt sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-129">Select a valid location in the warehouse that you’ve selected.</span></span> <span data-ttu-id="3f6b9-130">L'emplacement doit être associé à un profil d'emplacement, qui est contrôlé par le contenant.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-130">The location has to be associated with a location profile, which is license plate controlled.</span></span> <span data-ttu-id="3f6b9-131">Il servira de valeur par défaut, qui sera la valeur par défaut de toutes les lignes du journal.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-131">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="3f6b9-132">Si vous utilisez les valeurs d'exemple de USMF, sélectionnez Bulk-008.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-132">If you’re using the example values in USMF, select Bulk-008.</span></span>  
8. <span data-ttu-id="3f6b9-133">Cliquez avec le bouton droit sur la flèche de déroulement dans le champ Contenant, puis sélectionnez Afficher les détails.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-133">Right-click on the drop-down arrow in the License plate field and then select View details.</span></span>
9. <span data-ttu-id="3f6b9-134">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-134">Click New.</span></span>
10. <span data-ttu-id="3f6b9-135">Tapez une valeur dans le champ Contenant.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-135">In the License plate field, type a value.</span></span>
    * <span data-ttu-id="3f6b9-136">Notez la valeur.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-136">Make a note of the value.</span></span>  
11. <span data-ttu-id="3f6b9-137">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-137">Click Save.</span></span>
12. <span data-ttu-id="3f6b9-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-138">Close the page.</span></span>
13. <span data-ttu-id="3f6b9-139">Tapez une valeur dans le champ Contenant.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-139">In the License plate field, type a value.</span></span>
    * <span data-ttu-id="3f6b9-140">Entrez la valeur du conteneur que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-140">Enter the value of the license plate that you just created.</span></span> <span data-ttu-id="3f6b9-141">Il servira de valeur par défaut, qui sera la valeur par défaut de toutes les lignes du journal.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-141">This will serve as a default value, which will default to all lines in the journal.</span></span>  
14. <span data-ttu-id="3f6b9-142">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-142">Click OK.</span></span>

## <a name="add-a-line"></a><span data-ttu-id="3f6b9-143">Ajouter une ligne</span><span class="sxs-lookup"><span data-stu-id="3f6b9-143">Add a line</span></span>
1. <span data-ttu-id="3f6b9-144">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-144">Click Add line.</span></span>
2. <span data-ttu-id="3f6b9-145">Tapez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-145">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="3f6b9-146">Entrez le numéro d'article que vous avez utilisé dans la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-146">Enter the item number that you used on the purchase order line.</span></span>  
3. <span data-ttu-id="3f6b9-147">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-147">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="3f6b9-148">Entrez la quantité que vous souhaitez enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-148">Enter the quantity that you want to register.</span></span>  
    * <span data-ttu-id="3f6b9-149">Le champ Date détermine la date à laquelle la quantité disponible de cet article sera enregistrée dans le stock.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-149">The Date field determines the date on which the on-hand quantity of this item will be registered in the inventory.</span></span>  
    * <span data-ttu-id="3f6b9-150">L'ID de lot sera renseigné par le système s'il peut être identifié de manière unique à partir des informations fournies.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-150">The lot ID will be populated by the system if it can be uniquely identified from the information provided.</span></span> <span data-ttu-id="3f6b9-151">Sinon, vous devrez l'ajouter manuellement.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-151">Otherwise you will have to add this manually.</span></span> <span data-ttu-id="3f6b9-152">Il s'agit d'un champ obligatoire, qui lie cet enregistrement à une ligne spécifique d'un document source.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-152">This is a mandatory field, which links this registration to a specific source document line.</span></span>  

## <a name="complete-the-registration"></a><span data-ttu-id="3f6b9-153">Terminer l'enregistrement</span><span class="sxs-lookup"><span data-stu-id="3f6b9-153">Complete the registration</span></span>
1. <span data-ttu-id="3f6b9-154">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-154">Click Validate.</span></span>
    * <span data-ttu-id="3f6b9-155">Cela vérifie que le journal est prêt à être validé.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-155">This checks that the journal is ready to be posted.</span></span> <span data-ttu-id="3f6b9-156">Si la validation échoue, vous devrez corriger les erreurs avant de pouvoir valider le journal.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-156">If the validation fails you will need to fix the errors before you can post the journal.</span></span>  
2. <span data-ttu-id="3f6b9-157">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-157">Click OK.</span></span>
    * <span data-ttu-id="3f6b9-158">Après avoir cliqué sur OK, vérifiez le message.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-158">After you clicked OK, check the message.</span></span> <span data-ttu-id="3f6b9-159">Il doit y avoir un message indiquant que le journal est OK.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-159">There should be a message saying that the journal is OK.</span></span>  
3. <span data-ttu-id="3f6b9-160">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-160">Click Post.</span></span>
4. <span data-ttu-id="3f6b9-161">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-161">Click OK.</span></span>
    * <span data-ttu-id="3f6b9-162">Après avoir cliqué sur OK, vérifiez la barre des messages.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-162">After you have clicked OK, check the message bar.</span></span> <span data-ttu-id="3f6b9-163">Il doit y avoir un message indiquant que l'opération a réussi.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-163">There should be a message saying that the operation completed.</span></span>  
5. <span data-ttu-id="3f6b9-164">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3f6b9-164">Close the page.</span></span>

