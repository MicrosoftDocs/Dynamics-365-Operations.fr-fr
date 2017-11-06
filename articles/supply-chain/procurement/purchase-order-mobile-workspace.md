---
title: Espace de travail mobile Approbation des commandes fournisseur
description: "Cette rubrique fournit des informations sur l'espace de travail mobile Approbation des commandes fournisseur, qui permet d'afficher les commandes fournisseur et d'y répondre par des actions. Par exemple, vous pouvez approuver ou rejeter une commande fournisseur."
author: mkirknel
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, Retail
ms.custom: 30211
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 60744c2b90e64ac77155ba28cdc4fcf65fee1bb6
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="purchase-order-approval-mobile-workspace"></a><span data-ttu-id="b9b2b-104">Espace de travail mobile Approbation des commandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="b9b2b-104">Purchase order approval mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]

<span data-ttu-id="b9b2b-105">Cette rubrique fournit des informations sur l'espace de travail mobile **Approbation des commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-105">This topic provides information about the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="b9b2b-106">Cet espace de travail permet d'afficher les commandes fournisseur et d'y répondre par des actions.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-106">This workspace lets you view purchase orders and respond to them through actions.</span></span> <span data-ttu-id="b9b2b-107">Par exemple, vous pouvez approuver ou rejeter une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-107">For example, you can approve or reject a purchase order.</span></span>
 
## <a name="overview"></a><span data-ttu-id="b9b2b-108">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="b9b2b-108">Overview</span></span> 
<span data-ttu-id="b9b2b-109">Les commandes fournisseur qui nécessitent une approbation passent par un workflow d'approbation.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-109">Purchase orders that requires approval go through an approval workflow.</span></span> <span data-ttu-id="b9b2b-110">Le workflow peut inclure plusieurs étapes qui nécessitent qu'une ou plusieurs personnes effectuent des actions.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-110">The workflow can include various steps that require that one or more people take action.</span></span> <span data-ttu-id="b9b2b-111">Par exemple, une personne devra peut-être exécuter une tâche ou approuver la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-111">For example, a person might have to complete a task or approve the purchase order.</span></span> 

<span data-ttu-id="b9b2b-112">L'espace de travail mobile **Approbation des commandes fournisseur** permet d'afficher facilement les commandes fournisseur depuis votre appareil mobile et d'y répondre.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-112">The **Purchase order approval** mobile workspace lets you easily view and respond to purchase orders from your mobile device.</span></span> <span data-ttu-id="b9b2b-113">Cet espace de travail permet également d'effectuer les mêmes actions de workflow que celles que vous pouvez effectuer dans le client Web Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-113">This workspace also lets you take the same workflow actions that you can take from the Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, web client.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b9b2b-114">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="b9b2b-114">Prerequisites</span></span>
<span data-ttu-id="b9b2b-115">Les conditions préalables varient, en fonction de la version de Finance and Operations qui a été déployée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-115">The prerequisites vary, depending on the version of Finance and Operations that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a><span data-ttu-id="b9b2b-116">Les prérequis si vous utilisez Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (Juillet 2017)</span><span class="sxs-lookup"><span data-stu-id="b9b2b-116">Prerequisites if you use Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017)</span></span> 
<span data-ttu-id="b9b2b-117">Si Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (Juillet 2017) a été déployé pour votre organisation, l'administrateur système doit publier l'espace de travail mobile **Approbation des commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-117">If Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017), has been deployed for your organization, the system administrator must publish the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="b9b2b-118">Pour obtenir des instructions, voir [Publier un espace de travail mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="b9b2b-118">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="b9b2b-119">Conditions préalables si vous utilisez la version 1611 de Microsoft Dynamics 365 for Operations avec la mise à jour de plateforme 3 ou ultérieure</span><span class="sxs-lookup"><span data-stu-id="b9b2b-119">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="b9b2b-120">Si la version 1611 de Microsoft Dynamics 365 for Operations avec la mise à jour de plateforme 3 ou ultérieure a été déployée pour votre organisation, l'administrateur système doit effectuer les tâches préalables suivantes.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-120">If Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="b9b2b-121">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="b9b2b-121">Prerequisite</span></span></th>
<th><span data-ttu-id="b9b2b-122">Rôle</span><span class="sxs-lookup"><span data-stu-id="b9b2b-122">Role</span></span></th>
<th><span data-ttu-id="b9b2b-123">Description</span><span class="sxs-lookup"><span data-stu-id="b9b2b-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b9b2b-124">Implémenter KB 4017918.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-124">Implement KB 4017918.</span></span></td>
<td><span data-ttu-id="b9b2b-125">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="b9b2b-125">System administrator</span></span></td>
<td><span data-ttu-id="b9b2b-126">Le KB 4017918 est une mise à jour X++ ou un correctif de métadonnées qui contient l'espace de travail mobile <strong>Approbation des commandes fournisseur</strong>.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-126">KB 4017918 is an X++ update or metadata hotfix that contains the <strong>Purchase order approval</strong> mobile workspace.</span></span> <span data-ttu-id="b9b2b-127">Pour implémenter le KB 4017918, un administrateur système doit procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="b9b2b-127">To implement KB 4017918, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="b9b2b-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Télécharger le correctif de métadonnées de Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="b9b2b-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installez le correctif de métadonnées</a>.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="b9b2b-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Créez un module déployable</a> contenant le modèle <strong>SCMMobile</strong> et téléchargez le module déployable vers LCS.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="b9b2b-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Appliquer le package déployable</a>.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b9b2b-132">Publiez l'espace de travail mobile <strong>Approbation des commandes fournisseur</strong>.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-132">Publish the <strong>Purchase order approval</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="b9b2b-133">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="b9b2b-133">System administrator</span></span></td>
<td><span data-ttu-id="b9b2b-134">Voir <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publier un espace de travail mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-134">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="b9b2b-135">Télécharger et installer l'application mobile</span><span class="sxs-lookup"><span data-stu-id="b9b2b-135">Download and install the mobile app</span></span>
<span data-ttu-id="b9b2b-136">Téléchargez et installez l'application mobile Microsoft Dynamics 365 for Unified Operations :</span><span class="sxs-lookup"><span data-stu-id="b9b2b-136">Download and install the Microsoft Dynamics 365 for Unified Operations mobile app:</span></span>

