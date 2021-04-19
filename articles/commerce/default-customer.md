---
title: Créer un client par défaut
description: Cette rubrique décrit comment créer un client par défaut à utiliser lors de la création d’un canal dans Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ecdf4e5618d3397527bf83977857fbe3f8dbb265
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799177"
---
# <a name="create-a-default-customer"></a><span data-ttu-id="c9e17-103">Créer un client par défaut</span><span class="sxs-lookup"><span data-stu-id="c9e17-103">Create a default customer</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c9e17-104">Cette rubrique décrit comment créer un client par défaut à utiliser lors de la création d’un canal dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c9e17-104">This topic describes how to create a default customer to use when creating a channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c9e17-105">Lors de la création d’un canal, vous devrez indiquer un client par défaut.</span><span class="sxs-lookup"><span data-stu-id="c9e17-105">When creating a channel, you will need to provide a default customer.</span></span> <span data-ttu-id="c9e17-106">Un client par défaut peut facilement être créé après avoir d’abord créé le groupe de clients et le carnet d’adresses client.</span><span class="sxs-lookup"><span data-stu-id="c9e17-106">A default customer can easily be created after first creating the customer group and customer address book.</span></span>

## <a name="create-a-customer-group"></a><span data-ttu-id="c9e17-107">Création d’un groupe de clients</span><span class="sxs-lookup"><span data-stu-id="c9e17-107">Create a customer group</span></span>

<span data-ttu-id="c9e17-108">Si aucun groupe de clients n’existe encore, vous pouvez en créer.</span><span class="sxs-lookup"><span data-stu-id="c9e17-108">If no customer groups exist yet, you can create one.</span></span> <span data-ttu-id="c9e17-109">Les exemples peuvent être des groupes pour représenter différents groupes de clients, tels que la vente en gros, la vente au détail, Internet, les employés, etc.</span><span class="sxs-lookup"><span data-stu-id="c9e17-109">Examples may be groups to represent different customer groups, such as wholesale, retail, Internet, Employees, etc.</span></span>

<span data-ttu-id="c9e17-110">Pour créer un groupe de clients, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c9e17-110">To create a customer group, follow these steps.</span></span>

1. <span data-ttu-id="c9e17-111">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Clients \> Groupes de clients**.</span><span class="sxs-lookup"><span data-stu-id="c9e17-111">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> Customer groups**.</span></span>
1. <span data-ttu-id="c9e17-112">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c9e17-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c9e17-113">Dans la zone **Groupe de clients**, entrez un ID groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="c9e17-113">In the **Customer group** box, enter a customer group ID.</span></span>
1. <span data-ttu-id="c9e17-114">Entrez une description adéquate dans la zone **Description**.</span><span class="sxs-lookup"><span data-stu-id="c9e17-114">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="c9e17-115">Entrez une valeur adéquate dans la zone **Conditions de paiement**.</span><span class="sxs-lookup"><span data-stu-id="c9e17-115">In the **Terms of payment** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="c9e17-116">Dans la zone **Intervalle entre la date d’échéance de la facture et le paiement**, entrez une valeur appropriée.</span><span class="sxs-lookup"><span data-stu-id="c9e17-116">In the **Time between invoice due date and payment date** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="c9e17-117">Dans la zone **Groupe de taxes par défaut**, entrez un groupe de taxes, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="c9e17-117">In the **Default tax group** box, enter a tax group if applicable.</span></span>
1. <span data-ttu-id="c9e17-118">Cochez la case **Prix, taxe incluse** le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="c9e17-118">Select the **Prices include sales tax** check box if applicable.</span></span>
1. <span data-ttu-id="c9e17-119">Dans la zone **Motif d’annulation par défaut**, entrez une valeur appropriée, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="c9e17-119">In the **Default write-off reason** box, enter an appropriate value, if applicable.</span></span>

<span data-ttu-id="c9e17-120">L’image suivante montre plusieurs groupes de clients configurés.</span><span class="sxs-lookup"><span data-stu-id="c9e17-120">The following image shows several configured customer groups.</span></span>

