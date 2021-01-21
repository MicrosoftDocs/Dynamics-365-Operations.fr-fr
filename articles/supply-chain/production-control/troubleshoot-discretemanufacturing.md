---
title: Résoudre le problème de fabrication discrète
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation de la fabrication discrète.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 604e0c3406b15d885991fcb067e93ef83533e3b0
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516780"
---
# <a name="troubleshoot-discrete-manufacturing"></a><span data-ttu-id="f37a3-103">Résoudre le problème de fabrication discrète</span><span class="sxs-lookup"><span data-stu-id="f37a3-103">Troubleshoot discrete manufacturing</span></span>

<span data-ttu-id="f37a3-104">Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation de la fabrication discrète.</span><span class="sxs-lookup"><span data-stu-id="f37a3-104">This topic describes how to fix issues that you might encounter while you work with discrete manufacturing.</span></span>

## <a name="i-receive-the-following-error-message-warehouse-management-processes-are-currently-being-used-if-work-lines-are-not-yet-registered-you-can-cancel-the-created-work-and-any-load-or-shipment-lines-and-then-continue-with-the-picking-or-shipping-process"></a><span data-ttu-id="f37a3-105">Je reçois le message d'erreur suivant : « Les processus de gestion d'entrepôt sont actuellement utilisés.</span><span class="sxs-lookup"><span data-stu-id="f37a3-105">I receive the following error message: "Warehouse management processes are currently being used.</span></span> <span data-ttu-id="f37a3-106">Si les lignes de travail ne sont pas encore enregistrées, vous pouvez annuler le travail créé et toutes les lignes de chargement ou d'expédition, puis poursuivre le processus de retrait ou d'expédition. »</span><span class="sxs-lookup"><span data-stu-id="f37a3-106">If work lines are not yet registered, you can cancel the created work and any load or shipment lines, and then continue with the picking or shipping process."</span></span>

### <a name="issue-description"></a><span data-ttu-id="f37a3-107">Description du problème</span><span class="sxs-lookup"><span data-stu-id="f37a3-107">Issue description</span></span>

<span data-ttu-id="f37a3-108">Ce problème se produit si vous essayez de réserver ou de libérer du travail pour une ligne, mais que la transaction de stock a un statut de *Retiré*, ce qui indique que le matériel a été retiré.</span><span class="sxs-lookup"><span data-stu-id="f37a3-108">This issue occurs if you try to reserve or release work for a line, but the inventory transaction has a status of *Picked*, which indicates that the material has been picked.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f37a3-109">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="f37a3-109">Issue resolution</span></span>

<span data-ttu-id="f37a3-110">Pour régler ce problème, exécutez l'une des étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f37a3-110">To fix this issue, follow one of these steps.</span></span>

- <span data-ttu-id="f37a3-111">Redéfinissez le statut de l'ordre de fabrication sur *Estimé* ou *Libéré*.</span><span class="sxs-lookup"><span data-stu-id="f37a3-111">Change the status of the production order back to *Estimated* or *Released*.</span></span>
- <span data-ttu-id="f37a3-112">Ouvrez la page de détails de la l'ordre de fabrication concerné.</span><span class="sxs-lookup"><span data-stu-id="f37a3-112">Open the details page for the relevant production order.</span></span> <span data-ttu-id="f37a3-113">Dans le volet Actions, sur l'onglet **Entrepôt**, dans le groupe **Arrêt**, sélectionnez **Arrêter et annuler le retrait** pour annuler el retrait de toutes les transactions retirées.</span><span class="sxs-lookup"><span data-stu-id="f37a3-113">On the Action Pane, on the **Warehouse** tab, in the **Stop** group, select **Stop and unpick** to unpick all picked transactions.</span></span> <span data-ttu-id="f37a3-114">Puis sélectionnez **Supprimer l'arrêt** pour traiter l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="f37a3-114">Then select **Remove stop** to process the production order.</span></span>

<span data-ttu-id="f37a3-115">Voici une explication des fonctions *Annuler le retrait* et *Arrêter* :</span><span class="sxs-lookup"><span data-stu-id="f37a3-115">Here is an explanation of the *Unpick* and *Stop* functions:</span></span>

