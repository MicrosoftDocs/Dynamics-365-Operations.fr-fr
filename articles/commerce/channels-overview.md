---
title: Vue d’ensemble des canaux
description: Cette rubrique présente une vue d’ensemble des canaux dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 7f5d527dd14d24c06aef874de0088bb07c49849b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800541"
---
# <a name="channels-overview"></a><span data-ttu-id="0d475-103">Vue d’ensemble des canaux</span><span class="sxs-lookup"><span data-stu-id="0d475-103">Channels overview</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0d475-104">Cette rubrique présente une vue d’ensemble des canaux dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0d475-104">This topic presents an overview of channels in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="0d475-105">Elle inclut des informations sur les tâches que vous devez effectuer avant et après avoir paramétré chaque canal.</span><span class="sxs-lookup"><span data-stu-id="0d475-105">It includes information about the tasks that you must complete both before and after you set up each channel.</span></span>

## <a name="types-of-channels"></a><span data-ttu-id="0d475-106">Types de canaux</span><span class="sxs-lookup"><span data-stu-id="0d475-106">Types of Channels</span></span>

<span data-ttu-id="0d475-107">Dynamics 365 Commerce prend en charge trois types de canaux différents : vente au détail, centre d’appels et canaux en ligne.</span><span class="sxs-lookup"><span data-stu-id="0d475-107">Dynamics 365 Commerce supports three different channel types: retail, call center, and online channels.</span></span>

### <a name="retail-channels"></a><span data-ttu-id="0d475-108">Canaux de vente au détail</span><span class="sxs-lookup"><span data-stu-id="0d475-108">Retail channels</span></span>

<span data-ttu-id="0d475-109">Les canaux de vente au détail représentent les magasins physiques standards.</span><span class="sxs-lookup"><span data-stu-id="0d475-109">Retail channels represent standard brick-and-mortar stores.</span></span> <span data-ttu-id="0d475-110">Chaque magasin peut avoir ses propres registres, comptes de revenus et dépenses et personnel de point de vente (PDV).</span><span class="sxs-lookup"><span data-stu-id="0d475-110">Each store can have its own point of sale (POS) registers, income and expense accounts, and staff.</span></span> 

### <a name="call-center-channels"></a><span data-ttu-id="0d475-111">Canaux de centre d’appels</span><span class="sxs-lookup"><span data-stu-id="0d475-111">Call center channels</span></span>

<span data-ttu-id="0d475-112">Les canaux de centre d’appels représentent la gestion des commandes et des clients du centre d’appels.</span><span class="sxs-lookup"><span data-stu-id="0d475-112">Call center channels represent call center order and customer management.</span></span>

### <a name="online-channels"></a><span data-ttu-id="0d475-113">Canaux en ligne</span><span class="sxs-lookup"><span data-stu-id="0d475-113">Online channels</span></span>

<span data-ttu-id="0d475-114">Les canaux en ligne représentent les vitrines de commerce électronique en ligne.</span><span class="sxs-lookup"><span data-stu-id="0d475-114">Online channels represent online e-Commerce storefronts.</span></span> <span data-ttu-id="0d475-115">Une fois qu’un canal en ligne est créé, un site doit être créé à l’aide de l’outil générateur de site Microsoft Dynamics 365 Commerce ou d’une autre solution de commerce électronique tiers.</span><span class="sxs-lookup"><span data-stu-id="0d475-115">Once an online channel is created, a site must be created using the Microsoft Dynamics 365 Commerce Site Builder tool or other third-party e-Commerce solution.</span></span>

## <a name="channel-setup-basics"></a><span data-ttu-id="0d475-116">Principes de base du paramétrage des canaux</span><span class="sxs-lookup"><span data-stu-id="0d475-116">Channel setup basics</span></span>

