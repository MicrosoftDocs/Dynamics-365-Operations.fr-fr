---
title: Créer et mettre à jour une stratégie de retour et de remboursement pour un canal
description: Cette rubrique explique comment configurer une stratégie de retour et de remboursement pour un canal.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: 66bb9bbd338561315f2f69ae4aff86a67513b190
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3022592"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a><span data-ttu-id="6be27-103">Créer et mettre à jour une stratégie de retour et de remboursement pour un canal</span><span class="sxs-lookup"><span data-stu-id="6be27-103">Create and update a returns and refunds policy for a channel</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]


## <a name="overview"></a><span data-ttu-id="6be27-104">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="6be27-104">Overview</span></span>

<span data-ttu-id="6be27-105">La stratégie de retour de canal dans Dynamics 365 Commerce permet aux détaillants de définir des mesures d'exécution sur lesquelles les offres de paiement peuvent être autorisées pour le traitement d'un retour sur un point de vente (PDV).</span><span class="sxs-lookup"><span data-stu-id="6be27-105">The channel return policy in Dynamics 365 Commerce enables retailers to set enforcements on which payment tenders can be allowed for processing a return on a point of sale (POS) device.</span></span>  

<span data-ttu-id="6be27-106">Cette rubrique donne les étapes permettant de configurer une stratégie de retour et de remboursement pour un canal.</span><span class="sxs-lookup"><span data-stu-id="6be27-106">This topic describes the steps to set up a returns and refunds policy for a channel.</span></span>

<span data-ttu-id="6be27-107">La portée de la politique se limite actuellement à la définition des offres de paiement qui peuvent être autorisées pour un canal.</span><span class="sxs-lookup"><span data-stu-id="6be27-107">The scope of the policy is currently limited to setting the payment tenders that can be allowed for a channel.</span></span> <span data-ttu-id="6be27-108">La liste « autorisée » est basée sur les modes de paiement utilisés pour effectuer l'achat.</span><span class="sxs-lookup"><span data-stu-id="6be27-108">The "allowed" list is based on the payment methods used to make the purchase.</span></span> <span data-ttu-id="6be27-109">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6be27-109">For example:</span></span>

- <span data-ttu-id="6be27-110">Si un achat a été effectué à l'aide d'une carte-cadeau, la stratégie du magasin consiste à traiter les remboursements uniquement sur une nouvelle carte-cadeau ou à accorder un crédit au magasin.</span><span class="sxs-lookup"><span data-stu-id="6be27-110">If a purchase was made using a gift card, the store policy is to process refunds only to a new gift card or to give store credit.</span></span> 
- <span data-ttu-id="6be27-111">Si une vente a est effectuée en espèces, les options de remboursement autorisées sont les espèces, les cartes-cadeaux et le compte client, mais pas les cartes de crédit.</span><span class="sxs-lookup"><span data-stu-id="6be27-111">If a sale is made using cash, the options allowed for refund are cash, gift card, and customer account, but not credit card.</span></span> 


## <a name="enable-return-policy"></a><span data-ttu-id="6be27-112">Activer la stratégie de retour</span><span class="sxs-lookup"><span data-stu-id="6be27-112">Enable return policy</span></span>

<span data-ttu-id="6be27-113">Pour activer la fonctionnalité de stratégie de retour de canal, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6be27-113">To enable the channel return policy functionality, do the following:</span></span>

1. <span data-ttu-id="6be27-114">Accédez à l'espace de travail **Gestion des fonctionnalités** dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6be27-114">Go to the **Feature Management** workspace in Dynamics 365 Commerce.</span></span>
2. <span data-ttu-id="6be27-115">Recherchez la fonctionnalité **Activer les stratégies de retour de canal** dans la liste des noms de fonction.</span><span class="sxs-lookup"><span data-stu-id="6be27-115">Search for the **Enable channel return policies** feature in the list of feature names.</span></span>
3. <span data-ttu-id="6be27-116">Sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="6be27-116">Select **Enable now**.</span></span> 

## <a name="configure-return-policy"></a><span data-ttu-id="6be27-117">Configurer la stratégie de retour</span><span class="sxs-lookup"><span data-stu-id="6be27-117">Configure return policy</span></span>

<span data-ttu-id="6be27-118">Suivez ces étapes pour configurer une politique de retour pour un magasin de détail ou un canal de vente en ligne.</span><span class="sxs-lookup"><span data-stu-id="6be27-118">Follow these steps to configure a return policy for a retail store or online retail channel.</span></span>

