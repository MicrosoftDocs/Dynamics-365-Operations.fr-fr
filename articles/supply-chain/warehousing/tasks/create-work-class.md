---
title: Créer une classe de travail
description: Cette procédure décrit le processus de paramétrage d'une classe de travail.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a965906bfbf6411986594ddd5c67beb426268367
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217101"
---
# <a name="create-a-work-class"></a><span data-ttu-id="19d29-103">Créer une classe de travail</span><span class="sxs-lookup"><span data-stu-id="19d29-103">Create a work class</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="19d29-104">Cette procédure décrit le processus de paramétrage d'une classe de travail.</span><span class="sxs-lookup"><span data-stu-id="19d29-104">This procedure shows you how to set up a work class.</span></span> <span data-ttu-id="19d29-105">Les classes de travail sont utilisées pour diriger et/ou limiter le type de lignes de commande de travail qu'un employé de l'entrepôt peut traiter sur un périphérique portable.</span><span class="sxs-lookup"><span data-stu-id="19d29-105">Work classes are used to direct and/or limit the type of work order lines that a warehouse worker can process on a mobile device.</span></span> <span data-ttu-id="19d29-106">Les lignes qu'un employé peut traiter sont déterminées à partir des classes de travail sur les éléments du menu du périphérique portable auquel l'employé de l'entrepôt a accès et de la classe de travail spécifiée sur les lignes de travail.</span><span class="sxs-lookup"><span data-stu-id="19d29-106">The lines that a worker can process are determined from the work classes on the mobile device menu items that the warehouse worker has access to and the work class that's specified on the work lines.</span></span> <span data-ttu-id="19d29-107">Les classes de travail peuvent également être utilisées pour valider l'emplacement de rangement d'une ligne de commande de travail.</span><span class="sxs-lookup"><span data-stu-id="19d29-107">Work classes can also be used to validate the put location for a work order line.</span></span> <span data-ttu-id="19d29-108">Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="19d29-108">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="19d29-109">Cette procédure est destinée au gestionnaire d'entrepôts.</span><span class="sxs-lookup"><span data-stu-id="19d29-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="19d29-110">Accédez à Gestion des entrepôts > Configuration > Travail > Classes de travail.</span><span class="sxs-lookup"><span data-stu-id="19d29-110">Go to Warehouse management > Setup > Work > Work classes.</span></span>
2. <span data-ttu-id="19d29-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="19d29-111">Click New.</span></span>
3. <span data-ttu-id="19d29-112">Tapez une valeur dans le champ ID classe de travail.</span><span class="sxs-lookup"><span data-stu-id="19d29-112">In the Work class ID field, type a value.</span></span>
4. <span data-ttu-id="19d29-113">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="19d29-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="19d29-114">Sélectionnez une option dans le champ Type d'ordre d'exécution.</span><span class="sxs-lookup"><span data-stu-id="19d29-114">In the Work order type field, select an option.</span></span>
6. <span data-ttu-id="19d29-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="19d29-115">Click New.</span></span>
7. <span data-ttu-id="19d29-116">Dans le champ Emplacement, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="19d29-116">In the Location type field, type a value.</span></span>
    * <span data-ttu-id="19d29-117">Si vous sélectionnez un type d'emplacement, ceci définit une restriction quant au lieu dans lequel les articles peuvent être mis une fois qu'ils ont été prélevés.</span><span class="sxs-lookup"><span data-stu-id="19d29-117">If you select a location type, this sets a restriction on where items can be put after they've been picked.</span></span> <span data-ttu-id="19d29-118">Ce paramètre est utilisé lors de tentatives d'une directive d'emplacement pour résoudre l'emplacement, ou si un employé de l'entrepôt fournit manuellement l'emplacement pour l'élément du menu du périphérique portable.</span><span class="sxs-lookup"><span data-stu-id="19d29-118">This setting is used when a location directive tries to resolve the location, or if a warehouse worker manually provides the location for the mobile device menu item.</span></span>  
8. <span data-ttu-id="19d29-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="19d29-119">Close the page.</span></span>

