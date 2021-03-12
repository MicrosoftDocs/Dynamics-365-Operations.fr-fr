---
title: Créer un client par défaut
description: Cette rubrique décrit comment créer un client par défaut à utiliser lors de la création d'un canal dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 1dd4dfc5b8ca7af66941d081b4c20be0f5d6001d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993398"
---
# <a name="create-a-default-customer"></a><span data-ttu-id="3ad4a-103">Créer un client par défaut</span><span class="sxs-lookup"><span data-stu-id="3ad4a-103">Create a default customer</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3ad4a-104">Cette rubrique décrit comment créer un client par défaut à utiliser lors de la création d'un canal dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-104">This topic describes how to create a default customer to use when creating a channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3ad4a-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="3ad4a-105">Overview</span></span>

<span data-ttu-id="3ad4a-106">Lors de la création d'un canal, vous devrez indiquer un client par défaut.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-106">When creating a channel, you will need to provide a default customer.</span></span> <span data-ttu-id="3ad4a-107">Un client par défaut peut facilement être créé après avoir d'abord créé le groupe de clients et le carnet d'adresses client.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-107">A default customer can easily be created after first creating the customer group and customer address book.</span></span>

## <a name="create-a-customer-group"></a><span data-ttu-id="3ad4a-108">Création d'un groupe de clients</span><span class="sxs-lookup"><span data-stu-id="3ad4a-108">Create a customer group</span></span>

<span data-ttu-id="3ad4a-109">Si aucun groupe de clients n'existe encore, vous pouvez en créer.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-109">If no customer groups exist yet, you can create one.</span></span> <span data-ttu-id="3ad4a-110">Les exemples peuvent être des groupes pour représenter différents groupes de clients, tels que la vente en gros, la vente au détail, Internet, les employés, etc.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-110">Examples may be groups to represent different customer groups, such as wholesale, retail, Internet, Employees, etc.</span></span>

<span data-ttu-id="3ad4a-111">Pour créer un groupe de clients, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-111">To create a customer group, follow these steps.</span></span>

1. <span data-ttu-id="3ad4a-112">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Clients \> Groupes de clients**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-112">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> Customer groups**.</span></span>
1. <span data-ttu-id="3ad4a-113">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="3ad4a-114">Dans la zone **Groupe de clients**, entrez un ID groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-114">In the **Customer group** box, enter a customer group ID.</span></span>
1. <span data-ttu-id="3ad4a-115">Entrez une description adéquate dans la zone **Description**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-115">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="3ad4a-116">Entrez une valeur adéquate dans la zone **Conditions de paiement**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-116">In the **Terms of payment** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="3ad4a-117">Dans la zone **Intervalle entre la date d'échéance de la facture et le paiement**, entrez une valeur appropriée.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-117">In the **Time between invoice due date and payment date** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="3ad4a-118">Dans la zone **Groupe de taxes par défaut**, entrez un groupe de taxes, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-118">In the **Default tax group** box, enter a tax group if applicable.</span></span>
1. <span data-ttu-id="3ad4a-119">Cochez la case **Prix, taxe incluse** le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-119">Select the **Prices include sales tax** check box if applicable.</span></span>
1. <span data-ttu-id="3ad4a-120">Dans la zone **Motif d'annulation par défaut**, entrez une valeur appropriée, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-120">In the **Default write-off reason** box, enter an appropriate value, if applicable.</span></span>

<span data-ttu-id="3ad4a-121">L'image suivante montre plusieurs groupes de clients configurés.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-121">The following image shows several configured customer groups.</span></span>