- <span data-ttu-id="f37a3-116">**Annuler le retrait** – Cette fonction inverse le statut des mouvements de stock pour les lignes de nomenclature (BOM) et les lignes de formule qui ont un statut de *Retiré* par le biais de *En commande*.</span><span class="sxs-lookup"><span data-stu-id="f37a3-116">**Unpick** – This function reverses the status of inventory transactions for bill of materials (BOM) lines and formula lines that have a status from *Picked* through *On order*.</span></span> <span data-ttu-id="f37a3-117">Lorsque le travail de prélèvement des matières premières est terminé, le statut des lignes est défini sur *Retiré*.</span><span class="sxs-lookup"><span data-stu-id="f37a3-117">When work for raw material picking is completed, the status of the lines is set to *Picked*.</span></span> <span data-ttu-id="f37a3-118">Ce statut empêche la remise à zéro de l'ordre de fabrication sur le statut *Créé*.</span><span class="sxs-lookup"><span data-stu-id="f37a3-118">This status prevents the production order from being reset to *Created* status.</span></span> <span data-ttu-id="f37a3-119">Dans ce cas, vous pouvez utiliser la fonction *Annuler le retrait* pour annuler les transactions du statut *Retiré*, puis réinitialisez l'ordre de fabrication sur le statut *Créé*.</span><span class="sxs-lookup"><span data-stu-id="f37a3-119">In this case, you can use the *Unpick* function to revert the transactions from *Picked* status and then reset the production order to *Created* status.</span></span>
- <span data-ttu-id="f37a3-120">**Arrêter** – Cette fonction définit un indicateur **Arrêté** sur l'ordre de fabrication pour empêcher toute mise à jour du statut de la commande.</span><span class="sxs-lookup"><span data-stu-id="f37a3-120">**Stop** – This function sets a **Stopped** flag on the production order to prevent any status update on the order.</span></span> <span data-ttu-id="f37a3-121">Vous pouvez trouver l'indicateur **Arrêté** sur le raccourci **Entrepôt** de la page de détails de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="f37a3-121">You can find the **Stopped** flag on the **Warehouse** FastTab of the production order details page.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f37a3-122">Les boutons ne sont visibles que lorsque l'ordre de fabrication est créé pour les articles activés pour les processus d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="f37a3-122">The buttons are visible only when the production order is created for items that are enabled for warehouse processes.</span></span>
> - <span data-ttu-id="f37a3-123">Le groupe **Arrêter** est visible uniquement sur l'onglet **Entrepôt** du volet Actions de la page des détails de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="f37a3-123">The **Stop** group is visible only on the **Warehouse** tab on the Action Pane of the production order details page.</span></span> <span data-ttu-id="f37a3-124">Ce n'est pas visible sur le raccourci **Entrepôt** de la page de liste **Ordres de fabrication**.</span><span class="sxs-lookup"><span data-stu-id="f37a3-124">It isn't visible on the **Warehouse** FastTab of the **Production orders** list page.</span></span>

## <a name="the-matching-resource-name-isnt-updated-after-i-change-a-worker-name-in-the-global-address-book"></a><span data-ttu-id="f37a3-125">Le nom de ressource correspondant n'est pas mis à jour une fois que j'ai modifié le nom d'un collaborateur dans le carnet d'adresses global.</span><span class="sxs-lookup"><span data-stu-id="f37a3-125">The matching resource name isn't updated after I change a worker name in the global address book.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f37a3-126">Description du problème</span><span class="sxs-lookup"><span data-stu-id="f37a3-126">Issue description</span></span>

<span data-ttu-id="f37a3-127">Si vous modifiez le nom d'un collaborateur dans le carnet d'adresses global, le nom de la ressource correspondante n'est pas mis à jour dans le générique du groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="f37a3-127">If you change a worker name in the global address book, the matching resource name isn't updated in the resource group master.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f37a3-128">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="f37a3-128">Issue resolution</span></span>

