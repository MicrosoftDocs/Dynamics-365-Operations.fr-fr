---
title: Ajouter ou copier des baux (version préliminaire)
description: Cette rubrique décrit comment créer un bail en saisissant des informations pour celui-ci dans Location d’actifs ou en copiant les informations depuis un bail existant.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: abbf04d009a4b347792cd8b317e334da2a4cbbee
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969601"
---
# <a name="add-or-copy-leases-preview"></a><span data-ttu-id="aadae-103">Ajouter ou copier des baux (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="aadae-103">Add or copy leases (Preview)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aadae-104">Cette rubrique explique comment créer un bail de A à Z dans Location d’actifs et comment créer un bail en copiant un bail existant.</span><span class="sxs-lookup"><span data-stu-id="aadae-104">This topic explains how to create a lease from scratch in Asset leasing, and also how to create a lease by copying an existing lease.</span></span> <span data-ttu-id="aadae-105">Le processus de création d’un bail de A à Z implique de saisir les informations pour le nouveau bail et de créer un échéancier de bail.</span><span class="sxs-lookup"><span data-stu-id="aadae-105">The process for creating a lease from scratch involves entering information for the new lease and then creating a lease schedule.</span></span> <span data-ttu-id="aadae-106">Après la configuration d’au moins un bail, vous pourriez trouver plus simple de copier les informations à partir d’un bail existant et de modifier ces informations comme l’exige la création d’un nouveau bail.</span><span class="sxs-lookup"><span data-stu-id="aadae-106">After at least one lease has been set up, you might find it easier to copy the information from an existing lease and then edit that information as you require to create a new lease.</span></span>

## <a name="create-a-lease"></a><span data-ttu-id="aadae-107">Créer un bail</span><span class="sxs-lookup"><span data-stu-id="aadae-107">Create a lease</span></span>

<span data-ttu-id="aadae-108">Procédez comme suit pour créer un bail dans Location d’actifs.</span><span class="sxs-lookup"><span data-stu-id="aadae-108">Follow these steps to create a lease in Asset leasing.</span></span>

1. <span data-ttu-id="aadae-109">Sur la page **Récapitulatif du bail**, dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="aadae-109">On the **Lease summary** page, on the Action Pane, select **New**.</span></span>
2. <span data-ttu-id="aadae-110">Entrez les informations du bail.</span><span class="sxs-lookup"><span data-stu-id="aadae-110">Enter the lease information.</span></span> <span data-ttu-id="aadae-111">Les champs obligatoires sont encadrés en rouge.</span><span class="sxs-lookup"><span data-stu-id="aadae-111">Fields that are required have red borders.</span></span>

## <a name="create-a-lease-schedule"></a><span data-ttu-id="aadae-112">Créer un échéancier de bail</span><span class="sxs-lookup"><span data-stu-id="aadae-112">Create a lease schedule</span></span>

<span data-ttu-id="aadae-113">Une fois que vous avez terminé de saisir les informations relatives au bail, procédez comme suit pour créer un échéancier de bail.</span><span class="sxs-lookup"><span data-stu-id="aadae-113">After you've finished entering information for the lease, follow these steps to create a lease schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="aadae-114">Les dimensions financières peuvent changer en fonction des dimensions financières personnalisées.</span><span class="sxs-lookup"><span data-stu-id="aadae-114">The financial dimensions might change based on any custom financial dimensions.</span></span>

1. <span data-ttu-id="aadae-115">Sélectionnez **Créer des échéanciers** pour générer les registres de location.</span><span class="sxs-lookup"><span data-stu-id="aadae-115">Select **Create schedules** to generate the lease books.</span></span> <span data-ttu-id="aadae-116">Les registres de bail comprennent les échéanciers de paiement, d’amortissement et de dépenses.</span><span class="sxs-lookup"><span data-stu-id="aadae-116">The lease books include the payment, amortization, depreciation, and expense schedules.</span></span>
2. <span data-ttu-id="aadae-117">Pour accéder aux registres de bail et afficher les échéanciers récemment créés, sélectionnez l’onglet **Registres**.</span><span class="sxs-lookup"><span data-stu-id="aadae-117">To access the lease books and view the newly created schedules, select the **Books** tab.</span></span>

    <span data-ttu-id="aadae-118">La page **Détails du registre** montre comment le bail est comptabilisé par les registres qui lui ont été attribués.</span><span class="sxs-lookup"><span data-stu-id="aadae-118">The **Book details** page shows how the lease is accounted for by the books that have been allocated to it.</span></span> <span data-ttu-id="aadae-119">De là, vous pouvez afficher les échéanciers de bail.</span><span class="sxs-lookup"><span data-stu-id="aadae-119">From here, you can view the lease schedules.</span></span>

    <span data-ttu-id="aadae-120">L’échéancier de paiement contient les entrées de l’onglet **Lignes d’échéancier de paiement** sur la page **Ajouter un bail**.</span><span class="sxs-lookup"><span data-stu-id="aadae-120">The payment schedule contains the inputs from the **Payment schedule lines** tab on the **Add lease** page.</span></span> <span data-ttu-id="aadae-121">Vous pouvez toujours modifier chaque montant de paiement et paiement variable.</span><span class="sxs-lookup"><span data-stu-id="aadae-121">You can still change each payment amount and variable payment.</span></span> <span data-ttu-id="aadae-122">Le passif locatif est calculé en fonction de l’échéancier de paiement modifié.</span><span class="sxs-lookup"><span data-stu-id="aadae-122">The lease liability is calculated based on the modified payment schedule.</span></span>

