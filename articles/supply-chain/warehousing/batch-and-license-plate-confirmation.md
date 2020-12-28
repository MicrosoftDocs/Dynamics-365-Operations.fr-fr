---
title: Confirmation du contenant et du lot
description: Cette rubrique décrit comment vous paramétrez et appliquez la confirmation du contenant et du lot d'un périphérique mobile.
author: Mirzaab
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a953b677b1188750241772d7ae966a1dba77b92e
ms.sourcegitcommit: 9f32389715b226c11e74c53547527e0a8b51e300
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/12/2020
ms.locfileid: "4514300"
---
# <a name="batch-and-license-plate-confirmation"></a><span data-ttu-id="9926e-103">Confirmation du contenant et du lot</span><span class="sxs-lookup"><span data-stu-id="9926e-103">Batch and license plate confirmation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9926e-104">La confirmation du lot vous permet de confirmer que le lot approprié est prélevé du périphérique mobile.</span><span class="sxs-lookup"><span data-stu-id="9926e-104">Batch confirmation allows you to confirm that the correct batch is being picked from the mobile device.</span></span> <span data-ttu-id="9926e-105">Lors du prélèvement initial du travail pour les éléments au-dessus uniquement, où lot au-dessus indique que le lot dépasse l'emplacement dans la hiérarchie de recherche, vous devez vérifier que le lot sélectionné correspond au lot de la ligne de travail.</span><span class="sxs-lookup"><span data-stu-id="9926e-105">On the initial pick of work for batch above-items only, where batch above indicates that batch ranges higher than location in the search hierarchy, you must verify that the batch that is picked matches the batch on the work line.</span></span>

<span data-ttu-id="9926e-106">La confirmation du contenant vous permet de confirmer que le contenant approprié est prélevé du périphérique mobile.</span><span class="sxs-lookup"><span data-stu-id="9926e-106">License plate confirmation allows you to confirm that the correct license plate is being picked from the mobile device.</span></span> <span data-ttu-id="9926e-107">Lors du travail de prélèvement d'un emplacement intermédiaire, vous devez vérifier que le contenant qui est prélevé correspond au contenant associé au travail.</span><span class="sxs-lookup"><span data-stu-id="9926e-107">When picking work from a stage location, you must verify that the license plate that is picked matches the license plate that is associated with the work.</span></span> <span data-ttu-id="9926e-108">Si le travail est lancé en analysant un contenant, cette étape de confirmation sera ignorée.</span><span class="sxs-lookup"><span data-stu-id="9926e-108">If the work is started by scanning a license plate, this confirmation step will be skipped.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="9926e-109">Dans ce cas</span><span class="sxs-lookup"><span data-stu-id="9926e-109">Where it applies</span></span>

<span data-ttu-id="9926e-110">La confirmation s'applique dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="9926e-110">Confirmation applies in the following scenarios:</span></span>

- <span data-ttu-id="9926e-111">La confirmation de lot s'applique aux prélèvements d'origine du travail des éléments au-dessus.</span><span class="sxs-lookup"><span data-stu-id="9926e-111">Batch confirmation applies to the initial picks of work for batch above-items.</span></span>
- <span data-ttu-id="9926e-112">La confirmation de contenant s'applique aux prélèvements à partir des emplacements intermédiaires.</span><span class="sxs-lookup"><span data-stu-id="9926e-112">License plate confirmation applies to picks from stage locations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9926e-113">Le réapprovisionnement n'est pas pris en charge pour la confirmation de contenant.</span><span class="sxs-lookup"><span data-stu-id="9926e-113">Replenishment is not supported for license plate confirmation.</span></span> <span data-ttu-id="9926e-114">Lors de l'exécution du travail de réapprovisionnement, aucune étape de confirmation de contenant n'est créée.</span><span class="sxs-lookup"><span data-stu-id="9926e-114">When executing replenishment work, no license plate confirmation step is created.</span></span>

## <a name="set-up-batch-and-license-plate-confirmation"></a><span data-ttu-id="9926e-115">Configurer la confirmation du contenant et du lot</span><span class="sxs-lookup"><span data-stu-id="9926e-115">Set up batch and license plate confirmation</span></span>

<span data-ttu-id="9926e-116">Vous pouvez configurer la confirmation du lot et du contenant à l'aide des options de menu du périphérique mobile.</span><span class="sxs-lookup"><span data-stu-id="9926e-116">You can configure batch and license plate confirmation from the mobile device menu items.</span></span>

1. <span data-ttu-id="9926e-117">Dans les options de menu de l'appareil mobile, accédez à Paramétrage de la confirmation du travail.</span><span class="sxs-lookup"><span data-stu-id="9926e-117">From the mobile device menu items, enter the work confirmation setup.</span></span>  
1. <span data-ttu-id="9926e-118">Permet de sélectionner l'option pour la confirmation du lot ou du contenant.</span><span class="sxs-lookup"><span data-stu-id="9926e-118">Select the option for either batch or license plate confirmation.</span></span> <span data-ttu-id="9926e-119">Les deux options sont disponibles pour les prélèvements de type travail qui n'ont pas la confirmation automatique activée.</span><span class="sxs-lookup"><span data-stu-id="9926e-119">Both options are available for work type picks that do not have automatic confirmation enabled.</span></span>  
