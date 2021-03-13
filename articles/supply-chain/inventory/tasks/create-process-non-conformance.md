---
title: Créer et traiter une conformité
description: Cette rubrique explique comment effectuer la gestion de non-conformité, en fonction d'un ordre de qualité existant.
author: perlynne
manager: tfehr
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4525e79cb388cc9bbcfe1d038a53cf53916a678c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5008072"
---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="adb68-103">Créer et traiter une conformité</span><span class="sxs-lookup"><span data-stu-id="adb68-103">Create and process a conformance</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="adb68-104">Cette rubrique explique comment effectuer la gestion de non-conformité, en fonction d'un ordre de qualité existant.</span><span class="sxs-lookup"><span data-stu-id="adb68-104">This topic explains how to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="adb68-105">Vous pouvez exécuter cet enregistrement de la société de démonstration USMF et utiliser les valeurs suggérées.</span><span class="sxs-lookup"><span data-stu-id="adb68-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="adb68-106">Généralement, cette procédure est réalisée par le commis à la qualité.</span><span class="sxs-lookup"><span data-stu-id="adb68-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="adb68-107">Il est indispensable de commencer par suivre les instructions de la section [Inspecter la qualité des marchandises](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="adb68-107">As a prerequisite, complete the instructions in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span> <span data-ttu-id="adb68-108">Pour traiter l'approbation d'une non-conformité, l'utilisateur qui exécute l'enregistrement de la tâche doit spécifier une valeur « Nom » affectée sur la page Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="adb68-108">To process the approval of a nonconformance, the user who runs the task recording must have a "Name" value assigned on the Users page.</span></span> <span data-ttu-id="adb68-109">Pour utiliser les notes de document, l'utilisateur doit également avoir activé la gestion des documents dans les options d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="adb68-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="adb68-110">Sélectionnez un ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="adb68-110">Select a quality order</span></span>
1. <span data-ttu-id="adb68-111">Dans le volet de navigation, accédez à **Modules > Gestion des stocks > Tâches périodiques > Gestion de la qualité > Ordres de qualité**.</span><span class="sxs-lookup"><span data-stu-id="adb68-111">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="adb68-112">Dans la liste, sélectionnez l'ordre de qualité créé dans la section [Inspecter la qualité des marchandises](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="adb68-112">In the list, select the quality order that was created in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="adb68-113">Créer une non-conformité</span><span class="sxs-lookup"><span data-stu-id="adb68-113">Create a nonconformance</span></span>
1. <span data-ttu-id="adb68-114">Sélectionnez **Recherches** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="adb68-114">On the Action Pane, select **Inquiries**.</span></span>
2. <span data-ttu-id="adb68-115">Sélectionnez **Non-conformités**.</span><span class="sxs-lookup"><span data-stu-id="adb68-115">Select **Non conformances**.</span></span>
3. <span data-ttu-id="adb68-116">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="adb68-116">Select **New**.</span></span>
4. <span data-ttu-id="adb68-117">Dans le menu déroulant du champ **Type de problème**, sélectionnez le problème qui a été trouvé au cours du processus d'inspection.</span><span class="sxs-lookup"><span data-stu-id="adb68-117">In the drop-down menu of the **Problem type** field, select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="adb68-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="adb68-118">Select **OK**.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="adb68-119">Approuver/rejeter une non-conformité</span><span class="sxs-lookup"><span data-stu-id="adb68-119">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="adb68-120">Sélectionnez **Fonctions**.</span><span class="sxs-lookup"><span data-stu-id="adb68-120">Select **Functions**.</span></span>
2. <span data-ttu-id="adb68-121">Sélectionnez **Approuver la non-conformité**.</span><span class="sxs-lookup"><span data-stu-id="adb68-121">Select **Approve non conformance**.</span></span> <span data-ttu-id="adb68-122">Pour cet exemple, approuvez la non-conformité.</span><span class="sxs-lookup"><span data-stu-id="adb68-122">For this example, approve the nonconformance.</span></span> <span data-ttu-id="adb68-123">Les non-conformités approuvées peuvent être associées à des opérations associées au travail d'enregistrement qui est exécuté dans le cadre de la gestion de la non-conformité et, comme dans cette rubrique, le traitement de la gestion des corrections.</span><span class="sxs-lookup"><span data-stu-id="adb68-123">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this topic, the processing of correction handling.</span></span>  
3. <span data-ttu-id="adb68-124">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="adb68-124">Select **Yes**.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="adb68-125">Créer une action de correction</span><span class="sxs-lookup"><span data-stu-id="adb68-125">Create a correction action</span></span>
1. <span data-ttu-id="adb68-126">Sélectionnez **Corrections**.</span><span class="sxs-lookup"><span data-stu-id="adb68-126">Select **Corrections**.</span></span>
2. <span data-ttu-id="adb68-127">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="adb68-127">Select **New**.</span></span>
3. <span data-ttu-id="adb68-128">Dans le champ **Numéro personnel** de la nouvelle ligne, sélectionnez l'enregistrement souhaité dans le menu déroulant qui s'affiche.</span><span class="sxs-lookup"><span data-stu-id="adb68-128">In the **Personnel number** field of the new row, select the desired record from the drop down menu.</span></span>
4. <span data-ttu-id="adb68-129">Cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="adb68-129">Click **Select**.</span></span>
5. <span data-ttu-id="adb68-130">Sélectionnez **Lier**.</span><span class="sxs-lookup"><span data-stu-id="adb68-130">Select **Attach**.</span></span> <span data-ttu-id="adb68-131">Créez une remarque sur la correction.</span><span class="sxs-lookup"><span data-stu-id="adb68-131">Create a note about the correction.</span></span> <span data-ttu-id="adb68-132">Pour cet exemple, l'action consiste à contacter le fournisseur pour présenter l'incident de non-conformité.</span><span class="sxs-lookup"><span data-stu-id="adb68-132">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
6. <span data-ttu-id="adb68-133">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="adb68-133">Select **New**.</span></span>
7. <span data-ttu-id="adb68-134">Sélectionnez **Note**.</span><span class="sxs-lookup"><span data-stu-id="adb68-134">Select **Note**.</span></span> <span data-ttu-id="adb68-135">Selon le paramétrage d'état, différents types de documents peuvent être imprimés sur les états associés à la gestion de non-conformité.</span><span class="sxs-lookup"><span data-stu-id="adb68-135">Depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
8. <span data-ttu-id="adb68-136">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="adb68-136">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="adb68-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="adb68-137">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="adb68-138">Maintenir une correction</span><span class="sxs-lookup"><span data-stu-id="adb68-138">Maintain a correction</span></span>
1. <span data-ttu-id="adb68-139">Sélectionnez **Marquer comme terminé**.</span><span class="sxs-lookup"><span data-stu-id="adb68-139">Select **Mark complete**.</span></span>
2. <span data-ttu-id="adb68-140">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="adb68-140">Select **OK**.</span></span>
3. <span data-ttu-id="adb68-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="adb68-141">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="adb68-142">Clôturer une non-conformité</span><span class="sxs-lookup"><span data-stu-id="adb68-142">Close a nonconformance</span></span>
1. <span data-ttu-id="adb68-143">Sélectionnez **Fonctions**.</span><span class="sxs-lookup"><span data-stu-id="adb68-143">Select **Functions**.</span></span>
2. <span data-ttu-id="adb68-144">Sélectionnez **Clôturer la non-conformité**.</span><span class="sxs-lookup"><span data-stu-id="adb68-144">Select **Close non conformance**.</span></span>
3. <span data-ttu-id="adb68-145">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="adb68-145">Select **Yes**.</span></span>
4. <span data-ttu-id="adb68-146">Fermez les pages.</span><span class="sxs-lookup"><span data-stu-id="adb68-146">Close the pages.</span></span>