4. <span data-ttu-id="aadae-123">Après avoir examiné l’échéancier de paiement, sélectionnez **Confirmer l’échéancier**.</span><span class="sxs-lookup"><span data-stu-id="aadae-123">After you've finished reviewing the payment schedule, select **Confirm schedule**.</span></span> <span data-ttu-id="aadae-124">Une fois l’échéancier confirmé, le bail n’est plus disponible pour modification.</span><span class="sxs-lookup"><span data-stu-id="aadae-124">After the schedule is confirmed, the lease is no longer available for editing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aadae-125">Le système calcule automatiquement la durée du bail à partir des lignes de l’échéancier de paiement sur la page **Ajouter un bail**.</span><span class="sxs-lookup"><span data-stu-id="aadae-125">The system automatically calculates the lease term from the payment schedule lines on the **Add lease** page.</span></span>
    >
    > <span data-ttu-id="aadae-126">Pour calculer la durée du bail en mois, le système recherche la différence entre la date de début et la date de fin pour une ligne de paiement spécifique.</span><span class="sxs-lookup"><span data-stu-id="aadae-126">To calculate the lease term in months, the system finds the difference between the start date and the end date for a specific payment schedule line.</span></span> <span data-ttu-id="aadae-127">Il passe ensuite à la ligne de l’échéancier de paiement suivante et recherche à nouveau la différence.</span><span class="sxs-lookup"><span data-stu-id="aadae-127">It then moves to the next payment schedule line and finds the difference again.</span></span> <span data-ttu-id="aadae-128">Enfin, le système additionne tous les montants pour déterminer la durée du bail en mois.</span><span class="sxs-lookup"><span data-stu-id="aadae-128">Finally, the system sums all the amounts to determine the lease term in months.</span></span>

5. <span data-ttu-id="aadae-129">Pour afficher les charges d’intérêts de la période calculées, ouvrez la page **Échéancier de l’amortissement du passif**.</span><span class="sxs-lookup"><span data-stu-id="aadae-129">To view the calculated period interest expenses, open the **Liability amortization schedule** page.</span></span> <span data-ttu-id="aadae-130">Pour afficher l’amortissement linéaire calculé, ouvrez la page **Échéancier d’amortissement des actifs**.</span><span class="sxs-lookup"><span data-stu-id="aadae-130">To view calculated straight-line depreciation, open the **Asset depreciation schedule** page.</span></span>
6. <span data-ttu-id="aadae-131">Après avoir examiné le montant calculé, vous pouvez créer l’écriture de journal de reconnaissance initiale sur la page **Reconnaissance initiale**.</span><span class="sxs-lookup"><span data-stu-id="aadae-131">After you've finished reviewing the calculated amount, you can create the initial recognition journal entry on the **Initial recognition** page.</span></span> <span data-ttu-id="aadae-132">Vous recevez un message indiquant que le journal a été créé.</span><span class="sxs-lookup"><span data-stu-id="aadae-132">You receive a message that states that the journal has been created.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aadae-133">L’écriture de journal n’est pas validée dans le grand livre tant que vous ne validez pas manuellement l’écriture.</span><span class="sxs-lookup"><span data-stu-id="aadae-133">The journal entry isn't posted to General ledger until you manually post the entry.</span></span>

7. <span data-ttu-id="aadae-134">Pour consulter l’entrée de comptabilisation initiale proposée avant de la publier, sélectionnez **Journal de location d’actifs**.</span><span class="sxs-lookup"><span data-stu-id="aadae-134">To review the proposed initial recognition entry before you post it, select **Asset leasing journal**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aadae-135">Le journal de location d’actifs ne peut pas être créé manuellement.</span><span class="sxs-lookup"><span data-stu-id="aadae-135">The Asset leasing journal can't be created manually.</span></span> <span data-ttu-id="aadae-136">Il est automatiquement créé lors de la création des échéanciers de location.</span><span class="sxs-lookup"><span data-stu-id="aadae-136">It's automatically created when lease schedules are created.</span></span>

