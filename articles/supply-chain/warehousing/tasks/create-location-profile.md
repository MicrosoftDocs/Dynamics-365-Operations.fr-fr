---
title: Créer un profil d'emplacement
description: Cette rubrique explique comment créer un profil d'emplacement dans Dynamics 365 Supply Chain Management.
author: ShylaThompson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 36bad7424ac247b8fd9a819928837de619e9e258
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2026783"
---
# <a name="create-a-location-profile"></a><span data-ttu-id="5f596-103">Créer un profil d'emplacement</span><span class="sxs-lookup"><span data-stu-id="5f596-103">Create a location profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5f596-104">Cette rubrique explique comment créer un profil d'emplacement dans Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5f596-104">This topic explains how to create a location profile in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="5f596-105">Chaque emplacement de l'entrepôt doit avoir un profil d'emplacement associé qui décrit les propriétés de l'emplacement, par exemple, si l'emplacement autorise les articles mixtes.</span><span class="sxs-lookup"><span data-stu-id="5f596-105">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location, for example, whether the location allows mixed items.</span></span> <span data-ttu-id="5f596-106">Dans cette procédure, nous créerons un profil pour un emplacement qui ne nécessite pas de contrôle de contenant.</span><span class="sxs-lookup"><span data-stu-id="5f596-106">In this procedure we’ll create a profile for a location that doesn’t require license plate control.</span></span> <span data-ttu-id="5f596-107">Nous autoriserons les articles mixtes et les statuts de stock mixtes, ainsi que l'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="5f596-107">We’ll enable mixed items, and mixed inventory statuses, and allow cycle counting.</span></span> <span data-ttu-id="5f596-108">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="5f596-108">You can use this procedure in the USMF demo data company.</span></span>


1. <span data-ttu-id="5f596-109">Dans le volet de navigation, accédez à **Modules > Gestion des entrepôts > Paramétrage > Entrepôt > Profils d'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="5f596-109">In the navigation pane, go to **Modules > Warehouse management > Setup > Warehouse > Location profiles**.</span></span>
2. <span data-ttu-id="5f596-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5f596-110">Select **New**.</span></span>
3. <span data-ttu-id="5f596-111">Tapez une valeur dans le champ **ID profil d'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="5f596-111">In the **Location profile ID** field, type a value.</span></span>
4. <span data-ttu-id="5f596-112">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="5f596-112">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="5f596-113">Entrez ou sélectionnez une valeur dans le champ **Format de l'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="5f596-113">In the **Location format** field, enter or select a value.</span></span>
6. <span data-ttu-id="5f596-114">Entrez ou sélectionnez une valeur dans le champ **Type d'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="5f596-114">In the **Location type** field, enter or select a value.</span></span>
7. <span data-ttu-id="5f596-115">Entrez ou sélectionnez une valeur dans le champ **ID profil de gestion des quais**.</span><span class="sxs-lookup"><span data-stu-id="5f596-115">In the **Dock management profile ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="5f596-116">Sélectionnez **Oui** dans le champ **Autoriser les articles mixtes**.</span><span class="sxs-lookup"><span data-stu-id="5f596-116">Select **Yes** in the **Allow mixed items** field.</span></span>
9. <span data-ttu-id="5f596-117">Sélectionnez **Oui** dans le champ **Autoriser les statuts de stock mixtes**.</span><span class="sxs-lookup"><span data-stu-id="5f596-117">Select **Yes** in the **Allow mixed inventory statuses** field.</span></span>
10. <span data-ttu-id="5f596-118">Sélectionnez **Oui** dans le champ **Autoriser l'inventaire tournant**.</span><span class="sxs-lookup"><span data-stu-id="5f596-118">Select **Yes** in the **Allow cycle counting** field.</span></span>
11. <span data-ttu-id="5f596-119">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5f596-119">Select **Save**.</span></span>