![Groupes de clients](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a><span data-ttu-id="c9e17-122">Créez un carnet d’adresses clients.</span><span class="sxs-lookup"><span data-stu-id="c9e17-122">Create a customer address book</span></span>

<span data-ttu-id="c9e17-123">Un client doit être associé à un carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="c9e17-123">A customer needs to be associated with an address book.</span></span> <span data-ttu-id="c9e17-124">Si ça n’est pas déjà fait, vous devrez en créer un.</span><span class="sxs-lookup"><span data-stu-id="c9e17-124">If one has not yet been created, then you will need to create one.</span></span>

<span data-ttu-id="c9e17-125">Pour créer un carnet d’adresses clients, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c9e17-125">To create a customer address book, follow these steps.</span></span>

1. <span data-ttu-id="c9e17-126">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Carnets d’adresses**.</span><span class="sxs-lookup"><span data-stu-id="c9e17-126">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Address Books**.</span></span>
1. <span data-ttu-id="c9e17-127">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c9e17-127">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c9e17-128">Dans la zone **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="c9e17-128">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="c9e17-129">Entrez une description dans la zone **Description**.</span><span class="sxs-lookup"><span data-stu-id="c9e17-129">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="c9e17-130">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c9e17-130">On the action pane, select **Save**.</span></span>

<span data-ttu-id="c9e17-131">L’image suivante présente un exemple de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="c9e17-131">The following image shows an example address book.</span></span>

![Carnet d’adresses](media/address-book.png)

## <a name="create-a-default-customer"></a><span data-ttu-id="c9e17-133">Créer un client par défaut</span><span class="sxs-lookup"><span data-stu-id="c9e17-133">Create a default customer</span></span>

<span data-ttu-id="c9e17-134">Pour créer un client par défaut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c9e17-134">To create a default customer, follow these steps.</span></span>

1. <span data-ttu-id="c9e17-135">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Clients \> Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="c9e17-135">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="c9e17-136">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c9e17-136">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c9e17-137">Dans la liste déroulante **Type**, sélectionnez « Personne ».</span><span class="sxs-lookup"><span data-stu-id="c9e17-137">In the **Type** drop-down list, select "Person".</span></span>
1. <span data-ttu-id="c9e17-138">Dans la liste déroulante **Compte client**, sélectionnez ou entrez un numéro de compte (par exemple, « 100001 »).</span><span class="sxs-lookup"><span data-stu-id="c9e17-138">In the **Customer account** drop-down list, select or enter an account number (for example, "100001").</span></span>
1. <span data-ttu-id="c9e17-139">Dans la liste déroulante **Prénom**, sélectionnez ou entrez un nom (par exemple, « Par défaut »).</span><span class="sxs-lookup"><span data-stu-id="c9e17-139">In the **First name** drop-down list, select or enter a name (for example, "Default").</span></span>
1. <span data-ttu-id="c9e17-140">Dans la liste déroulante **Deuxième prénom**, sélectionnez ou entrez un nom (par exemple, « Vente au détail »).</span><span class="sxs-lookup"><span data-stu-id="c9e17-140">In the **Middle name** drop-down list, select or enter a name (for example, "Retail").</span></span>
1. <span data-ttu-id="c9e17-141">Dans la liste déroulante **Nom**, sélectionnez ou entrez un nom (par exemple, « Client »).</span><span class="sxs-lookup"><span data-stu-id="c9e17-141">In the **Last name** drop-down list, select or enter a name (for example, "Customer").</span></span>
1. <span data-ttu-id="c9e17-142">Dans la liste déroulante **Devise**, sélectionnez ou entrez une devise (par exemple, « USD »).</span><span class="sxs-lookup"><span data-stu-id="c9e17-142">In the **Currency** drop-down list, select or enter a currency (for example, "USD").</span></span>
1. <span data-ttu-id="c9e17-143">Dans la liste déroulante **Devise**, sélectionnez le groupe de clients créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="c9e17-143">In the **Currency** drop-down list, select the customer group created previously.</span></span>
1. <span data-ttu-id="c9e17-144">Dans la liste déroulante **Carnets d’adresses**, sélectionnez un carnet d’adresses client existant.</span><span class="sxs-lookup"><span data-stu-id="c9e17-144">In the **Address books**  drop-down list, select an existing customer address book.</span></span>
1. <span data-ttu-id="c9e17-145">Sélectionnez **Sauvegarder** pour enregistrer et revenir à l’écran des détails du client pour le nouveau client.</span><span class="sxs-lookup"><span data-stu-id="c9e17-145">Select **Save** to save and return to customer details screen for the new customer.</span></span>

> [!NOTE]
> <span data-ttu-id="c9e17-146">Il n’est pas nécessaire d’ajouter une adresse pour un client par défaut.</span><span class="sxs-lookup"><span data-stu-id="c9e17-146">It is not necessary to add an address for a default customer.</span></span>

<span data-ttu-id="c9e17-147">L’image suivant présente un exemple de création de client.</span><span class="sxs-lookup"><span data-stu-id="c9e17-147">The following image shows an example of customer creation.</span></span>

![Création de client par défaut](media/default-customer-creation.png)

<span data-ttu-id="c9e17-149">L’image suivante montre une configuration client par défaut.</span><span class="sxs-lookup"><span data-stu-id="c9e17-149">The following image shows a default customer configuration.</span></span>

![Exemple de configuration client](media/default-customer-configuration1.png)

<span data-ttu-id="c9e17-151">La plupart des valeurs par défaut sur l’écran des détails client peuvent rester, mais deux valeurs doivent être modifiées.</span><span class="sxs-lookup"><span data-stu-id="c9e17-151">Most of the default values on the customer detials screen can remain, but two values should be changed.</span></span>

1. <span data-ttu-id="c9e17-152">Sur l’écran des détails du client, développez **Valeurs par défaut de commande client**.</span><span class="sxs-lookup"><span data-stu-id="c9e17-152">On the customer details screen, expand **Sales order defaults**.</span></span>
1. <span data-ttu-id="c9e17-153">Dans la liste déroulante **Site**, sélectionnez ou entrez un site préconfiguré.</span><span class="sxs-lookup"><span data-stu-id="c9e17-153">In the **Site** drop-down list, select or enter a pre-configured site.</span></span>
1. <span data-ttu-id="c9e17-154">Dans la liste déroulante **Entrepôt**, sélectionnez ou entrez un entrepôt préconfiguré.</span><span class="sxs-lookup"><span data-stu-id="c9e17-154">In the **Warehouse** drop-down list, and select or enter a pre-configured warehouse.</span></span>

<span data-ttu-id="c9e17-155">L’image suivant présente un exemple de configuration client.</span><span class="sxs-lookup"><span data-stu-id="c9e17-155">The following image shows an example customer configuration.</span></span>

![Exemple de configuration client](media/default-customer-configuration2.png)

## <a name="additional-resources"></a><span data-ttu-id="c9e17-157">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c9e17-157">Additional resources</span></span>

[<span data-ttu-id="c9e17-158">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="c9e17-158">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="c9e17-159">Conditions préalables au paramétrage du canal</span><span class="sxs-lookup"><span data-stu-id="c9e17-159">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
