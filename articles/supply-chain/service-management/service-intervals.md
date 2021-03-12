---
title: Intervalles de services
description: L'intervalle de services indique la fréquence de création des lignes de commande de service pour les lignes d'accord de service lorsque vous créez des commandes de service.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b14061d5356cd61ab8cb1b1b2fbba859c16f904
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974408"
---
# <a name="service-intervals"></a><span data-ttu-id="7c958-103">Intervalles de services</span><span class="sxs-lookup"><span data-stu-id="7c958-103">Service intervals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7c958-104">L'intervalle d'accords de service indique la fréquence de création des lignes de commande de service pour les lignes d'accord de service lorsque vous créez automatiquement des commandes de service.</span><span class="sxs-lookup"><span data-stu-id="7c958-104">The service agreement interval indicates the frequency with which service order lines are created for service agreement lines when you create service orders automatically.</span></span>

<span data-ttu-id="7c958-105">Dans ce dernier cas de figure, les lignes de commande de service sont créées en fonction de l'intervalle spécifié pour la ligne d'accord de service à partir de la date de début de la ligne d'accord.</span><span class="sxs-lookup"><span data-stu-id="7c958-105">When you create service orders automatically, service order lines are created according to the interval that you have specified for the service agreement line from the start date of the agreement line.</span></span>

<span data-ttu-id="7c958-106">Si le champ **Intervalle** de la ligne d'accord de service dans la page **Accords de service** est vide, la ligne est un événement unique et ne permet pas de créer des commandes de service de manière répétée.</span><span class="sxs-lookup"><span data-stu-id="7c958-106">If the **Interval** field of a service agreement line in the **Service agreements** page is blank, the line is a one-time event, and it is not used to create service orders repeatedly.</span></span>

## <a name="example"></a><span data-ttu-id="7c958-107">Exemple</span><span class="sxs-lookup"><span data-stu-id="7c958-107">Example</span></span>

<span data-ttu-id="7c958-108">Cet exemple illustre la manière dont un intervalle de services affecte les lignes d'accord de service et les lignes de commande de service sur une commande de service.</span><span class="sxs-lookup"><span data-stu-id="7c958-108">This example illustrates how a service interval will affect service agreement lines and service order lines on a service order.</span></span>

### <a name="create-a-service-agreement"></a><span data-ttu-id="7c958-109">Créer un accord de service</span><span class="sxs-lookup"><span data-stu-id="7c958-109">Create a service agreement</span></span>

<span data-ttu-id="7c958-110">Commencez par créer un accord de service, puis définissez l'option **Combiner les commandes de service** sur **Par accord de service**.</span><span class="sxs-lookup"><span data-stu-id="7c958-110">First, you create a service agreement and set the **Combine service orders** option to **By service agreement**.</span></span>

1. <span data-ttu-id="7c958-111">Cliquez sur **Accords de service**</span><span class="sxs-lookup"><span data-stu-id="7c958-111">Click **Service agreements**</span></span>
2. <span data-ttu-id="7c958-112">Dans le **volet Actions**, sous l'onglet **Accord de service**, dans le groupe **Nouveau**, cliquez sur **Accord de service** pour créer un accord de service.</span><span class="sxs-lookup"><span data-stu-id="7c958-112">On the **Action Pane**, on the **Service agreement** tab, in the **New** group, click **Service agreement** to create a new service agreement.</span></span>
3. <span data-ttu-id="7c958-113">Saisissez une description, sélectionnez un projet dans le champ **ID projet**, puis entrez une date dans le champ **Date de début**.</span><span class="sxs-lookup"><span data-stu-id="7c958-113">Enter a description, select a project in the **Project ID** field, and enter a date in the **Start date** field.</span></span>
4. <span data-ttu-id="7c958-114">Dans le champ **Combiner les commandes de service**, sélectionnez **Par accord de service**.</span><span class="sxs-lookup"><span data-stu-id="7c958-114">In the **Combine service orders** field, select **By service agreement**.</span></span>

