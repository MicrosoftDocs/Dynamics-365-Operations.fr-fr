--- 
title: "Déclarer comme terminé à un emplacement de contrôle de contenant"
description: "Ce guide de tâche présente un exemple de déclaration de fin à un emplacement qui ne fait pas l'objet d'un contrôle de contenant."
author: ChristianRytt
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 34fac03a0ff3d71a2349b66f8f85e4e124dcd708
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="report-as-finished-to-a-plate-controlled-location"></a><span data-ttu-id="786bf-103">Déclarer comme terminé à un emplacement de contrôle de contenant</span><span class="sxs-lookup"><span data-stu-id="786bf-103">Report as finished to a plate-controlled location</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="786bf-104">Ce guide de tâche présente un exemple de déclaration de fin à un emplacement qui ne fait pas l'objet d'un contrôle de contenant.</span><span class="sxs-lookup"><span data-stu-id="786bf-104">This task guide shows an example of reporting as finished to a location that isn't license plate–controlled.</span></span> <span data-ttu-id="786bf-105">Une stratégie de travail applicable correspond est une condition préalable pour cette tâche.</span><span class="sxs-lookup"><span data-stu-id="786bf-105">An applicable work policy is the prerequisite for this task.</span></span> <span data-ttu-id="786bf-106">Un guide de tâche précédent a indiqué le paramétrage de la stratégie de travail.</span><span class="sxs-lookup"><span data-stu-id="786bf-106">A previous task guide showed the setup of the work policy.</span></span> <span data-ttu-id="786bf-107">L'application Dynamics AX 7.0.1 ou ultérieure est requise pour ce guide de tâche.</span><span class="sxs-lookup"><span data-stu-id="786bf-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>




## <a name="set-up-an-output-location"></a><span data-ttu-id="786bf-108">Définir un emplacement de sortie</span><span class="sxs-lookup"><span data-stu-id="786bf-108">Set up an output location</span></span>
1. <span data-ttu-id="786bf-109">Accédez à Administration d'organisation > Ressources > Groupes de ressources.</span><span class="sxs-lookup"><span data-stu-id="786bf-109">Go to Organization administration > Resources > Resource groups.</span></span>
2. <span data-ttu-id="786bf-110">Sélectionnez le groupe de ressources 5102 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="786bf-110">In the list, select resource group '5102'.</span></span>
3. <span data-ttu-id="786bf-111">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="786bf-111">Click Edit.</span></span>
4. <span data-ttu-id="786bf-112">Entrez 51 dans le champ Entrepôt de sortie.</span><span class="sxs-lookup"><span data-stu-id="786bf-112">In the Output warehouse field, enter '51'.</span></span>
5. <span data-ttu-id="786bf-113">Entrez 001 dans le champ Emplacement de sortie.</span><span class="sxs-lookup"><span data-stu-id="786bf-113">In the Output location field, enter '001'.</span></span>
    * <span data-ttu-id="786bf-114">L'emplacement 001 n'est un emplacement qui fait l'objet d'un contrôle de contenant.</span><span class="sxs-lookup"><span data-stu-id="786bf-114">Location 001 isn't a license plate–controlled location.</span></span> <span data-ttu-id="786bf-115">Vous pouvez uniquement paramétrer un emplacement de sortie faisant l'objet d'un contrôle de contenant si une stratégie de travail applicable existe pour l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="786bf-115">You can set up a non–license plate output location only if an applicable work policy exists for the location.</span></span>  

## <a name="create-a-production-order-and-report-it-as-finished"></a><span data-ttu-id="786bf-116">Créer un ordre de fabrication et le déclarer comme terminé</span><span class="sxs-lookup"><span data-stu-id="786bf-116">Create a production order and report it as finished</span></span>
1. <span data-ttu-id="786bf-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="786bf-117">Close the page.</span></span>
2. <span data-ttu-id="786bf-118">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="786bf-118">Go to Production control > Production orders > All production orders.</span></span>
3. <span data-ttu-id="786bf-119">Cliquez sur Nouvel ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="786bf-119">Click New production order.</span></span>
4. <span data-ttu-id="786bf-120">Entrez L0101 dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="786bf-120">In the Item number field, enter 'L0101'.</span></span>
5. <span data-ttu-id="786bf-121">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="786bf-121">Click Create.</span></span>
6. <span data-ttu-id="786bf-122">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="786bf-122">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="786bf-123">Cliquez sur Estimer.</span><span class="sxs-lookup"><span data-stu-id="786bf-123">Click Estimate.</span></span>
8. <span data-ttu-id="786bf-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="786bf-124">Click OK.</span></span>
9. <span data-ttu-id="786bf-125">Cliquez sur Démarrer.</span><span class="sxs-lookup"><span data-stu-id="786bf-125">Click Start.</span></span>
10. <span data-ttu-id="786bf-126">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="786bf-126">Click the General tab.</span></span>
11. <span data-ttu-id="786bf-127">Dans le champ Consommation de nomenclature automatique, sélectionnez Jamais.</span><span class="sxs-lookup"><span data-stu-id="786bf-127">In the Automatic BOM consumption field, select 'Never'.</span></span>
12. <span data-ttu-id="786bf-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="786bf-128">Click OK.</span></span>
13. <span data-ttu-id="786bf-129">Cliquez sur Déclaration de fin.</span><span class="sxs-lookup"><span data-stu-id="786bf-129">Click Report as finished.</span></span>
14. <span data-ttu-id="786bf-130">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="786bf-130">Click the General tab.</span></span>
15. <span data-ttu-id="786bf-131">Dans le champ Accepter les erreurs, sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="786bf-131">Select Yes in the Accept error field.</span></span>
16. <span data-ttu-id="786bf-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="786bf-132">Click OK.</span></span>
17. <span data-ttu-id="786bf-133">Cliquez sur Entrepôt dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="786bf-133">On the Action Pane, click Warehouse.</span></span>
18. <span data-ttu-id="786bf-134">Cliquez sur Détails du travail.</span><span class="sxs-lookup"><span data-stu-id="786bf-134">Click Work details.</span></span>
    * <span data-ttu-id="786bf-135">Lorsque l'ordre de fabrication a été déclaré comme terminé, aucune tâche de rangement n'a été générée.</span><span class="sxs-lookup"><span data-stu-id="786bf-135">When the production order was reported as finished, no work was generated for put-away.</span></span> <span data-ttu-id="786bf-136">Cela se produit car une stratégie de travail est définie et empêche la tâche d'être générée lorsque le produit L0101 est déclaré comme terminé à l'emplacement 001.</span><span class="sxs-lookup"><span data-stu-id="786bf-136">This occurs because a work policy is defined that prevents work from being generated when product L0101 is reported as finished to location 001.</span></span>  


