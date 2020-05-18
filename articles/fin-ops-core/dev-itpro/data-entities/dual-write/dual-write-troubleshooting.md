---
title: Résolution générale des problèmes
description: Cette rubrique fournit des informations sur la résolution générale des problèmes liés à l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 8cc7c11233c745719af72222eba02fb71d7a8944
ms.sourcegitcommit: 4edc658448612afbf1c1663c166d12e08e4c4165
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2020
ms.locfileid: "3340928"
---
# <a name="general-troubleshooting"></a><span data-ttu-id="d3430-103">Résolution générale des problèmes</span><span class="sxs-lookup"><span data-stu-id="d3430-103">General troubleshooting</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="d3430-104">Cette rubrique fournit des informations sur la résolution générale des problèmes liés à l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d3430-104">This topic provides general troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3430-105">Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d'administrateur système ou les identifiants d'admin client Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d3430-105">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="d3430-106">La section pour chaque problème explique si un rôle spécifique ou des informations d'identification sont requis.</span><span class="sxs-lookup"><span data-stu-id="d3430-106">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a><span data-ttu-id="d3430-107">Lorsque vous essayez d'installer le package de double écriture à l'aide de l'outil Package Deployer, aucune solution disponible n'est affichée.</span><span class="sxs-lookup"><span data-stu-id="d3430-107">When you try to install the dual-write package by using the package deployer tool, no available solutions are shown</span></span>

<span data-ttu-id="d3430-108">Certaines versions de l'outil Package Deployer sont incompatibles avec le package de solution de double écriture.</span><span class="sxs-lookup"><span data-stu-id="d3430-108">Some versions of the package deployer tool are incompatible with the dual-write solution package.</span></span> <span data-ttu-id="d3430-109">Pour installer correctement le package, assurez-vous d'utiliser la [version 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) ou une version ultérieure de l'outil Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="d3430-109">To successfully install the package, be sure to use [version 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) or later of the package deployer tool.</span></span>

<span data-ttu-id="d3430-110">Après avoir installé l'outil Package Deployer, installez le package de solution en suivant ces étapes.</span><span class="sxs-lookup"><span data-stu-id="d3430-110">After you install the package deployer tool, install the solution package by following these steps.</span></span>

1. <span data-ttu-id="d3430-111">Téléchargez le dernier fichier de package de solution depuis Yammer.com.</span><span class="sxs-lookup"><span data-stu-id="d3430-111">Download the latest solution package file from Yammer.com.</span></span> <span data-ttu-id="d3430-112">Une fois le fichier zip du package téléchargé, cliquez dessus avec le bouton droit et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d3430-112">After the package zip file is downloaded, right-click it, and select **Properties**.</span></span> <span data-ttu-id="d3430-113">Cochez la case **Débloquer**, puis sélectionnez **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="d3430-113">Select the **Unblock** check box, and then select **Apply**.</span></span> <span data-ttu-id="d3430-114">Si vous ne voyez pas la case à cocher **Débloquer**, le fichier zip est déjà débloqué et vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="d3430-114">If you don't see the **Unblock** check box, the zip file is already unblocked, and you can skip this step.</span></span>

    ![Boîte de dialogue Propriétés](media/unblock_option.png)

2. <span data-ttu-id="d3430-116">Extrayez le fichier zip du package et copiez tous les fichiers dans le dossier **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438**.</span><span class="sxs-lookup"><span data-stu-id="d3430-116">Extract the package zip file, and copy all the files in the **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438** folder.</span></span>

    ![Contenu du dossier Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438](media/extract_package.png)