![Groupes de clients](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a><span data-ttu-id="3ad4a-123">Créez un carnet d'adresses clients.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-123">Create a customer address book</span></span>

<span data-ttu-id="3ad4a-124">Un client doit être associé à un carnet d'adresses.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-124">A customer needs to be associated with an address book.</span></span> <span data-ttu-id="3ad4a-125">Si ça n'est pas déjà fait, vous devrez en créer un.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-125">If one has not yet been created, then you will need to create one.</span></span>

<span data-ttu-id="3ad4a-126">Pour créer un carnet d'adresses clients, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-126">To create a customer address book, follow these steps.</span></span>

1. <span data-ttu-id="3ad4a-127">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Carnets d'adresses**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-127">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Address Books**.</span></span>
1. <span data-ttu-id="3ad4a-128">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-128">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="3ad4a-129">Dans la zone **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-129">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="3ad4a-130">Entrez une description dans la zone **Description**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-130">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="3ad4a-131">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-131">On the action pane, select **Save**.</span></span>

<span data-ttu-id="3ad4a-132">L'image suivante présente un exemple de carnet d'adresses.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-132">The following image shows an example address book.</span></span>

![Carnet d'adresses](media/address-book.png)

## <a name="create-a-default-customer"></a><span data-ttu-id="3ad4a-134">Créer un client par défaut</span><span class="sxs-lookup"><span data-stu-id="3ad4a-134">Create a default customer</span></span>

<span data-ttu-id="3ad4a-135">Pour créer un client par défaut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-135">To create a default customer, follow these steps.</span></span>

1. <span data-ttu-id="3ad4a-136">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Clients \> Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-136">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="3ad4a-137">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="3ad4a-138">Dans la liste déroulante **Type**, sélectionnez « Personne ».</span><span class="sxs-lookup"><span data-stu-id="3ad4a-138">In the **Type** drop-down list, select "Person".</span></span>
1. <span data-ttu-id="3ad4a-139">Dans la liste déroulante **Compte client**, sélectionnez ou entrez un numéro de compte (par exemple, « 100001 »).</span><span class="sxs-lookup"><span data-stu-id="3ad4a-139">In the **Customer account** drop-down list, select or enter an account number (for example, "100001").</span></span>
1. <span data-ttu-id="3ad4a-140">Dans la liste déroulante **Prénom**, sélectionnez ou entrez un nom (par exemple, « Par défaut »).</span><span class="sxs-lookup"><span data-stu-id="3ad4a-140">In the **First name** drop-down list, select or enter a name (for example, "Default").</span></span>
1. <span data-ttu-id="3ad4a-141">Dans la liste déroulante **Deuxième prénom**, sélectionnez ou entrez un nom (par exemple, « Vente au détail »).</span><span class="sxs-lookup"><span data-stu-id="3ad4a-141">In the **Middle name** drop-down list, select or enter a name (for example, "Retail").</span></span>
1. <span data-ttu-id="3ad4a-142">Dans la liste déroulante **Nom**, sélectionnez ou entrez un nom (par exemple, « Client »).</span><span class="sxs-lookup"><span data-stu-id="3ad4a-142">In the **Last name** drop-down list, select or enter a name (for example, "Customer").</span></span>
1. <span data-ttu-id="3ad4a-143">Dans la liste déroulante **Devise**, sélectionnez ou entrez une devise (par exemple, « USD »).</span><span class="sxs-lookup"><span data-stu-id="3ad4a-143">In the **Currency** drop-down list, select or enter a currency (for example, "USD").</span></span>
1. <span data-ttu-id="3ad4a-144">Dans la liste déroulante **Devise**, sélectionnez le groupe de clients créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-144">In the **Currency** drop-down list, select the customer group created previously.</span></span>
1. <span data-ttu-id="3ad4a-145">Dans la liste déroulante **Carnets d'adresses**, sélectionnez un carnet d'adresses client existant.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-145">In the **Address books**  drop-down list, select an existing customer address book.</span></span>
1. <span data-ttu-id="3ad4a-146">Sélectionnez **Sauvegarder** pour enregistrer et revenir à l'écran des détails du client pour le nouveau client.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-146">Select **Save** to save and return to customer details screen for the new customer.</span></span>

> [!NOTE]
> <span data-ttu-id="3ad4a-147">Il n'est pas nécessaire d'ajouter une adresse pour un client par défaut.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-147">It is not necessary to add an address for a default customer.</span></span>

<span data-ttu-id="3ad4a-148">L'image suivant présente un exemple de création de client.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-148">The following image shows an example of customer creation.</span></span>

![Création de client par défaut](media/default-customer-creation.png)

<span data-ttu-id="3ad4a-150">L'image suivante montre une configuration client par défaut.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-150">The following image shows a default customer configuration.</span></span>

![Exemple de configuration client](media/default-customer-configuration1.png)

<span data-ttu-id="3ad4a-152">La plupart des valeurs par défaut sur l'écran des détails client peuvent rester, mais deux valeurs doivent être modifiées.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-152">Most of the default values on the customer detials screen can remain, but two values should be changed.</span></span>

1. <span data-ttu-id="3ad4a-153">Sur l'écran des détails du client, développez **Valeurs par défaut de commande client**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-153">On the customer details screen, expand **Sales order defaults**.</span></span>
1. <span data-ttu-id="3ad4a-154">Dans la liste déroulante **Site**, sélectionnez ou entrez un site préconfiguré.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-154">In the **Site** drop-down list, select or enter a pre-configured site.</span></span>
1. <span data-ttu-id="3ad4a-155">Dans la liste déroulante **Entrepôt**, sélectionnez ou entrez un entrepôt préconfiguré.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-155">In the **Warehouse** drop-down list, and select or enter a pre-configured warehouse.</span></span>

<span data-ttu-id="3ad4a-156">L'image suivant présente un exemple de configuration client.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-156">The following image shows an example customer configuration.</span></span>

![Exemple de configuration client](media/default-customer-configuration2.png)

## <a name="additional-resources"></a><span data-ttu-id="3ad4a-158">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3ad4a-158">Additional resources</span></span>

[<span data-ttu-id="3ad4a-159">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="3ad4a-159">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="3ad4a-160">Conditions préalables au paramétrage du canal</span><span class="sxs-lookup"><span data-stu-id="3ad4a-160">Channel setup prerequisites</span></span>](channels-prerequisites.md)
