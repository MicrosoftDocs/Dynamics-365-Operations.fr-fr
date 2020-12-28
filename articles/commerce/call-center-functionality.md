---
title: Fonctionnalité de vente du centre d'appels
description: Cette rubrique fournit une vue d'ensemble de la fonctionnalité de vente du centre d'appels dans Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 7091e8ba7940e358d77c69c63e26c8f3d9337713
ms.sourcegitcommit: 4c6d31f3ebd88212d3d1497a4bba9c64c5300444
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2020
ms.locfileid: "4412414"
---
# <a name="call-center-sales-functionality"></a><span data-ttu-id="b0a92-103">Fonctionnalité de vente du centre d'appels</span><span class="sxs-lookup"><span data-stu-id="b0a92-103">Call center sales functionality</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="b0a92-104">Dans Dynamics 365 Commerce, un centre d'appels est un type de canal qui peut être défini dans l'application.</span><span class="sxs-lookup"><span data-stu-id="b0a92-104">In Dynamics 365 Commerce, a call center is a type of channel that can be defined in the application.</span></span> <span data-ttu-id="b0a92-105">La définition d'un canal spécifique pour vos entités de centre d'appels permet au système d'associer les valeurs par défaut de données spécifiques et les valeurs par défaut du traitement des commandes aux commandes client créées par un utilisateur du canal de centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="b0a92-105">Defining a specific channel for your call center entities allows the system to tie specific data defaults and order processing defaults to sales orders created by a user of the call center channel.</span></span>

<span data-ttu-id="b0a92-106">Les fonctionnalités du centre d'appels comprennent les prix et les promotions avancés, les catalogues, les cartes cadeaux, les programmes de fidélité et les coupons.</span><span class="sxs-lookup"><span data-stu-id="b0a92-106">Call center features include advanced price and promotions, catalogs, gift cards, loyalty programs, and coupons.</span></span> <span data-ttu-id="b0a92-107">Les commandes du centre d'appels sont également utilisées par l'application POS pour prendre en charge les scénarios d'exécution des commandes sur plusieurs canaux.</span><span class="sxs-lookup"><span data-stu-id="b0a92-107">Call center orders are also leveraged by the point of sale (POS) application to support cross-channel order fulfillment scenarios.</span></span>

<span data-ttu-id="b0a92-108">Il est important de noter que le module Centre d'appels peut être utilisé par d'autres secteurs d'activité en dehors de Commerce, mais la version actuelle de l'application de centre d'appels n'a pas été optimisée pour une utilisation dans les scénarios de traitement des commandes interentreprises (B2B), ou les scénarios où les commandes contiennent un grand nombre de lignes de vente.</span><span class="sxs-lookup"><span data-stu-id="b0a92-108">It's important to note that while the call center module can be utilized by other industries outside of Commerce, the current release of the call center application hasn't been optimized for use in business-to-business (B2B) order processing scenarios, or scenarios where orders have a large number of sales lines.</span></span> <span data-ttu-id="b0a92-109">Il est recommandé aux utilisateurs qui souhaitent utiliser les fonctionnalités du centre d'appels pour le traitement des commandes en dehors du traitement standard des transactions destinées directement aux consommateurs, de prendre le temps nécessaire de tester et de valider que l'activation de la fonctionnalité de centre d'appels répond aux besoins fonctionnels et de performances.</span><span class="sxs-lookup"><span data-stu-id="b0a92-109">It's recommended that users who want to utilize the call center features for order processing outside of typical direct-to-consumer transaction processing, take adequate time to test and validate that enabling call center functionality will meet functional and performance needs.</span></span>

<span data-ttu-id="b0a92-110">Outre la prise en charge de la création des commandes, le module Centre d'appels fournit également une application de service client conviviale qui permet aux utilisateurs de localiser facilement les comptes client et d'examiner l'ensemble des données et attributs de commande client associés.</span><span class="sxs-lookup"><span data-stu-id="b0a92-110">In addition to supporting order creation, the call center module also provides a user-friendly customer service application that makes it easier for users to locate customer accounts and review all of the related customer order data and attributes.</span></span> <span data-ttu-id="b0a92-111">L'écran du service client est conçu pour permettre à un utilisateur d'accéder rapidement aux données associées aux commandes afin de répondre aux questions les plus courantes transmises par les clients.</span><span class="sxs-lookup"><span data-stu-id="b0a92-111">The customer service screen is designed to enable a user to quickly access order-related data that will allow them to answer the most common order-related questions received from customers.</span></span>

<span data-ttu-id="b0a92-112">Cette page fournit des liens vers la documentation appropriée associée au paramétrage, à la configuration et à l'utilisation fonctionnelle des fonctionnalités du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="b0a92-112">This page provides links to relevant documentation related to the setup, configuration, and functional use of the call center features.</span></span>


## <a name="configure-the-call-center"></a><span data-ttu-id="b0a92-113">Configurer le centre d'appels</span><span class="sxs-lookup"><span data-stu-id="b0a92-113">Configure the call center</span></span>

[<span data-ttu-id="b0a92-114">Paramétrer des canaux de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="b0a92-114">Set up call center channels</span></span>](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a><span data-ttu-id="b0a92-115">Configurer le traitement des commandes</span><span class="sxs-lookup"><span data-stu-id="b0a92-115">Configure order processing</span></span>

[<span data-ttu-id="b0a92-116">Paramétrer et utiliser les alertes pour fraude dans le centre d'appels</span><span class="sxs-lookup"><span data-stu-id="b0a92-116">Set up and work with call center fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="b0a92-117">Configurer et utiliser les blocages de commande dans le centre d'appels</span><span class="sxs-lookup"><span data-stu-id="b0a92-117">Configure and work with call center order holds</span></span>](work-with-order-holds.md)

## <a name="configure-payment-processing"></a><span data-ttu-id="b0a92-118">Configurer le traitement des paiements</span><span class="sxs-lookup"><span data-stu-id="b0a92-118">Configure payment processing</span></span>

[<span data-ttu-id="b0a92-119">Modes de paiement dans les centres d'appels</span><span class="sxs-lookup"><span data-stu-id="b0a92-119">Payment methods in call centers</span></span>](work-with-payments.md)

## <a name="configure-delivery-modes"></a><span data-ttu-id="b0a92-120">Configurer les modes de livraison</span><span class="sxs-lookup"><span data-stu-id="b0a92-120">Configure delivery modes</span></span>

[<span data-ttu-id="b0a92-121">Configurer les modes de livraison et les frais du centre d'appels</span><span class="sxs-lookup"><span data-stu-id="b0a92-121">Configure call center delivery modes and charges</span></span>](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a><span data-ttu-id="b0a92-122">Configurer le marketing direct</span><span class="sxs-lookup"><span data-stu-id="b0a92-122">Configure direct marketing</span></span>

[<span data-ttu-id="b0a92-123">Catalogues de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="b0a92-123">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="b0a92-124">Paramétrer l'analyse RFM (récence, fréquence et valeur monétaire)</span><span class="sxs-lookup"><span data-stu-id="b0a92-124">Set up Recency, Frequency, and Monetary (RFM) analysis</span></span>](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a><span data-ttu-id="b0a92-125">Configurer les programmes de continuité</span><span class="sxs-lookup"><span data-stu-id="b0a92-125">Configure continuity programs</span></span>

[<span data-ttu-id="b0a92-126">Paramétrer des programmes périodiques pour les centres d'appels</span><span class="sxs-lookup"><span data-stu-id="b0a92-126">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
