---
title: Résoudre les problèmes d'optimisation de la planification
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation de l'optimisation de la planification.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 8e67a6faf52b51264555b06f56b289d19ca580d6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992493"
---
# <a name="troubleshoot-planning-optimization"></a><span data-ttu-id="3faac-103">Résoudre les problèmes d'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="3faac-103">Troubleshoot Planning Optimization</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3faac-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de l'utilisation de l'optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="3faac-104">This topic describes how to fix common issues that you might encounter while working with Planning Optimization.</span></span>

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a><span data-ttu-id="3faac-105">L'installation du complément Optimisation de la planification n'a pas aboutie</span><span class="sxs-lookup"><span data-stu-id="3faac-105">Installation of the Planning Optimization add-in doesn't complete</span></span>

<span data-ttu-id="3faac-106">L'Optimisation de la planification nécessite que Lifecycle Services (LCS) soit activé, un environnement à haute disponibilité, niveau 2 ou supérieur (pas un environnement OneBox), avec Dynamics 365 Supply Chain Management version 10.0.7 ou les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="3faac-106">Planning Optimization requires a Lifecycle Services (LCS) enabled, high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="3faac-107">Si vous essayez d'installer le complément dans un environnement OneBox, l'installation ne va pas aboutir.</span><span class="sxs-lookup"><span data-stu-id="3faac-107">If you try to install the add-in on a OneBox environment, the installation won't complete.</span></span>

<span data-ttu-id="3faac-108">**Correction** : Annulez l'installation et utilisez un environnement à haute disponibilité, de niveau 2 ou supérieur (pas un environnement OneBox).</span><span class="sxs-lookup"><span data-stu-id="3faac-108">**Fix**: Cancel the installation and use a high-availability environment, tier 2 or higher (not a OneBox environment).</span></span>

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a><span data-ttu-id="3faac-109">La planification des travaux par lots échoue lorsque l'optimisation de la planification est activée.</span><span class="sxs-lookup"><span data-stu-id="3faac-109">Planning of batch jobs fails when Planning Optimization is enabled</span></span>

<span data-ttu-id="3faac-110">Lorsque vous activez l'optimisation de la planification, le moteur de planification principal intégré est automatiquement désactivé.</span><span class="sxs-lookup"><span data-stu-id="3faac-110">When you enable Planning Optimization, the built-in master planning engine is automatically disabled.</span></span> <span data-ttu-id="3faac-111">Les traitements par lots de planification créés pour le moteur de planification intégré de Supply Chain Management vont échouer s'ils sont déclenchés tandis que l'optimisation de la planification est activée.</span><span class="sxs-lookup"><span data-stu-id="3faac-111">Master planning batch jobs that were created for the built-in Supply Chain Management planning engine will fail if they are triggered while Planning Optimization is enabled.</span></span> <span data-ttu-id="3faac-112">Vous risquez de recevoir un message d'erreur tel que *Cette opération a déclenché la planification principale qui n'est pas prise en charge lorsque l'optimisation de la planification est activée*.</span><span class="sxs-lookup"><span data-stu-id="3faac-112">You may receive an error message such as *This operation triggered master planning that isn't supported when Planning Optimization is enabled*.</span></span>

<span data-ttu-id="3faac-113">**Correction** : Annulez tous les travaux par lots de planification principale créés pour le moteur de planification intégré de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3faac-113">**Fix**: Cancel all master planning batch jobs that were created for the built-in Supply Chain Management planning engine.</span></span>

## <a name="planning-optimization-results-are-different-from-earlier-results"></a><span data-ttu-id="3faac-114">Les résultats de l'optimisation de la planification sont différents des résultats précédents</span><span class="sxs-lookup"><span data-stu-id="3faac-114">Planning Optimization results are different from earlier results</span></span>

<span data-ttu-id="3faac-115">L'optimisation de la planification diffère de la conception de planification principale intégrée dans certains domaines.</span><span class="sxs-lookup"><span data-stu-id="3faac-115">Planning Optimization differs from the built-in master planning design in some areas.</span></span> <span data-ttu-id="3faac-116">Cela peut également être dû à des fonctionnalités en attente.</span><span class="sxs-lookup"><span data-stu-id="3faac-116">This can also be caused by pending features.</span></span>

