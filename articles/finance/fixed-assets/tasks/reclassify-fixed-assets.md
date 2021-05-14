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
ms.openlocfilehash: fbfb754459fad1f3b1509f4f9c65c20e0385b013
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944710"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="1b147-103">Reclassifier des immobilisations</span><span class="sxs-lookup"><span data-stu-id="1b147-103">Reclassify fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1b147-104">Pour reclassifier une immobilisation, vous devez la transférer à un nouveau groupe d’immobilisations ou lui affecter un nouveau numéro d’immobilisation au sein du même groupe.</span><span class="sxs-lookup"><span data-stu-id="1b147-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="1b147-105">Lorsqu’une immobilisation est reclassifiée :</span><span class="sxs-lookup"><span data-stu-id="1b147-105">When a fixed asset is reclassified:</span></span>

- <span data-ttu-id="1b147-106">Tous les registres de l’immobilisation existante sont créés pour la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="1b147-106">All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="1b147-107">Les informations paramétrées pour l’immobilisation originale sont copiées vers la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="1b147-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="1b147-108">Le statut des registres de l’immobilisation originale est Clôturé.</span><span class="sxs-lookup"><span data-stu-id="1b147-108">The status of the books for the original fixed asset is Closed.</span></span> 

- <span data-ttu-id="1b147-109">Les nouveaux registres des nouvelles immobilisations indiquent la date de reclassification dans le champ **Date d’acquisition**.</span><span class="sxs-lookup"><span data-stu-id="1b147-109">The new books for the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="1b147-110">La date dans le champ **Date d’exécution de l’amortissement** est copiée à partir des informations originales relatives à l’actif.</span><span class="sxs-lookup"><span data-stu-id="1b147-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="1b147-111">Si l’amortissement a déjà commencé, le champ **Date du dernier amortissement** affiche la date de la reclassification.</span><span class="sxs-lookup"><span data-stu-id="1b147-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

- <span data-ttu-id="1b147-112">Les transactions d’immobilisation existantes relatives à l’immobilisation originale sont annulées et regénérées pour la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="1b147-112">The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

- <span data-ttu-id="1b147-113">Lorsqu'un actif faisant l'objet d'une transaction de transfert a été reclassé, le système affiche un message dans le **Centre d'action** pour indiquer qu'une opération de transfert n'a pas été effectuée pendant le processus de reclassement.</span><span class="sxs-lookup"><span data-stu-id="1b147-113">When an asset that has a transfer transaction has been reclassified, the system will display a message in the **Action center** to indicate that a transfer transaction wasn't completed during the reclassification process.</span></span> <span data-ttu-id="1b147-114">Il est nécessaire de terminer une transaction de transfert pour déplacer les transactions de reclassement existantes vers les dimensions financières appropriées.</span><span class="sxs-lookup"><span data-stu-id="1b147-114">It's necessary to complete a transfer transaction to move the existing reclassification transactions to the appropriate financial dimensions.</span></span> 

   <span data-ttu-id="1b147-115">Au cours du processus de reclassement, le système exécute les actions suivantes pour reclasser le solde de l'actif de l'actif d'origine vers le nouvel actif.</span><span class="sxs-lookup"><span data-stu-id="1b147-115">During the reclassification process, the system runs the following actions to reclassify the asset balance from the original asset to the new asset.</span></span> 
   
   - <span data-ttu-id="1b147-116">Le processus de reclassement copie les données du livre d'immobilisations d'origine vers le nouveau livre d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="1b147-116">The reclassification process copies the data from the original fixed asset book to the new fixed asset book.</span></span>

   - <span data-ttu-id="1b147-117">La transaction de reclassement utilise les informations de l'acquisition comptabilisée d'origine qui incluent des informations sur la dimension financière qui sont incluses dans la transaction d'acquisition.</span><span class="sxs-lookup"><span data-stu-id="1b147-117">The reclassification transaction uses information from the original posted acquisition that includes financial dimension information that is included in the acquisition transaction.</span></span>  
   
   - <span data-ttu-id="1b147-118">Dans le même temps, le processus de reclassement annule la transaction initiale d'acquisition et de transfert d'actifs.</span><span class="sxs-lookup"><span data-stu-id="1b147-118">At the same time, the reclassification process reverses the original asset acquisition and asset transfer transaction.</span></span> 

<span data-ttu-id="1b147-119">Le diagramme et la procédure suivants fournissent un exemple du processus de reclassement.</span><span class="sxs-lookup"><span data-stu-id="1b147-119">The following diagram and procedure provide an example of the reclassification process.</span></span> 

<span data-ttu-id="1b147-120">[![Schéma illustrant le processus de reclassement](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span><span class="sxs-lookup"><span data-stu-id="1b147-120">[![Diagram showing the reclassicification process](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span></span>

<span data-ttu-id="1b147-121">Procédez comme suit pour reclassifier une immobilisation :</span><span class="sxs-lookup"><span data-stu-id="1b147-121">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="1b147-122">Allez dans **Immobilisations > Tâches périodiques > Reclassement.**</span><span class="sxs-lookup"><span data-stu-id="1b147-122">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="1b147-123">Dans le champ **Groupe d’immobilisations**, sélectionnez le groupe à reclasser.</span><span class="sxs-lookup"><span data-stu-id="1b147-123">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="1b147-124">Dans le champ **Numéro d’immobilisation**, sélectionnez l’immobilisation à reclasser.</span><span class="sxs-lookup"><span data-stu-id="1b147-124">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="1b147-125">Dans le champ **Nouveau groupe d’immobilisations**, sélectionnez un groupe vers lequel transférer l’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="1b147-125">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="1b147-126">Si le nouveau groupe d’immobilisations est associé à une souche de numéros, le champ **Nouveau numéro d’immobilisation** est mis à jour avec le numéro de la nouvelle souche de numéros du groupe d’immobilisations.</span><span class="sxs-lookup"><span data-stu-id="1b147-126">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="1b147-127">Sinon, le champ **Nouveau numéro d’immobilisation** est mis à jour avec le numéro de la nouvelle souche de numéros configuré dans la page **Paramètres d’immobilisation**.</span><span class="sxs-lookup"><span data-stu-id="1b147-127">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="1b147-128">Si une souche de numéros n’est pas configurée dans la page **Paramètres d’immobilisation**, entrez un nombre dans le champ **Nouveau numéro d’immobilisation**.</span><span class="sxs-lookup"><span data-stu-id="1b147-128">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="1b147-129">Dans le champ **Date de reclassification**, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="1b147-129">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="1b147-130">Dans le champ **Souche de N° documents**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1b147-130">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="1b147-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b147-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
