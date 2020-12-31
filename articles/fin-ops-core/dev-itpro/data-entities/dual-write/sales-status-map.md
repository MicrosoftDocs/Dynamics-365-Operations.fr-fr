---
title: Configurer le mappage pour les champs de statut de la commande client
description: Cette rubrique explique comment configurer les champs de statut de la commande client pour la double écriture.
author: dasani-madipalli
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 5855581100606003c1faf6b88a0ab234ae378893
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4452557"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a><span data-ttu-id="bd2f5-103">Configurer le mappage pour les champs de statut de la commande client</span><span class="sxs-lookup"><span data-stu-id="bd2f5-103">Set up the mapping for the sales order status fields</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bd2f5-104">Les champs qui indiquent le statut de la commande client ont des valeurs d’énumération différentes dans Microsoft Dynamics 365 Supply Chain Management et Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-104">The fields that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="bd2f5-105">Une configuration supplémentaire est requise pour mapper ces champs en double écriture.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-105">Additional setup is required to map these fields in dual-write.</span></span>

## <a name="fields-in-supply-chain-management"></a><span data-ttu-id="bd2f5-106">Champs dans Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="bd2f5-106">Fields in Supply Chain Management</span></span>

<span data-ttu-id="bd2f5-107">Dans Supply Chain Management, deux champs reflètent le statut de la commande client.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-107">In Supply Chain Management, two fields reflect the status of the sales order.</span></span> <span data-ttu-id="bd2f5-108">Les champs que vous devez mapper sont **Statut** et **Statut du document**.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-108">The fields that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="bd2f5-109">L’énumération de **Statut** spécifie le statut global de la commande.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="bd2f5-110">Ce statut est indiqué sur l’en-tête de la commande.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-110">This status is shown on the order header.</span></span>

