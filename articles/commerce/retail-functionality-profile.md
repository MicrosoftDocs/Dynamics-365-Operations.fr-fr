---
title: Créer un profil de fonctionnalité de vente au détail
description: Cette rubrique décrit comment créer un profil de fonctionnalité dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: a53fc77a7d457534428929bd431175be7cf450f7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979645"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="089fe-103">Créer un profil de fonctionnalité de vente au détail</span><span class="sxs-lookup"><span data-stu-id="089fe-103">Create a retail functionality profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="089fe-104">Cette rubrique décrit comment créer un profil de fonctionnalité dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="089fe-104">This topic describes how to create a functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="089fe-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="089fe-105">Overview</span></span>

<span data-ttu-id="089fe-106">Le profil de fonctionnalité Commerce fournit divers paramètres utilisés pour les canaux en ligne.</span><span class="sxs-lookup"><span data-stu-id="089fe-106">The commerce functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="089fe-107">Chaque canal doit préciser un profil de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="089fe-107">Each channel must specify a functionality profile.</span></span>

## <a name="create-a-functionality-profile"></a><span data-ttu-id="089fe-108">Créer un profil de fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="089fe-108">Create a functionality profile</span></span>

<span data-ttu-id="089fe-109">Pour créer un profil de fonctionnalité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="089fe-109">To create a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="089fe-110">Dans le volet de navigation, accédez à **Modules \> Paramétrage du canal \> Profils POS \> Profils de fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="089fe-110">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="089fe-111">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="089fe-111">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="089fe-112">Dans le champ **Profil**, saisissez un ID pour le profil (« FN006 » dans l'exemple d'image ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="089fe-112">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="089fe-113">Dans le champ **Description**, saisissez une valeur (« Profil Adventure Works » dans l'exemple d'image ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="089fe-113">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="089fe-114">Dans la section **Général**, sélectionnez un pays pour la valeur **ISO** locale.</span><span class="sxs-lookup"><span data-stu-id="089fe-114">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="089fe-115">Dans la section **Général**, modifiez les autres paramètres, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="089fe-115">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="089fe-116">Dans la section **Général**, sélectionnez un **ID profil du ticket de caisse** pour les tickets de caisse par e-mail.</span><span class="sxs-lookup"><span data-stu-id="089fe-116">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="089fe-117">Dans la section **Fonctions**, modifiez les autres paramètres, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="089fe-117">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="089fe-118">Dans la section **Montant**, modifiez les paramètres, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="089fe-118">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="089fe-119">Dans la section **Codes info**, modifiez les paramètres, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="089fe-119">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="089fe-120">Dans la section **Numérotation des tickets de caisse**, modifiez les paramètres, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="089fe-120">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="089fe-121">L'image suivante présente un exemple de profil de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="089fe-121">The following image shows an example functionality profile.</span></span>
  
![Exemple de profil de fonctionnalité](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="089fe-123">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="089fe-123">Additional resources</span></span>

[<span data-ttu-id="089fe-124">Codes info et groupes de codes info</span><span class="sxs-lookup"><span data-stu-id="089fe-124">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="089fe-125">Créer un carnet d'adresses</span><span class="sxs-lookup"><span data-stu-id="089fe-125">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="089fe-126">Aperçu de la mise en page de l'écran</span><span class="sxs-lookup"><span data-stu-id="089fe-126">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="089fe-127">Configuration et installation d'une Retail Hardware Station</span><span class="sxs-lookup"><span data-stu-id="089fe-127">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 
