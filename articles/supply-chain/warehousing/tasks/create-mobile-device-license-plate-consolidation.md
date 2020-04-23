---
title: Créer une option de menu d'appareil mobile pour la consolidation de contenants
description: Cette procédure décrit comment créer une option de menu d'appareil mobile pour le travail de consolidation de contenants.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7dc52284473f3e3275675b608386641c8570218b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217124"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a><span data-ttu-id="285d8-103">Créer une option de menu d'appareil mobile pour la consolidation de contenants</span><span class="sxs-lookup"><span data-stu-id="285d8-103">Create a mobile device menu item for license plate consolidation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="285d8-104">Cette procédure décrit comment créer une option de menu d'appareil mobile pour le travail de consolidation de contenants.</span><span class="sxs-lookup"><span data-stu-id="285d8-104">This procedure shows you how to create a mobile device menu item for license plate consolidation work.</span></span> <span data-ttu-id="285d8-105">Cela permet aux magasiniers de consolider les articles d'un contenant avec les articles d'un autre contenant dans le même emplacement.</span><span class="sxs-lookup"><span data-stu-id="285d8-105">This enables warehouse workers to consolidate items on one license plate with items on another license place within the same location.</span></span> <span data-ttu-id="285d8-106">Par exemple, ils peuvent utiliser cette procédure si les étapes intermédiaires suivantes sont les mêmes sur les deux ordres d'exécution, de sorte que le travail ne doit être exécuté qu'une seule fois pour les articles fusionnés.</span><span class="sxs-lookup"><span data-stu-id="285d8-106">For example, they might use this if subsequent staging steps were the same on both work orders, so that the work only needs to be performed once for the merged items.</span></span> <span data-ttu-id="285d8-107">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="285d8-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="285d8-108">La tâche est généralement effectuée par un responsable d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="285d8-108">The task would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="285d8-109">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="285d8-109">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

1. <span data-ttu-id="285d8-110">Accédez à Gestion des entrepôts > Configuration > Appareil mobile > Options de menu d'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="285d8-110">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="285d8-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="285d8-111">Click New.</span></span>
3. <span data-ttu-id="285d8-112">Saisissez une valeur dans le champ Nom de l'option de menu.</span><span class="sxs-lookup"><span data-stu-id="285d8-112">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="285d8-113">Tapez une valeur dans le champ Titre.</span><span class="sxs-lookup"><span data-stu-id="285d8-113">In the Title field, type a value.</span></span>
5. <span data-ttu-id="285d8-114">Dans le champ Mode, sélectionnez « Indirect ».</span><span class="sxs-lookup"><span data-stu-id="285d8-114">In the Mode field, select 'Indirect'.</span></span>
6. <span data-ttu-id="285d8-115">Dans le champ Code d'activité, sélectionnez « Consolider les contenants ».</span><span class="sxs-lookup"><span data-stu-id="285d8-115">In the Activity code field, select 'Consolidate license plates'.</span></span>

