---
title: Prise en main de l'Optimisation de la planification
description: Cette rubrique explique comment utiliser la fonctionnalité d'Optimisation de la planification.
author: ChristianRytt
manager: tfehr
ms.date: 05/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ce1bbb18e9a448e84d001a4195421d2b0e4af5be
ms.sourcegitcommit: c0d37fdd70f3dec4605fdee6f981f84a49be9b9e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2020
ms.locfileid: "3339876"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="b5f27-103">Prise en main de l'Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="b5f27-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b5f27-104">La fonctionnalité d'Optimisation de la planification ne prend actuellement pas en charge toutes les fonctionnalités disponibles dans le moteur de planification intégré à Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b5f27-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="b5f27-105">Par conséquent, il est important d'évaluer si la fonctionnalité définie, qui est actuellement disponible dans Optimisation de la planification, répondra à vos attentes.</span><span class="sxs-lookup"><span data-stu-id="b5f27-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="b5f27-106">Par défaut, la fonctionnalité d'Optimisation de la planification n'est pas activée dans Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b5f27-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="b5f27-107">Par conséquent, vous avez une possibilité de faire votre évaluation avant qu'elle ne s'est activée.</span><span class="sxs-lookup"><span data-stu-id="b5f27-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="b5f27-108">Éventuellement, Optimisation de la planification remplacera le moteur de planification de Supply Chain Management existant.</span><span class="sxs-lookup"><span data-stu-id="b5f27-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="b5f27-109">Avant d'activer l'Optimisation de la planification, nous vous recommandons fortement d'évaluer les résultats de l'analyse de concordance d'Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="b5f27-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="b5f27-110">Pour plus d'informations, voir [Analyse de concordance d'Optimisation de la planification](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="b5f27-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="availability"></a><span data-ttu-id="b5f27-111">Disponibilité</span><span class="sxs-lookup"><span data-stu-id="b5f27-111">Availability</span></span>
<span data-ttu-id="b5f27-112">L'optimisation de la planification est actuellement disponible dans les zones géographiques Azure suivantes : États-Unis, Canada, Europe, Royaume-Uni et Australie.</span><span class="sxs-lookup"><span data-stu-id="b5f27-112">Planning Optimization is currently available in the following Azure geographies: United States, Canada, Europe, United Kingdom, and Australia.</span></span> <span data-ttu-id="b5f27-113">Si vous essayez d'installer le complément à partir d'une autre région géographique, LCS affichera un message indiquant que cette zone géographique n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="b5f27-113">If you try to install the add-in from another geographic region, then LCS will show a message that this geographic is not supported.</span></span>

<span data-ttu-id="b5f27-114">Notez que Optimisation de la planification ne prend pas en charge les déploiements locaux de Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b5f27-114">Note that Planning Optimization does not support on-premises deployments of Dynamics 365 Supply Chain Management.</span></span>

### <a name="licensing"></a><span data-ttu-id="b5f27-115">Gestionnaire de licences</span><span class="sxs-lookup"><span data-stu-id="b5f27-115">Licensing</span></span>

<span data-ttu-id="b5f27-116">Si vous pouvez exécuter la planification à l'aide de votre licence actuelle, vous n'avez pas à en acheter une supplémentaire pour commencer à utiliser Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="b5f27-116">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="b5f27-117">Installer le complément</span><span class="sxs-lookup"><span data-stu-id="b5f27-117">Install the add-in</span></span>

<span data-ttu-id="b5f27-118">Pour utiliser l'Optimisation de la planification, installez le complément d'Optimisation de la planification pour Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b5f27-118">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="b5f27-119">Vous pouvez accéder au complément depuis votre projet LCS et activer la fonctionnalité d'Optimisation de la planification depuis l'interface utilisateur de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b5f27-119">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="b5f27-120">La configuration requise pour l'optimisation de la planification est un environnement à haute disponibilité compatible LCS, niveau 2 ou supérieur (pas un environnement OneBox), avec Dynamics 365 Supply Chain Management version 10.0.7 ou les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="b5f27-120">The requirement for Planning Optimization is an LCS enabled high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="b5f27-121">Si vous essayez d'installer le complément dans un environnement OneBox, l'installation ne se terminera pas et vous devrez annuler l'installation.</span><span class="sxs-lookup"><span data-stu-id="b5f27-121">If you try to install the add-in on a OneBox environment, the installation will not complete and you will need to cancel the installation.</span></span>