<span data-ttu-id="7c958-115">Vous avez créé l'accord de service suivant :</span><span class="sxs-lookup"><span data-stu-id="7c958-115">You have now created the following service agreement:</span></span>

| <span data-ttu-id="7c958-116">Projet</span><span class="sxs-lookup"><span data-stu-id="7c958-116">Project</span></span>      | <span data-ttu-id="7c958-117">Date de début</span><span class="sxs-lookup"><span data-stu-id="7c958-117">Start date</span></span>                                                                         |
|--------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="7c958-118">Votre projet</span><span class="sxs-lookup"><span data-stu-id="7c958-118">Your project</span></span> | <span data-ttu-id="7c958-119">Date spécifiée pour le projet.</span><span class="sxs-lookup"><span data-stu-id="7c958-119">The date you specified for the project.</span></span> <span data-ttu-id="7c958-120">Dans cet exemple, la date du jour est utilisée.</span><span class="sxs-lookup"><span data-stu-id="7c958-120">In this example, the current date is used.</span></span> |

### <a name="create-a-service-agreement-line"></a><span data-ttu-id="7c958-121">Créer une ligne d'accord de service</span><span class="sxs-lookup"><span data-stu-id="7c958-121">Create a service agreement line</span></span>

<span data-ttu-id="7c958-122">Créez ensuite une ligne d'accord de service dont le type de transaction est **Heure**.</span><span class="sxs-lookup"><span data-stu-id="7c958-122">Next, you create a service agreement line that has the transaction type **Hour**.</span></span>

<span data-ttu-id="7c958-123">Pour terminer cette partie de l'exemple, vous devez créer un intervalle de services de 10 jours dans la page **Intervalles de services**.</span><span class="sxs-lookup"><span data-stu-id="7c958-123">To complete this part of the example, you must create a service interval of 10 days in the **Service intervals** page.</span></span> 

1. <span data-ttu-id="7c958-124">Sélectionnez l'accord de service que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="7c958-124">Select the service agreement that you just created.</span></span> 
2. <span data-ttu-id="7c958-125">Dans l'organisateur **Lignes**, cliquez sur le bouton **Ajouter** pour créer une ligne dans le volet inférieur de la page **Accords de service**.</span><span class="sxs-lookup"><span data-stu-id="7c958-125">On the **Lines** FastTab, click the **Add** button to create a new line in the lower pane of the **Service agreements** page.</span></span>
3. <span data-ttu-id="7c958-126">Dans le champ **Type de transaction**, sélectionnez **Heure**.</span><span class="sxs-lookup"><span data-stu-id="7c958-126">In the **Transaction type** field, select **Hour**.</span></span>
4. <span data-ttu-id="7c958-127">Dans le champ **Collaborateur**, sélectionnez le collaborateur qui fournira le service.</span><span class="sxs-lookup"><span data-stu-id="7c958-127">In the **Worker** field, select the worker who will deliver the service.</span></span>
5. <span data-ttu-id="7c958-128">Dans le champ **Intervalle de services**, sélectionnez l'intervalle de 10 jours.</span><span class="sxs-lookup"><span data-stu-id="7c958-128">In the **Service interval** field, select the 10 days interval.</span></span>

<span data-ttu-id="7c958-129">Vous avez créé une ligne d'accord de service avec les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7c958-129">You have now created a service agreement line with the following information:</span></span>

