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
ms.openlocfilehash: 14da5fd2b409790de2269036ccb941ffa6d3311c
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478306"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="e796c-103">Créer un profil de fonctionnalité de vente au détail</span><span class="sxs-lookup"><span data-stu-id="e796c-103">Create a retail functionality profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e796c-104">Cette rubrique décrit comment créer un profil de fonctionnalité dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e796c-104">This topic describes how to create a functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="e796c-105">Le profil de fonctionnalité Commerce fournit divers paramètres utilisés pour les canaux en ligne.</span><span class="sxs-lookup"><span data-stu-id="e796c-105">The commerce functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="e796c-106">Chaque canal doit préciser un profil de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="e796c-106">Each channel must specify a functionality profile.</span></span>

## <a name="create-a-functionality-profile"></a><span data-ttu-id="e796c-107">Créer un profil de fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="e796c-107">Create a functionality profile</span></span>

<span data-ttu-id="e796c-108">Pour créer un profil de fonctionnalité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e796c-108">To create a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="e796c-109">Dans le volet de navigation, accédez à **Modules \> Paramétrage du canal \> Profils POS \> Profils de fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="e796c-109">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="e796c-110">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e796c-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="e796c-111">Dans le champ **Profil**, saisissez un ID pour le profil (« FN006 » dans l'exemple d'image ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="e796c-111">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="e796c-112">Dans le champ **Description**, saisissez une valeur (« Profil Adventure Works » dans l'exemple d'image ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="e796c-112">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="e796c-113">Dans la section **Général**, sélectionnez un pays pour la valeur **ISO** locale.</span><span class="sxs-lookup"><span data-stu-id="e796c-113">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="e796c-114">Dans la section **Général**, modifiez les autres paramètres, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e796c-114">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="e796c-115">Dans la section **Général**, sélectionnez un **ID profil du ticket de caisse** pour les tickets de caisse par e-mail.</span><span class="sxs-lookup"><span data-stu-id="e796c-115">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="e796c-116">Dans la section **Fonctions**, modifiez les autres paramètres, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e796c-116">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="e796c-117">Dans la section **Montant**, modifiez les paramètres, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e796c-117">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="e796c-118">Dans la section **Codes info**, modifiez les paramètres, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e796c-118">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="e796c-119">Dans la section **Numérotation des tickets de caisse**, modifiez les paramètres, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e796c-119">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="e796c-120">L'image suivante présente un exemple de profil de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="e796c-120">The following image shows an example functionality profile.</span></span>
  
![Exemple de profil de fonctionnalité](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="e796c-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e796c-122">Additional resources</span></span>

[<span data-ttu-id="e796c-123">Codes info et groupes de codes info</span><span class="sxs-lookup"><span data-stu-id="e796c-123">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="e796c-124">Créer un carnet d'adresses</span><span class="sxs-lookup"><span data-stu-id="e796c-124">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="e796c-125">Aperçu de la mise en page de l'écran</span><span class="sxs-lookup"><span data-stu-id="e796c-125">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="e796c-126">Configuration et installation d'une Retail Hardware Station</span><span class="sxs-lookup"><span data-stu-id="e796c-126">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