<span data-ttu-id="f37a3-129">Ce scénario n'est pas actuellement prise en charge.</span><span class="sxs-lookup"><span data-stu-id="f37a3-129">This scenario isn't currently supported.</span></span> <span data-ttu-id="f37a3-130">Pour résoudre le problème, vous devez mettre à jour manuellement le nom de la ressource.</span><span class="sxs-lookup"><span data-stu-id="f37a3-130">To fix the issue, you must manually update the resource name.</span></span>

## <a name="when-i-create-a-new-production-order-i-dont-receive-the-following-message-insert-the-active-version-of-bill-of-material-and-route"></a><span data-ttu-id="f37a3-131">Lorsque je crée un ordre de fabrication, je ne reçois pas le message suivant : « Insérer la version active de la nomenclature et de la gamme ? »</span><span class="sxs-lookup"><span data-stu-id="f37a3-131">When I create a new production order, I don't receive the following message: "Insert the active version of bill of material and route?"</span></span>

### <a name="issue-description"></a><span data-ttu-id="f37a3-132">Description du problème</span><span class="sxs-lookup"><span data-stu-id="f37a3-132">Issue description</span></span>

<span data-ttu-id="f37a3-133">Lorsque vous créez un ordre de fabrication, après avoir saisi le numéro d'article, les champs **Site** et **Entrepôt** sont automatiquement définis sur le site et l'entrepôt par défaut défini sur la page **Paramètres de commande par défaut** pour l'article de produits finis.</span><span class="sxs-lookup"><span data-stu-id="f37a3-133">When you create a new production order, after you enter the item number, the **Site** and **Warehouse** fields are automatically set to the default site and warehouse that are defined on the **Default order settings** page for the finished goods item.</span></span> <span data-ttu-id="f37a3-134">De plus, le numéro de nomenclature et le numéro de gamme actifs sont automatiquement saisis.</span><span class="sxs-lookup"><span data-stu-id="f37a3-134">Additionally, the active BOM number and route number are automatically entered.</span></span> <span data-ttu-id="f37a3-135">Vous ne recevez pas le message suivant qui vous invite à saisir ces valeurs :</span><span class="sxs-lookup"><span data-stu-id="f37a3-135">You don't receive the following message that prompts you for those values:</span></span>

> <span data-ttu-id="f37a3-136">Insérer la version active pour la nomenclature et la gamme ?</span><span class="sxs-lookup"><span data-stu-id="f37a3-136">Insert active version for bill of material and route?</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f37a3-137">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="f37a3-137">Issue resolution</span></span>

<span data-ttu-id="f37a3-138">Vous n'êtes pas invité à insérer des numéros de nomenclature et de gamme si vous sélectionnez un produit pour lequel un site et un entrepôt sont définis sur la page **Paramètres de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="f37a3-138">You aren't prompted to insert BOM and route numbers if you select a product that a site and warehouse are defined for on the **Default order settings** page.</span></span> <span data-ttu-id="f37a3-139">Vous êtes invité uniquement si ces valeurs ne sont pas définies pour le produit sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f37a3-139">You're prompted only if those values aren't defined for the selected product.</span></span>

## <a name="production-orders-arent-shown-on-the-marking-page"></a><span data-ttu-id="f37a3-140">Les ordres de fabrication ne sont pas affichés sur la page de marquage.</span><span class="sxs-lookup"><span data-stu-id="f37a3-140">Production orders aren't shown on the Marking page.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f37a3-141">Description du problème</span><span class="sxs-lookup"><span data-stu-id="f37a3-141">Issue description</span></span>

<span data-ttu-id="f37a3-142">Certains ordres de fabrication ne sont pas affichés sur la page de **marquage**.</span><span class="sxs-lookup"><span data-stu-id="f37a3-142">Some production orders aren't shown on the **Marking** page.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f37a3-143">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="f37a3-143">Issue resolution</span></span>

<span data-ttu-id="f37a3-144">Les produits qui ont la configuration suivante ne sont pas disponibles pour le marquage.</span><span class="sxs-lookup"><span data-stu-id="f37a3-144">Products that have the following configuration aren't available for marking.</span></span> <span data-ttu-id="f37a3-145">Par conséquent, ils ne seront pas affichés sur la page de **marquage** :</span><span class="sxs-lookup"><span data-stu-id="f37a3-145">Therefore, they won't be shown on the **Marking** page:</span></span>

