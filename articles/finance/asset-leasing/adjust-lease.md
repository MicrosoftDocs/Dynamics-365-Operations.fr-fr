---
title: Ajuster les baux
description: La rubrique explique comment ajuster un bail. Un ajustement peut être nécessaire si les conditions du bail sont modifiées, si le bail est prolongé ou si d’autres circonstances changent.
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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9d1c6e20e72fb2816c32e71e8921a94724ae5656
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4443384"
---
# <a name="adjust-leases"></a><span data-ttu-id="63145-104">Ajuster les baux</span><span class="sxs-lookup"><span data-stu-id="63145-104">Adjust leases</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63145-105">La rubrique explique comment ajuster un bail.</span><span class="sxs-lookup"><span data-stu-id="63145-105">The topic explains how to adjust a lease.</span></span> <span data-ttu-id="63145-106">Un ajustement peut être nécessaire si les conditions du bail sont modifiées, si le bail est prolongé ou si d’autres circonstances changent.</span><span class="sxs-lookup"><span data-stu-id="63145-106">Adjustment might be required if the lease terms are modified, the lease is extended, or other circumstances change.</span></span> <span data-ttu-id="63145-107">La location d’actifs est conforme aux directives fournies par l’article 842 sur la codification des normes comptables (ASC 842) et la norme internationale en matière de génération des états financiers 16 (IFRS 16) concernant les modifications des baux.</span><span class="sxs-lookup"><span data-stu-id="63145-107">Asset leasing complies with the guidance that Accounting Standards Codification Topic 842 (ASC 842) and International Financial Reporting Standard 16 (IFRS 16) provide about lease modifications.</span></span> <span data-ttu-id="63145-108">ASC 842-20-15-1 définit une modification de bail comme toute modification des termes et conditions d’un contrat qui entraîne une modification de la portée ou de la prise en compte d’un bail.</span><span class="sxs-lookup"><span data-stu-id="63145-108">ASC 842-20-15-1 defines a lease modification as any change to the terms and conditions of a contract that causes a change in the scope of, or the consideration for, a lease.</span></span> <span data-ttu-id="63145-109">Le paragraphe 39 d’IFRS 16 indique qu’un locataire doit réévaluer le passif locatif afin qu’il reflète les modifications des paiements de location.</span><span class="sxs-lookup"><span data-stu-id="63145-109">Paragraph 39 of IFRS 16 states that a lessee must revalue the lease liability so that it reflects changes to the lease payments.</span></span>

<span data-ttu-id="63145-110">Pour les organisations qui respectent l’ASC 842 ou l’IFRS 16, un bail est réévalué pour refléter une modification de la valeur actuelle des paiements minimaux de location minimums à venir (PVFMLP).</span><span class="sxs-lookup"><span data-stu-id="63145-110">For organizations that adhere to ASC 842 or IFRS 16, a lease is remeasured to reflect a change in the present value of the future minimum lease payments (PVFMLP).</span></span> <span data-ttu-id="63145-111">Si la PVFMLP augmente, l’écriture de journal créée est un débit au droit d’utilisation de l’actif et un crédit au passif locatif pour la différence entre la nouvelle PVFMLP et la précédente PVFMLP.</span><span class="sxs-lookup"><span data-stu-id="63145-111">If the PVFMLP increases, the journal entry that is created will be a debit to the right-of-use (ROU) asset and a credit to the lease liability for the difference between the new PVFMLP and the previous PVFMLP.</span></span> <span data-ttu-id="63145-112">Si la PVFMLP diminue, l’écriture de journal est un débit au passif locatif et un crédit au droit d’utilisation de l’actif pour la différence.</span><span class="sxs-lookup"><span data-stu-id="63145-112">If the PVFMLP decreases, the journal entry will be a debit to the lease liability and a credit to the ROU asset for the difference.</span></span>

<span data-ttu-id="63145-113">Si l’ajustement diminue le droit d’utilisation de l’actif au-delà de 0 (zéro), le reste est crédité au gain sur le compte de validation des modifications du bail spécifié sur la page **Comptes de validation de bail**.</span><span class="sxs-lookup"><span data-stu-id="63145-113">If the adjustment decreases the ROU asset past 0 (zero), the remainder will be credited to the gain on lease modification posting account that is specified on the **Lease posting accounts** page.</span></span> <span data-ttu-id="63145-114">Le système comptabilise ces transactions et d’autres écritures d’ajustement, telles que les changements de classification, les coûts directs initiaux, les incitations à la location, les acomptes et les coûts de démantèlement qui résultent des modifications de location.</span><span class="sxs-lookup"><span data-stu-id="63145-114">The system accounts for these transactions and other adjustment entries, such as classification changes, initial direct costs, lease incentives, prepayments, and dismantling costs that arise from lease modifications.</span></span>

