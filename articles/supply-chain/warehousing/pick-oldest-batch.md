---
title: Prélever le lot le plus ancien sur un appareil mobile
description: Cette rubrique décrit comment vous paramétrez et appliquez les options de prélèvement du lot le plus ancien à partir d'un appareil mobile.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f235c34d6369c6f0584a7bac1c1be75f3d84c9c0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427768"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a><span data-ttu-id="5232a-103">Prélever le lot le plus ancien sur un appareil mobile</span><span class="sxs-lookup"><span data-stu-id="5232a-103">Pick oldest batch on a mobile device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5232a-104">Vous pouvez accéder à la configuration **Prélever le traitement par lots le plus ancien** via le menu d'un appareil mobile qui vous permet de forcer ou d'avertir des collaborateurs de l'entrepôt pour qu'ils prélèvent le lot le plus ancien de son emplacement actuel.</span><span class="sxs-lookup"><span data-stu-id="5232a-104">You can access the configuration **Pick oldest batch** via a mobile device menu and it allows you to force or warn warehouse workers to pick the oldest batch in their current location.</span></span>  

## <a name="where-it-applies"></a><span data-ttu-id="5232a-105">Dans ce cas</span><span class="sxs-lookup"><span data-stu-id="5232a-105">Where it applies</span></span>
<span data-ttu-id="5232a-106">Le prélèvement du lot le plus ancien est configuré sur les options du menu de l'appareil mobile et applique le prélèvement pour les articles du lot ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="5232a-106">Pick oldest batch is configured on mobile device menu items and effects the pick for batch below items.</span></span>

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a><span data-ttu-id="5232a-107">Comment définir la configuration du prélèvement du lot le plus ancien</span><span class="sxs-lookup"><span data-stu-id="5232a-107">How to set up the configuration for Pick oldest batch</span></span> 
<span data-ttu-id="5232a-108">Pour les articles définis pour utiliser le travail existant, **Prélever le traitement par lots le plus ancien** peut être défini sur **Aucun**, **Avertir** ou **Forcer** du menu d'un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="5232a-108">For items that are set to use existing work, **Pick oldest batch** can be set to **None**, **Warn**, or **Force** from a mobile device menu.</span></span>

<span data-ttu-id="5232a-109">**Aucun** : Les collaborateurs ne recevront aucun message et ils seront autorisés à prélever n'importe quel lot dans leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="5232a-109">**None**: Workers will not receive any messages and they will be allowed to pick any batch in their location.</span></span>

<span data-ttu-id="5232a-110">**Avertir** et **Forcer** : Une liste des lots avec la date d'expiration la plus ancienne sera affichée au-dessus du contrôle du lot lorsque le collaborateur sélectionne un lot.</span><span class="sxs-lookup"><span data-stu-id="5232a-110">**Warn** and **Force**:  A list of the batch(es) with the oldest expiration date will be displayed above the batch control when the worker selects a batch.</span></span> <span data-ttu-id="5232a-111">Si l'emplacement est contrôlé par le contenant, une liste des contenants avec le lot le plus ancien sera affichée au-dessus du contrôle du contenant.</span><span class="sxs-lookup"><span data-stu-id="5232a-111">If the location is license plate controlled, a list of license plates that have the oldest batch will be displayed above the license plate control.</span></span> 
-   <span data-ttu-id="5232a-112">**Avertir** : Si un collaborateur choisit un contenant ou un lot qui ne s'affiche pas dans la liste, le contrôle sera grisé et un avertissement indiquera qu'il existe un lot plus ancien à sélectionner.</span><span class="sxs-lookup"><span data-stu-id="5232a-112">**Warn**: If a worker chooses a license plate or batch that is not on the shown list, the control will be blanked and a warning will be shown that there is an older batch to select.</span></span> <span data-ttu-id="5232a-113">Pour pouvoir poursuivre le travail, le collaborateur peut resélectionner le même contenant ou lot.</span><span class="sxs-lookup"><span data-stu-id="5232a-113">To be allowed to continue the work, the worker can select the same license plate or batch again.</span></span>  
-   <span data-ttu-id="5232a-114">**Forcer** : Les collaborateurs continueront à recevoir le message qu'il existe un lot plus ancien à prélever.</span><span class="sxs-lookup"><span data-stu-id="5232a-114">**Force**: Workers will continue to receive the message that there is an older batch to pick.</span></span>