1. <span data-ttu-id="6be27-119">Accédez à **Retail et Commerce** \> **Paramétrage du canal** \> **Retours** \> **Politique de retour de canal**.</span><span class="sxs-lookup"><span data-stu-id="6be27-119">Go to **Retail and Commerce** \> **Channel Setup** \> **Returns** \> **Channel return policy**.</span></span>

2. <span data-ttu-id="6be27-120">Sélectionnez **Nouveau** pour créer un modèle de stratégie de retour.</span><span class="sxs-lookup"><span data-stu-id="6be27-120">Select **New** to create a new return policy template.</span></span> <span data-ttu-id="6be27-121">Pour utiliser un modèle existant, sélectionnez le modèle dans le volet de gauche.</span><span class="sxs-lookup"><span data-stu-id="6be27-121">To use an existing template, select the template in the left pane.</span></span> <span data-ttu-id="6be27-122">Pour les nouveaux modèles, ajoutez un nom et une description qui vous aideront à identifier la stratégie lorsqu'elle est appliquée au canal.</span><span class="sxs-lookup"><span data-stu-id="6be27-122">For new templates, add a name and description that will help you identify the policy when it is being applied to the channel.</span></span>

   <span data-ttu-id="6be27-123">![Ajouter une nouvelle stratégie de retour](media/Return-policy-page1.png "Ajouter une nouvelle stratégie de retour")</span><span class="sxs-lookup"><span data-stu-id="6be27-123">![Add new return policy](media/Return-policy-page1.png "Add new return rolicy")</span></span>
     
   
3. <span data-ttu-id="6be27-124">Dans la section **Modes de paiement des remboursements autorisés**, définissez les offres de paiement de retour **autorisés** pour chaque mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="6be27-124">In the **Allowed refund payment methods** section, define **Allowed** return payment tenders that are specific to each payment method.</span></span>
   <span data-ttu-id="6be27-125">![Ajouter des modes de paiement](media/Return-policy-page2.PNG "Définir les modes de paiement autorisés par type de paiement")</span><span class="sxs-lookup"><span data-stu-id="6be27-125">![Add payment methods](media/Return-policy-page2.PNG "Set allowed payment methods per payment type")</span></span>
   
    > [!IMPORTANT]
    > - <span data-ttu-id="6be27-126">Les modes de paiement sont dérivés des modes de paiement définis pour l'organisation.</span><span class="sxs-lookup"><span data-stu-id="6be27-126">The payment methods are derived from the payment methods set for the organization.</span></span>
    > - <span data-ttu-id="6be27-127">L'ajout d'un type d'offre de retour autorisé pour chaque mode de paiement répertorié garantit que les retours peuvent être effectués pour le type d'offre de retour autorisé.</span><span class="sxs-lookup"><span data-stu-id="6be27-127">Adding an allowed return tender type for each listed payment method will ensure that returns can be made to the allowed return tender type.</span></span>
    
