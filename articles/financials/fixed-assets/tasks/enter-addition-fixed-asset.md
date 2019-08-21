---
title: Saisie d'un supplément à une immobilisation
description: Cette procédure décrit comment ajouter un supplément à une immobilisation existante.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fe1a1d4db696ac013afee05b697b301383232134
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839951"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a><span data-ttu-id="2cf14-103">Saisie d'un supplément à une immobilisation</span><span class="sxs-lookup"><span data-stu-id="2cf14-103">Enter an addition to a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2cf14-104">Cette procédure décrit comment ajouter un supplément à une immobilisation existante.</span><span class="sxs-lookup"><span data-stu-id="2cf14-104">This procedure shows how to add an addition to an existing fixed asset.</span></span> <span data-ttu-id="2cf14-105">L'objectif des ajouts d'immobilisations est de suivre les suppléments, la maintenance, ou les améliorations d'un actif, à titre indicatif uniquement.</span><span class="sxs-lookup"><span data-stu-id="2cf14-105">The purpose of Fixed asset additions is to track item additions, maintenance, or improvements for an asset, and is informational only.</span></span> <span data-ttu-id="2cf14-106">Toutes les modifications de la valeur ou de la durée de vie de l'immobilisation doivent être apportées séparément.</span><span class="sxs-lookup"><span data-stu-id="2cf14-106">Any changes to the fixed asset value or service life must be made separately.</span></span>   

<span data-ttu-id="2cf14-107">La procédure utilise le rôle de comptable et les données de démonstration pour l'entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="2cf14-107">The procedure uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="2cf14-108">Dans le volet de navigation, accédez à **Modules > Immobilisations > Immobilisations > Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="2cf14-108">In the Navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="2cf14-109">Dans la liste, recherchez et sélectionnez l'immobilisation à ajouter.</span><span class="sxs-lookup"><span data-stu-id="2cf14-109">In the list, find and select the fixed asset for the addition.</span></span>
3. <span data-ttu-id="2cf14-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2cf14-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="2cf14-111">Dans le volet Actions, cliquez sur **Immobilisation**.</span><span class="sxs-lookup"><span data-stu-id="2cf14-111">On the Action Pane, click **Fixed asset**.</span></span>
5. <span data-ttu-id="2cf14-112">Cliquez sur **Ajouts d'immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="2cf14-112">Click **Fixed asset additions**.</span></span>
6. <span data-ttu-id="2cf14-113">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2cf14-113">Click **New**.</span></span>
7. <span data-ttu-id="2cf14-114">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="2cf14-114">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="2cf14-115">Dans le champ **Date d'acquisition**, définissez la date de l'achat ou du service en supplément.</span><span class="sxs-lookup"><span data-stu-id="2cf14-115">In the **Acquisition date** field, set the date of the addition purchase or service.</span></span>
9. <span data-ttu-id="2cf14-116">Dans le champ **Coût unitaire**, entrez le coût de l'article, de la maintenance ou de toute autre amélioration de l'actif.</span><span class="sxs-lookup"><span data-stu-id="2cf14-116">In the **Unit cost** field, enter the cost of the item, maintenance, or other improvement for the asset.</span></span>
10. <span data-ttu-id="2cf14-117">Entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="2cf14-117">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="2cf14-118">Le coût total n'aura pas d'impact sur la valeur de l'immobilisation. Il sert uniquement pour le suivi et à titre indicatif.</span><span class="sxs-lookup"><span data-stu-id="2cf14-118">The total cost will have no impact on the value of the fixed asset and is for tracking and informational purposes only.</span></span> <span data-ttu-id="2cf14-119">Si le coût est ensuite capitalisé, une transaction d'augmentation doit être validée séparément.</span><span class="sxs-lookup"><span data-stu-id="2cf14-119">If the cost will be capitalized, then a write-up adjustment transaction must be posted separately.</span></span>  
11. <span data-ttu-id="2cf14-120">Cliquez sur l'onglet **Général**.</span><span class="sxs-lookup"><span data-stu-id="2cf14-120">Click the **General** tab.</span></span>

    * <span data-ttu-id="2cf14-121">Définissez **Augmente la durée de vie** sur **Oui** si le supplément augmente la durée de vie de l'actif.</span><span class="sxs-lookup"><span data-stu-id="2cf14-121">Set **Increases service life** to **Yes** if the addition increases the service life of the asset.</span></span>  
    * <span data-ttu-id="2cf14-122">Ce champ est fourni uniquement à titre indicatif.</span><span class="sxs-lookup"><span data-stu-id="2cf14-122">This field is informational only.</span></span> <span data-ttu-id="2cf14-123">Pour augmenter la durée de vie, modifiez la durée de vie sur les modèles de valeur et/ou les registres des amortissements pour l'actif.</span><span class="sxs-lookup"><span data-stu-id="2cf14-123">To increase the service life, modify the Service life on the Value models and/or Depreciation books for the asset.</span></span>  

