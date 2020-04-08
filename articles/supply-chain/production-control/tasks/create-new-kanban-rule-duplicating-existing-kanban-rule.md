---
title: Créer une règle de kanban en dupliquant une règle de kanban existante
description: Cette procédure consiste à créer un doublon d'une règle de kanban existante.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, InventItemIdLookupSimple
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0bc65dd80221cedd25890037afcb3d2617f22793
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149192"
---
# <a name="create-a-new-kanban-rule-by-duplicating-an-existing-kanban-rule"></a><span data-ttu-id="61f53-103">Créer une règle de kanban en dupliquant une règle de kanban existante</span><span class="sxs-lookup"><span data-stu-id="61f53-103">Create a new kanban rule by duplicating an existing kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="61f53-104">Cette procédure consiste à créer un doublon d'une règle de kanban existante.</span><span class="sxs-lookup"><span data-stu-id="61f53-104">This procedure focuses on creating a duplicate of an existing kanban rule.</span></span> <span data-ttu-id="61f53-105">Cela peut s'avérer utile si vous souhaitez créer de nouvelles règles de kanban à partir de règles de kanban existantes.</span><span class="sxs-lookup"><span data-stu-id="61f53-105">This is useful if you want to create new kanban rules based on existing kanban rules.</span></span> <span data-ttu-id="61f53-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="61f53-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="61f53-107">Cette procédure est destinée à l'ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production pour un flux de production modifié ou une nouvelle règle d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="61f53-107">This procedure is intended for the process engineer or the value stream manager as they prepare production for a changed production flow or a new replenishment rule.</span></span>


## <a name="select-a-kanban-rule"></a><span data-ttu-id="61f53-108">Sélectionner une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="61f53-108">Select a kanban rule</span></span>
1. <span data-ttu-id="61f53-109">Accédez aux règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="61f53-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="61f53-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="61f53-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="61f53-111">Sélectionnez la règle de kanban 000017 pour le produit M0006.</span><span class="sxs-lookup"><span data-stu-id="61f53-111">Select kanban rule 000017 for Product M0006.</span></span>  

## <a name="duplicate-a-kanban-rule"></a><span data-ttu-id="61f53-112">Dupliquer une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="61f53-112">Duplicate a kanban rule</span></span>
1. <span data-ttu-id="61f53-113">Cliquez sur Dupliquer une règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="61f53-113">Click Duplicate kanban rule.</span></span>
    * <span data-ttu-id="61f53-114">Lors de la duplication d'une règle de kanban, il est possible de modifier le type, les dates, les activités et la sélection des produits.</span><span class="sxs-lookup"><span data-stu-id="61f53-114">When duplicating a kanban rule, it is possible to change type, dates, activities, and the product selection.</span></span> <span data-ttu-id="61f53-115">Modifiez le produit pour cette procédure à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="61f53-115">Change the product for this procedure in the next step.</span></span>  
2. <span data-ttu-id="61f53-116">Dans le champ Produit, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="61f53-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="61f53-117">Sélectionnez M0007.</span><span class="sxs-lookup"><span data-stu-id="61f53-117">Select M0007.</span></span>  
3. <span data-ttu-id="61f53-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="61f53-118">Click OK.</span></span>
    * <span data-ttu-id="61f53-119">Notez qu'un doublon de la règle de kanban 000017 est créé.</span><span class="sxs-lookup"><span data-stu-id="61f53-119">Note that a duplicate of kanban rule 000017 is created.</span></span>    

