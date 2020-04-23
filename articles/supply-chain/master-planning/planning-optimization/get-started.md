---
title: Prise en main de l'Optimisation de la planification
description: Cette rubrique explique comment utiliser la fonctionnalité d'Optimisation de la planification.
author: ChristianRytt
manager: tfehr
ms.date: 02/10/2020
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
ms.openlocfilehash: 4f9124e824a0b6d5035b2567cb19c2c494390d55
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213513"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="cca15-103">Prise en main de l'Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="cca15-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cca15-104">La fonctionnalité d'Optimisation de la planification ne prend actuellement pas en charge toutes les fonctionnalités disponibles dans le moteur de planification intégré à Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cca15-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="cca15-105">Par conséquent, il est important d'évaluer si la fonctionnalité définie, qui est actuellement disponible dans Optimisation de la planification, répondra à vos attentes.</span><span class="sxs-lookup"><span data-stu-id="cca15-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="cca15-106">Par défaut, la fonctionnalité d'Optimisation de la planification n'est pas activée dans Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="cca15-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="cca15-107">Par conséquent, vous avez une possibilité de faire votre évaluation avant qu'elle ne s'est activée.</span><span class="sxs-lookup"><span data-stu-id="cca15-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="cca15-108">Éventuellement, Optimisation de la planification remplacera le moteur de planification de Supply Chain Management existant.</span><span class="sxs-lookup"><span data-stu-id="cca15-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="cca15-109">Avant d'activer l'Optimisation de la planification, nous vous recommandons fortement d'évaluer les résultats de l'analyse de concordance d'Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="cca15-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="cca15-110">Pour plus d'informations, voir [Analyse de concordance d'Optimisation de la planification](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="cca15-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="licensing"></a><span data-ttu-id="cca15-111">Gestionnaire de licences</span><span class="sxs-lookup"><span data-stu-id="cca15-111">Licensing</span></span>

<span data-ttu-id="cca15-112">Si vous pouvez exécuter la planification à l'aide de votre licence actuelle, vous n'avez pas à en acheter une supplémentaire pour commencer à utiliser Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="cca15-112">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="cca15-113">Installer le complément</span><span class="sxs-lookup"><span data-stu-id="cca15-113">Install the add-in</span></span>

<span data-ttu-id="cca15-114">Pour utiliser l'Optimisation de la planification, installez le complément d'Optimisation de la planification pour Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cca15-114">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="cca15-115">Vous pouvez accéder au complément depuis votre projet LCS et activer la fonctionnalité d'Optimisation de la planification depuis l'interface utilisateur de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cca15-115">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="cca15-116">La configuration requise pour l'optimisation de la planification est un environnement à haute disponibilité compatible LCS (pas un environnement OneBox), avec Dynamics 365 Supply Chain Management version 10.0.7 ou les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="cca15-116">The requirement for Planning Optimization is an LCS enabled high-availability environment (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span>

1. <span data-ttu-id="cca15-117">Connectez-vous à LCS, et ouvrez l'environnement souhaité.</span><span class="sxs-lookup"><span data-stu-id="cca15-117">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="cca15-118">Accédez à **Détails complets**.</span><span class="sxs-lookup"><span data-stu-id="cca15-118">Go to **Full details**.</span></span>
1. <span data-ttu-id="cca15-119">Faites défiler jusqu'à l'organisateur **Compléments d'environnement**.</span><span class="sxs-lookup"><span data-stu-id="cca15-119">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="cca15-120">Sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="cca15-120">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="cca15-121">Sélectionnez **Optimisation de la planification**.</span><span class="sxs-lookup"><span data-stu-id="cca15-121">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="cca15-122">Suivez le guide d'installation, et acceptez les conditions générales du contrat.</span><span class="sxs-lookup"><span data-stu-id="cca15-122">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="cca15-123">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="cca15-123">Select **Install**.</span></span>
1. <span data-ttu-id="cca15-124">Sur l'organisateur **Compléments d'environnement** devriez voir que Planning Optimization est en cours d'installation.</span><span class="sxs-lookup"><span data-stu-id="cca15-124">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="cca15-125">Après quelques minutes **Installation** devrait passer à **Installé** (vous devrez peut-être actualiser la page).</span><span class="sxs-lookup"><span data-stu-id="cca15-125">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="cca15-126">Après l'installation, vous pouvez activer Planning Optimization dans Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cca15-126">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="cca15-127">Intégration d'Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="cca15-127">Planning Optimization integration</span></span>

<span data-ttu-id="cca15-128">Pour configurer si le complément de l'Optimisation de la planification doit être utilisée pour la planification, accédez à **Planification** \> **Paramétrage** \> **Paramètres d'intégration**.</span><span class="sxs-lookup"><span data-stu-id="cca15-128">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="cca15-129">Statut de la connexion</span><span class="sxs-lookup"><span data-stu-id="cca15-129">Connection status</span></span>

<span data-ttu-id="cca15-130">Le statut de connexion indique le statut actuel de la connexion entre Supply Chain Management et le service Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="cca15-130">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="cca15-131">Le tableau suivant présente les valeurs possibles.</span><span class="sxs-lookup"><span data-stu-id="cca15-131">The following table shows the possible values.</span></span>

| <span data-ttu-id="cca15-132">Statut de la connexion</span><span class="sxs-lookup"><span data-stu-id="cca15-132">Connection status</span></span> | <span data-ttu-id="cca15-133">Description</span><span class="sxs-lookup"><span data-stu-id="cca15-133">Description</span></span> | <span data-ttu-id="cca15-134">L'Optimisation de la planification peut-elle être utilisée ?</span><span class="sxs-lookup"><span data-stu-id="cca15-134">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="cca15-135">Connecté</span><span class="sxs-lookup"><span data-stu-id="cca15-135">Connected</span></span> | <span data-ttu-id="cca15-136">Une connexion a été établie entre le service d'Optimisation de la planification et Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cca15-136">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="cca15-137">Oui</span><span class="sxs-lookup"><span data-stu-id="cca15-137">Yes</span></span> |
| <span data-ttu-id="cca15-138">Activation de la connexion</span><span class="sxs-lookup"><span data-stu-id="cca15-138">Enabling connection</span></span> | <span data-ttu-id="cca15-139">Une demande pour activer la connexion au service d'Optimisation de la planification est actuellement en cours.</span><span class="sxs-lookup"><span data-stu-id="cca15-139">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="cca15-140">Non</span><span class="sxs-lookup"><span data-stu-id="cca15-140">No</span></span> |
| <span data-ttu-id="cca15-141">Déconnecté</span><span class="sxs-lookup"><span data-stu-id="cca15-141">Disconnected</span></span> | <span data-ttu-id="cca15-142">Il n'existe aucune connexion au service d'Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="cca15-142">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="cca15-143">La connexion peut être activée depuis LCS, comme décrit précédemment dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="cca15-143">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="cca15-144">Non</span><span class="sxs-lookup"><span data-stu-id="cca15-144">No</span></span> |
| <span data-ttu-id="cca15-145">Désactivation de la connexion</span><span class="sxs-lookup"><span data-stu-id="cca15-145">Disabling connection</span></span> | <span data-ttu-id="cca15-146">Une demande pour désactiver la connexion au service d'Optimisation de la planification est actuellement en cours.</span><span class="sxs-lookup"><span data-stu-id="cca15-146">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="cca15-147">Non</span><span class="sxs-lookup"><span data-stu-id="cca15-147">No</span></span> |
| <span data-ttu-id="cca15-148">Récupération du statut</span><span class="sxs-lookup"><span data-stu-id="cca15-148">Getting status</span></span> | <span data-ttu-id="cca15-149">Le système est en attente des informations relatives au statut provenant d'Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="cca15-149">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="cca15-150">Non</span><span class="sxs-lookup"><span data-stu-id="cca15-150">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="cca15-151">Utilisation de l'option Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="cca15-151">The Use Planning Optimization option</span></span>

<span data-ttu-id="cca15-152">Le paramètre de l'option **Utiliser l'Optimisation de la planification** détermine quel moteur de planification est utilisé pour la planification :</span><span class="sxs-lookup"><span data-stu-id="cca15-152">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="cca15-153">**Oui** – L'Optimisation de la planification est utilisée pour la planification.</span><span class="sxs-lookup"><span data-stu-id="cca15-153">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="cca15-154">**Non** – Le moteur de planification intégré dans Supply Chain Management est utilisé pour la planification.</span><span class="sxs-lookup"><span data-stu-id="cca15-154">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="cca15-155">Si des traitements par lots existants de planification créés pour le moteur de planification intégré de Supply Chain Management sont déclenchés tandis que l'option **Utiliser l'Optimisation de la planification** est définie sur **Oui**, ces tâches échoueront.</span><span class="sxs-lookup"><span data-stu-id="cca15-155">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="cca15-156">Intégration à la configuration</span><span class="sxs-lookup"><span data-stu-id="cca15-156">Integration with the setup</span></span>

<span data-ttu-id="cca15-157">Si l'aperçu Optimisation de la planification est activé, la planification est effectuée à l'aide du complément Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="cca15-157">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="cca15-158">Dans ce cas, les résultats de la planification et le fonctionnalités sont concernés.</span><span class="sxs-lookup"><span data-stu-id="cca15-158">In this case, master planning results and features are affected.</span></span>

## <a name="related-resources"></a><span data-ttu-id="cca15-159">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="cca15-159">Related resources</span></span>

[<span data-ttu-id="cca15-160">Conditions générales pour l'aperçu</span><span class="sxs-lookup"><span data-stu-id="cca15-160">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="cca15-161">Vue d'ensemble de l'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="cca15-161">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="cca15-162">Analyse de concordance d'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="cca15-162">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="cca15-163">Afficher l'historique du plan et les journaux de planification</span><span class="sxs-lookup"><span data-stu-id="cca15-163">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="cca15-164">Appliquer les filtres à un plan</span><span class="sxs-lookup"><span data-stu-id="cca15-164">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="cca15-165">Annuler une tâche de planification</span><span class="sxs-lookup"><span data-stu-id="cca15-165">Cancel a planning job</span></span>](cancel-planning-job.md)
