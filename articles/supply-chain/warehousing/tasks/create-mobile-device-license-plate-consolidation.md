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
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3f5f572461de007f137ffa7ea05c535371f95b7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977236"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a><span data-ttu-id="e2cde-103">Créer une option de menu d'appareil mobile pour la consolidation de contenants</span><span class="sxs-lookup"><span data-stu-id="e2cde-103">Create a mobile device menu item for license plate consolidation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e2cde-104">Cette procédure décrit comment créer une option de menu d'appareil mobile pour le travail de consolidation de contenants.</span><span class="sxs-lookup"><span data-stu-id="e2cde-104">This procedure shows you how to create a mobile device menu item for license plate consolidation work.</span></span> <span data-ttu-id="e2cde-105">Cela permet aux magasiniers de consolider les articles d'un contenant avec les articles d'un autre contenant dans le même emplacement.</span><span class="sxs-lookup"><span data-stu-id="e2cde-105">This enables warehouse workers to consolidate items on one license plate with items on another license place within the same location.</span></span> <span data-ttu-id="e2cde-106">Par exemple, ils peuvent utiliser cette procédure si les étapes intermédiaires suivantes sont les mêmes sur les deux ordres d'exécution, de sorte que le travail ne doit être exécuté qu'une seule fois pour les articles fusionnés.</span><span class="sxs-lookup"><span data-stu-id="e2cde-106">For example, they might use this if subsequent staging steps were the same on both work orders, so that the work only needs to be performed once for the merged items.</span></span> <span data-ttu-id="e2cde-107">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="e2cde-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="e2cde-108">La tâche est généralement effectuée par un responsable d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e2cde-108">The task would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="e2cde-109">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="e2cde-109">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

1. <span data-ttu-id="e2cde-110">Accédez à Gestion des entrepôts > Configuration > Appareil mobile > Options de menu d'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="e2cde-110">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="e2cde-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e2cde-111">Click New.</span></span>
3. <span data-ttu-id="e2cde-112">Saisissez une valeur dans le champ Nom de l'option de menu.</span><span class="sxs-lookup"><span data-stu-id="e2cde-112">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="e2cde-113">Tapez une valeur dans le champ Titre.</span><span class="sxs-lookup"><span data-stu-id="e2cde-113">In the Title field, type a value.</span></span>
5. <span data-ttu-id="e2cde-114">Dans le champ Mode, sélectionnez « Indirect ».</span><span class="sxs-lookup"><span data-stu-id="e2cde-114">In the Mode field, select 'Indirect'.</span></span>
6. <span data-ttu-id="e2cde-115">Dans le champ Code d'activité, sélectionnez « Consolider les contenants ».</span><span class="sxs-lookup"><span data-stu-id="e2cde-115">In the Activity code field, select 'Consolidate license plates'.</span></span>