<span data-ttu-id="0d475-117">Le paramétrage des canaux est effectuée dans l’outil Commerce.</span><span class="sxs-lookup"><span data-stu-id="0d475-117">Channel set up is performed in the Commerce tool.</span></span> <span data-ttu-id="0d475-118">Chaque canal peut avoir ses propres modes de paiement, groupes de prix, hiérarchies de produits, assortiments et ensemble de produits.</span><span class="sxs-lookup"><span data-stu-id="0d475-118">Each channel can have its own payment methods, price groups, product hierarchies, assortments, and set of products.</span></span> <span data-ttu-id="0d475-119">Une fois un canal créé, vous affectez les produits dont vous souhaitez la présence dans ce magasin et que vous voulez vendre.</span><span class="sxs-lookup"><span data-stu-id="0d475-119">After you create a channel, you assign the products that you want it to carry and sell.</span></span> <span data-ttu-id="0d475-120">Chaque type de canal possède un ensemble unique de fonctionnalités qui peuvent avoir besoin d’être configurées.</span><span class="sxs-lookup"><span data-stu-id="0d475-120">Each channel type has a unique set of features that may need to be configured.</span></span> <span data-ttu-id="0d475-121">Par exemple, un canal de vente au détail a besoin d’employés, de registres et de clients affectés.</span><span class="sxs-lookup"><span data-stu-id="0d475-121">For example, a retail channel needs assigned employees, registers, and customers.</span></span> <span data-ttu-id="0d475-122">Une fois qu’un nouveau canal est créé, il doit être affecté à une hiérarchie d’organisation.</span><span class="sxs-lookup"><span data-stu-id="0d475-122">Once a new channel is created, it needs to be assigned to an organization hierarchy.</span></span>

## <a name="channel-setup-prerequisites"></a><span data-ttu-id="0d475-123">Conditions préalables au paramétrage du canal</span><span class="sxs-lookup"><span data-stu-id="0d475-123">Channel setup prerequisites</span></span>

<span data-ttu-id="0d475-124">Avant de pouvoir paramétrer un canal, vous devez effectuer certaines tâches prérequises en fonction du type de canal.</span><span class="sxs-lookup"><span data-stu-id="0d475-124">Before you can set up a channel, you must complete some prerequisite tasks based on the channel type.</span></span> <span data-ttu-id="0d475-125">Pour plus d’informations, voir [Conditions préalables au paramétrage du canal](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="0d475-125">For more information, see [Channel setup prerequisites](channels-prerequisites.md).</span></span>

## <a name="set-up-a-channel"></a><span data-ttu-id="0d475-126">Paramétrer un canal</span><span class="sxs-lookup"><span data-stu-id="0d475-126">Set up a channel</span></span>

<span data-ttu-id="0d475-127">Après avoir effectué les tâches prérequises, pour obtenir des instructions de paramétrage supplémentaires, utilisez les liens suivants.</span><span class="sxs-lookup"><span data-stu-id="0d475-127">After you complete the prerequisite tasks, for further setup instructions, use the following links.</span></span>

- [<span data-ttu-id="0d475-128">Paramétrer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="0d475-128">Set up a retail channel</span></span>](channel-setup-retail.md)
- [<span data-ttu-id="0d475-129">Paramétrer un canal de centre d’appels</span><span class="sxs-lookup"><span data-stu-id="0d475-129">Set up a call center channel</span></span>](channel-setup-callcenter.md)
- [<span data-ttu-id="0d475-130">Paramétrer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="0d475-130">Set up an online channel</span></span>](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a><span data-ttu-id="0d475-131">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0d475-131">Additional resources</span></span>

[<span data-ttu-id="0d475-132">Conditions préalables au paramétrage du canal</span><span class="sxs-lookup"><span data-stu-id="0d475-132">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="0d475-133">Paramétrer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="0d475-133">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="0d475-134">Paramétrer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="0d475-134">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="0d475-135">Paramétrer un canal de centre d’appels</span><span class="sxs-lookup"><span data-stu-id="0d475-135">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="0d475-136">Configurer des hiérarchies d’organisation</span><span class="sxs-lookup"><span data-stu-id="0d475-136">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]