<span data-ttu-id="bd2f5-111">L’énumération de **Statut** a les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="bd2f5-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="bd2f5-112">Commande en cours</span><span class="sxs-lookup"><span data-stu-id="bd2f5-112">Open Order</span></span>
- <span data-ttu-id="bd2f5-113">Livré(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-113">Delivered</span></span>
- <span data-ttu-id="bd2f5-114">Facturé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-114">Invoiced</span></span>
- <span data-ttu-id="bd2f5-115">Annulé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-115">Cancelled</span></span>

<span data-ttu-id="bd2f5-116">L’énumération de **Statut du document** spécifie le document le plus récent généré pour la commande.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="bd2f5-117">Par exemple, si la commande est confirmée, ce document est une confirmation de commande client.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="bd2f5-118">Si une commande client est partiellement facturée et que la ligne restante est confirmée, le statut du document reste **Facture**, car la facture est générée plus tard dans le processus.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice**, because the invoice is generated later in the process.</span></span>

<span data-ttu-id="bd2f5-119">L’énumération de **Statut du document** a les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="bd2f5-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="bd2f5-120">Confirmation</span><span class="sxs-lookup"><span data-stu-id="bd2f5-120">Confirmation</span></span>
- <span data-ttu-id="bd2f5-121">Prélèvements</span><span class="sxs-lookup"><span data-stu-id="bd2f5-121">Picking List</span></span>
- <span data-ttu-id="bd2f5-122">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="bd2f5-122">Packing Slip</span></span>
- <span data-ttu-id="bd2f5-123">Facture</span><span class="sxs-lookup"><span data-stu-id="bd2f5-123">Invoice</span></span>

## <a name="fields-in-sales"></a><span data-ttu-id="bd2f5-124">Champs dans Sales</span><span class="sxs-lookup"><span data-stu-id="bd2f5-124">Fields in Sales</span></span>

<span data-ttu-id="bd2f5-125">Dans Sales, deux champs indiquent le statut de la commande.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-125">In Sales, two fields indicate the status of the order.</span></span> <span data-ttu-id="bd2f5-126">Les champs que vous devez mapper sont **Statut** et **Statut de traitement**.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-126">The fields that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="bd2f5-127">L’énumération de **Statut** spécifie le statut global de la commande.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="bd2f5-128">Il présente les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="bd2f5-128">It has the following values:</span></span>

- <span data-ttu-id="bd2f5-129">Actif.ve</span><span class="sxs-lookup"><span data-stu-id="bd2f5-129">Active</span></span>
- <span data-ttu-id="bd2f5-130">Soumis</span><span class="sxs-lookup"><span data-stu-id="bd2f5-130">Submitted</span></span>
- <span data-ttu-id="bd2f5-131">Exécuté</span><span class="sxs-lookup"><span data-stu-id="bd2f5-131">Fulfilled</span></span>
- <span data-ttu-id="bd2f5-132">Facturé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-132">Invoiced</span></span>
- <span data-ttu-id="bd2f5-133">Annulé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-133">Cancelled</span></span>

<span data-ttu-id="bd2f5-134">L’énumération de **Statut de traitement** a été introduite afin que le statut puisse être mappé plus précisément avec Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="bd2f5-135">Le tableau suivant montre le mappage du **Statut de traitement** dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="bd2f5-136">Statut de traitement</span><span class="sxs-lookup"><span data-stu-id="bd2f5-136">Processing Status</span></span>   | <span data-ttu-id="bd2f5-137">Statut dans Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="bd2f5-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="bd2f5-138">Statut de document dans Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="bd2f5-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="bd2f5-139">Actif.ve</span><span class="sxs-lookup"><span data-stu-id="bd2f5-139">Active</span></span>              | <span data-ttu-id="bd2f5-140">Commande en cours</span><span class="sxs-lookup"><span data-stu-id="bd2f5-140">Open Order</span></span>                        | <span data-ttu-id="bd2f5-141">None</span><span class="sxs-lookup"><span data-stu-id="bd2f5-141">None</span></span>                                       |
| <span data-ttu-id="bd2f5-142">Confirmée</span><span class="sxs-lookup"><span data-stu-id="bd2f5-142">Confirmed</span></span>           | <span data-ttu-id="bd2f5-143">Commande en cours</span><span class="sxs-lookup"><span data-stu-id="bd2f5-143">Open Order</span></span>                        | <span data-ttu-id="bd2f5-144">Confirmation</span><span class="sxs-lookup"><span data-stu-id="bd2f5-144">Confirmation</span></span>                               |
| <span data-ttu-id="bd2f5-145">Prélevé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-145">Picked</span></span>              | <span data-ttu-id="bd2f5-146">Commande en cours</span><span class="sxs-lookup"><span data-stu-id="bd2f5-146">Open Order</span></span>                        | <span data-ttu-id="bd2f5-147">Prélèvements</span><span class="sxs-lookup"><span data-stu-id="bd2f5-147">Picking List</span></span>                               |
| <span data-ttu-id="bd2f5-148">Partiellement livré</span><span class="sxs-lookup"><span data-stu-id="bd2f5-148">Partially Delivered</span></span> | <span data-ttu-id="bd2f5-149">Commande en cours</span><span class="sxs-lookup"><span data-stu-id="bd2f5-149">Open Order</span></span>                        | <span data-ttu-id="bd2f5-150">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="bd2f5-150">Packing Slip</span></span>                               |
| <span data-ttu-id="bd2f5-151">Livré(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-151">Delivered</span></span>           | <span data-ttu-id="bd2f5-152">Livré(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-152">Delivered</span></span>                         | <span data-ttu-id="bd2f5-153">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="bd2f5-153">Packing Slip</span></span>                               |
| <span data-ttu-id="bd2f5-154">Partiellement facturé</span><span class="sxs-lookup"><span data-stu-id="bd2f5-154">Partially Invoiced</span></span>  | <span data-ttu-id="bd2f5-155">Livré(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-155">Delivered</span></span>                         | <span data-ttu-id="bd2f5-156">Facture</span><span class="sxs-lookup"><span data-stu-id="bd2f5-156">Invoice</span></span>                                    |
| <span data-ttu-id="bd2f5-157">Facturé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-157">Invoiced</span></span>            | <span data-ttu-id="bd2f5-158">Facturé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-158">Invoiced</span></span>                          | <span data-ttu-id="bd2f5-159">Facture</span><span class="sxs-lookup"><span data-stu-id="bd2f5-159">Invoice</span></span>                                    |
| <span data-ttu-id="bd2f5-160">Annulé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-160">Cancelled</span></span>           | <span data-ttu-id="bd2f5-161">Annulé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-161">Cancelled</span></span>                         | <span data-ttu-id="bd2f5-162">Non applicable</span><span class="sxs-lookup"><span data-stu-id="bd2f5-162">Not applicable</span></span>                             |

<span data-ttu-id="bd2f5-163">Le tableau suivant montre le mappage du **Statut de traitement** entre Sales et Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="bd2f5-164">Statut de traitement</span><span class="sxs-lookup"><span data-stu-id="bd2f5-164">Processing Status</span></span>   | <span data-ttu-id="bd2f5-165">Statut dans Sales</span><span class="sxs-lookup"><span data-stu-id="bd2f5-165">Status in Sales</span></span> | <span data-ttu-id="bd2f5-166">Statut dans Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="bd2f5-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="bd2f5-167">Actif.ve</span><span class="sxs-lookup"><span data-stu-id="bd2f5-167">Active</span></span>              | <span data-ttu-id="bd2f5-168">Actif.ve</span><span class="sxs-lookup"><span data-stu-id="bd2f5-168">Active</span></span>          | <span data-ttu-id="bd2f5-169">Commande en cours</span><span class="sxs-lookup"><span data-stu-id="bd2f5-169">Open Order</span></span>                        |
| <span data-ttu-id="bd2f5-170">Confirmée</span><span class="sxs-lookup"><span data-stu-id="bd2f5-170">Confirmed</span></span>           | <span data-ttu-id="bd2f5-171">Soumis</span><span class="sxs-lookup"><span data-stu-id="bd2f5-171">Submitted</span></span>       | <span data-ttu-id="bd2f5-172">Commande en cours</span><span class="sxs-lookup"><span data-stu-id="bd2f5-172">Open Order</span></span>                        |
| <span data-ttu-id="bd2f5-173">Prélevé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-173">Picked</span></span>              | <span data-ttu-id="bd2f5-174">Soumis</span><span class="sxs-lookup"><span data-stu-id="bd2f5-174">Submitted</span></span>       | <span data-ttu-id="bd2f5-175">Commande en cours</span><span class="sxs-lookup"><span data-stu-id="bd2f5-175">Open Order</span></span>                        |
| <span data-ttu-id="bd2f5-176">Partiellement livré</span><span class="sxs-lookup"><span data-stu-id="bd2f5-176">Partially Delivered</span></span> | <span data-ttu-id="bd2f5-177">Actif.ve</span><span class="sxs-lookup"><span data-stu-id="bd2f5-177">Active</span></span>          | <span data-ttu-id="bd2f5-178">Commande en cours</span><span class="sxs-lookup"><span data-stu-id="bd2f5-178">Open Order</span></span>                        |
| <span data-ttu-id="bd2f5-179">Partiellement facturé</span><span class="sxs-lookup"><span data-stu-id="bd2f5-179">Partially Invoiced</span></span>  | <span data-ttu-id="bd2f5-180">Actif.ve</span><span class="sxs-lookup"><span data-stu-id="bd2f5-180">Active</span></span>          | <span data-ttu-id="bd2f5-181">Commande en cours</span><span class="sxs-lookup"><span data-stu-id="bd2f5-181">Open Order</span></span>                        |
| <span data-ttu-id="bd2f5-182">Partiellement facturé</span><span class="sxs-lookup"><span data-stu-id="bd2f5-182">Partially Invoiced</span></span>  | <span data-ttu-id="bd2f5-183">Exécuté</span><span class="sxs-lookup"><span data-stu-id="bd2f5-183">Fulfilled</span></span>       | <span data-ttu-id="bd2f5-184">Livré(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-184">Delivered</span></span>                         |
| <span data-ttu-id="bd2f5-185">Facturé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-185">Invoiced</span></span>            | <span data-ttu-id="bd2f5-186">Facturé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-186">Invoiced</span></span>        | <span data-ttu-id="bd2f5-187">Facturé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-187">Invoiced</span></span>                          |
| <span data-ttu-id="bd2f5-188">Annulé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-188">Cancelled</span></span>           | <span data-ttu-id="bd2f5-189">Annulé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-189">Cancelled</span></span>       | <span data-ttu-id="bd2f5-190">Annulé(e)</span><span class="sxs-lookup"><span data-stu-id="bd2f5-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="bd2f5-191">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="bd2f5-191">Setup</span></span>

<span data-ttu-id="bd2f5-192">Pour configurer le mappage des champs de statut de la commande client, vous devez activer les attributs **IsSOPIntegrationEnabled** et **isIntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-192">To set up the mapping for the sales order status fields, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="bd2f5-193">Pour activer l’attribut **IsSOPIntegrationEnabled**, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="bd2f5-194">Dans un navigateur, accédez à `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="bd2f5-195">Remplacez **\<test-name\>** avec le lien de votre entreprise vers Sales.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="bd2f5-196">Sur la page qui s’ouvre, recherchez **organisationid**, et notez la valeur.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-196">On the page that is opened, find **organizationid**, and make a note of the value.</span></span>

    ![Recherche de Organizationid](media/sales-map-orgid.png)

3. <span data-ttu-id="bd2f5-198">Dans Sales, ouvrez la console du navigateur et exécutez le script suivant.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="bd2f5-199">Utilisez la valeur **organisationid** de l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-199">Use the **organizationid** value from step 2.</span></span>

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on record update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Code JavaScript dans la console du navigateur](media/sales-map-script.png)

4. <span data-ttu-id="bd2f5-201">Vérifiez que **IsSOPIntegrationEnabled** est défini sur **true**.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="bd2f5-202">Utilisez l’URL de l’étape 1 pour vérifier la valeur.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-202">Use the URL from step 1 to check the value.</span></span>

    ![IsSOPIntegrationEnabled défini sur true](media/sales-map-integration-enabled.png)

<span data-ttu-id="bd2f5-204">Pour activer l’attribut **isIntegrationUser**, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="bd2f5-205">Dans Sales, accédez à **Paramètre \> Personnalisation \> Personnaliser le système**, sélectionnez **Entité utilisateur**, puis ouvrez **Écran \> Utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-205">In Sales, go to **Setting \> Customization \> Customize the System**, select **User entity**, and then open **Form \> User**.</span></span>

    ![Ouverture de l’écran utilisateur](media/sales-map-user.png)

2. <span data-ttu-id="bd2f5-207">Dans Field Explorer, recherchez **Mode utilisateur de l’intégration** et double-cliquez dessus pour l’ajouter à l’écran.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-207">In Field Explorer, find **Integration user mode**, and double-click it to add it to the form.</span></span> <span data-ttu-id="bd2f5-208">Enregistrez votre modification.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-208">Save your change.</span></span>

    ![Ajout du champ Mode utilisateur de l’intégration à l’écran](media/sales-map-field-explorer.png)

3. <span data-ttu-id="bd2f5-210">Dans Sales, accédez à **Paramètre \> Sécurité \> Utilisateurs** et changez les vues de **Utilisateurs activés** à **Utilisateurs de l’application**.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-210">In Sales, go to **Setting \> Security \> Users**, and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![Modification de la vue de Utilisateurs activés à Utilisateurs de l’application](media/sales-map-enabled-users.png)

4. <span data-ttu-id="bd2f5-212">Sélectionnez les deux entrées pour **DualWrite IntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Liste des utilisateurs d’application](media/sales-map-user-mode.png)

5. <span data-ttu-id="bd2f5-214">Changer la valeur du champ **Mode utilisateur de l’intégration** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-214">Change the value of the **Integration user mode** field to **Yes**.</span></span>

    ![Changement de la valeur du champ Mode utilisateur de l’intégration](media/sales-map-user-mode-yes.png)

<span data-ttu-id="bd2f5-216">Vos commandes client sont maintenant mappées.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-216">Your sales orders are now mapped.</span></span>
