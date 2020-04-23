---
title: Créer une règle de kanban en dupliquant une règle de kanban existante
description: Cette procédure consiste à créer un doublon d'une règle de kanban existante.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 84a0093d95c2f7084c7a0ed17f8b2f86d654b5d7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212206"
---
# <a name="create-a-new-kanban-rule-by-duplicating-an-existing-kanban-rule"></a><span data-ttu-id="602e4-103">Créer une règle de kanban en dupliquant une règle de kanban existante</span><span class="sxs-lookup"><span data-stu-id="602e4-103">Create a new kanban rule by duplicating an existing kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="602e4-104">Cette procédure consiste à créer un doublon d'une règle de kanban existante.</span><span class="sxs-lookup"><span data-stu-id="602e4-104">This procedure focuses on creating a duplicate of an existing kanban rule.</span></span> <span data-ttu-id="602e4-105">Cela peut s'avérer utile si vous souhaitez créer de nouvelles règles de kanban à partir de règles de kanban existantes.</span><span class="sxs-lookup"><span data-stu-id="602e4-105">This is useful if you want to create new kanban rules based on existing kanban rules.</span></span> <span data-ttu-id="602e4-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="602e4-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="602e4-107">Cette procédure est destinée à l'ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production pour un flux de production modifié ou une nouvelle règle d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="602e4-107">This procedure is intended for the process engineer or the value stream manager as they prepare production for a changed production flow or a new replenishment rule.</span></span>


## <a name="select-a-kanban-rule"></a><span data-ttu-id="602e4-108">Sélectionner une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="602e4-108">Select a kanban rule</span></span>
1. <span data-ttu-id="602e4-109">Accédez aux règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="602e4-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="602e4-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="602e4-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="602e4-111">Sélectionnez la règle de kanban 000017 pour le produit M0006.</span><span class="sxs-lookup"><span data-stu-id="602e4-111">Select kanban rule 000017 for Product M0006.</span></span>  

## <a name="duplicate-a-kanban-rule"></a><span data-ttu-id="602e4-112">Dupliquer une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="602e4-112">Duplicate a kanban rule</span></span>
1. <span data-ttu-id="602e4-113">Cliquez sur Dupliquer une règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="602e4-113">Click Duplicate kanban rule.</span></span>
    * <span data-ttu-id="602e4-114">Lors de la duplication d'une règle de kanban, il est possible de modifier le type, les dates, les activités et la sélection des produits.</span><span class="sxs-lookup"><span data-stu-id="602e4-114">When duplicating a kanban rule, it is possible to change type, dates, activities, and the product selection.</span></span> <span data-ttu-id="602e4-115">Modifiez le produit pour cette procédure à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="602e4-115">Change the product for this procedure in the next step.</span></span>  
2. <span data-ttu-id="602e4-116">Dans le champ Produit, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="602e4-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="602e4-117">Sélectionnez M0007.</span><span class="sxs-lookup"><span data-stu-id="602e4-117">Select M0007.</span></span>  
3. <span data-ttu-id="602e4-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="602e4-118">Click OK.</span></span>
    * <span data-ttu-id="602e4-119">Notez qu'un doublon de la règle de kanban 000017 est créé.</span><span class="sxs-lookup"><span data-stu-id="602e4-119">Note that a duplicate of kanban rule 000017 is created.</span></span>    

