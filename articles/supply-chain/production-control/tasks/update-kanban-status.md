---
title: Mettre à jour le statut d'opération kanban
description: Lorsqu'un kanban est vidé par erreur ou qu'un kanban reçu doit être vidé, vous devez mettre le statut du kanban à jour.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb8559c0843d7e6e538b5b29dc394a50d05462ee
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210339"
---
# <a name="update-kanban-status"></a><span data-ttu-id="d1d5b-103">Mettre à jour le statut d'opération kanban</span><span class="sxs-lookup"><span data-stu-id="d1d5b-103">Update kanban status</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d1d5b-104">Lorsqu'un kanban est vidé par erreur ou qu'un kanban reçu doit être vidé, vous devez mettre le statut du kanban à jour.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-104">When a kanban is emptied by mistake or a received kanban needs to be emptied, you need to update kanban status.</span></span> <span data-ttu-id="d1d5b-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d1d5b-106">Cette procédure est destinée au responsable de magasin.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-106">This procedure is intended for the shop supervisor.</span></span>


## <a name="find-the-kanban"></a><span data-ttu-id="d1d5b-107">Recherchez le kanban.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-107">Find the kanban.</span></span>
1. <span data-ttu-id="d1d5b-108">Accédez à Contrôle de la production > Kanban > Kanbans.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-108">Go to Production control > Kanban > Kanbans.</span></span>
2. <span data-ttu-id="d1d5b-109">Ouvrez le filtre de colonnes Statut de l'unité de manutention.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-109">Open Handling unit status column filter.</span></span>
3. <span data-ttu-id="d1d5b-110">Cliquez sur Effacer.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-110">Click Clear.</span></span>
    * <span data-ttu-id="d1d5b-111">Cela réinitialise les filtres.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-111">This resets the filters.</span></span>  
4. <span data-ttu-id="d1d5b-112">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-112">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d1d5b-113">Par exemple, filtrez sur le champ Numéro de carte avec une valeur de « 000149 ».</span><span class="sxs-lookup"><span data-stu-id="d1d5b-113">For example, filter on the Card number field with a value of '000149'.</span></span>

## <a name="change-emptied-status-to-received-status"></a><span data-ttu-id="d1d5b-114">Remplacer le statut vidé par le statut reçu</span><span class="sxs-lookup"><span data-stu-id="d1d5b-114">Change emptied status to received status</span></span>
1. <span data-ttu-id="d1d5b-115">Cliquez sur Contrepasser l'unité de manutention vide.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-115">Click Reverse empty handling unit.</span></span>
2. <span data-ttu-id="d1d5b-116">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-116">Click OK.</span></span>
    * <span data-ttu-id="d1d5b-117">Notez que le statut de l'unité de manutention est Reçu.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-117">Notice that the Handling unit status is Received.</span></span>  

## <a name="change-received-status-to-emptied-status"></a><span data-ttu-id="d1d5b-118">Remplacer le statut reçu par le statut vidé</span><span class="sxs-lookup"><span data-stu-id="d1d5b-118">Change received status to emptied status</span></span>
1. <span data-ttu-id="d1d5b-119">Cliquez sur Kanban vide.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-119">Click Empty kanban.</span></span>
2. <span data-ttu-id="d1d5b-120">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d1d5b-121">Notez que le statut de l'unité de manutention est Vidé.</span><span class="sxs-lookup"><span data-stu-id="d1d5b-121">Notice that the Handling unit status is Emptied.</span></span>  