3. <span data-ttu-id="d3430-118">Collez tous les fichiers copiés dans le dossier **Outils** de l'outil Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="d3430-118">Paste all the copied files into the **Tools** folder of the package deployer tool.</span></span> 
4. <span data-ttu-id="d3430-119">Exécutez **PackageDeployer.exe** pour sélectionner l'environnement Common Data Service et installez les solutions.</span><span class="sxs-lookup"><span data-stu-id="d3430-119">Run **PackageDeployer.exe** to select the Common Data Service environment and install the solutions.</span></span>

    ![Contenu du dossier Outils](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details"></a><span data-ttu-id="d3430-121">Activer et afficher le journal de suivi des plug-ins dans Common Data Service pour afficher les détails de l'erreur</span><span class="sxs-lookup"><span data-stu-id="d3430-121">Enable and view the plug-in trace log in Common Data Service to view error details</span></span>

<span data-ttu-id="d3430-122">**Rôle requis pour activer le journal de suivi et afficher les erreurs :** Administrateur système</span><span class="sxs-lookup"><span data-stu-id="d3430-122">**Required role to turn on the trace log and view errors:** System admin</span></span>

<span data-ttu-id="d3430-123">Pour activer le journal de suivi, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d3430-123">To turn on the trace log, follow these steps.</span></span>

1. <span data-ttu-id="d3430-124">Connectez-vous à l'application pilotée par modèle dans Dynamics 365, ouvrez la page **Paramètres**, puis, sous **Système**, sélectionnez **Administration**.</span><span class="sxs-lookup"><span data-stu-id="d3430-124">Sign in to the model-driven app in Dynamics 365, open the **Settings** page, and then, under **System**, select **Administration**.</span></span>
2. <span data-ttu-id="d3430-125">Sur la page **Administration**, sélectionnez **Paramètres système**.</span><span class="sxs-lookup"><span data-stu-id="d3430-125">On the **Administration** page, select **System Settings**.</span></span>
3. <span data-ttu-id="d3430-126">Sur l'onglet **Personnalisation**, dans le champ **Suivi de plug-ins et d'activités de workflow personnalisées**, sélectionnez **Tout** pour activer le journal de suivi du plug-in.</span><span class="sxs-lookup"><span data-stu-id="d3430-126">On the **Customization** tab, in the **Plug-in and custom workflow activity tracing** field, select **All** to enable the plug-in trace log.</span></span> <span data-ttu-id="d3430-127">Si vous souhaitez consigner les journaux de suivi uniquement lorsque des exceptions se produisent, sélectionnez plutôt **Exception**.</span><span class="sxs-lookup"><span data-stu-id="d3430-127">If you want to log trace logs only when exceptions occur, you can select **Exception** instead.</span></span>


<span data-ttu-id="d3430-128">Pour afficher le journal de suivi, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d3430-128">To view the trace log, follow these steps.</span></span>

1. <span data-ttu-id="d3430-129">Connectez-vous à l'application pilotée par modèle dans Dynamics 365, ouvrez la page **Paramètres**, puis, sous **Personnalisation**, sélectionnez **Journal de suivi du plug-in**.</span><span class="sxs-lookup"><span data-stu-id="d3430-129">Sign in to the model-driven app in Dynamics 365, open the **Settings** page, and then, under **Customization**, select **Plug-in Trace Log**.</span></span>
2. <span data-ttu-id="d3430-130">Recherchez les journaux de suivi où le champ **Nom du type** est défini sur **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.</span><span class="sxs-lookup"><span data-stu-id="d3430-130">Find the trace logs where the **Type Name** field is set to **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.</span></span>
3. <span data-ttu-id="d3430-131">Double-cliquez sur un élément pour afficher le journal complet, puis, sur le raccourci **Exécution**, passez en revue le texte du **Bloc de message**.</span><span class="sxs-lookup"><span data-stu-id="d3430-131">Double-click an item to view the full log, and then, on the **Execution** FastTab, review the **Message Block** text.</span></span>

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a><span data-ttu-id="d3430-132">Activez le mode débogage pour résoudre les problèmes de synchronisation en direct dans les applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d3430-132">Enable debug mode to troubleshoot live synchronization issues in Finance and Operations apps</span></span>

<span data-ttu-id="d3430-133">**Rôle requis pour afficher les erreurs :** Les erreurs de double écriture d'administrateur système provenant de Common Data Service peuvent s'afficher dans l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d3430-133">**Required role to view the errors:** System admin Dual-write errors that originate in Common Data Service can appear in the Finance and Operations app.</span></span> <span data-ttu-id="d3430-134">Dans certains cas, le texte intégral du message d'erreur n'est pas disponible, car le message est trop long ou contient des informations d'identification personnelle (IIP).</span><span class="sxs-lookup"><span data-stu-id="d3430-134">In some cases, the full text of the error message isn't available because the message is too long or contains personally identifying information (PII).</span></span> <span data-ttu-id="d3430-135">Vous pouvez activer la journalisation détaillée des erreurs en procédant comme suit.</span><span class="sxs-lookup"><span data-stu-id="d3430-135">You can turn on verbose logging for errors by following these steps.</span></span>

1. <span data-ttu-id="d3430-136">Toutes les configurations de projet dans les applications Finance and Operations ont une propriété **IsDebugMode** dans l'entité **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d3430-136">All project configurations in Finance and Operations apps have an **IsDebugMode** property in the **DualWriteProjectConfiguration** entity.</span></span> <span data-ttu-id="d3430-137">Ouvrez l'entité **DualWriteProjectConfiguration** à l'aide du module complémentaire Excel.</span><span class="sxs-lookup"><span data-stu-id="d3430-137">Open the **DualWriteProjectConfiguration** entity by using the Excel add-in.</span></span>

    > [!TIP]
    > <span data-ttu-id="d3430-138">Un moyen simple d'ouvrir l'entité consiste à activer le mode **Conception** dans le module complémentaire Excel, puis ajoutez **DualWriteProjectConfigurationEntity** à la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="d3430-138">An easy way to open the entity is to turn on **Design** mode in the Excel add-in and then add **DualWriteProjectConfigurationEntity** to the worksheet.</span></span> <span data-ttu-id="d3430-139">Pour en savoir plus, voir [Ouvrir des données d'entité dans Excel et les mettre à jour à l'aide du module complémentaire Excel](../../office-integration/use-excel-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="d3430-139">For more information, see [Open entity data in Excel and update it by using the Excel add-in](../../office-integration/use-excel-add-in.md).</span></span>

2. <span data-ttu-id="d3430-140">Définissez la propriété **IsDebugMode** sur **Oui** pour le projet.</span><span class="sxs-lookup"><span data-stu-id="d3430-140">Set the **IsDebugMode** property to **Yes** for the project.</span></span>
3. <span data-ttu-id="d3430-141">Exécutez le scénario qui génère des erreurs.</span><span class="sxs-lookup"><span data-stu-id="d3430-141">Run the scenario that is generating errors.</span></span>
4. <span data-ttu-id="d3430-142">Les journaux détaillés sont disponibles dans la table DualWriteErrorLog.</span><span class="sxs-lookup"><span data-stu-id="d3430-142">The verbose logs are available in the DualWriteErrorLog table.</span></span> <span data-ttu-id="d3430-143">Pour rechercher des données dans le navigateur de table, utilisez l'URL suivante (remplacez **XXX**, le cas échéant) :</span><span class="sxs-lookup"><span data-stu-id="d3430-143">To look up data in the table browser, use the following URL (replace **XXX** as appropriate):</span></span>

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=>DualWriteErrorLog`

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a><span data-ttu-id="d3430-144">Vérifier les erreurs de synchronisation sur la machine virtuelle pour l'application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d3430-144">Check synchronization errors on the virtual machine for the Finance and Operations app</span></span>

<span data-ttu-id="d3430-145">**Rôle requis pour afficher les erreurs :** Administrateur système</span><span class="sxs-lookup"><span data-stu-id="d3430-145">**Required role to view the errors:** System administrator</span></span>

1. <span data-ttu-id="d3430-146">Connectez-vous à Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d3430-146">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="d3430-147">Ouvrez le projet LCS que vous avez choisi pour effectuer le test de double écriture.</span><span class="sxs-lookup"><span data-stu-id="d3430-147">Open the LCS project that you chose to do the dual-write testing for.</span></span>
3. <span data-ttu-id="d3430-148">Sélectionnez la vignette **Environnements hébergés dans le cloud**.</span><span class="sxs-lookup"><span data-stu-id="d3430-148">Select the **Cloud-hosted environments** tile.</span></span>
4. <span data-ttu-id="d3430-149">Utilisez Remote Desktop pour vous connecter à la machine virtuelle pour l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d3430-149">Use Remote Desktop to sign in to the virtual machine (VM) for the Finance and Operations app.</span></span> <span data-ttu-id="d3430-150">Utilisez le compte local affiché dans LCS.</span><span class="sxs-lookup"><span data-stu-id="d3430-150">Use the local account that is shown in LCS.</span></span>
5. <span data-ttu-id="d3430-151">Ouvrez l'observateur d'événements.</span><span class="sxs-lookup"><span data-stu-id="d3430-151">Open Event viewer.</span></span>
6. <span data-ttu-id="d3430-152">Sélectionnez **Journaux des applications et des services \> Microsoft \> Dynamics \> AX-DualWriteSync \> Opérationnel**.</span><span class="sxs-lookup"><span data-stu-id="d3430-152">Select **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span>
7. <span data-ttu-id="d3430-153">Consultez la liste des erreurs récentes.</span><span class="sxs-lookup"><span data-stu-id="d3430-153">Review the list of recent errors.</span></span>

## <a name="unlink-and-link-another-common-data-service-environment-from-a-finance-and-operations-app"></a><span data-ttu-id="d3430-154">Dissocier et lier un autre environnement Common Data Service depuis une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d3430-154">Unlink and link another Common Data Service environment from a Finance and Operations app</span></span>

<span data-ttu-id="d3430-155">**Rôle requis pour dissocier l'environnement :** Administrateur système pour l'application Finance and Operations ou Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d3430-155">**Required role to unlink the environment:** System administrator for either Finance and Operations app or Common Data Service.</span></span>

1. <span data-ttu-id="d3430-156">Connectez-vous à l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d3430-156">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="d3430-157">Accédez à **Espaces de travail \> Gestion des données** et sélectionnez la vignette **Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="d3430-157">Go to **Workspaces \> Data management**, and select the **Dual Write** tile.</span></span>
3. <span data-ttu-id="d3430-158">Sélectionnez toutes les mises en correspondance en cours d'exécution et sélectionnez **Arrêter**.</span><span class="sxs-lookup"><span data-stu-id="d3430-158">Select all running mappings, and then select **Stop**.</span></span>
4. <span data-ttu-id="d3430-159">Cliquez sur **Supprimer le lien avec l'environnement**.</span><span class="sxs-lookup"><span data-stu-id="d3430-159">Select **Unlink environment**.</span></span>
5. <span data-ttu-id="d3430-160">Sélectionnez **Oui** pour confirmer l'opération.</span><span class="sxs-lookup"><span data-stu-id="d3430-160">Select **Yes** to confirm the operation.</span></span>

<span data-ttu-id="d3430-161">Vous pouvez maintenant lier un nouvel environnement.</span><span class="sxs-lookup"><span data-stu-id="d3430-161">You can now link a new environment.</span></span>

## <a name="unable-to-view-the-sales-order-line-information-form"></a><span data-ttu-id="d3430-162">Impossible d'afficher le formulaire d'informations de ligne de la commande client</span><span class="sxs-lookup"><span data-stu-id="d3430-162">Unable to view the sales order line Information form</span></span> 

<span data-ttu-id="d3430-163">Lorsque vous créez une commande client dans Dynamics 365 Sales, cliquer sur **+ Ajouter des produits** peut vous rediriger vers le formulaire de ligne de commande Dynamics 365 Project Operations.</span><span class="sxs-lookup"><span data-stu-id="d3430-163">When you create a sales order in Dynamics 365 Sales, clicking on **+ Add products** might redirect you to the Dynamics 365 Project Operations order line form.</span></span> <span data-ttu-id="d3430-164">Il n'y a aucun moyen à partir de ce formulaire pour afficher le formulaire de ligne de commande client **Informations**.</span><span class="sxs-lookup"><span data-stu-id="d3430-164">There is no way from that form to view the sales order line **Information** form.</span></span> <span data-ttu-id="d3430-165">L'option pour **Informations** n'apparaît pas dans la liste déroulante sous **Nouvelle ligne de commande**.</span><span class="sxs-lookup"><span data-stu-id="d3430-165">The option for **Information** does not appear in the dropdown below **New Order Line**.</span></span> <span data-ttu-id="d3430-166">Cela se produit car Project Operations a été installé dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d3430-166">This happens because Project Operations has been installed in your environment.</span></span>

<span data-ttu-id="d3430-167">Pour réactiver l'option de formulaire **Informations**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d3430-167">To re-enable the **Information** form option, follow these steps:</span></span>
1. <span data-ttu-id="d3430-168">Accédez à l'entité **Ligne de commande**.</span><span class="sxs-lookup"><span data-stu-id="d3430-168">Navigate to the **Order Line** entity.</span></span>
2. <span data-ttu-id="d3430-169">Recherchez le formulaire **Informations** sous le nœud de formulaires.</span><span class="sxs-lookup"><span data-stu-id="d3430-169">Find the **Information** form under the forms node.</span></span> 
3. <span data-ttu-id="d3430-170">Sélectionnez le formulaire **Informations** et cliquez sur **Activer les rôles de sécurité**.</span><span class="sxs-lookup"><span data-stu-id="d3430-170">Select the **Information** form and click **Enable security roles**.</span></span> 
4. <span data-ttu-id="d3430-171">Modifiez le paramètre de sécurité sur **Afficher pour tout le monde**.</span><span class="sxs-lookup"><span data-stu-id="d3430-171">Change the security setting to **Display to everyone**.</span></span>