1. <span data-ttu-id="b5f27-122">Connectez-vous à LCS, et ouvrez l'environnement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b5f27-122">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="b5f27-123">Accédez à **Détails complets**.</span><span class="sxs-lookup"><span data-stu-id="b5f27-123">Go to **Full details**.</span></span>
1. <span data-ttu-id="b5f27-124">Faites défiler jusqu'à l'organisateur **Compléments d'environnement**.</span><span class="sxs-lookup"><span data-stu-id="b5f27-124">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="b5f27-125">Sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="b5f27-125">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="b5f27-126">Sélectionnez **Optimisation de la planification**.</span><span class="sxs-lookup"><span data-stu-id="b5f27-126">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="b5f27-127">Suivez le guide d'installation, et acceptez les conditions générales du contrat.</span><span class="sxs-lookup"><span data-stu-id="b5f27-127">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="b5f27-128">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="b5f27-128">Select **Install**.</span></span>
1. <span data-ttu-id="b5f27-129">Sur l'organisateur **Compléments d'environnement** devriez voir que Planning Optimization est en cours d'installation.</span><span class="sxs-lookup"><span data-stu-id="b5f27-129">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="b5f27-130">Après quelques minutes **Installation** devrait passer à **Installé** (vous devrez peut-être actualiser la page).</span><span class="sxs-lookup"><span data-stu-id="b5f27-130">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="b5f27-131">Après l'installation, vous pouvez activer Planning Optimization dans Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b5f27-131">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="b5f27-132">Intégration d'Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="b5f27-132">Planning Optimization integration</span></span>

<span data-ttu-id="b5f27-133">Pour configurer si le complément de l'Optimisation de la planification doit être utilisée pour la planification, accédez à **Planification** \> **Paramétrage** \> **Paramètres d'intégration**.</span><span class="sxs-lookup"><span data-stu-id="b5f27-133">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="b5f27-134">Statut de la connexion</span><span class="sxs-lookup"><span data-stu-id="b5f27-134">Connection status</span></span>

<span data-ttu-id="b5f27-135">Le statut de connexion indique le statut actuel de la connexion entre Supply Chain Management et le service Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="b5f27-135">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="b5f27-136">Le tableau suivant présente les valeurs possibles.</span><span class="sxs-lookup"><span data-stu-id="b5f27-136">The following table shows the possible values.</span></span>

