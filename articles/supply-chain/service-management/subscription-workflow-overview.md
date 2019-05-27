---
title: Vue d'ensemble du workflow de l'abonnement
description: Cette rubrique fournit une vue d'ensemble du workflow de l'abonnement.
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b5cff6910dcb273fc081443546676426387f6625
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566408"
---
# <a name="subscription-workflow-overview"></a><span data-ttu-id="e996a-103">Vue d'ensemble du workflow de l'abonnement</span><span class="sxs-lookup"><span data-stu-id="e996a-103">Subscription workflow overview</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e996a-104">Vous êtes l'administrateur des abonnements pour une société d'éclairage qui offre des abonnements pour la maintenance de rails de projecteurs.</span><span class="sxs-lookup"><span data-stu-id="e996a-104">You are the subscriptions administrator for a light company that offers subscriptions for lighting rig maintenance.</span></span> <span data-ttu-id="e996a-105">Un client contacte votre société pour acheter un abonnement annuel pour la maintenance de rails de projecteurs.</span><span class="sxs-lookup"><span data-stu-id="e996a-105">A customer contacts your company to purchase a yearly subscription for lighting rig maintenance.</span></span>

## <a name="setting-up-subscriptions"></a><span data-ttu-id="e996a-106">Paramétrage des abonnements</span><span class="sxs-lookup"><span data-stu-id="e996a-106">Setting up subscriptions</span></span>

<span data-ttu-id="e996a-107">Pour paramétrer un abonnement, vous devez tout d'abord créer un groupe d'abonnements pour le nouvel accord de service ou vérifier qu'un groupe d'abonnements existe.</span><span class="sxs-lookup"><span data-stu-id="e996a-107">To set up a subscription, you must first create a subscription group for the new service agreement or verify that a subscription group exists.</span></span> <span data-ttu-id="e996a-108">Si un groupe d'abonnements existe, vous devez le paramétrer pour envoyer une facture annuelle au client et régulariser le produit des ventes chaque mois de l'année.</span><span class="sxs-lookup"><span data-stu-id="e996a-108">If a subscription group exists, you must set it up to invoice the customer yearly and to accrue sales revenue every month of the year.</span></span> <span data-ttu-id="e996a-109">Pour plus d'informations sur la procédure de paramétrage des abonnements, voir [Paramétrer des groupes d'abonnements](set-up-subscription-groups.md).</span><span class="sxs-lookup"><span data-stu-id="e996a-109">For more information about how to set up subscriptions, see [Set up subscription groups](set-up-subscription-groups.md).</span></span>

<span data-ttu-id="e996a-110">Après la création du groupe d'abonnements, vous pouvez créer l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="e996a-110">After the subscription group is created, you can create the subscription.</span></span> <span data-ttu-id="e996a-111">Pour plus d'informations sur la création de services récurrents, voir [Création des services récurrents à partir d'un groupe d'abonnements](create-service-subscriptions-from-subscription-group.md).</span><span class="sxs-lookup"><span data-stu-id="e996a-111">For more information about how to create service subscriptions, see [Create service subscriptions from a subscription group](create-service-subscriptions-from-subscription-group.md).</span></span>

## <a name="create-and-modify-subscription-transactions"></a><span data-ttu-id="e996a-112">Création et modification de transactions d'abonnement</span><span class="sxs-lookup"><span data-stu-id="e996a-112">Create and modify subscription transactions</span></span>

<span data-ttu-id="e996a-113">Après avoir paramétré l'abonnement, vous créez la transaction de frais d'abonnement pour la première période de facturation, à savoir un an.</span><span class="sxs-lookup"><span data-stu-id="e996a-113">After you set up the subscription, you create the subscription fee transaction for the first invoicing period, which is one year.</span></span> <span data-ttu-id="e996a-114">Les transactions sont du type **Normal**.</span><span class="sxs-lookup"><span data-stu-id="e996a-114">The transactions are of the **Regular** type.</span></span> <span data-ttu-id="e996a-115">Par conséquent, vous pouvez uniquement créer des transactions d'abonnement dans lesquelles les dates de début et de fin correspondent aux périodes créées précédemment dans l'écran **Types de période**.</span><span class="sxs-lookup"><span data-stu-id="e996a-115">Therefore, you can only create subscription transactions where the from date and the to date correspond to periods that were previously created in the **Period types** form.</span></span> <span data-ttu-id="e996a-116">Pour plus d'informations les transactions de frais, voir [Créer des transactions de redevance](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="e996a-116">For more information about fee transactions, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="e996a-117">Après avoir paramétré l'abonnement pour votre client, vous vous rappelez que celui-ci a négocié une remise de 10 % sur tous les prix de la liste des offres de service.</span><span class="sxs-lookup"><span data-stu-id="e996a-117">After you set up the subscription for your customer, you remember that they have negotiated a 10 percent discount on all list prices for service offerings.</span></span> <span data-ttu-id="e996a-118">Ainsi, vous devez réduire le prix des frais de transaction que vous avez créés.</span><span class="sxs-lookup"><span data-stu-id="e996a-118">Therefore, you must reduce the price of the transaction fee that you created.</span></span>