- <span data-ttu-id="f37a3-146">Les produits sont définis comme des produits du type *Poids variable*.</span><span class="sxs-lookup"><span data-stu-id="f37a3-146">The products are defined as products of the *catch weight* type.</span></span>
- <span data-ttu-id="f37a3-147">Ils sont activés pour les processus d'entrepôt avancés.</span><span class="sxs-lookup"><span data-stu-id="f37a3-147">They are enabled for the advanced warehouse processes.</span></span>
- <span data-ttu-id="f37a3-148">Ils sont configurés pour être contrôlés par le principe *Coût standard*.</span><span class="sxs-lookup"><span data-stu-id="f37a3-148">They are configured to be controlled by the *Standard cost* principle.</span></span>

## <a name="when-i-try-to-end-a-production-order-i-receive-the-following-error-message-calculating-bom-consumptioncost-value-must-be-negative-upon-issue-from-inventory"></a><span data-ttu-id="f37a3-149">Lorsque j'essaie de mettre fin à un ordre de fabrication, je reçois le message d'erreur suivant : « Le calcul de la valeur de consommation de la nomenclature doit être négatif lors de la sortie du stock. »</span><span class="sxs-lookup"><span data-stu-id="f37a3-149">When I try to end a production order, I receive the following error message: "Calculating BOM consumptionCost value must be negative upon issue from inventory."</span></span>

<span data-ttu-id="f37a3-150">Ce problème a été résolu dans la version 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="f37a3-150">This issue was fixed in release 10.0.15.</span></span>

## <a name="when-the-status-of-a-production-order-is-changed-from-reported-as-finished-to-end-i-receive-the-following-error-messages-update-conflict-the-standard-cost-does-not-match-with-the-financial-inventory-value-after-the-update-and-a-critical-error-has-occurred-in-function-inventcostmovementcheckvariance"></a><span data-ttu-id="f37a3-151">Lorsque le statut d'un ordre de fabrication passe de Signalé comme terminé à Fin, je reçois les messages d'erreur suivants : « Conflit de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="f37a3-151">When the status of a production order is changed from Reported as finished to End, I receive the following error messages: "Update conflict.</span></span> <span data-ttu-id="f37a3-152">Le coût standard ne correspond pas à la valeur de stock financière après la mise à jour » et « Une erreur critique s'est produite dans la fonction InventCostMovement.checkVariance ».</span><span class="sxs-lookup"><span data-stu-id="f37a3-152">The standard cost does not match with the financial inventory value after the update" and "A critical error has occurred in function InventCostMovement.checkVariance."</span></span>

<span data-ttu-id="f37a3-153">Ce problème se produit car les données sous-jacentes ont été modifiées par un autre processus.</span><span class="sxs-lookup"><span data-stu-id="f37a3-153">This issue occurs because the underlying data was changed by another process.</span></span> <span data-ttu-id="f37a3-154">Le processus essaiera de mettre à jour les données jusqu'à cinq fois.</span><span class="sxs-lookup"><span data-stu-id="f37a3-154">The process will try to update the data up to five times.</span></span> <span data-ttu-id="f37a3-155">Si le conflit persiste après cinq tentatives, vous recevrez les messages d'erreur suivants :</span><span class="sxs-lookup"><span data-stu-id="f37a3-155">If the conflict still exists after five attempts, you will receive the following error messages:</span></span>

> <span data-ttu-id="f37a3-156">Conflit de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="f37a3-156">Update conflict.</span></span> <span data-ttu-id="f37a3-157">Le coût standard ne correspond pas à la valeur de stock financière après la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="f37a3-157">The standard cost does not match with the financial inventory value after the update.</span></span>

> <span data-ttu-id="f37a3-158">Une erreur critique s'est produite dans la fonction InventCostMovement.checkVariance.</span><span class="sxs-lookup"><span data-stu-id="f37a3-158">A critical error has occurred in function InventCostMovement.checkVariance.</span></span>

