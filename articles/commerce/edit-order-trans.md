---
title: Modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones
description: Cette rubrique décrit comment modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones dans Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5113f7ac0d308076ebaa9daeca0929eb537e94ab
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792679"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a><span data-ttu-id="78717-103">Modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones</span><span class="sxs-lookup"><span data-stu-id="78717-103">Edit and audit online order and asynchronous customer order transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78717-104">Cette rubrique décrit comment modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="78717-104">This topic describes how to edit and audit online order and asynchronous customer order transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="78717-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="78717-105">Overview</span></span>

<span data-ttu-id="78717-106">Entre les versions 10.0.5 et 10.0.6 de Commerce, la prise en charge de la modification des transactions au comptant sans livraison (comme les ventes et le vidage de caisse) et des transactions de gestion de trésorerie (comme les entrées de fonds et la suppression des offres) a été ajoutée.</span><span class="sxs-lookup"><span data-stu-id="78717-106">Between Commerce versions 10.0.5 and 10.0.6, support was added for editing cash and carry transactions (such as sales and returns) and cash management transactions (such as float entry and tender removal).</span></span> <span data-ttu-id="78717-107">Dans Commerce version 10.0.7, la prise en charge de la modification des transactions de commande en ligne et des transactions de commande client asynchrones a été ajoutée.</span><span class="sxs-lookup"><span data-stu-id="78717-107">In Commerce version 10.0.7, support was added for editing online order transactions and asynchronous customer order transactions.</span></span>

## <a name="edit-and-audit-order-transactions"></a><span data-ttu-id="78717-108">Modifier et vérifier des transactions de commandes</span><span class="sxs-lookup"><span data-stu-id="78717-108">Edit and audit order transactions</span></span>

<span data-ttu-id="78717-109">Pour modifier et vérifier les transactions de commande dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="78717-109">To edit and audit order transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="78717-110">Installez [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).</span><span class="sxs-lookup"><span data-stu-id="78717-110">Install the [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).</span></span>
1. <span data-ttu-id="78717-111">Dans la page **Paramètres des ventes au détail**, sous l’onglet **Commandes client**, dans le raccourci **Commande**, spécifiez un code de blocage pour **Code de blocage pour les erreurs de synchronisation des commandes**.</span><span class="sxs-lookup"><span data-stu-id="78717-111">On the **Retail parameters** page, on the **Customer orders** tab, on the **Order** FastTab, specify a hold code for **Hold code for order synchronization errors**.</span></span>
1. <span data-ttu-id="78717-112">Ouvrez l’espace de travail **Finances du magasin**.</span><span class="sxs-lookup"><span data-stu-id="78717-112">Open the **Store financials** workspace.</span></span> <span data-ttu-id="78717-113">Les vignettes **Erreurs de synchronisation des commandes en ligne** et **Erreurs de synchronisation des commandes client** fournissent une vue préfiltrée de la page des transactions de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="78717-113">The **Online order synchronization errors** and **Customer order synchronization errors** tiles provide a prefiltered view of the retail transaction page.</span></span> <span data-ttu-id="78717-114">Chaque vignette affiche les enregistrements de transaction dont la synchronisation a échoué pour le type de commande correspondant.</span><span class="sxs-lookup"><span data-stu-id="78717-114">Each shows the transaction records that have failed synchronization for the corresponding order type.</span></span>
1. <span data-ttu-id="78717-115">Ouvrez la page **Erreurs de synchronisation des commandes en ligne** ou la page **Erreurs de synchronisation des commandes client**.</span><span class="sxs-lookup"><span data-stu-id="78717-115">Open either the **Online order synchronization errors** page or the **Customer order synchronization errors** page.</span></span> <span data-ttu-id="78717-116">Sélectionnez un enregistrement pour afficher les détails de l’erreur de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="78717-116">Select a record to view the synchronization error details.</span></span> <span data-ttu-id="78717-117">Le raccourci **État de la synchronisation** fournit les détails d’erreur suivants :</span><span class="sxs-lookup"><span data-stu-id="78717-117">The **Synchronization status** FastTab provides the following error details:</span></span>

    - <span data-ttu-id="78717-118">Statut de commande en attente</span><span class="sxs-lookup"><span data-stu-id="78717-118">Pending order status</span></span>
    - <span data-ttu-id="78717-119">Détails des erreurs de commande</span><span class="sxs-lookup"><span data-stu-id="78717-119">Order error details</span></span>
    - <span data-ttu-id="78717-120">Date et heure de modification</span><span class="sxs-lookup"><span data-stu-id="78717-120">Modified date and time</span></span>
    - <span data-ttu-id="78717-121">Nombre de nouvelles tentatives</span><span class="sxs-lookup"><span data-stu-id="78717-121">Retry count</span></span>