- [<span data-ttu-id="b9b2b-137">Pour les téléphones Android</span><span class="sxs-lookup"><span data-stu-id="b9b2b-137">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
- [<span data-ttu-id="b9b2b-138">Pour les iPhones</span><span class="sxs-lookup"><span data-stu-id="b9b2b-138">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="b9b2b-139">Connexion à l'application mobile</span><span class="sxs-lookup"><span data-stu-id="b9b2b-139">Sign in to the mobile app</span></span>

1. <span data-ttu-id="b9b2b-140">Démarrez l'application sur votre appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-140">Start the app on your mobile device.</span></span>
2. <span data-ttu-id="b9b2b-141">Entrez votre URL Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-141">Enter your Microsoft Dynamics 365 URL.</span></span>
3. <span data-ttu-id="b9b2b-142">Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d'utilisateur et mot de passe.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-142">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="b9b2b-143">Entrez vos informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-143">Enter your credentials.</span></span>
4. <span data-ttu-id="b9b2b-144">Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s'affichent.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-144">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="b9b2b-145">Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-145">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

![Espace de travail Approbation des commandes fournisseur dans la liste des espaces de travail disponibles](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a><span data-ttu-id="b9b2b-147">Afficher les commandes qui vous sont affectées</span><span class="sxs-lookup"><span data-stu-id="b9b2b-147">View orders that are assigned to you</span></span>
1. <span data-ttu-id="b9b2b-148">Sur votre appareil mobile, sélectionnez l'espace de travail **Approbation des commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-148">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="b9b2b-149">Sélectionnez **Commandes qui me sont affectées** pour afficher toutes les commandes fournisseur pour lesquelles il vous a été demandé d'effectuer des actions dans le workflow d'approbation des commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-149">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="b9b2b-150">Sélectionnez un ordre.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-150">Select an order.</span></span> <span data-ttu-id="b9b2b-151">Dans la page **Détails de la commande**, les informations et les lignes d'en-tête de commande s'affichent.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-151">On the **Order details** page, you will see the order header information and lines.</span></span> <span data-ttu-id="b9b2b-152">Vous trouverez également des instructions à partir de la tâche de workflow.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-152">You can also find guidelines from the workflow task.</span></span>
4. <span data-ttu-id="b9b2b-153">Sélectionnez **Répartitions comptables** pour ouvrir la page **Répartitions comptables de l'en-tête**.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-153">Select **Accounting distributions** to open the **Header accounting distributions** page.</span></span>
5. <span data-ttu-id="b9b2b-154">Revenez à la page **Détails de la commande**, puis sélectionnez une ligne.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-154">Return to the **Order details** page, and select a line.</span></span> <span data-ttu-id="b9b2b-155">Dans les détails de la ligne de commande, vous pouvez également explorer les répartitions comptables spécifiques à la ligne.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-155">From the order line details, you can also explore the line-specific accounting distributions.</span></span>

## <a name="complete-an-action-on-the-purchase-order"></a><span data-ttu-id="b9b2b-156">Effectuer une action sur la commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="b9b2b-156">Complete an action on the purchase order</span></span>
<span data-ttu-id="b9b2b-157">Après avoir affiché la commande fournisseur qui vous est affectée et avoir lu les instructions du workflow, vous devez être prêt à effectuer des actions.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-157">After you've viewed the purchase order that is assigned to you and read the workflow instructions, you should be ready to take action.</span></span>

1. <span data-ttu-id="b9b2b-158">Sur votre appareil mobile, sélectionnez l'espace de travail **Approbation des commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-158">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="b9b2b-159">Sélectionnez **Commandes qui me sont affectées** pour afficher toutes les commandes fournisseur pour lesquelles il vous a été demandé d'effectuer des actions dans le workflow d'approbation des commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-159">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="b9b2b-160">Sélectionnez une commande, puis affichez la page de détails.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-160">Select an order, and view the details page.</span></span>
4. <span data-ttu-id="b9b2b-161">Sélectionnez **Actions** pour afficher les actions disponibles.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-161">Select **Actions** to show the available actions.</span></span> <span data-ttu-id="b9b2b-162">Les actions disponibles dépendent de la tâche qui vous a été affectée.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-162">The actions that are available depend on the task that has been assigned to you.</span></span>

    | <span data-ttu-id="b9b2b-163">Action de tâche</span><span class="sxs-lookup"><span data-stu-id="b9b2b-163">Task action</span></span>    | <span data-ttu-id="b9b2b-164">Action d'approbation</span><span class="sxs-lookup"><span data-stu-id="b9b2b-164">Approval action</span></span>  |
    |----------------|------------------|
    | <span data-ttu-id="b9b2b-165">Terminer</span><span class="sxs-lookup"><span data-stu-id="b9b2b-165">Complete</span></span>       | <span data-ttu-id="b9b2b-166">Approuver</span><span class="sxs-lookup"><span data-stu-id="b9b2b-166">Approve</span></span>          |
    | <span data-ttu-id="b9b2b-167">Retourner</span><span class="sxs-lookup"><span data-stu-id="b9b2b-167">Return</span></span>         | <span data-ttu-id="b9b2b-168">Rejeter</span><span class="sxs-lookup"><span data-stu-id="b9b2b-168">Reject</span></span>           |
    | <span data-ttu-id="b9b2b-169">Demander une modification</span><span class="sxs-lookup"><span data-stu-id="b9b2b-169">Request change</span></span> | <span data-ttu-id="b9b2b-170">Demander une modification</span><span class="sxs-lookup"><span data-stu-id="b9b2b-170">Request change</span></span>   |
    | <span data-ttu-id="b9b2b-171">Déléguer</span><span class="sxs-lookup"><span data-stu-id="b9b2b-171">Delegate</span></span>       | <span data-ttu-id="b9b2b-172">Déléguer</span><span class="sxs-lookup"><span data-stu-id="b9b2b-172">Delegate</span></span>         |

5. <span data-ttu-id="b9b2b-173">Sélectionnez l'action appropriée.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-173">Select the appropriate action.</span></span>
6. <span data-ttu-id="b9b2b-174">Dans la page **Terminer la tâche**, entrez un commentaire.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-174">On the **Complete task** page, enter a comment.</span></span> <span data-ttu-id="b9b2b-175">Notez que si vous sélectionnez l'action **Déléguer**, vous devez sélectionner un utilisateur auquel déléguer la tâche.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-175">Note that if you select the **Delegate** action, you must select a user to delegate the task to.</span></span>
7. <span data-ttu-id="b9b2b-176">Sélectionnez **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-176">Select **Done**.</span></span> <span data-ttu-id="b9b2b-177">Après avoir actualisé votre espace de travail, la commande fournisseur ne figurera plus dans votre liste.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-177">After you refresh your workspace, the purchase order will no longer be in your list.</span></span> 