4. <span data-ttu-id="6be27-128">Associez le modèle de stratégie de retour avec les magasins où il est utilisé.</span><span class="sxs-lookup"><span data-stu-id="6be27-128">Associate the return policy template with the stores where it will be used.</span></span> <span data-ttu-id="6be27-129">Sélectionnez **Ajouter** dans l'onglet **Canaux de vente au détail** et associez les canaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="6be27-129">Select **Add** in the **Retail Channels** tab and associate the available channels.</span></span> 

    - <span data-ttu-id="6be27-130">Dans la boîte de dialogue **Choisir des nœuds d'organisation**, sélectionnez les magasins, les régions et les organisations auxquels le modèle doit être associé.</span><span class="sxs-lookup"><span data-stu-id="6be27-130">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>
    - <span data-ttu-id="6be27-131">Un seul modèle de stratégie de retour peut être associé avec chaque magasin.</span><span class="sxs-lookup"><span data-stu-id="6be27-131">Only one return policy template can be associated with each store.</span></span>
    - <span data-ttu-id="6be27-132">Utilisez les boutons de flèche pour sélectionner les magasins, les régions ou les organisations.</span><span class="sxs-lookup"><span data-stu-id="6be27-132">Use the arrow buttons to select stores, regions, or organizations.</span></span>
    - <span data-ttu-id="6be27-133">La date d'entrée en vigueur de la stratégie est la date à laquelle les stratégies sont appliquées aux canaux et les travaux de canal sont exécutés.</span><span class="sxs-lookup"><span data-stu-id="6be27-133">The effective date on the policy will be the date on which the policies are applied to the channels and the channel jobs are run.</span></span> 

    <span data-ttu-id="6be27-134">![Boîte de dialogue Choisir des nœuds d'organisation](media/Return-policy-page3.PNG "Boîte de dialogue Choisir des nœuds d'organisation")</span><span class="sxs-lookup"><span data-stu-id="6be27-134">![Choose organization nodes dialog box](media/Return-policy-page3.PNG "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="6be27-135">Dans la page **Programme de distribution**, exécutez la tâche **1070** pour mettre la stratégie de retour de canal à la disposition du PDV.</span><span class="sxs-lookup"><span data-stu-id="6be27-135">On the **Distribution schedule** page, run the **1070** job to make the channel return policy available to the POS.</span></span>

## <a name="preview-the-channel-return-policy-in-the-pos"></a><span data-ttu-id="6be27-136">Aperçu de la stratégie de retour du canal dans le PDV</span><span class="sxs-lookup"><span data-stu-id="6be27-136">Preview the channel return policy in the POS</span></span>

<span data-ttu-id="6be27-137">Suivez les étapes de l'un des exemples suivants pour afficher les types d'offre de retour autorisés dans le PDV.</span><span class="sxs-lookup"><span data-stu-id="6be27-137">Follow the steps in either of the following examples to view the allowed return tender types in POS.</span></span>

1. <span data-ttu-id="6be27-138">Connectez-vous au point de vente en tant que caissier ou gestionnaire.</span><span class="sxs-lookup"><span data-stu-id="6be27-138">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="6be27-139">Sous **Équipes et tiroirs-caisses**, sélectionnez **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="6be27-139">Under **Shift and Drawer**, select **Show journal**.</span></span>
3. <span data-ttu-id="6be27-140">Sélectionnez la transaction qui fait partie du retour.</span><span class="sxs-lookup"><span data-stu-id="6be27-140">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="6be27-141">Sélectionnez les articles à rembourser et choisissez le mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="6be27-141">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="6be27-142">Si l'offre de paiement sélectionnée figure dans la liste autorisée des types d'offre de retour, le caissier peut terminer la transaction.</span><span class="sxs-lookup"><span data-stu-id="6be27-142">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="6be27-143">Si l'offre de paiement sélectionnée n'est pas autorisée, un message d'erreur s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6be27-143">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="6be27-144">Sélectionnez **Montant dû** pour afficher une liste de tous les types d'offre de retour autorisés.</span><span class="sxs-lookup"><span data-stu-id="6be27-144">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="6be27-145">- ou -</span><span class="sxs-lookup"><span data-stu-id="6be27-145">-or-</span></span>

1. <span data-ttu-id="6be27-146">Connectez-vous au point de vente en tant que caissier ou gestionnaire.</span><span class="sxs-lookup"><span data-stu-id="6be27-146">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="6be27-147">Sélectionnez **Transaction de retour** et saisissez l'ID du ticket de caisse à l'aide d'un scanner de codes-barres ou manuellement.</span><span class="sxs-lookup"><span data-stu-id="6be27-147">Select **Return Transaction** and enter the receipt ID using a barcode scan or by manual entry.</span></span> 
3. <span data-ttu-id="6be27-148">Sélectionnez la transaction qui fait partie du retour.</span><span class="sxs-lookup"><span data-stu-id="6be27-148">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="6be27-149">Sélectionnez les articles à rembourser et choisissez le mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="6be27-149">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="6be27-150">Si l'offre de paiement sélectionnée figure dans la liste autorisée des types d'offre de retour, le caissier peut terminer la transaction.</span><span class="sxs-lookup"><span data-stu-id="6be27-150">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="6be27-151">Si l'offre de paiement sélectionnée n'est pas autorisée, un message d'erreur s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6be27-151">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="6be27-152">Sélectionnez **Montant dû** pour afficher une liste de tous les types d'offre de retour autorisés.</span><span class="sxs-lookup"><span data-stu-id="6be27-152">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="6be27-153">![Remboursement non autorisé](media/Return-policy-page6.png "Type de remboursement non autorisé")</span><span class="sxs-lookup"><span data-stu-id="6be27-153">![Refund not allowed](media/Return-policy-page6.png "Refund type not allowed")</span></span>



<span data-ttu-id="6be27-154">![Liste des modes de paiement](media/Return-policy-page5.PNG "Types de remboursement autorisés")</span><span class="sxs-lookup"><span data-stu-id="6be27-154">![List of payment methods](media/Return-policy-page5.PNG "Refund types allowed")</span></span>