<span data-ttu-id="f37a3-159">Ce comportement est fait exprès.</span><span class="sxs-lookup"><span data-stu-id="f37a3-159">This behavior is by design.</span></span> <span data-ttu-id="f37a3-160">Pour corriger le problème, reprenez le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="f37a3-160">To mitigate the issue, resume the batch job.</span></span> <span data-ttu-id="f37a3-161">Il devrait finir de s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="f37a3-161">It should finish running.</span></span>

<span data-ttu-id="f37a3-162">Si le traitement par lots échoue systématiquement après sa reprise, vérifiez que la précision d'arrondi de la devise par défaut de la comptabilité est conforme à l'arrondi appliqué aux valeurs de la table InventSum.</span><span class="sxs-lookup"><span data-stu-id="f37a3-162">If the batch job consistently fails after you resume it, verify that the rounding precision for the ledger's default currency is compliant with the rounding that is applied to values in the InventSum table.</span></span> <span data-ttu-id="f37a3-163">Si la précision d'arrondi a été remplacée par une valeur non conforme, vous devez probablement la remettre à une valeur conforme.</span><span class="sxs-lookup"><span data-stu-id="f37a3-163">If the rounding precision has been changed to a non-compliant value, you probably must change it back to a compliant value.</span></span> <span data-ttu-id="f37a3-164">Recherchez **ModifiedDateTime**.</span><span class="sxs-lookup"><span data-stu-id="f37a3-164">Look for **ModifiedDateTime**.</span></span> <span data-ttu-id="f37a3-165">Dans ce cas, la valeur indiquera généralement que la précision d'arrondi a été récemment modifiée.</span><span class="sxs-lookup"><span data-stu-id="f37a3-165">In this case, the value will typically show that the rounding precision was recently changed.</span></span>

## <a name="when-i-release-to-a-warehouse-i-receive-the-following-error-message-item-rm-could-not-be-fully-reserved-ensure-that-the-full-quantity-is-available-or-reserve-the-items-manually-if-the-reservation-field-on-the-bom-line-is-set-to-manual-or-started-could-not-release-the-order-to-warehouse-because-some-materials-could-not-be-reserved-however-the-status-is-updated-to-released"></a><span data-ttu-id="f37a3-166">Lorsque je libère dans un entrepôt, je reçois le message d'erreur suivant : « L'article RM n'a pas pu être entièrement réservé.</span><span class="sxs-lookup"><span data-stu-id="f37a3-166">When I release to a warehouse, I receive the following error message: "Item RM could not be fully reserved.</span></span> <span data-ttu-id="f37a3-167">Assurez-vous que la quantité totale est disponible ou réservez les articles manuellement si le champ Réservation de la ligne de nomenclature est défini sur Manuel ou Démarré.</span><span class="sxs-lookup"><span data-stu-id="f37a3-167">Ensure that the full quantity is available, or reserve the items manually if the Reservation field on the BOM line is set to Manual or Started.</span></span> <span data-ttu-id="f37a3-168">Impossible de libérer la commande dans l'entrepôt, car certaines matières premières n'ont pas pu être réservées. »</span><span class="sxs-lookup"><span data-stu-id="f37a3-168">Could not release the order to warehouse because some materials could not be reserved."</span></span> <span data-ttu-id="f37a3-169">Cependant, le statut est mis à jour sur Validé.</span><span class="sxs-lookup"><span data-stu-id="f37a3-169">However, the status is updated to Released.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f37a3-170">Description du problème</span><span class="sxs-lookup"><span data-stu-id="f37a3-170">Issue description</span></span>

<span data-ttu-id="f37a3-171">Si tous les articles de ligne de nomenclature ne sont pas physiquement disponibles lorsqu'un ordre de fabrication est lancé, la stratégie **Libération dans l'entrepôt** est définie sur *Exiger une réservation complète* sur l'ordre de fabrication, vous recevrez le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="f37a3-171">If not all BOM line items are physically available when a production order is released, and the **Release to warehouse** policy is set to *Require full reservation* on the production order, you will receive the following error message:</span></span>