8. <span data-ttu-id="aadae-137">Lorsque vous avez terminé de consulter l’écriture initiale du journal de comptabilisation et que vous êtes prêt à la publier, sélectionnez **Publier** pour comptabiliser l’actif au titre du droit d’utilisation (ROU) et le passif de location dans le grand livre.</span><span class="sxs-lookup"><span data-stu-id="aadae-137">When you've finished reviewing the initial recognition journal entry and are ready to post it, select **Post** to recognize the right-of-use (ROU) asset and lease liability in General ledger.</span></span>

## <a name="copy-a-lease"></a><span data-ttu-id="aadae-138">Copier un bail</span><span class="sxs-lookup"><span data-stu-id="aadae-138">Copy a lease</span></span>

<span data-ttu-id="aadae-139">Le leasing d’actifs vous permet de copier les détails d’un bail pour en créer un contenant les mêmes informations.</span><span class="sxs-lookup"><span data-stu-id="aadae-139">Asset leasing lets you copy the details of a lease to create a new lease that has the same information.</span></span> <span data-ttu-id="aadae-140">Vous pouvez ensuite modifier les champs du bail avant de créer les échéanciers pour le bail copié.</span><span class="sxs-lookup"><span data-stu-id="aadae-140">You can then change the lease fields before you create the schedules for the copied lease.</span></span>

1. <span data-ttu-id="aadae-141">Sur la page **Récapitulatif du bail**, sélectionnez le bail à copier, puis, dans le volet Actions, sélectionnez **Copier le bail**.</span><span class="sxs-lookup"><span data-stu-id="aadae-141">On the **Lease summary** page, select the lease to copy, and then, on the Action Pane, select **Copy lease**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aadae-142">Si le paramètre **Manuel** est désactivé pour la séquence de numéros pour les ID de bail, le numéro suivant de la séquence est automatiquement généré comme ID de bail du bail copié.</span><span class="sxs-lookup"><span data-stu-id="aadae-142">If the **Manual** parameter is turned off for the number sequence for lease IDs, the next number in the sequence is automatically generated as the lease ID of the copied lease.</span></span> <span data-ttu-id="aadae-143">Si le paramètre **Manuel** est activé, vous recevez un message qui vous invite à saisir l’ID du bail avant de procéder à la copie du bail.</span><span class="sxs-lookup"><span data-stu-id="aadae-143">If the **Manual** parameter is turned on, you receive a message that prompts you to enter the lease ID before you proceed to copy the lease.</span></span>

2. <span data-ttu-id="aadae-144">Sélectionnez **Copie**.</span><span class="sxs-lookup"><span data-stu-id="aadae-144">Select **Copy**.</span></span> <span data-ttu-id="aadae-145">Les détails du bail à partir du bail sélectionné sont copiés dans un nouveau bail.</span><span class="sxs-lookup"><span data-stu-id="aadae-145">The lease details from the selected lease are copied to a new lease.</span></span> <span data-ttu-id="aadae-146">Vous pouvez ensuite modifier les détails du nouveau bail avant de l’enregistrer et de créer les échéanciers de bail.</span><span class="sxs-lookup"><span data-stu-id="aadae-146">You can then edit the details of the new lease before you save it and create the lease schedules.</span></span>

## <a name="asset-leasing-journal"></a><span data-ttu-id="aadae-147">Journal de leasing d’actifs</span><span class="sxs-lookup"><span data-stu-id="aadae-147">Asset leasing journal</span></span>

<span data-ttu-id="aadae-148">Toutes les écritures de journal créées dans Leasing d’actifs sont contenues dans le journal Leasing d’actifs.</span><span class="sxs-lookup"><span data-stu-id="aadae-148">All journal entries that are created in Asset leasing are contained in the Asset leasing journal.</span></span> <span data-ttu-id="aadae-149">Sur la page **Journal de leasing d’actifs** (**Leasing d’actifs\> Entrées de journal \> Journal de location d’actifs**), vous pouvez filtrer par statut de validation, afficher des écritures de journal spécifiques et les pièces justificatives, et valider les écritures de journal non comptabilisées.</span><span class="sxs-lookup"><span data-stu-id="aadae-149">On the **Asset leasing journal** page (**Asset leasing \> Journal entries \> Asset leasing journal**), you can filter by posting status, view specific journal entries and the vouchers, and post unposted journal entries.</span></span>

> [!NOTE]
> <span data-ttu-id="aadae-150">Le journal de location d’actifs ne peut pas être créé manuellement.</span><span class="sxs-lookup"><span data-stu-id="aadae-150">The Asset leasing journal can't be created manually.</span></span> <span data-ttu-id="aadae-151">Il est automatiquement créé lors de la création des échéanciers de location.</span><span class="sxs-lookup"><span data-stu-id="aadae-151">It's automatically created when lease schedules are created.</span></span>
