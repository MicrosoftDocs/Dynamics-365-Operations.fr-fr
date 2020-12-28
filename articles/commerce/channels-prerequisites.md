---
title: Conditions préalables au paramétrage du canal
description: Cette rubrique présente une vue d'ensemble des conditions préalables au paramétrage des canaux dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 0da0457240cf12686fff2fa929c7fb510c11f242
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412227"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="ac041-103">Conditions préalables au paramétrage du canal</span><span class="sxs-lookup"><span data-stu-id="ac041-103">Channel setup prerequisites</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ac041-104">Cette rubrique présente une vue d'ensemble des conditions préalables au paramétrage du canal dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ac041-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ac041-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="ac041-105">Overview</span></span>

<span data-ttu-id="ac041-106">Avant qu'un canal Dynamics 365 Commerce puisse être créé, plusieurs tâches prérequises doivent être effectuées.</span><span class="sxs-lookup"><span data-stu-id="ac041-106">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="ac041-107">Les listes de tâches prérequises suivantes sont organisées par type de canal.</span><span class="sxs-lookup"><span data-stu-id="ac041-107">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="ac041-108">Certains documents sont en cours de rédaction et les liens seront mis à jour au fur et à mesure que de nouveaux contenus seront publiés.</span><span class="sxs-lookup"><span data-stu-id="ac041-108">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="ac041-109">Initialisation</span><span class="sxs-lookup"><span data-stu-id="ac041-109">Initialization</span></span>

- [<span data-ttu-id="ac041-110">Initialiser les données de départ</span><span class="sxs-lookup"><span data-stu-id="ac041-110">Initialize seed data</span></span>](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="ac041-111">Prérequis globaux requis pour tous les types de canaux</span><span class="sxs-lookup"><span data-stu-id="ac041-111">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="ac041-112">Définissez et configurez votre structure d'entité juridique</span><span class="sxs-lookup"><span data-stu-id="ac041-112">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="ac041-113">Configurer votre hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="ac041-113">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="ac041-114">Paramétrer un entrepôt</span><span class="sxs-lookup"><span data-stu-id="ac041-114">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="ac041-115">Configurer la taxe de vente</span><span class="sxs-lookup"><span data-stu-id="ac041-115">Configure sales tax</span></span>](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="ac041-116">Paramétrer un profil de notification par e-mail</span><span class="sxs-lookup"><span data-stu-id="ac041-116">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="ac041-117">Définir des souches de numéros</span><span class="sxs-lookup"><span data-stu-id="ac041-117">Set up number sequences</span></span>](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="ac041-118">Paramétrer un client et un carnet d'adresses par défaut</span><span class="sxs-lookup"><span data-stu-id="ac041-118">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="ac041-119">Conditions préalables du canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="ac041-119">Retail channel prerequisites</span></span>

- [<span data-ttu-id="ac041-120">Codes info et groupes de codes info</span><span class="sxs-lookup"><span data-stu-id="ac041-120">Info codes and info code groups</span></span>](info-codes-retail.md)
- [<span data-ttu-id="ac041-121">Paramétrer un profil de fonctionnalité de la vente au détail</span><span class="sxs-lookup"><span data-stu-id="ac041-121">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="ac041-122">Paramétrer un carnet d'adresses d'employé</span><span class="sxs-lookup"><span data-stu-id="ac041-122">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="ac041-123">Paramétrer une mise en page d'écran</span><span class="sxs-lookup"><span data-stu-id="ac041-123">Set up a screen layout</span></span>](pos-screen-layouts.md)
- [<span data-ttu-id="ac041-124">Paramétrer une station matérielle</span><span class="sxs-lookup"><span data-stu-id="ac041-124">Set up a hardware station</span></span>](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="ac041-125">Conditions préalables du canal de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="ac041-125">Call Center channel prerequisites</span></span>

- <span data-ttu-id="ac041-126">Paramètres du centre d'appels</span><span class="sxs-lookup"><span data-stu-id="ac041-126">Call center parameters</span></span>
- [<span data-ttu-id="ac041-127">Commande au centre d'appels et modes de paiement des remboursements</span><span class="sxs-lookup"><span data-stu-id="ac041-127">Call center order and refund payment methods</span></span>](work-with-payments.md)
- [<span data-ttu-id="ac041-128">Modes de livraison et frais du centre d'appels</span><span class="sxs-lookup"><span data-stu-id="ac041-128">Call center modes of delivery and charges</span></span>](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a><span data-ttu-id="ac041-129">Conditions préalables pour les canaux en ligne</span><span class="sxs-lookup"><span data-stu-id="ac041-129">Online channel prerequisites</span></span>

- [<span data-ttu-id="ac041-130">Créer un profil de fonctionnalité en ligne</span><span class="sxs-lookup"><span data-stu-id="ac041-130">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="ac041-131">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ac041-131">Additional resources</span></span>

[<span data-ttu-id="ac041-132">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="ac041-132">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="ac041-133">Vue d'ensemble des organisations et des hiérarchies d'organisation</span><span class="sxs-lookup"><span data-stu-id="ac041-133">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="ac041-134">Configurer des hiérarchies d'organisation</span><span class="sxs-lookup"><span data-stu-id="ac041-134">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="ac041-135">Créer des entités juridiques</span><span class="sxs-lookup"><span data-stu-id="ac041-135">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="ac041-136">Paramétrer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="ac041-136">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="ac041-137">Paramétrer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="ac041-137">Set up an online channel</span></span>](channel-setup-online.md)
