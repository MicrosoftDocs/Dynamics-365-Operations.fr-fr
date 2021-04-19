---
title: Reclassifier des immobilisations
description: Pour reclassifier une immobilisation, vous devez la transférer à un nouveau groupe d’immobilisations ou lui affecter un nouveau numéro d’immobilisation au sein du même groupe.
author: saraschi2
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8935213c4629de408a48df5e54a2122324e1b3e7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823930"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="b1104-103">Reclassifier des immobilisations</span><span class="sxs-lookup"><span data-stu-id="b1104-103">Reclassify fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b1104-104">Pour reclassifier une immobilisation, vous devez la transférer à un nouveau groupe d’immobilisations ou lui affecter un nouveau numéro d’immobilisation au sein du même groupe.</span><span class="sxs-lookup"><span data-stu-id="b1104-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="b1104-105">Lorsqu’une immobilisation est reclassifiée :</span><span class="sxs-lookup"><span data-stu-id="b1104-105">When a fixed asset is reclassified:</span></span>

* <span data-ttu-id="b1104-106">Tous les registres de l’immobilisation existante sont créés pour la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="b1104-106">All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="b1104-107">Les informations paramétrées pour l’immobilisation originale sont copiées vers la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="b1104-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="b1104-108">Le statut des registres de l’immobilisation originale est Clôturé.</span><span class="sxs-lookup"><span data-stu-id="b1104-108">The status of the books for the original fixed asset is Closed.</span></span> 

* <span data-ttu-id="b1104-109">Les nouveaux registres des nouvelles immobilisations indiquent la date de reclassification dans le champ **Date d’acquisition**.</span><span class="sxs-lookup"><span data-stu-id="b1104-109">The new books of the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="b1104-110">La date dans le champ **Date d’exécution de l’amortissement** est copiée à partir des informations originales relatives à l’actif.</span><span class="sxs-lookup"><span data-stu-id="b1104-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="b1104-111">Si l’amortissement a déjà commencé, le champ **Date du dernier amortissement** affiche la date de la reclassification.</span><span class="sxs-lookup"><span data-stu-id="b1104-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

* <span data-ttu-id="b1104-112">Les transactions d’immobilisation existantes relatives à l’immobilisation originale sont annulées et regénérées pour la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="b1104-112">The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

<span data-ttu-id="b1104-113">Procédez comme suit pour reclassifier une immobilisation :</span><span class="sxs-lookup"><span data-stu-id="b1104-113">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="b1104-114">Allez dans **Immobilisations > Tâches périodiques > Reclassement.**</span><span class="sxs-lookup"><span data-stu-id="b1104-114">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="b1104-115">Dans le champ **Groupe d’immobilisations**, sélectionnez le groupe à reclasser.</span><span class="sxs-lookup"><span data-stu-id="b1104-115">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="b1104-116">Dans le champ **Numéro d’immobilisation**, sélectionnez l’immobilisation à reclasser.</span><span class="sxs-lookup"><span data-stu-id="b1104-116">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="b1104-117">Dans le champ **Nouveau groupe d’immobilisations**, sélectionnez un groupe vers lequel transférer l’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="b1104-117">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="b1104-118">Si le nouveau groupe d’immobilisations est associé à une souche de numéros, le champ **Nouveau numéro d’immobilisation** est mis à jour avec le numéro de la nouvelle souche de numéros du groupe d’immobilisations.</span><span class="sxs-lookup"><span data-stu-id="b1104-118">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="b1104-119">Sinon, le champ **Nouveau numéro d’immobilisation** est mis à jour avec le numéro de la nouvelle souche de numéros configuré dans la page **Paramètres d’immobilisation**.</span><span class="sxs-lookup"><span data-stu-id="b1104-119">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="b1104-120">Si une souche de numéros n’est pas configurée dans la page **Paramètres d’immobilisation**, entrez un nombre dans le champ **Nouveau numéro d’immobilisation**.</span><span class="sxs-lookup"><span data-stu-id="b1104-120">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="b1104-121">Dans le champ **Date de reclassification**, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="b1104-121">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="b1104-122">Dans le champ **Souche de N° documents**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b1104-122">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="b1104-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1104-123">Click **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]