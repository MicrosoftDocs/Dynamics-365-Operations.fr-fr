---
title: Souche de numéros de la gestion du transport
description: Cette rubrique décrit comment configurer des souches de numéros pour la gestion du transport.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: f3da757cbf47e0e1af781b720d17a673e19aeb3b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807678"
---
# <a name="transportation-management-number-sequence"></a><span data-ttu-id="4375f-103">Souche de numéros de la gestion du transport</span><span class="sxs-lookup"><span data-stu-id="4375f-103">Transportation management number sequence</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4375f-104">Utilisez la page **Souche de numéros** dans le module de gestion des transports pour configurer divers numéros professionnels.</span><span class="sxs-lookup"><span data-stu-id="4375f-104">Use the **Number sequences** page in the transportation management module to set up various pro numbers.</span></span> <span data-ttu-id="4375f-105">Les numéros professionnels sont utilisés par les transporteurs pour organiser et suivre la progression de chaque expédition.</span><span class="sxs-lookup"><span data-stu-id="4375f-105">Pro numbers are used by carriers to organize and track the progress of each shipment.</span></span>

## <a name="create-a-number-sequence-for-a-pro-number"></a><span data-ttu-id="4375f-106">Créez une souche de numéros pour un numéro professionnel</span><span class="sxs-lookup"><span data-stu-id="4375f-106">Create a number sequence for a pro number</span></span>

<span data-ttu-id="4375f-107">Pour créer une souche de numéros pour un numéro professionnel, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4375f-107">To create a number sequence for a pro number, do the following:</span></span>

1. <span data-ttu-id="4375f-108">Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Souches de numéros**.</span><span class="sxs-lookup"><span data-stu-id="4375f-108">Go to **Transportation management \> Setup \> Carriers \> Number sequences**.</span></span>
1. <span data-ttu-id="4375f-109">Sélectionnez **Nouveau** pour créer une souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="4375f-109">Select **New** to create a new number sequence.</span></span>
1. <span data-ttu-id="4375f-110">Entrez un ID unique et un nom descriptif pour la souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="4375f-110">Enter a unique ID and descriptive name for the number sequence.</span></span>
1. <span data-ttu-id="4375f-111">Dans le champ **Type de souche de numéros**, *Numéro Professionnel* est la seule option.</span><span class="sxs-lookup"><span data-stu-id="4375f-111">In the **Number sequence type** field, *Pro number* is the only option.</span></span>
1. <span data-ttu-id="4375f-112">Dans le champ **Chiffre de contrôle**, *Chiffre de contrôle* est la seule option et est configuré comme un moteur générique.</span><span class="sxs-lookup"><span data-stu-id="4375f-112">In the **Check digit** field, *Check digit* is the only option and is set up as a generic engine.</span></span>
1. <span data-ttu-id="4375f-113">Sur le raccourci **Souche**, fournissez des informations sur la souche.</span><span class="sxs-lookup"><span data-stu-id="4375f-113">On the **Sequence** FastTab, provide information about the sequence.</span></span>
1. <span data-ttu-id="4375f-114">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4375f-114">Close the page.</span></span>

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a><span data-ttu-id="4375f-115">Lier une souche de numéros à un transporteur</span><span class="sxs-lookup"><span data-stu-id="4375f-115">Link a number sequence to a shipping carrier</span></span>

<span data-ttu-id="4375f-116">Pour lier une souche de numéros à un opérateur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4375f-116">To link a number sequence to a carrier, do the following:</span></span>

1. <span data-ttu-id="4375f-117">Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Transporteurs**.</span><span class="sxs-lookup"><span data-stu-id="4375f-117">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="4375f-118">Sélectionnez un transporteur.</span><span class="sxs-lookup"><span data-stu-id="4375f-118">Select a shipping carrier.</span></span>
1. <span data-ttu-id="4375f-119">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="4375f-119">Select **Edit**.</span></span>
1. <span data-ttu-id="4375f-120">Sur le raccourci **Aperçu**, sélectionnez une option dans le champ **Souche de numéros professionnels**.</span><span class="sxs-lookup"><span data-stu-id="4375f-120">On the **Overview** FastTab, select an option in the **Pro number sequence** field.</span></span>
1. <span data-ttu-id="4375f-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4375f-121">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]