1. <span data-ttu-id="78717-122">Si les détails de l’erreur indiquent que l’enregistrement doit être corrigé, sélectionnez **Office Add in**, puis sélectionnez **Modifier la transaction sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="78717-122">If the error details indicate that the record must be fixed, select **Office Add in**, and then select **Edit selected transaction**.</span></span> <span data-ttu-id="78717-123">Un fichier Excel affichant les détails de la transaction sélectionnée s’ouvert.</span><span class="sxs-lookup"><span data-stu-id="78717-123">An Excel file that shows the details of the selected transaction is opened.</span></span>

    - <span data-ttu-id="78717-124">Si la transaction en cours de modification est une transaction de commande en ligne, le fichier Excel contient les feuilles de calcul suivantes :</span><span class="sxs-lookup"><span data-stu-id="78717-124">If the transaction that is being edited is an online order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="78717-125">**Transaction** – Cette feuille de calcul contient les détails de l’en-tête pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="78717-125">**Transaction** – This worksheet has the header details for the transaction.</span></span>
        - <span data-ttu-id="78717-126">**Transaction de vente** – Cette feuille de calcul contient les détails de la ligne pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="78717-126">**Sales transaction** – This worksheet has the line details for the transaction.</span></span>
        - <span data-ttu-id="78717-127">**Transactions de paiement** – Cette feuille de calcul contient les détails des lignes de paiement pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="78717-127">**Payment transactions** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="78717-128">**Transactions de remise** – Cette feuille de calcul contient les détails de la remise pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="78717-128">**Discount transactions** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="78717-129">**Transactions de taxe** – Cette feuille de calcul contient les détails de la taxe pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="78717-129">**Tax transactions** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="78717-130">**Transactions de frais** – Cette feuille de calcul contient les détails des frais pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="78717-130">**Charges transactions** – This worksheet has the charges-related data for the transaction.</span></span>

    - <span data-ttu-id="78717-131">Si la transaction en cours de modification est une transaction de commande client asynchrone, le fichier Excel contient les feuilles de calcul suivantes :</span><span class="sxs-lookup"><span data-stu-id="78717-131">If the transaction that is being edited is an asynchronous customer order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="78717-132">**Lignes** – Cette feuille de calcul contient les détails de l’en-tête et de la ligne pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="78717-132">**Lines** – This worksheet has the header and line details for the transaction.</span></span>
        - <span data-ttu-id="78717-133">**Paiements** – Cette feuille de calcul contient les détails des lignes de paiement pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="78717-133">**Payments** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="78717-134">**Remises** – Cette feuille de calcul contient les détails de la remise pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="78717-134">**Discounts** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="78717-135">**Taxes** – Cette feuille de calcul contient les détails de la taxe pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="78717-135">**Taxes** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="78717-136">**Frais** – Cette feuille de calcul contient les détails des frais pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="78717-136">**Charges** – This worksheet has the charges-related data for the transaction.</span></span>