<span data-ttu-id="63145-115">Pour obtenir des indications spécifiques sur les transactions d’ajustement de bail, nous vous recommandons de consulter IFRS 16 et ASC 842.</span><span class="sxs-lookup"><span data-stu-id="63145-115">For specific guidance about lease adjustment transactions, we recommend that you see IFRS 16 and ASC 842.</span></span>

<span data-ttu-id="63145-116">Pour ajuster un bail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="63145-116">To adjust a lease, follow these steps.</span></span> <span data-ttu-id="63145-117">Les données modifiées mettent à jour les échéanciers de bail après l’exécution de création d’un échéancier.</span><span class="sxs-lookup"><span data-stu-id="63145-117">The modified data will update lease schedules after the Create schedule process is run.</span></span>

1. <span data-ttu-id="63145-118">Accédez à **Location d’actifs \> Baux \> Récapitulatif du bail**.</span><span class="sxs-lookup"><span data-stu-id="63145-118">Go to **Asset leasing \> Leases \> Lease summary**.</span></span>
2. <span data-ttu-id="63145-119">Sur la page **Récapitulatif du bail**, sélectionnez le bail à ajuster, puis sélectionnez **Ajuster le bail**.</span><span class="sxs-lookup"><span data-stu-id="63145-119">On the **Lease summary** page, select the lease to adjust, and then select **Adjust lease**.</span></span>
3. <span data-ttu-id="63145-120">Sur la page **Ajuster le bail**, entrez les nouvelles informations pour le bail ajusté.</span><span class="sxs-lookup"><span data-stu-id="63145-120">On the **Adjust lease** page, enter the new information for the adjusted lease.</span></span>

    <span data-ttu-id="63145-121">Notez que la page **Ajuster le bail** ressemble à la page **Ajouter un bail**.</span><span class="sxs-lookup"><span data-stu-id="63145-121">Notice that the **Adjust lease** page resembles the **Add lease** page.</span></span> <span data-ttu-id="63145-122">De plus, tout comme la date de début que vous spécifiez lorsque vous ajoutez un bail détermine le moment où le nouveau bail commence, le champ **Date de modification** sur la page **Ajuster le bail** détermine le début du bail modifié.</span><span class="sxs-lookup"><span data-stu-id="63145-122">Additionally, just as the commencement date that you specify when you add a lease determines when the new lease starts, the **Modification date** field on the **Adjust lease** page determines when the modified lease starts.</span></span> <span data-ttu-id="63145-123">Cette date ne peut pas être postérieure à la date de début des échéances de paiement.</span><span class="sxs-lookup"><span data-stu-id="63145-123">This date can't be after the start date on the payment schedule lines.</span></span>

    > [!NOTE]
    > <span data-ttu-id="63145-124">Les champs **Considérations du droit d’utilisation** s’appliquent à l’ajustement du bail.</span><span class="sxs-lookup"><span data-stu-id="63145-124">The **ROU considerations** fields apply to the lease adjustment.</span></span> <span data-ttu-id="63145-125">Si aucun coût direct initial, aucune incitation à la location, aucun paiement anticipé ou aucun coût de démantèlement n’est associé au bail modifié, vous devez laisser ces champs vides.</span><span class="sxs-lookup"><span data-stu-id="63145-125">If no initial direct costs, lease incentives, prepayments, or dismantling costs are associated with the modified lease, you should leave these fields blank.</span></span> <span data-ttu-id="63145-126">Les montants d’origine ne s’appliqueront pas au bail mis à jour.</span><span class="sxs-lookup"><span data-stu-id="63145-126">The original amounts won't apply to the updated lease.</span></span> <span data-ttu-id="63145-127">Tous les frais supplémentaires encourus lors de la modification du bail doivent être inscrits sur la page **Ajuster le bail**.</span><span class="sxs-lookup"><span data-stu-id="63145-127">Any additional costs that are incurred when the lease is modified should be entered on the **Adjust lease** page.</span></span>
    > 
    > <span data-ttu-id="63145-128">Par exemple, un bailleur offre une incitation de 1 000 $ pour accepter une prolongation du bail.</span><span class="sxs-lookup"><span data-stu-id="63145-128">For example, a lessor provides a $1,000 incentive for agreeing to a lease extension.</span></span> <span data-ttu-id="63145-129">Dans ce cas, lorsque vous ajustez le bail pour tenir compte de l’extension, vous entrez **1 000** dans le champ **Incitations à la location**.</span><span class="sxs-lookup"><span data-stu-id="63145-129">In this case, when you adjust the lease to account for the extension, you enter **1,000** in the **Lease incentives** field.</span></span> <span data-ttu-id="63145-130">Si aucune incitation n’est associée à l’ajustement du bail, vous devez effacer toute valeur précédemment saisie dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="63145-130">If no incentives are associated with the lease adjustment, you should clear any value that was previously entered in this field.</span></span> <span data-ttu-id="63145-131">La même logique est appliquée à d’autres considérations du droit d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="63145-131">The same logic is applied to other ROU considerations.</span></span>

    <span data-ttu-id="63145-132">Les échéanciers de paiement du bail ajusté doivent être créés sur une base prospective.</span><span class="sxs-lookup"><span data-stu-id="63145-132">The payment schedule lines of the adjusted lease should be created on a prospective basis.</span></span> <span data-ttu-id="63145-133">Les échéanciers de paiement créés sur une base prospective ne peuvent pas démarrer avant que les modifications du bail entrent en vigueur.</span><span class="sxs-lookup"><span data-stu-id="63145-133">Payment schedule lines that are created on a prospective basis can't start before the lease modifications take effect.</span></span>

    <span data-ttu-id="63145-134">Les étapes suivantes sont presque identiques aux étapes de comptabilisation initiale d’un bail.</span><span class="sxs-lookup"><span data-stu-id="63145-134">The following steps are almost identical to the steps for initially recognizing a lease.</span></span>