> <span data-ttu-id="f37a3-172">L'article RM n'a pas pu être entièrement réservé.</span><span class="sxs-lookup"><span data-stu-id="f37a3-172">Item RM could not be fully reserved.</span></span> <span data-ttu-id="f37a3-173">Assurez-vous que la quantité totale est disponible ou réservez les articles manuellement si le champ Réservation de la ligne de nomenclature est défini sur Manuel ou Démarré.</span><span class="sxs-lookup"><span data-stu-id="f37a3-173">Ensure that the full quantity is available, or reserve the items manually if the Reservation field on the BOM line is set to Manual or Started.</span></span> <span data-ttu-id="f37a3-174">Impossible de libérer la commande dans l'entrepôt, car certaines matières premières n'ont pas pu être réservées.</span><span class="sxs-lookup"><span data-stu-id="f37a3-174">Could not release the order to warehouse because some materials could not be reserved.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f37a3-175">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="f37a3-175">Issue resolution</span></span>

<span data-ttu-id="f37a3-176">Ce comportement est fait exprès et fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="f37a3-176">This behavior is by design and is working as expected.</span></span>

## <a name="when-i-try-to-end-a-production-order-and-report-as-finished-i-receive-the-following-error-message-total-good-quantity-reported-as-finished-for-the-production-will-be-1-feedback-for-the-last-operation-is-000-in-total"></a><span data-ttu-id="f37a3-177">Lorsque j'essaie de mettre fin à un ordre de fabrication et de signaler que la production est terminée, je reçois le message d'erreur suivant : « La quantité totale correcte rapportée comme terminée pour la production sera %1.</span><span class="sxs-lookup"><span data-stu-id="f37a3-177">When I try to end a production order and report as finished, I receive the following error message: "Total good quantity reported as finished for the production will be %1.</span></span> <span data-ttu-id="f37a3-178">Rétroaction pour la dernière opération de 0,00 au total. »</span><span class="sxs-lookup"><span data-stu-id="f37a3-178">Feedback for the last operation is 0.00 in total."</span></span>

### <a name="issue-description"></a><span data-ttu-id="f37a3-179">Description du problème</span><span class="sxs-lookup"><span data-stu-id="f37a3-179">Issue description</span></span>

<span data-ttu-id="f37a3-180">Lorsque vous essayez de publier un rapport en tant que journal terminé sur un ordre de fabrication, vous recevez le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="f37a3-180">When you try to post a report as finished journal on a production order, you receive the following error message:</span></span>

> <span data-ttu-id="f37a3-181">La quantité correcte totale déclarée terminée en production sera %1.</span><span class="sxs-lookup"><span data-stu-id="f37a3-181">Total good quantity reported as finished for the production will be %1.</span></span> <span data-ttu-id="f37a3-182">Rétroaction pour la dernière opération de 0,00 au total.</span><span class="sxs-lookup"><span data-stu-id="f37a3-182">Feedback for the last operation is 0.00 in total.</span></span>

### <a name="possible-cause"></a><span data-ttu-id="f37a3-183">Raison possible</span><span class="sxs-lookup"><span data-stu-id="f37a3-183">Possible cause</span></span>

<span data-ttu-id="f37a3-184">Ce problème se produit si les quantités enregistrées lors des dernières opérations étaient incorrectes.</span><span class="sxs-lookup"><span data-stu-id="f37a3-184">This issue occurs if the quantities that were posted in the last operations were incorrect.</span></span> <span data-ttu-id="f37a3-185">Par exemple, si la production est lancée, mais que la quantité à démarrer n'est pas allouée, le journal des fiches production sera enregistré sans aucune ligne.</span><span class="sxs-lookup"><span data-stu-id="f37a3-185">For example, if production is started, but the quantity that must be started isn't allocated, the route card journal will be posted without any lines.</span></span> <span data-ttu-id="f37a3-186">Pour confirmer la situation, ouvrez l'ordre de fabrication, puis, dans le volet Actions, sur l'onglet **Afficher**, sélectionnez **Fiche production**.</span><span class="sxs-lookup"><span data-stu-id="f37a3-186">To confirm the situation, open the production order, and then, on the Action Pane, on the **View** tab, select **Route card**.</span></span>

### <a name="workaround"></a><span data-ttu-id="f37a3-187">Solution de contournement</span><span class="sxs-lookup"><span data-stu-id="f37a3-187">Workaround</span></span>