<span data-ttu-id="e996a-119">Plus tard le même jour, votre contact client vous appelle pour dire que, bien que son employeur souhaite toujours l'accord de service pour le rail de projecteurs, il prévoit d'acquérir un nouveau rail de projecteurs au cours de l'année.</span><span class="sxs-lookup"><span data-stu-id="e996a-119">Later in the day, your customer contact calls to say that, although they still want the service agreement for the lighting rig, they plan to introduce a new lighting rig later in the year.</span></span> <span data-ttu-id="e996a-120">Il demande donc une maintenance uniquement jusqu'en octobre 2013.</span><span class="sxs-lookup"><span data-stu-id="e996a-120">Therefore, they only need maintenance coverage until October 2013.</span></span> <span data-ttu-id="e996a-121">Pour réduire le nombre de mois pour l'abonnement souscrit par le client, vous créez une nouvelle transaction de frais d'abonnement de type **Jours de réduction**.</span><span class="sxs-lookup"><span data-stu-id="e996a-121">To reduce the number of months for the customer’s subscription, you create a new subscription fee transaction of the **Reduction days** type.</span></span> <span data-ttu-id="e996a-122">Pour plus d'informations sur la réduction des jours, voir [Réduction des jours sur les frais d'abonnement](reduce-the-days-on-subscription-fees.md).</span><span class="sxs-lookup"><span data-stu-id="e996a-122">For more information about how to reduce days, see [Reduce the days on subscription fees](reduce-the-days-on-subscription-fees.md).</span></span>

## <a name="invoice-and-accrue-subscription-transactions"></a><span data-ttu-id="e996a-123">Facturation et provisionnement de transactions d'abonnement</span><span class="sxs-lookup"><span data-stu-id="e996a-123">Invoice and accrue subscription transactions</span></span>

<span data-ttu-id="e996a-124">Vous avez terminé de paramétrer l'abonnement et vous êtes prêt à envoyer la facture à votre client pour cet abonnement.</span><span class="sxs-lookup"><span data-stu-id="e996a-124">You have now finished setting up the subscription, and you are ready to invoice your customer for it.</span></span> <span data-ttu-id="e996a-125">Pour plus d'informations sur la facturation d'abonnements, voir [Facturation de transactions d'abonnement](invoice-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="e996a-125">For more information about how to invoice subscriptions, see [Invoice subscription transactions](invoice-subscription-transactions.md).</span></span>

<span data-ttu-id="e996a-126">Deux jours plus tard, votre client appelle pour dire que l'abonnement doit être facturé en dollars US et non en euros.</span><span class="sxs-lookup"><span data-stu-id="e996a-126">Two days later, your customer calls to say that the subscription should be invoiced in U.S. dollars, not Euros.</span></span> <span data-ttu-id="e996a-127">Vous créez donc un avoir et une transaction d'abonnement libellée dans la devise correcte.</span><span class="sxs-lookup"><span data-stu-id="e996a-127">Therefore, you create a credit note, and you also create a new subscription transaction in the correct currency.</span></span> <span data-ttu-id="e996a-128">Pour plus d'informations sur le crédit des transactions d'abonnements, voir [Crédit de transactions d'abonnement](credit-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="e996a-128">For more information about how to credit subscription transactions, see [Credit subscription transactions](credit-subscription-transactions.md).</span></span>

<span data-ttu-id="e996a-129">À la fin de chaque mois, vous provisionnez le produit d'un mois de l'abonnement du client sur le compte de résultat et sur les comptes des travaux en cours.</span><span class="sxs-lookup"><span data-stu-id="e996a-129">At the end of each month, one month's revenue can be accrued from the customer's subscription to the profit and loss account and the WIP accounts.</span></span> <span data-ttu-id="e996a-130">Pour plus d'informations sur le produit à recevoir pour les abonnements, voir [Provisionner le produit d'abonnement](accrue-subscription-revenue.md).</span><span class="sxs-lookup"><span data-stu-id="e996a-130">For more information about how to accrue revenue for subscriptions, see [Accrue subscription revenue](accrue-subscription-revenue.md).</span></span>

  


