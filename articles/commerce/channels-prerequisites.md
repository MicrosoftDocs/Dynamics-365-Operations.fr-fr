---
title: Conditions préalables au paramétrage du canal
description: Cette rubrique présente une vue d’ensemble des conditions préalables au paramétrage des canaux dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 02/21/2020
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
ms.openlocfilehash: 270f751e860e56a03e20df720c088f275d0298e7
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477922"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="55f92-103">Conditions préalables à la configuration de canal</span><span class="sxs-lookup"><span data-stu-id="55f92-103">Channel setup prerequisites</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="55f92-104">Cette rubrique présente une vue d’ensemble des conditions préalables au paramétrage de canal dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="55f92-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="55f92-105">Avant qu'un canal Dynamics 365 Commerce puisse être créé, plusieurs tâches prérequises doivent être effectuées.</span><span class="sxs-lookup"><span data-stu-id="55f92-105">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="55f92-106">Les listes de tâches prérequises suivantes sont organisées par type de canal.</span><span class="sxs-lookup"><span data-stu-id="55f92-106">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="55f92-107">Certains documents sont en cours de rédaction et les liens seront mis à jour au fur et à mesure que de nouveaux contenus seront publiés.</span><span class="sxs-lookup"><span data-stu-id="55f92-107">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="55f92-108">Initialisation</span><span class="sxs-lookup"><span data-stu-id="55f92-108">Initialization</span></span>

- [<span data-ttu-id="55f92-109">Initialiser les données de départ</span><span class="sxs-lookup"><span data-stu-id="55f92-109">Initialize seed data</span></span>](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="55f92-110">Prérequis globaux requis pour tous les types de canaux</span><span class="sxs-lookup"><span data-stu-id="55f92-110">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="55f92-111">Définissez et configurez votre structure d'entité juridique</span><span class="sxs-lookup"><span data-stu-id="55f92-111">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="55f92-112">Configurer votre hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="55f92-112">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="55f92-113">Paramétrer un entrepôt</span><span class="sxs-lookup"><span data-stu-id="55f92-113">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="55f92-114">Configurer la taxe de vente</span><span class="sxs-lookup"><span data-stu-id="55f92-114">Configure sales tax</span></span>](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="55f92-115">Paramétrer un profil de notification par e-mail</span><span class="sxs-lookup"><span data-stu-id="55f92-115">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="55f92-116">Définir des souches de numéros</span><span class="sxs-lookup"><span data-stu-id="55f92-116">Set up number sequences</span></span>](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="55f92-117">Paramétrer un client et un carnet d'adresses par défaut</span><span class="sxs-lookup"><span data-stu-id="55f92-117">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="55f92-118">Conditions préalables du canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="55f92-118">Retail channel prerequisites</span></span>

- [<span data-ttu-id="55f92-119">Codes info et groupes de codes info</span><span class="sxs-lookup"><span data-stu-id="55f92-119">Info codes and info code groups</span></span>](info-codes-retail.md)
- [<span data-ttu-id="55f92-120">Paramétrer un profil de fonctionnalité de la vente au détail</span><span class="sxs-lookup"><span data-stu-id="55f92-120">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="55f92-121">Paramétrer un carnet d'adresses d'employé</span><span class="sxs-lookup"><span data-stu-id="55f92-121">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="55f92-122">Paramétrer une mise en page d'écran</span><span class="sxs-lookup"><span data-stu-id="55f92-122">Set up a screen layout</span></span>](pos-screen-layouts.md)
- [<span data-ttu-id="55f92-123">Paramétrer une station matérielle</span><span class="sxs-lookup"><span data-stu-id="55f92-123">Set up a hardware station</span></span>](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="55f92-124">Conditions préalables du canal de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="55f92-124">Call Center channel prerequisites</span></span>

- <span data-ttu-id="55f92-125">Paramètres du centre d'appels</span><span class="sxs-lookup"><span data-stu-id="55f92-125">Call center parameters</span></span>
- [<span data-ttu-id="55f92-126">Commande au centre d'appels et modes de paiement des remboursements</span><span class="sxs-lookup"><span data-stu-id="55f92-126">Call center order and refund payment methods</span></span>](work-with-payments.md)
- [<span data-ttu-id="55f92-127">Modes de livraison et frais du centre d'appels</span><span class="sxs-lookup"><span data-stu-id="55f92-127">Call center modes of delivery and charges</span></span>](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a><span data-ttu-id="55f92-128">Conditions préalables pour les canaux en ligne</span><span class="sxs-lookup"><span data-stu-id="55f92-128">Online channel prerequisites</span></span>

- [<span data-ttu-id="55f92-129">Créer un profil de fonctionnalité en ligne</span><span class="sxs-lookup"><span data-stu-id="55f92-129">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="55f92-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="55f92-130">Additional resources</span></span>

[<span data-ttu-id="55f92-131">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="55f92-131">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="55f92-132">Vue d'ensemble des organisations et des hiérarchies d'organisation</span><span class="sxs-lookup"><span data-stu-id="55f92-132">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="55f92-133">Configurer des hiérarchies d'organisation</span><span class="sxs-lookup"><span data-stu-id="55f92-133">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="55f92-134">Créer des entités juridiques</span><span class="sxs-lookup"><span data-stu-id="55f92-134">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="55f92-135">Paramétrer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="55f92-135">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="55f92-136">Paramétrer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="55f92-136">Set up an online channel</span></span>](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
