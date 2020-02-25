---
title: Prise en main de l'Optimisation de la planification
description: Cette rubrique explique comment utiliser la fonctionnalité d'Optimisation de la planification.
author: ChristianRytt
manager: AnnBe
ms.date: 01/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 3e0371c6addc0412dc2fc105891b012941e92a06
ms.sourcegitcommit: e5a3c85a322a9216b8f176536d664fef40ae0bec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/17/2020
ms.locfileid: "2971462"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="d1515-103">Prise en main de l'Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="d1515-103">Get started with Planning Optimization</span></span>

<span data-ttu-id="d1515-104">La fonctionnalité d'Optimisation de la planification ne prend actuellement pas en charge toutes les fonctionnalités disponibles dans le moteur de planification intégré à Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d1515-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="d1515-105">Par conséquent, il est important d'évaluer si la fonctionnalité définie, qui est actuellement disponible dans Optimisation de la planification, répondra à vos attentes.</span><span class="sxs-lookup"><span data-stu-id="d1515-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="d1515-106">Par défaut, la fonctionnalité d'Optimisation de la planification n'est pas activée dans Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d1515-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="d1515-107">Par conséquent, vous avez une possibilité de faire votre évaluation avant qu'elle ne s'est activée.</span><span class="sxs-lookup"><span data-stu-id="d1515-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="d1515-108">Éventuellement, Optimisation de la planification remplacera le moteur de planification de Supply Chain Management existant.</span><span class="sxs-lookup"><span data-stu-id="d1515-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="d1515-109">Avant d'activer l'Optimisation de la planification, nous vous recommandons fortement d'évaluer les résultats de l'analyse de concordance d'Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="d1515-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="d1515-110">Pour plus d'informations, voir [Analyse de concordance d'Optimisation de la planification](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="d1515-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="licensing"></a><span data-ttu-id="d1515-111">Gestionnaire de licences</span><span class="sxs-lookup"><span data-stu-id="d1515-111">Licensing</span></span>

<span data-ttu-id="d1515-112">Si vous pouvez exécuter la planification à l'aide de votre licence actuelle, vous n'avez pas à en acheter une supplémentaire pour commencer à utiliser Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="d1515-112">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="d1515-113">Installer le complément</span><span class="sxs-lookup"><span data-stu-id="d1515-113">Install the add-in</span></span>

<span data-ttu-id="d1515-114">Pour utiliser l'Optimisation de la planification, installez le complément d'Optimisation de la planification pour Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d1515-114">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="d1515-115">Vous pouvez accéder au complément depuis votre projet LCS et activer la fonctionnalité d'Optimisation de la planification depuis l'interface utilisateur de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d1515-115">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

1. <span data-ttu-id="d1515-116">Connectez-vous à LCS, et ouvrez l'environnement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d1515-116">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="d1515-117">Accédez à **Détails complets**.</span><span class="sxs-lookup"><span data-stu-id="d1515-117">Go to **Full details**.</span></span>
1. <span data-ttu-id="d1515-118">Faites défiler jusqu'à l'organisateur **Compléments d'environnement**.</span><span class="sxs-lookup"><span data-stu-id="d1515-118">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="d1515-119">Sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="d1515-119">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="d1515-120">Sélectionnez **Optimisation de la planification**.</span><span class="sxs-lookup"><span data-stu-id="d1515-120">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="d1515-121">Suivez le guide d'installation, et acceptez les conditions générales du contrat.</span><span class="sxs-lookup"><span data-stu-id="d1515-121">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="d1515-122">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="d1515-122">Select **Install**.</span></span>
1. <span data-ttu-id="d1515-123">Sur l'organisateur **Compléments d'environnement** devriez voir que Planning Optimization est en cours d'installation.</span><span class="sxs-lookup"><span data-stu-id="d1515-123">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="d1515-124">Après quelques minutes **Installation** devrait passer à **Installé** (vous devrez peut-être actualiser la page).</span><span class="sxs-lookup"><span data-stu-id="d1515-124">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="d1515-125">Après l'installation, vous pouvez activer Planning Optimization dans Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d1515-125">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="d1515-126">Intégration d'Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="d1515-126">Planning Optimization integration</span></span>

<span data-ttu-id="d1515-127">Pour configurer si le complément de l'Optimisation de la planification doit être utilisée pour la planification, accédez à **Planification** \> **Paramétrage** \> **Paramètres d'intégration**.</span><span class="sxs-lookup"><span data-stu-id="d1515-127">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="d1515-128">Statut de la connexion</span><span class="sxs-lookup"><span data-stu-id="d1515-128">Connection status</span></span>

<span data-ttu-id="d1515-129">Le statut de connexion indique le statut actuel de la connexion entre Supply Chain Management et le service Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="d1515-129">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="d1515-130">Le tableau suivant présente les valeurs possibles.</span><span class="sxs-lookup"><span data-stu-id="d1515-130">The following table shows the possible values.</span></span>

| <span data-ttu-id="d1515-131">Statut de la connexion</span><span class="sxs-lookup"><span data-stu-id="d1515-131">Connection status</span></span> | <span data-ttu-id="d1515-132">Description</span><span class="sxs-lookup"><span data-stu-id="d1515-132">Description</span></span> | <span data-ttu-id="d1515-133">L'Optimisation de la planification peut-elle être utilisée ?</span><span class="sxs-lookup"><span data-stu-id="d1515-133">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="d1515-134">Connecté</span><span class="sxs-lookup"><span data-stu-id="d1515-134">Connected</span></span> | <span data-ttu-id="d1515-135">Une connexion a été établie entre le service d'Optimisation de la planification et Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d1515-135">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="d1515-136">Oui</span><span class="sxs-lookup"><span data-stu-id="d1515-136">Yes</span></span> |
| <span data-ttu-id="d1515-137">Activation de la connexion</span><span class="sxs-lookup"><span data-stu-id="d1515-137">Enabling connection</span></span> | <span data-ttu-id="d1515-138">Une demande pour activer la connexion au service d'Optimisation de la planification est actuellement en cours.</span><span class="sxs-lookup"><span data-stu-id="d1515-138">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="d1515-139">Non</span><span class="sxs-lookup"><span data-stu-id="d1515-139">No</span></span> |
| <span data-ttu-id="d1515-140">Déconnecté</span><span class="sxs-lookup"><span data-stu-id="d1515-140">Disconnected</span></span> | <span data-ttu-id="d1515-141">Il n'existe aucune connexion au service d'Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="d1515-141">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="d1515-142">La connexion peut être activée depuis LCS, comme décrit précédemment dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="d1515-142">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="d1515-143">Non</span><span class="sxs-lookup"><span data-stu-id="d1515-143">No</span></span> |
| <span data-ttu-id="d1515-144">Désactivation de la connexion</span><span class="sxs-lookup"><span data-stu-id="d1515-144">Disabling connection</span></span> | <span data-ttu-id="d1515-145">Une demande pour désactiver la connexion au service d'Optimisation de la planification est actuellement en cours.</span><span class="sxs-lookup"><span data-stu-id="d1515-145">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="d1515-146">Non</span><span class="sxs-lookup"><span data-stu-id="d1515-146">No</span></span> |
| <span data-ttu-id="d1515-147">Récupération du statut</span><span class="sxs-lookup"><span data-stu-id="d1515-147">Getting status</span></span> | <span data-ttu-id="d1515-148">Le système est en attente des informations relatives au statut provenant d'Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="d1515-148">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="d1515-149">Non</span><span class="sxs-lookup"><span data-stu-id="d1515-149">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="d1515-150">Utilisation de l'option Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="d1515-150">The Use Planning Optimization option</span></span>

<span data-ttu-id="d1515-151">Le paramètre de l'option **Utiliser l'Optimisation de la planification** détermine quel moteur de planification est utilisé pour la planification :</span><span class="sxs-lookup"><span data-stu-id="d1515-151">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="d1515-152">**Oui** – L'Optimisation de la planification est utilisée pour la planification.</span><span class="sxs-lookup"><span data-stu-id="d1515-152">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="d1515-153">**Non** – Le moteur de planification intégré dans Supply Chain Management est utilisé pour la planification.</span><span class="sxs-lookup"><span data-stu-id="d1515-153">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="d1515-154">Si des traitements par lots existants de planification créés pour le moteur de planification intégré de Supply Chain Management sont déclenchés tandis que l'option **Utiliser l'Optimisation de la planification** est définie sur **Oui**, ces tâches échoueront.</span><span class="sxs-lookup"><span data-stu-id="d1515-154">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="d1515-155">Intégration à la configuration</span><span class="sxs-lookup"><span data-stu-id="d1515-155">Integration with the setup</span></span>

<span data-ttu-id="d1515-156">Si l'aperçu Optimisation de la planification est activé, la planification est effectuée à l'aide du complément Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="d1515-156">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="d1515-157">Dans ce cas, les résultats de la planification et le fonctionnalités sont concernés.</span><span class="sxs-lookup"><span data-stu-id="d1515-157">In this case, master planning results and features are affected.</span></span>

## <a name="related-resources"></a><span data-ttu-id="d1515-158">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="d1515-158">Related resources</span></span>

[<span data-ttu-id="d1515-159">Conditions générales pour l'aperçu</span><span class="sxs-lookup"><span data-stu-id="d1515-159">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="d1515-160">Vue d'ensemble de l'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="d1515-160">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="d1515-161">Analyse de concordance d'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="d1515-161">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="d1515-162">Afficher l'historique du plan et les journaux de planification</span><span class="sxs-lookup"><span data-stu-id="d1515-162">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="d1515-163">Appliquer les filtres à un plan</span><span class="sxs-lookup"><span data-stu-id="d1515-163">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="d1515-164">Annuler une tâche de planification</span><span class="sxs-lookup"><span data-stu-id="d1515-164">Cancel a planning job</span></span>](cancel-planning-job.md)
