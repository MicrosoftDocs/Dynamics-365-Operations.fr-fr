---
title: Créer un profil de fonctionnalité en ligne
description: Cette rubrique décrit comment créer un profil de fonctionnalité en ligne dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.openlocfilehash: 5ecbfcf3fa78ad2909a7cc9988ab1edaf2b98376
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412390"
---
# <a name="create-an-online-functionality-profile"></a><span data-ttu-id="350b6-103">Créer un profil de fonctionnalité en ligne</span><span class="sxs-lookup"><span data-stu-id="350b6-103">Create an online functionality profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="350b6-104">Cette rubrique présente une vue d'ensemble de la configuration d'un profil de fonctionnalité en ligne pour Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="350b6-104">This topic presents an overview of setting up an online functionality profile for Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="350b6-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="350b6-105">Overview</span></span>

<span data-ttu-id="350b6-106">Le profil de fonctionnalité en ligne fournit divers paramètres utilisés pour les canaux en ligne.</span><span class="sxs-lookup"><span data-stu-id="350b6-106">The online functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="350b6-107">Chaque canal en ligne doit spécifier un profil de fonctionnalité en ligne.</span><span class="sxs-lookup"><span data-stu-id="350b6-107">Each online channel must specify an online functionality profile.</span></span>

## <a name="create-an-online-functionality-profile"></a><span data-ttu-id="350b6-108">Créer un profil de fonctionnalité en ligne</span><span class="sxs-lookup"><span data-stu-id="350b6-108">Create an online functionality profile</span></span>

<span data-ttu-id="350b6-109">La procédure suivante explique comment créer un profil de fonctionnalité en ligne à partir de l'application Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="350b6-109">The following procedure explains how to create an online functionality profile from within Commerce Headquarters app.</span></span>

1. <span data-ttu-id="350b6-110">Dans le volet de navigation, accédez à **Modules \> Paramétrage du canal \> Paramétrage du magasin en ligne \> Profils de fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="350b6-110">In the navigation pane, go to **Modules \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="350b6-111">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="350b6-111">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="350b6-112">Dans le champ **Profil**, saisissez un ID pour le profil.</span><span class="sxs-lookup"><span data-stu-id="350b6-112">In the **Profile** field, enter an ID for the profile.</span></span>
1. <span data-ttu-id="350b6-113">Dans le champ **Description**, saisissez une valeur (« Profil Adventure Works » dans l'exemple d'image ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="350b6-113">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="350b6-114">Dans la section **Fonctions**, modifiez les paramètres **PANIER**, **CLIENTS DE VENTE AU DÉTAIL** ou **CAISSE** si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="350b6-114">In the **Functions** section, modify the **CART**, **RETAIL CUSTOMERS**, or **CHECKOUT** settings, as needed.</span></span>
1. <span data-ttu-id="350b6-115">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="350b6-115">On the action pane, select **Save**.</span></span>

<span data-ttu-id="350b6-116">L'image suivante présente un exemple de profil de fonctionnalité en ligne.</span><span class="sxs-lookup"><span data-stu-id="350b6-116">The following image shows an example online functionality profile.</span></span>
  
![Exemple de profil de fonctionnalité en ligne](media/online-functionality-profile.png)

## <a name="functions"></a><span data-ttu-id="350b6-118">Fonctions</span><span class="sxs-lookup"><span data-stu-id="350b6-118">Functions</span></span>

- <span data-ttu-id="350b6-119">**Produits agrégés** : si activée, cette fonction permet au panier de mettre à jour la quantité lorsque le même article est ajouté plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="350b6-119">**Aggregate products**: When enabled, this function allows the cart to update quantity when the same item is added multiple times.</span></span>
- <span data-ttu-id="350b6-120">**Autoriser l'extraction sans paiement** : si activée, cette fonction gère le scénario lorsque les articles ajoutés au panier atteignent 0,00 $.</span><span class="sxs-lookup"><span data-stu-id="350b6-120">**Allow checkout with no payments**: When enabled, this function handles the scenario when items added to cart have a price $0.00.</span></span>
- <span data-ttu-id="350b6-121">**Créer un client en mode asynchrone** : paramètre hérité qui s'applique aux canaux de commerce électronique tiers et ne s'applique pas au site de commerce électronique Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="350b6-121">**Create customer in async mode**: This is a legacy setting applicable to third-party e-Commerce channels and is not applicable to the Dynamics 365 e-Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="350b6-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="350b6-122">Additional resources</span></span>

[<span data-ttu-id="350b6-123">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="350b6-123">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="350b6-124">Conditions préalables au paramétrage du canal</span><span class="sxs-lookup"><span data-stu-id="350b6-124">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="350b6-125">Paramétrer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="350b6-125">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="350b6-126">Paramétrer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="350b6-126">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="350b6-127">Paramétrer un canal de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="350b6-127">Set up a call center channel</span></span>](channel-setup-callcenter.md)