| <span data-ttu-id="7c958-130">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="7c958-130">Transaction type</span></span> | <span data-ttu-id="7c958-131">Date de début</span><span class="sxs-lookup"><span data-stu-id="7c958-131">Start date</span></span>                               | <span data-ttu-id="7c958-132">Intervalle de services</span><span class="sxs-lookup"><span data-stu-id="7c958-132">Service interval</span></span> |
|------------------|------------------------------------------|------------------|
| <span data-ttu-id="7c958-133">Heure</span><span class="sxs-lookup"><span data-stu-id="7c958-133">Hour</span></span>             | <span data-ttu-id="7c958-134">Date du jour.</span><span class="sxs-lookup"><span data-stu-id="7c958-134">The current date.</span></span>                        | <span data-ttu-id="7c958-135">Tous les 10 jours</span><span class="sxs-lookup"><span data-stu-id="7c958-135">Every 10 days</span></span>    |
| <span data-ttu-id="7c958-136">Travailleur</span><span class="sxs-lookup"><span data-stu-id="7c958-136">Worker</span></span>           | <span data-ttu-id="7c958-137">Travailleur qui exécute le service.</span><span class="sxs-lookup"><span data-stu-id="7c958-137">The worker who will perform the service.</span></span> |                  |

<span data-ttu-id="7c958-138">Aucune fenêtre Délai n'est spécifiée pour la ligne.</span><span class="sxs-lookup"><span data-stu-id="7c958-138">There is no time window specified for the line.</span></span> 

### <a name="create-planned-service-orders"></a><span data-ttu-id="7c958-139">Création de commandes de service prévisionnelles</span><span class="sxs-lookup"><span data-stu-id="7c958-139">Create planned service orders</span></span>

<span data-ttu-id="7c958-140">Vous pouvez maintenant créer des commandes de service prévisionnelles et des lignes de commande de service pour le mois prochain.</span><span class="sxs-lookup"><span data-stu-id="7c958-140">You can now create planned service orders and service order lines for the coming month.</span></span>

1. <span data-ttu-id="7c958-141">Dans la page **Accords de service**, dans le **volet Actions**, sous l'onglet **Livrer**, cliquez sur **Commandes de service prévisionnelles**.</span><span class="sxs-lookup"><span data-stu-id="7c958-141">In the **Service agreements** page, on the **Action Pane**, on the **Deliver** tab, click **Planned service orders**.</span></span>
2. <span data-ttu-id="7c958-142">Dans la page **Créer des commandes de service**, entrez la date du jour dans le champ **Date de début** et une date correspondant à un mois à partir de la date du jour dans le champ **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="7c958-142">In the **Create service orders** page, enter the current date in the **From date** field and a date that is one month from the current date in the **To date** field.</span></span>
3. <span data-ttu-id="7c958-143">Définissez le curseur **Heure** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="7c958-143">Set the **Hour** slider to **Yes**.</span></span> 
4. <span data-ttu-id="7c958-144">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c958-144">Click **OK**.</span></span>

<span data-ttu-id="7c958-145">Comme il n'existe aucun regroupement sur la commande de service (définie par l'option **Par accord de service** du champ **Combiner les commandes de service**), une seule ligne de commande de service est créée par commande de service.</span><span class="sxs-lookup"><span data-stu-id="7c958-145">Because there is no grouping on the service order (defined by the **By service agreement** option in the **Combine service orders** field), one service order line is created per service order.</span></span>

### <a name="service-orders-created"></a><span data-ttu-id="7c958-146">Commandes de service créées</span><span class="sxs-lookup"><span data-stu-id="7c958-146">Service orders created</span></span>

<span data-ttu-id="7c958-147">Trois lignes de commande de service ont été créées dans le délai spécifié dans la boîte de dialogue **Créer des commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="7c958-147">Three service order lines have been created within the time frame that you specified in the **Create service orders** dialog box.</span></span> <span data-ttu-id="7c958-148">Vous pouvez afficher les lignes d'accord de service dans la page **Accords de service** (**volet Actions** \> **onglet Livrer** \>**bouton Afficher**).</span><span class="sxs-lookup"><span data-stu-id="7c958-148">You can view the service order lines in the **Service agreements** page (**Action Pane** \> **Deliver** tab \>**View** button).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7c958-149">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="7c958-149">Related topics</span></span>

[<span data-ttu-id="7c958-150">Paramétrage des intervalles de services</span><span class="sxs-lookup"><span data-stu-id="7c958-150">Set up service intervals</span></span>](set-up-service-intervals.md)  

