--- 
title: Reclassifier des immobilisations
description: "Pour reclassifier une immobilisation, vous devez la transférer à un nouveau groupe d'immobilisations ou lui affecter un nouveau numéro d'immobilisation au sein du même groupe."
author: saraschi2
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: d8e289e2c18fd28829fb4b749933ae1d84e0b631
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="8b616-103">Reclassifier des immobilisations</span><span class="sxs-lookup"><span data-stu-id="8b616-103">Reclassify fixed assets</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8b616-104">Pour reclassifier une immobilisation, vous devez la transférer à un nouveau groupe d'immobilisations ou lui affecter un nouveau numéro d'immobilisation au sein du même groupe.</span><span class="sxs-lookup"><span data-stu-id="8b616-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="8b616-105">Lorsqu'une immobilisation est reclassifiée :</span><span class="sxs-lookup"><span data-stu-id="8b616-105">When a fixed asset is reclassified:</span></span>

<span data-ttu-id="8b616-106">• Tous les modèles de valeur de l'immobilisation existante sont créés pour la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="8b616-106">• All value models for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="8b616-107">Les informations paramétrées pour l'immobilisation originale sont copiées vers la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="8b616-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="8b616-108">Le statut des modèles de valeur de l'immobilisation originale est Clôturé.</span><span class="sxs-lookup"><span data-stu-id="8b616-108">The status of the value models for the original fixed asset is Closed.</span></span> 

<span data-ttu-id="8b616-109">• Les nouveaux modèles de valeur des nouvelles immobilisations indiquent la date de reclassification dans le champ Date d'acquisition.</span><span class="sxs-lookup"><span data-stu-id="8b616-109">• The new value models of the new fixed asset contain the date of the reclassification in the Acquisition date field.</span></span> <span data-ttu-id="8b616-110">La date dans le champ Date d'exécution de l'amortissement est copiée à partir des informations originales relatives à l'actif.</span><span class="sxs-lookup"><span data-stu-id="8b616-110">The date in the Depreciation run date field is copied from the original asset information.</span></span> <span data-ttu-id="8b616-111">Si l'amortissement a déjà commencé, le champ Date du dernier amortissement affiche la date de la reclassification.</span><span class="sxs-lookup"><span data-stu-id="8b616-111">If the depreciation has already started, the Date when depreciation was last run field displays the date of the reclassification.</span></span> 

<span data-ttu-id="8b616-112">• Les transactions d'immobilisation existantes relatives à l'immobilisation originale sont annulées et regénérées pour la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="8b616-112">• The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

1. <span data-ttu-id="8b616-113">Allez dans Immobilisations > Tâches périodiques > Reclassement.</span><span class="sxs-lookup"><span data-stu-id="8b616-113">Go to Fixed assets > Periodic tasks > Reclassification.</span></span>
2. <span data-ttu-id="8b616-114">Dans le champ Groupe d'immobilisations, sélectionnez le groupe à reclasser.</span><span class="sxs-lookup"><span data-stu-id="8b616-114">In the Fixed asset group field, select the group to reclassify.</span></span>
3. <span data-ttu-id="8b616-115">Dans le champ Numéro d'immobilisation, sélectionnez l'immobilisation à reclasser.</span><span class="sxs-lookup"><span data-stu-id="8b616-115">In the Fixed asset number field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="8b616-116">Dans le champ Nouveau groupe d'immobilisations, sélectionnez un groupe vers lequel transférer l'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="8b616-116">In the New fixed asset group field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="8b616-117">Si le nouveau groupe d'immobilisations est associé à une souche de numéros, le champ Nouveau numéro d'immobilisation est mis à jour avec le numéro de la nouvelle souche de numéros du groupe d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="8b616-117">If the new fixed asset group is attached to a number sequence, the New fixed asset number field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="8b616-118">Sinon, le champ Nouveau numéro d'immobilisation est mis à jour avec le numéro de la nouvelle souche de numéros configuré dans la page Paramètres d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="8b616-118">Otherwise, the New fixed asset number field is updated with the number from the number sequence that is set up in the Fixed asset parameters page.</span></span> <span data-ttu-id="8b616-119">Si une souche de numéros n'est pas configurée dans la page Paramètres d'immobilisation, entrez un nombre dans le champ Nouveau numéro d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="8b616-119">If a number sequence is not set up in the Fixed asset parameters page, enter a number in the New fixed asset number field.</span></span>  
5. <span data-ttu-id="8b616-120">Dans le champ Date de reclassification, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="8b616-120">In the Reclassification date field, enter a date.</span></span>
6. <span data-ttu-id="8b616-121">Dans le champ Souche de N° documents, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8b616-121">In the Voucher series field, enter or select a value.</span></span>
7. <span data-ttu-id="8b616-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="8b616-122">Click OK.</span></span>