<span data-ttu-id="f37a3-188">Vous pouvez résoudre ce problème en publiant des journaux supplémentaires pour les opérations pour lesquelles les journaux n'ont pas été correctement validés.</span><span class="sxs-lookup"><span data-stu-id="f37a3-188">You can fix this issue by posting additional journals for the operations that the journals weren't correctly posted for.</span></span> <span data-ttu-id="f37a3-189">Redémarrez l'ordre de fabrication et sélectionnez pour valider les journaux supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="f37a3-189">Restart the production order, and select to post the additional journals.</span></span> <span data-ttu-id="f37a3-190">Cette action ne lancera pas l'ordre de fabrication, mais enregistrera les journaux.</span><span class="sxs-lookup"><span data-stu-id="f37a3-190">This action won't start the production order, but it will post the journals.</span></span> <span data-ttu-id="f37a3-191">La fiche production doit alors indiquer les quantités enregistrées et vous devez être en mesure de terminer les ordres de fabrication avec succès.</span><span class="sxs-lookup"><span data-stu-id="f37a3-191">The route card should then show the quantities that were posted, and you should be able to end the production orders successfully.</span></span>

## <a name="can-i-report-a-production-order-as-finished-while-i-report-the-error-quantity-but-not-while-i-report-the-time-or-material-quantity"></a><span data-ttu-id="f37a3-192">Puis-je déclarer un ordre de fabrication comme terminé pendant que je signale la quantité d'erreur, mais pas pendant que je signale le temps ou la quantité de matériel ?</span><span class="sxs-lookup"><span data-stu-id="f37a3-192">Can I report a production order as finished while I report the error quantity, but not while I report the time or material quantity?</span></span>

<span data-ttu-id="f37a3-193">Vous ne pouvez pas signaler la quantité d'erreur sur un ordre de fabrication, sauf si vous déclarez également la quantité correcte.</span><span class="sxs-lookup"><span data-stu-id="f37a3-193">You can't report the error quantity on a production order unless you also report the good quantity.</span></span> <span data-ttu-id="f37a3-194">Ce scénario n'est **pas** pris en charge.</span><span class="sxs-lookup"><span data-stu-id="f37a3-194">This scenario is **not** supported.</span></span> <span data-ttu-id="f37a3-195">La mise à jour de déclarer comme terminé finira par échouer lorsque vous essaierez de mettre fin à l'ordre de fabrication et vous recevrez le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="f37a3-195">The report as finished update will eventually fail when you try to end the production order, and you will receive the following error message:</span></span>

> <span data-ttu-id="f37a3-196">Quantité déclarée terminée manquante.</span><span class="sxs-lookup"><span data-stu-id="f37a3-196">Missing report as finished quantity.</span></span>

## <a name="can-i-trace-the-serial-numbers-of-finished-goods-against-the-serial-numbers-of-consumed-goods"></a><span data-ttu-id="f37a3-197">Puis-je effectuer le suivi des numéros de série des produits finis par rapport aux numéros de série des produits consommés ?</span><span class="sxs-lookup"><span data-stu-id="f37a3-197">Can I trace the serial numbers of finished goods against the serial numbers of consumed goods?</span></span>

<span data-ttu-id="f37a3-198">Vous ne pouvez pas effectuer le suivi des numéros de série des produits finis par rapport aux numéros de série des articles qu'un ordre de fabrication consomme pour fabriquer ces produits finis.</span><span class="sxs-lookup"><span data-stu-id="f37a3-198">You can't trace the serial numbers of finished goods against the serial numbers of material that a production order consumes to make those finished goods.</span></span> <span data-ttu-id="f37a3-199">Ce scénario n'est pas actuellement prise en charge.</span><span class="sxs-lookup"><span data-stu-id="f37a3-199">This scenario isn't currently supported.</span></span> <span data-ttu-id="f37a3-200">La solution consiste à créer des ordres de fabrication pour une quantité de 1.</span><span class="sxs-lookup"><span data-stu-id="f37a3-200">The workaround is to create production orders for a quantity of 1.</span></span>