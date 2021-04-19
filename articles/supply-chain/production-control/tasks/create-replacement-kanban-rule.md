---
title: Créer une règle de kanban de remplacement
description: Cette procédure se concentre sur le remplacement d’une règle de kanban existante par une nouvelle règle de kanban à une date spécifique.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d5aebd88dee9621d2c85af3a4fb5bf76ae8e6b80
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828944"
---
# <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="64ffa-103">Créer une règle de kanban de remplacement</span><span class="sxs-lookup"><span data-stu-id="64ffa-103">Create a replacement kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="64ffa-104">Cette procédure se concentre sur le remplacement d’une règle de kanban existante par une nouvelle règle de kanban à une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="64ffa-104">This procedure focuses on replacing an existing kanban rule with a new kanban rule on a specific date.</span></span> <span data-ttu-id="64ffa-105">Cela est utile lorsque des modifications du flux de production ou des règles de réapprovisionnement doivent être coordonnés et planifiées.</span><span class="sxs-lookup"><span data-stu-id="64ffa-105">This is useful when changes in the production flow or replenishment rules need to be coordinated and scheduled.</span></span> <span data-ttu-id="64ffa-106">La société fictive de démonstration utilisée pour créer cette procédure est USMF.</span><span class="sxs-lookup"><span data-stu-id="64ffa-106">The demo data company used to create procedure is USMF.</span></span> <span data-ttu-id="64ffa-107">Cette procédure est destinée à l’ingénieur processus ou au responsable de la chaîne de valeur quand ils préparent la production pour un flux de production modifié ou une nouvelle règle d’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="64ffa-107">This procedure is intended for the process engineer or the value stream manager when they prepare production for a changed production flow or a new replenishment rule.</span></span> <span data-ttu-id="64ffa-108">Cette tâche remplace la règle de kanban 000022 par une nouvelle règle et augmente la quantité maximale de 48 à 100 pour cette nouvelle règle.</span><span class="sxs-lookup"><span data-stu-id="64ffa-108">This task replaces kanban rule 000022 with a new rule and increases the maximum quantity from 48 to 100 for the new rule.</span></span>


## <a name="select-a-kanban-rule-to-replace"></a><span data-ttu-id="64ffa-109">Sélectionner la règle de kanban à remplacer</span><span class="sxs-lookup"><span data-stu-id="64ffa-109">Select a kanban rule to replace</span></span>
1. <span data-ttu-id="64ffa-110">Accédez aux règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="64ffa-110">Go to Kanban rules.</span></span>
2. <span data-ttu-id="64ffa-111">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="64ffa-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="64ffa-112">Sélectionnez la règle de kanban 000022.</span><span class="sxs-lookup"><span data-stu-id="64ffa-112">Select kanban rule 000022.</span></span>  

## <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="64ffa-113">Créer une règle de kanban de remplacement</span><span class="sxs-lookup"><span data-stu-id="64ffa-113">Create a replacement kanban rule</span></span>
1. <span data-ttu-id="64ffa-114">Cliquez sur Remplacer la règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="64ffa-114">Click Replace kanban rule.</span></span>
2. <span data-ttu-id="64ffa-115">Entrez une date et une heure dans le champ Date d’effet.</span><span class="sxs-lookup"><span data-stu-id="64ffa-115">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="64ffa-116">Sélectionnez une date dans le futur, dans une semaine par exemple.</span><span class="sxs-lookup"><span data-stu-id="64ffa-116">Select a date in the future, such as one week from now.</span></span> <span data-ttu-id="64ffa-117">Il s’agit de la date et de l’heure auxquelles la règle de kanban devient active et remplace la règle de kanban ancienne.</span><span class="sxs-lookup"><span data-stu-id="64ffa-117">This is the date and time when the new kanban rule becomes active and replaces the old kanban rule.</span></span>  
    * <span data-ttu-id="64ffa-118">Si la règle de kanban fait passer le chemin d’accès par le flux de production, une autre activité peut être sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="64ffa-118">If the kanban rule changes the path in the production flow,  another activity can be selected.</span></span>  <span data-ttu-id="64ffa-119">Dans cette procédure, nous maintiendrons l’activité intacte.</span><span class="sxs-lookup"><span data-stu-id="64ffa-119">In this procedure, we will keep the activity untouched.</span></span>  
3. <span data-ttu-id="64ffa-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="64ffa-120">Click OK.</span></span>
    * <span data-ttu-id="64ffa-121">Notez qu’une règle de kanban est créée pour remplacer la règle de kanban 000022.</span><span class="sxs-lookup"><span data-stu-id="64ffa-121">Notice that a new kanban rule is created to replace kanban rule 000022.</span></span>  
    * <span data-ttu-id="64ffa-122">La date d’effet est définie selon la date choisie lorsque vous remplacez la règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="64ffa-122">The effective date is set according to the date chosen when you replace the kanban rule.</span></span>  
4. <span data-ttu-id="64ffa-123">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="64ffa-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="64ffa-124">Sélectionnez la règle de kanban de remplacement 000022.</span><span class="sxs-lookup"><span data-stu-id="64ffa-124">Select the replaced kanban rule 000022.</span></span>  
    * <span data-ttu-id="64ffa-125">Notez que la règle de kanban de remplacement a la même date que la date d’expiration car il s’agit de la date à laquelle elle expirera.</span><span class="sxs-lookup"><span data-stu-id="64ffa-125">Notice that the replaced kanban rule has the same date as the Expiration date because this is the date when it will expire.</span></span>  
5. <span data-ttu-id="64ffa-126">Sélectionnez la ligne 1 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="64ffa-126">In the list, select row 1.</span></span>
    * <span data-ttu-id="64ffa-127">Sélectionnez la nouvelle règle de kanban en haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="64ffa-127">Select the new kanban rule on top of the list.</span></span> <span data-ttu-id="64ffa-128">Il s’agit de la règle de kanban avec le numéro de règle de kanban le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="64ffa-128">This is the kanban rule with the highest kanban rule number.</span></span>  
6. <span data-ttu-id="64ffa-129">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="64ffa-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="64ffa-130">Cliquez sur le numéro de la règle de kanban pour ouvrir la règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="64ffa-130">Click the kanban rule number to open the kanban rule.</span></span>  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a><span data-ttu-id="64ffa-131">Modifier la quantité maximale pour la règle de kanban de remplacement</span><span class="sxs-lookup"><span data-stu-id="64ffa-131">Modify maximum quantity for the replacement kanban rule</span></span>
1. <span data-ttu-id="64ffa-132">Définissez la quantité maximale sur 100.</span><span class="sxs-lookup"><span data-stu-id="64ffa-132">Set Maximum quantity to '100'.</span></span>
    * <span data-ttu-id="64ffa-133">Développez l’organisateur Quantités pour voir le champ Quantité maximale.</span><span class="sxs-lookup"><span data-stu-id="64ffa-133">Expand the Quantities FastTab to see the Maximum quantity field.</span></span> <span data-ttu-id="64ffa-134">Le fait de définir la quantité maximale sur 100 permet de traiter jusqu’à 100 kanbans.</span><span class="sxs-lookup"><span data-stu-id="64ffa-134">Changing the maximum quantity to 100 will allow up to 100 kanbans to be processed.</span></span>    <span data-ttu-id="64ffa-135">Il s’agit de la dernière étape de cette tâche.</span><span class="sxs-lookup"><span data-stu-id="64ffa-135">This is the last step in this task.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]