1. <span data-ttu-id="78717-137">Dans le fichier Excel, dans le champ **Statut de commande en attente**, entrez **Modification**, puis publiez la modification.</span><span class="sxs-lookup"><span data-stu-id="78717-137">In the Excel file, in the **Pending order status** field, enter **Editing**, and then publish the change.</span></span> <span data-ttu-id="78717-138">De cette façon, vous évitez que la tâche **Synchroniser la commande** qui s’exécute en mode lot ignore cet enregistrement pendant le traitement.</span><span class="sxs-lookup"><span data-stu-id="78717-138">In this way, you prevent the **Synchronize order** job that is running in batch mode from skipping this record during processing.</span></span>
1. <span data-ttu-id="78717-139">Dans le fichier Excel, modifiez les champs appropriés, puis chargez les données dans Commerce Headquarters en utilisant la fonctionnalité de publication du complément Dynamics Excel.</span><span class="sxs-lookup"><span data-stu-id="78717-139">In the Excel file, modify the appropriate fields, and then upload the data back into Commerce headquarters by using the publishing functionality of the Dynamics Excel Add-in.</span></span> <span data-ttu-id="78717-140">Une fois les données publiées, les modifications sont répercutées dans le système.</span><span class="sxs-lookup"><span data-stu-id="78717-140">After the data is published, the changes will be reflected in the system.</span></span> <span data-ttu-id="78717-141">Lors de la publication, aucune validation n’est exécutée pour les modifications effectuées par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="78717-141">During publication, no validation is done for changes that users make.</span></span>
1. <span data-ttu-id="78717-142">Vous pouvez afficher une piste d’audit complète des modifications en sélectionnant **Afficher la piste d’audit** dans l’en-tête **Transaction de vente au détail** pour les modifications au niveau de l’en-tête et dans la section et l’enregistrement appropriés dans la page de transaction appropriée.</span><span class="sxs-lookup"><span data-stu-id="78717-142">You can view a complete audit trail of the changes by selecting **View audit trail** in the **Retail transaction** header for the header-level changes, and in the relevant section and record on the appropriate transaction page.</span></span> <span data-ttu-id="78717-143">Par exemple, toutes les modifications liées aux lignes de vente seront affichées sur la page **Transactions de vente**, et toutes les modifications liées aux paiements seront affichées sur la page **Opérations de paiement**.</span><span class="sxs-lookup"><span data-stu-id="78717-143">For example, all changes that are related to sales lines will be shown on the **Sales transactions** page, and all changes that are related to payments will be shown on the **Payment transactions** page.</span></span> <span data-ttu-id="78717-144">Les détails d’audit suivants sont conservés pour les modifications :</span><span class="sxs-lookup"><span data-stu-id="78717-144">The following audit details are maintained for the changes:</span></span>

    - <span data-ttu-id="78717-145">Date et heure de modification</span><span class="sxs-lookup"><span data-stu-id="78717-145">Modified date and time</span></span>
    - <span data-ttu-id="78717-146">Champ</span><span class="sxs-lookup"><span data-stu-id="78717-146">Field</span></span>
    - <span data-ttu-id="78717-147">Ancienne valeur</span><span class="sxs-lookup"><span data-stu-id="78717-147">Old value</span></span>
    - <span data-ttu-id="78717-148">Nouvelle valeur</span><span class="sxs-lookup"><span data-stu-id="78717-148">New value</span></span>
    - <span data-ttu-id="78717-149">Modifié par</span><span class="sxs-lookup"><span data-stu-id="78717-149">Modified by</span></span>

1. <span data-ttu-id="78717-150">Après avoir effectué et publié vos modifications, sélectionnez **Synchroniser la commande** pour démarrer immédiatement le processus de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="78717-150">After you've made and published your changes, select **Synchronize order** to immediately start the synchronization process.</span></span> <span data-ttu-id="78717-151">Vous pouvez également attendre que le processus de synchronisation qui s’exécute en mode lot traite la transaction.</span><span class="sxs-lookup"><span data-stu-id="78717-151">Alternatively, you can wait for the synchronization process that is running in batch mode to process the transaction.</span></span>

<span data-ttu-id="78717-152">Par défaut, une fois les commandes synchronisées avec succès, elles sont mises en attente, en fonction du code de blocage défini dans les paramètres de Commerce.</span><span class="sxs-lookup"><span data-stu-id="78717-152">By default, after the orders are successfully synced, they are put in a hold status, based on the hold code that is defined in the Commerce parameters.</span></span> <span data-ttu-id="78717-153">Le blocage des commandes doit être supprimé pour que l’exécution des commandes ou d’autres opérations puissent être effectuées.</span><span class="sxs-lookup"><span data-stu-id="78717-153">The hold on the orders must be removed before the orders can be processed further for fulfillment or other operations.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="78717-154">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="78717-154">Additional resources</span></span>

[<span data-ttu-id="78717-155">Modifier et vérifier les transactions de gestion des disponibilités et des paiements au comptant sans livraison</span><span class="sxs-lookup"><span data-stu-id="78717-155">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="78717-156">Modifier les dimensions financières des transactions de vente au détail</span><span class="sxs-lookup"><span data-stu-id="78717-156">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="78717-157">Créer un classeur Excel pour modifier les transactions de vente au détail</span><span class="sxs-lookup"><span data-stu-id="78717-157">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="78717-158">Ajouter des champs à un classeur Excel pour modifier les transactions de vente au détail</span><span class="sxs-lookup"><span data-stu-id="78717-158">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]