---
title: Groupes de transporteurs
description: Cette rubrique décrit le paramétrage des données de groupes de transporteurs.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 95517153dda06cecf8e57b1f9b080aa07966c111
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247260"
---
# <a name="carrier-groups"></a><span data-ttu-id="01fda-103">Groupes de transporteurs</span><span class="sxs-lookup"><span data-stu-id="01fda-103">Carrier groups</span></span>

<span data-ttu-id="01fda-104">Un groupe de transporteurs est un ensemble de transporteurs et de services de transporteurs.</span><span class="sxs-lookup"><span data-stu-id="01fda-104">A carrier group is a collection of shipping carriers and carrier services.</span></span> <span data-ttu-id="01fda-105">Chaque groupe de transporteurs spécifie la séquence préférée pour les transporteurs et les services de transporteur qui lui appartiennent.</span><span class="sxs-lookup"><span data-stu-id="01fda-105">Each carrier group specifies the preferred sequence for the shipping carriers and carrier services that belong to it.</span></span>

<span data-ttu-id="01fda-106">Lorsque plusieurs transporteurs et services de transport existent pour le même segment d’itinéraire, vous pouvez spécifier un groupe de transporteurs au lieu d’un transporteur et d’un service de transporteur spécifiques dans le plan d’itinéraire ou le guide d’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="01fda-106">When multiple shipping carriers and carrier services exist for the same route segment, you can specify a carrier group instead of a specific shipping carrier and carrier service in the route plan or route guide.</span></span>

## <a name="create-a-carrier-group"></a><span data-ttu-id="01fda-107">Créer un groupe de transporteurs</span><span class="sxs-lookup"><span data-stu-id="01fda-107">Create a carrier group</span></span>

1. <span data-ttu-id="01fda-108">Allez dans **Gestion du transport &gt; Configuration &gt; Transporteurs &gt; Groupe de transporteurs**.</span><span class="sxs-lookup"><span data-stu-id="01fda-108">Go to **Transportation management &gt; Setup &gt; Carriers &gt; Carrier group**.</span></span>
1. <span data-ttu-id="01fda-109">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="01fda-109">Select **New**.</span></span>
1. <span data-ttu-id="01fda-110">Dans le champ **groupes de transporteurs**, entrez un identificateur unique (ID) pour le groupe.</span><span class="sxs-lookup"><span data-stu-id="01fda-110">In the **Carrier group** field, enter a unique identifier (ID) for the group.</span></span>
1. <span data-ttu-id="01fda-111">Dans le champ **Nom**, entrez un nom descriptif pour le groupe.</span><span class="sxs-lookup"><span data-stu-id="01fda-111">In the **Name** field, enter a descriptive name for the group.</span></span>
1. <span data-ttu-id="01fda-112">Sur le raccourci **Détails**, ajoutez une ligne et sélectionnez un transporteur et un service de transporteur correspondant.</span><span class="sxs-lookup"><span data-stu-id="01fda-112">On the **Details** FastTab, add a row, and select a shipping carrier and a carrier service for it.</span></span> <span data-ttu-id="01fda-113">Répétez cette étape jusqu’à ce que vous ayez ajouté autant de transporteurs que nécessaire pour le groupe.</span><span class="sxs-lookup"><span data-stu-id="01fda-113">Repeat this step until you've added as many carriers as you require for the group.</span></span>
1. <span data-ttu-id="01fda-114">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="01fda-114">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]