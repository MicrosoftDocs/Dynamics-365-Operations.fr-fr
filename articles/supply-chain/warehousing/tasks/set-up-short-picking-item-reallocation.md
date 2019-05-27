---
title: Paramétrer la réaffectation des articles pour les prélèvements partiels
description: Cette procédure décrit comment les magasiniers peuvent trouver rapidement d'autres emplacements si le stock n'est pas suffisant à l'emplacement où ils ont été redirigés.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bf56a0811c4793ee2e3eaf78c8696c3c29e984c3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560835"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="f36a9-103">Paramétrer la réaffectation des articles pour les prélèvements partiels</span><span class="sxs-lookup"><span data-stu-id="f36a9-103">Set up short picking item reallocation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f36a9-104">Cette procédure décrit comment les magasiniers peuvent trouver rapidement d'autres emplacements si le stock n'est pas suffisant à l'emplacement où ils ont été redirigés.</span><span class="sxs-lookup"><span data-stu-id="f36a9-104">This procedure shows you how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> <span data-ttu-id="f36a9-105">Il est possible d'utiliser un processus de réaffectation automatique, qui utilise des instructions d'emplacement pour récupérer les marchandises si elles sont disponibles dans un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="f36a9-105">It’s possible to use an automatic re-allocation process, which uses location directives to retrieve the goods if they’re available at another location.</span></span> <span data-ttu-id="f36a9-106">Lorsque la réaffectation manuelle est utilisée, la liste des emplacements avec la quantité disponible est affichée sur l'appareil mobile, ce qui permet au magasinier de choisir l'emplacement à partir duquel utiliser le stock.</span><span class="sxs-lookup"><span data-stu-id="f36a9-106">Alternatively, when manual re-allocation is used, a list of the locations with the available quantity is shown on the mobile device, allowing the warehouse worker to choose which location to use inventory from.</span></span> <span data-ttu-id="f36a9-107">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="f36a9-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="f36a9-108">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="f36a9-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-work-exceptions"></a><span data-ttu-id="f36a9-109">Définir des exceptions de travail</span><span class="sxs-lookup"><span data-stu-id="f36a9-109">Set up work exceptions</span></span>
1. <span data-ttu-id="f36a9-110">Allez dans Gestion des entrepôts > Paramétrage > Travail > Exceptions de travail.</span><span class="sxs-lookup"><span data-stu-id="f36a9-110">Go to Warehouse management > Setup > Work > Work exceptions.</span></span>
2. <span data-ttu-id="f36a9-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f36a9-111">Click New.</span></span>
    * <span data-ttu-id="f36a9-112">Il est possible de définir plusieurs exceptions de travail avec différentes stratégies de réaffectation des articles pour permettre au magasinier d'en choisir une selon les besoins de l'expédition qu'il traite.</span><span class="sxs-lookup"><span data-stu-id="f36a9-112">It’s possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>  
3. <span data-ttu-id="f36a9-113">Dans le champ Code d'exception de travail, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f36a9-113">In the Work exception code field, type a value.</span></span>
    * <span data-ttu-id="f36a9-114">Donnez à l'exception de travail un titre pour indiquer son utilité.</span><span class="sxs-lookup"><span data-stu-id="f36a9-114">Give the work exception a title to indicate what it’s used for.</span></span> <span data-ttu-id="f36a9-115">Par exemple, Prélèvement partiel manuel.</span><span class="sxs-lookup"><span data-stu-id="f36a9-115">For example, Short picking manual.</span></span>  
4. <span data-ttu-id="f36a9-116">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f36a9-116">In the Description field, type a value.</span></span>
5. <span data-ttu-id="f36a9-117">Dans le champ Type d'exception, sélectionnez « Prélèvement partiel ».</span><span class="sxs-lookup"><span data-stu-id="f36a9-117">In the Exception type field, select 'Short pick'.</span></span>
6. <span data-ttu-id="f36a9-118">Activez la case à cocher Ajuster le stock.</span><span class="sxs-lookup"><span data-stu-id="f36a9-118">Select the Adjust inventory check box.</span></span>
    * <span data-ttu-id="f36a9-119">Cette option signifie que le stock est automatiquement ajusté sur 0 à l'emplacement de prélèvement partiel.</span><span class="sxs-lookup"><span data-stu-id="f36a9-119">This option means that inventory will automatically be adjusted to 0 at the short picked location.</span></span>  
7. <span data-ttu-id="f36a9-120">Dans le champ Code type d'ajustement par défaut, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f36a9-120">In the Default adjustment type code field, enter or select a value.</span></span>
    * <span data-ttu-id="f36a9-121">Par exemple, dans USMF, vous pouvez sélectionner « Supprimer Res Adj Out ».</span><span class="sxs-lookup"><span data-stu-id="f36a9-121">For example, in USMF you can select 'Remove Res Adj Out'.</span></span>  
8. <span data-ttu-id="f36a9-122">Dans le champ Réaffectation des articles, sélectionnez « Manuel ».</span><span class="sxs-lookup"><span data-stu-id="f36a9-122">In the Item reallocation field, select 'Manual'.</span></span>
    * <span data-ttu-id="f36a9-123">Si vous sélectionnez Manuel ou Automatique et manuel, le magasinier doit être autorisé à utiliser la réaffectation manuelle.</span><span class="sxs-lookup"><span data-stu-id="f36a9-123">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="f36a9-124">Paramétrer un collaborateur pour utiliser la réaffectation manuelle des articles</span><span class="sxs-lookup"><span data-stu-id="f36a9-124">Set up a worker to use manual item reallocation</span></span>
1. <span data-ttu-id="f36a9-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f36a9-125">Close the page.</span></span>
2. <span data-ttu-id="f36a9-126">Allez dans Gestion des entrepôts > Paramétrage > Collaborateur.</span><span class="sxs-lookup"><span data-stu-id="f36a9-126">Go to Warehouse management > Setup > Worker.</span></span>
3. <span data-ttu-id="f36a9-127">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="f36a9-127">Click Edit.</span></span>
4. <span data-ttu-id="f36a9-128">Dans la liste, sélectionnez le collaborateur 24.</span><span class="sxs-lookup"><span data-stu-id="f36a9-128">In the list, select worker 24.</span></span>
5. <span data-ttu-id="f36a9-129">Développez la section Travail.</span><span class="sxs-lookup"><span data-stu-id="f36a9-129">Expand the Work section.</span></span>
6. <span data-ttu-id="f36a9-130">Sélectionnez Oui dans le champ Autoriser la réaffectation manuelle des articles.</span><span class="sxs-lookup"><span data-stu-id="f36a9-130">Select Yes in the Allow manual item reallocation field.</span></span>