<span data-ttu-id="3faac-117">**Correction** : Exécutez l'analyse d'ajustement de l'optimisation de la planification, puis analysez les résultats tout en vous référant à la documentation associée pour comprendre l'impact.</span><span class="sxs-lookup"><span data-stu-id="3faac-117">**Fix**: Run Planning Optimization fit analysis and then analyze the results while referring to the related documentation to understand the impact.</span></span> <span data-ttu-id="3faac-118">Pour plus d'informations, voir [Analyse de concordance d'Optimisation de la planification](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="3faac-118">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

## <a name="master-planning-doesnt-respect-the-coverage-time-fence"></a><span data-ttu-id="3faac-119">La planification ne respecte pas la plage de gestion de la couverture</span><span class="sxs-lookup"><span data-stu-id="3faac-119">Master planning doesn't respect the coverage time fence</span></span>

<span data-ttu-id="3faac-120">Cela est dû à une fonctionnalité en attente pour l'optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="3faac-120">This is caused by a pending feature for Planning Optimization.</span></span>

<span data-ttu-id="3faac-121">**Correction** : Jusqu'à ce que la fonction en attente soit disponible, filtrez ou supprimez les ordres planifiés pour supprimer les suggestions d'approvisionnement en dehors de la période de couverture.</span><span class="sxs-lookup"><span data-stu-id="3faac-121">**Fix**: Until the pending feature is available, filter or delete planned orders to remove supply suggestions outside of the coverage time fence.</span></span>

## <a name="cant-enable-planning-optimization"></a><span data-ttu-id="3faac-122">Impossible d'activer l'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="3faac-122">Can't enable Planning Optimization</span></span>

<span data-ttu-id="3faac-123">Le **Statut de connexion** doit être **Connecté** avant de pouvoir définir **Utiliser l'optimisation de la planification** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="3faac-123">The **Connection status** must be **Connected** before you can set **Use Planning Optimization** to **Yes**.</span></span> <span data-ttu-id="3faac-124">Pour plus d'informations, voir [Prise en main d'Optimisation de la planification](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="3faac-124">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="3faac-125">**Correction** : Assurez-vous que le complément Optimisation de la planification a été installé avec succès.</span><span class="sxs-lookup"><span data-stu-id="3faac-125">**Fix**: Make sure that the Planning Optimization add-in was installed successfully.</span></span>

## <a name="error-message-is-shown-during-ctp"></a><span data-ttu-id="3faac-126">Un message d'erreur s'affiche pendant le CTP</span><span class="sxs-lookup"><span data-stu-id="3faac-126">Error message is shown during CTP</span></span>

<span data-ttu-id="3faac-127">Si vous essayez d'exécuter capable to promise (CTP) à partir d'une commande client lorsque l'optimisation de la planification est activée, vous recevrez le message d'erreur suivant : *Cette opération a déclenché la planification principale qui n'est pas prise en charge lorsque l'optimisation de la planification est activée*.</span><span class="sxs-lookup"><span data-stu-id="3faac-127">If you try to run capable to promise (CTP) from a sales order when Planning Optimization is enabled, you will receive the following error message: *This operation triggered master planning that isn't supported when the Planning Optimization is enabled*.</span></span>

<span data-ttu-id="3faac-128">Ceci est lié à une fonctionnalité en attente qui est prévue dans le cadre de la prise en charge des ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="3faac-128">This is related to a pending feature that is planned as part of the support for production orders.</span></span>

<span data-ttu-id="3faac-129">**Correction :** Évitez les calculs de CTP lorsque l'optimisation de la planification est activée jusqu'à ce que la prise en charge de CTP soit disponible.</span><span class="sxs-lookup"><span data-stu-id="3faac-129">**Fix:** Avoid CTP calculations when Planning Optimization is enabled until CTP support is available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3faac-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3faac-130">Additional resources</span></span>

[<span data-ttu-id="3faac-131">Mise en route de l'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="3faac-131">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="3faac-132">Analyse de concordance pour l’optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="3faac-132">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)