4. <span data-ttu-id="63145-135">Sélectionnez **Créer des échéanciers** pour générer l’échéancier de paiement ajusté.</span><span class="sxs-lookup"><span data-stu-id="63145-135">Select **Create schedules** to generate the adjusted payment schedule.</span></span> <span data-ttu-id="63145-136">Vous recevez un message indiquant que l’échéancier de paiement a été créé pour le bail.</span><span class="sxs-lookup"><span data-stu-id="63145-136">You receive a message that states that the payment schedule has been created for the lease.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="63145-137">Avant de sélectionner **Créer des échéanciers**, veillez à ce que la date de modification et les échéanciers de paiement soient exacts.</span><span class="sxs-lookup"><span data-stu-id="63145-137">Before you select **Create schedules**, make sure that the modification date and payment schedule lines are accurate.</span></span> <span data-ttu-id="63145-138">Veillez également à ce que tous les coûts directs initiaux, les incitations à la location, les paiements anticipés ou les coûts de démantèlement correspondent uniquement aux coûts résultant de l’ajustement.</span><span class="sxs-lookup"><span data-stu-id="63145-138">Also make sure that all initial direct costs, lease incentives, prepayments, or dismantling costs correspond only to those costs that arise from the adjustment.</span></span>

5. <span data-ttu-id="63145-139">Pour afficher l’échéancier de paiement récemment créé, sélectionnez **Registres**, et ouvrez la page **Échéancier de paiement**.</span><span class="sxs-lookup"><span data-stu-id="63145-139">To view the newly created payment schedule, select **Books**, and open the **Payment schedule** page.</span></span>
6. <span data-ttu-id="63145-140">Sur la page **Échéancier de paiement**, vous pouvez modifier les montants de paiement ajustés avant de confirmer l’échéancier de paiement.</span><span class="sxs-lookup"><span data-stu-id="63145-140">On the **Payment schedule** page, you can edit the adjusted payment amounts before you confirm the payment schedule.</span></span> <span data-ttu-id="63145-141">Pour confirmer l’échéancier, sélectionnez **Confirmer l’échéancier**.</span><span class="sxs-lookup"><span data-stu-id="63145-141">To confirm the schedule, select **Confirm schedule**.</span></span>

    <span data-ttu-id="63145-142">Lorsque l’échéancier de paiement est confirmé, le nouvel amortissement des immobilisations et les nouveaux échéanciers de passif locatif sont créés.</span><span class="sxs-lookup"><span data-stu-id="63145-142">When the payment schedule is confirmed, the new asset depreciation and new lease liability schedules are created.</span></span>

