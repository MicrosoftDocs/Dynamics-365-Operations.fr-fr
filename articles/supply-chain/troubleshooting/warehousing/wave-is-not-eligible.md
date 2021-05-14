---
title: La vague n'est pas éligible pour le nettoyage
description: La vague n'est pas éligible pour le nettoyage
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3e5142cf40a6c0d308e8e952bbe17e85b498826d
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924325"
---
# <a name="wave-isnt-eligible-for-cleanup"></a><span data-ttu-id="8399e-103">La vague n'est pas éligible pour le nettoyage</span><span class="sxs-lookup"><span data-stu-id="8399e-103">Wave isn't eligible for cleanup</span></span>

<span data-ttu-id="8399e-104">Code d'erreur : WaveNotEligibleForCleanup</span><span class="sxs-lookup"><span data-stu-id="8399e-104">Error code: WaveNotEligibleForCleanup</span></span>

## <a name="symptoms"></a><span data-ttu-id="8399e-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="8399e-105">Symptoms</span></span>

<span data-ttu-id="8399e-106">Le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="8399e-106">The system shows the following error message:</span></span>

> <span data-ttu-id="8399e-107">La vague %1 n'est pas éligible pour le nettoyage.</span><span class="sxs-lookup"><span data-stu-id="8399e-107">Wave %1 is not eligible for cleanup.</span></span>

<span data-ttu-id="8399e-108">Les données de la vague ne peuvent pas être nettoyées.</span><span class="sxs-lookup"><span data-stu-id="8399e-108">The wave data can't be cleaned up.</span></span>  

## <a name="cause"></a><span data-ttu-id="8399e-109">Cause</span><span class="sxs-lookup"><span data-stu-id="8399e-109">Cause</span></span>

<span data-ttu-id="8399e-110">La vague est en cours de traitement, comme l'indique l'une des conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="8399e-110">The wave is currently being processed, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="8399e-111">Le champ **Statut de vague** est défini sur *En cours d’exécution*.</span><span class="sxs-lookup"><span data-stu-id="8399e-111">The **Wave status** field is set to *Executing*.</span></span>
- <span data-ttu-id="8399e-112">Lorsque vous sélectionnez **Traitement par lots** dans le groupe **Vague** de l'onglet **Vague** du volet Actions, le champ **Statut** n'est pas défini sur *Terminé*, *Erreur*, ou alors *Annulé*.</span><span class="sxs-lookup"><span data-stu-id="8399e-112">When you select **Batch job** in the **Wave** group on the **Wave** tab of the Action Pane, the **Status** field isn't set to *Ended*, *Error*, or *Canceled*.</span></span> <span data-ttu-id="8399e-113">Par conséquent, un traitement par lots est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="8399e-113">Therefore, a batch job is currently running.</span></span>

## <a name="resolution"></a><span data-ttu-id="8399e-114">Résolution</span><span class="sxs-lookup"><span data-stu-id="8399e-114">Resolution</span></span>

<span data-ttu-id="8399e-115">Dans le volet Actions, sur l'onglet **Vague**, dans le groupe **Vague**, sélectionnez **Traitement par lots**, puis suivez l'une de ces étapes :</span><span class="sxs-lookup"><span data-stu-id="8399e-115">On the Action Pane, on the **Wave** tab, in the **Wave** group, select **Batch job**, and then follow one of these steps:</span></span>

- <span data-ttu-id="8399e-116">Si le champ **Statut** est défini sur *Exécution* : Dans le volet Actions, sur l'onglet **Traitement par lots**, dans le groupe **Traitement par lots**, sélectionnez **Afficher les tâches**.</span><span class="sxs-lookup"><span data-stu-id="8399e-116">If the **Status** field is set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Batch job** group, select **View tasks**.</span></span> <span data-ttu-id="8399e-117">Vous pouvez suivre la progression en actualisant la page **Tâches des traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="8399e-117">You can follow the progress by refreshing the **Batch tasks** page.</span></span>
- <span data-ttu-id="8399e-118">Si le champ **Statut** n'est pas défini sur *Exécution* : Dans le volet Actions, sur l'onglet **Traitement par lots**, dans le groupe **Fonction**, sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="8399e-118">If the **Status** field isn't set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Functions** group, select **Change status**.</span></span> <span data-ttu-id="8399e-119">Dans le champ **Sélectionner un nouveau statut**, sélectionnez *En attente*.</span><span class="sxs-lookup"><span data-stu-id="8399e-119">In the **Select new status** field, select *Waiting*.</span></span> <span data-ttu-id="8399e-120">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="8399e-120">Then select **OK**.</span></span>
