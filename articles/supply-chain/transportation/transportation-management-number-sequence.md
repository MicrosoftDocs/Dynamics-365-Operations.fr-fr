---
title: Souche de numéros de la gestion du transport
description: Cette rubrique décrit comment configurer des souches de numéros pour la gestion du transport.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: cc19110f481c11ab28532d69a4689c1db048f6c3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233365"
---
# <a name="transportation-management-number-sequence"></a><span data-ttu-id="cf08c-103">Souche de numéros de la gestion du transport</span><span class="sxs-lookup"><span data-stu-id="cf08c-103">Transportation management number sequence</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cf08c-104">Utilisez la page **Souche de numéros** dans le module de gestion des transports pour configurer divers numéros professionnels.</span><span class="sxs-lookup"><span data-stu-id="cf08c-104">Use the **Number sequences** page in the transportation management module to set up various pro numbers.</span></span> <span data-ttu-id="cf08c-105">Les numéros professionnels sont utilisés par les transporteurs pour organiser et suivre la progression de chaque expédition.</span><span class="sxs-lookup"><span data-stu-id="cf08c-105">Pro numbers are used by carriers to organize and track the progress of each shipment.</span></span>

## <a name="create-a-number-sequence-for-a-pro-number"></a><span data-ttu-id="cf08c-106">Créez une souche de numéros pour un numéro professionnel</span><span class="sxs-lookup"><span data-stu-id="cf08c-106">Create a number sequence for a pro number</span></span>

<span data-ttu-id="cf08c-107">Pour créer une souche de numéros pour un numéro professionnel, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cf08c-107">To create a number sequence for a pro number, do the following:</span></span>

1. <span data-ttu-id="cf08c-108">Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Souches de numéros**.</span><span class="sxs-lookup"><span data-stu-id="cf08c-108">Go to **Transportation management \> Setup \> Carriers \> Number sequences**.</span></span>
1. <span data-ttu-id="cf08c-109">Sélectionnez **Nouveau** pour créer une souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="cf08c-109">Select **New** to create a new number sequence.</span></span>
1. <span data-ttu-id="cf08c-110">Entrez un ID unique et un nom descriptif pour la souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="cf08c-110">Enter a unique ID and descriptive name for the number sequence.</span></span>
1. <span data-ttu-id="cf08c-111">Dans le champ **Type de souche de numéros**, *Numéro Professionnel* est la seule option.</span><span class="sxs-lookup"><span data-stu-id="cf08c-111">In the **Number sequence type** field, *Pro number* is the only option.</span></span>
1. <span data-ttu-id="cf08c-112">Dans le champ **Chiffre de contrôle**, *Chiffre de contrôle* est la seule option et est configuré comme un moteur générique.</span><span class="sxs-lookup"><span data-stu-id="cf08c-112">In the **Check digit** field, *Check digit* is the only option and is set up as a generic engine.</span></span>
1. <span data-ttu-id="cf08c-113">Sur le raccourci **Souche**, fournissez des informations sur la souche.</span><span class="sxs-lookup"><span data-stu-id="cf08c-113">On the **Sequence** FastTab, provide information about the sequence.</span></span>
1. <span data-ttu-id="cf08c-114">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cf08c-114">Close the page.</span></span>

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a><span data-ttu-id="cf08c-115">Lier une souche de numéros à un transporteur</span><span class="sxs-lookup"><span data-stu-id="cf08c-115">Link a number sequence to a shipping carrier</span></span>

<span data-ttu-id="cf08c-116">Pour lier une souche de numéros à un opérateur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cf08c-116">To link a number sequence to a carrier, do the following:</span></span>

1. <span data-ttu-id="cf08c-117">Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Transporteurs**.</span><span class="sxs-lookup"><span data-stu-id="cf08c-117">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="cf08c-118">Sélectionnez un transporteur.</span><span class="sxs-lookup"><span data-stu-id="cf08c-118">Select a shipping carrier.</span></span>
1. <span data-ttu-id="cf08c-119">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="cf08c-119">Select **Edit**.</span></span>
1. <span data-ttu-id="cf08c-120">Sur le raccourci **Aperçu**, sélectionnez une option dans le champ **Souche de numéros professionnels**.</span><span class="sxs-lookup"><span data-stu-id="cf08c-120">On the **Overview** FastTab, select an option in the **Pro number sequence** field.</span></span>
1. <span data-ttu-id="cf08c-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cf08c-121">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]