| <span data-ttu-id="b5f27-137">Statut de la connexion</span><span class="sxs-lookup"><span data-stu-id="b5f27-137">Connection status</span></span> | <span data-ttu-id="b5f27-138">Description</span><span class="sxs-lookup"><span data-stu-id="b5f27-138">Description</span></span> | <span data-ttu-id="b5f27-139">L'Optimisation de la planification peut-elle être utilisée ?</span><span class="sxs-lookup"><span data-stu-id="b5f27-139">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="b5f27-140">Connecté</span><span class="sxs-lookup"><span data-stu-id="b5f27-140">Connected</span></span> | <span data-ttu-id="b5f27-141">Une connexion a été établie entre le service d'Optimisation de la planification et Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b5f27-141">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="b5f27-142">Oui</span><span class="sxs-lookup"><span data-stu-id="b5f27-142">Yes</span></span> |
| <span data-ttu-id="b5f27-143">Activation de la connexion</span><span class="sxs-lookup"><span data-stu-id="b5f27-143">Enabling connection</span></span> | <span data-ttu-id="b5f27-144">Une demande pour activer la connexion au service d'Optimisation de la planification est actuellement en cours.</span><span class="sxs-lookup"><span data-stu-id="b5f27-144">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="b5f27-145">Non</span><span class="sxs-lookup"><span data-stu-id="b5f27-145">No</span></span> |
| <span data-ttu-id="b5f27-146">Déconnecté</span><span class="sxs-lookup"><span data-stu-id="b5f27-146">Disconnected</span></span> | <span data-ttu-id="b5f27-147">Il n'existe aucune connexion au service d'Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="b5f27-147">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="b5f27-148">La connexion peut être activée depuis LCS, comme décrit précédemment dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b5f27-148">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="b5f27-149">Non</span><span class="sxs-lookup"><span data-stu-id="b5f27-149">No</span></span> |
| <span data-ttu-id="b5f27-150">Désactivation de la connexion</span><span class="sxs-lookup"><span data-stu-id="b5f27-150">Disabling connection</span></span> | <span data-ttu-id="b5f27-151">Une demande pour désactiver la connexion au service d'Optimisation de la planification est actuellement en cours.</span><span class="sxs-lookup"><span data-stu-id="b5f27-151">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="b5f27-152">Non</span><span class="sxs-lookup"><span data-stu-id="b5f27-152">No</span></span> |
| <span data-ttu-id="b5f27-153">Récupération du statut</span><span class="sxs-lookup"><span data-stu-id="b5f27-153">Getting status</span></span> | <span data-ttu-id="b5f27-154">Le système est en attente des informations relatives au statut provenant d'Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="b5f27-154">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="b5f27-155">Non</span><span class="sxs-lookup"><span data-stu-id="b5f27-155">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="b5f27-156">Utilisation de l'option Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="b5f27-156">The Use Planning Optimization option</span></span>

<span data-ttu-id="b5f27-157">Le paramètre de l'option **Utiliser l'Optimisation de la planification** détermine quel moteur de planification est utilisé pour la planification :</span><span class="sxs-lookup"><span data-stu-id="b5f27-157">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="b5f27-158">**Oui** – L'Optimisation de la planification est utilisée pour la planification.</span><span class="sxs-lookup"><span data-stu-id="b5f27-158">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="b5f27-159">**Non** – Le moteur de planification intégré dans Supply Chain Management est utilisé pour la planification.</span><span class="sxs-lookup"><span data-stu-id="b5f27-159">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="b5f27-160">Si des traitements par lots existants de planification créés pour le moteur de planification intégré de Supply Chain Management sont déclenchés tandis que l'option **Utiliser l'Optimisation de la planification** est définie sur **Oui**, ces tâches échoueront.</span><span class="sxs-lookup"><span data-stu-id="b5f27-160">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="b5f27-161">Intégration à la configuration</span><span class="sxs-lookup"><span data-stu-id="b5f27-161">Integration with the setup</span></span>

<span data-ttu-id="b5f27-162">Si l'aperçu Optimisation de la planification est activé, la planification est effectuée à l'aide du complément Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="b5f27-162">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="b5f27-163">Dans ce cas, les résultats de la planification et le fonctionnalités sont concernés.</span><span class="sxs-lookup"><span data-stu-id="b5f27-163">In this case, master planning results and features are affected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b5f27-164">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b5f27-164">Additional resources</span></span>

[<span data-ttu-id="b5f27-165">Conditions générales pour l'aperçu</span><span class="sxs-lookup"><span data-stu-id="b5f27-165">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="b5f27-166">Vue d'ensemble de l'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="b5f27-166">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="b5f27-167">Analyse de concordance d'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="b5f27-167">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="b5f27-168">Afficher l'historique du plan et les journaux de planification</span><span class="sxs-lookup"><span data-stu-id="b5f27-168">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="b5f27-169">Appliquer les filtres à un plan</span><span class="sxs-lookup"><span data-stu-id="b5f27-169">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="b5f27-170">Annuler une tâche de planification</span><span class="sxs-lookup"><span data-stu-id="b5f27-170">Cancel a planning job</span></span>](cancel-planning-job.md)