7. <span data-ttu-id="63145-143">Pour afficher le nouvel échéancier d’amortissement du passif locatif généré à partir des nouvelles entrées, fermez la page **Échéancier de paiement** et ouvrez la page **Programme d’amortissement du passif**.</span><span class="sxs-lookup"><span data-stu-id="63145-143">To view the new lease liability amortization schedule that is generated from the new inputs, close the **Payment schedule** page, and open the **Liability amortization schedule** page.</span></span>
8. <span data-ttu-id="63145-144">Pour afficher le nouvel échéancier d’amortissement des actifs, ouvrez la page **Programmes d’amortissement des actifs** de la page **Détails des registres**.</span><span class="sxs-lookup"><span data-stu-id="63145-144">To view the newly generated asset depreciation schedule, open the **Asset depreciation schedule** page from the **Book details** page.</span></span>
9. <span data-ttu-id="63145-145">Pour générer l’entrée de journal d’ajustement, sélectionnez **Fonction \> Ajustement de bail**.</span><span class="sxs-lookup"><span data-stu-id="63145-145">To generate the adjustment journal entry, select **Function \> Lease adjustment**.</span></span> <span data-ttu-id="63145-146">Vous recevez un message indiquant que l’entrée de journal d’ajustement a été créée.</span><span class="sxs-lookup"><span data-stu-id="63145-146">You receive a message that states that the adjustment journal entry has been created.</span></span> 
10. <span data-ttu-id="63145-147">Pour afficher l’entrée de journal, sélectionnez **Journaux \> Journal de location d’actifs**.</span><span class="sxs-lookup"><span data-stu-id="63145-147">To view the journal entry, select **Journals \> Asset leasing journal**.</span></span>
11. <span data-ttu-id="63145-148">Pour valider l’écriture de journal, sélectionnez la ligne, puis sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="63145-148">To post the journal entry, select the line, and then select **Post**.</span></span>

## <a name="view-lease-versions"></a><span data-ttu-id="63145-149">Voir les versions de bail</span><span class="sxs-lookup"><span data-stu-id="63145-149">View lease versions</span></span>

<span data-ttu-id="63145-150">Si un bail a été modifié, vous pouvez en afficher les différentes versions.</span><span class="sxs-lookup"><span data-stu-id="63145-150">If a lease has been modified, you can view the different versions of it.</span></span> <span data-ttu-id="63145-151">Vous pouvez également voir les échéanciers historiques et les détails des baux passés.</span><span class="sxs-lookup"><span data-stu-id="63145-151">You can also view the historical schedules and past lease details.</span></span>

1. <span data-ttu-id="63145-152">Sur la page **Récapitulatif du bail**, sélectionnez le bail à copier, puis, dans le volet Actions, sélectionnez **Historique de version des baux**.</span><span class="sxs-lookup"><span data-stu-id="63145-152">On the **Lease summary** page, select the lease, and then, on the Action Pane, select **Lease version history**.</span></span>

    <span data-ttu-id="63145-153">Si le bail sélectionné a été ajusté, la page **Historique de version des baux** montre les différentes versions de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="63145-153">If the selected lease has been adjusted, the **Lease version history** page shows the different versions of it.</span></span> <span data-ttu-id="63145-154">Le bail d’origine est étiqueté **1** et les versions ultérieures ont un ordre numérique croissant.</span><span class="sxs-lookup"><span data-stu-id="63145-154">The original lease is labeled **1**, and subsequent versions have ascending numerical order.</span></span>

    <span data-ttu-id="63145-155">Pour une version de location sélectionnée, vous pouvez afficher les dimensions financières, les détails du contrat, l’emplacement et les échéances de paiement.</span><span class="sxs-lookup"><span data-stu-id="63145-155">For a selected lease version, you can view the financial dimensions, contract details, location, and payment schedule lines.</span></span>

2. <span data-ttu-id="63145-156">Pour afficher les horaires historiques, ouvrez le bail modifié à partir de la page **Récapitulatif du bail**, sélectionnez le livre souhaité, puis, dans le volet Actions, sélectionnez **Historique de version des baux**.</span><span class="sxs-lookup"><span data-stu-id="63145-156">To view historical schedules, open the modified lease from the **Lease summary** page, select the desired book, and then, on the Action Pane, select **Book version history**.</span></span>
3. <span data-ttu-id="63145-157">Sur la page **Version des registres**, sélectionnez la version souhaitée et l’échéance souhaitée à afficher.</span><span class="sxs-lookup"><span data-stu-id="63145-157">On the **Book version** page, select the desired version and the desired schedule to view.</span></span>