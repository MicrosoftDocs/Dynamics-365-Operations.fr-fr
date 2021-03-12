---
title: Démarrage du module complémentaire de facturation électronique pour l’Italie
description: Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique pour l’Italie dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 08d41244d3ec785127db8f69e37dd522a463c388
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988538"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-italy"></a><span data-ttu-id="e2733-103">Démarrage du module complémentaire de facturation électronique pour l’Italie</span><span class="sxs-lookup"><span data-stu-id="e2733-103">Get started with the Electronic invoicing add-on for Italy</span></span>

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> <span data-ttu-id="e2733-104">Le module complémentaire de facturation électronique pour l’Italie peut ne pas prendre actuellement en charge toutes les fonctions disponibles pour les factures électroniques dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e2733-104">The Electronic invoicing add-on for Italy might not currently support all the functions that are available for electronic invoices in Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> 

<span data-ttu-id="e2733-105">Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique pour l’Italie.</span><span class="sxs-lookup"><span data-stu-id="e2733-105">This topic provides information that will help you get started with the Electronic invoicing add-on for Italy.</span></span> <span data-ttu-id="e2733-106">Elle vous guide tout au long des étapes de configuration spécifiques au pays dans Regulatory Configuration Services (RCS) et Finance.</span><span class="sxs-lookup"><span data-stu-id="e2733-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and Finance.</span></span> <span data-ttu-id="e2733-107">Elle vous guide également tout au long du processus d’envoi de factures électroniques générées au format **FatturaPA** propre à l’Italie via le service. Elle explique aussi comment passer en revue les résultats du traitement.</span><span class="sxs-lookup"><span data-stu-id="e2733-107">It also guides you through the process for submitting electronic invoices that are generated in the Italy-specific **FatturaPA** format through the service, and it explains how to review the results of processing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e2733-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="e2733-108">Prerequisites</span></span>

<span data-ttu-id="e2733-109">Avant d’effectuer les étapes de cette rubrique, vous devez effectuer les étapes de la rubrique [Démarrage du module complémentaire de facturation électronique](e-invoicing-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="e2733-109">Before you complete the steps in this topic, you must complete the steps in [Get started with the Electronic invoicing add-on](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="e2733-110">Paramétrage RCS</span><span class="sxs-lookup"><span data-stu-id="e2733-110">RCS setup</span></span>

<span data-ttu-id="e2733-111">Lors du paramétrage de RCS, vous effectuerez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="e2733-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="e2733-112">Importer la fonctionnalité de facturation électronique pour l’exportation des factures électroniques client au format **FatturaPA**.</span><span class="sxs-lookup"><span data-stu-id="e2733-112">Import the e-Invoicing feature for the export of customer electronic invoices in the **FatturaPA** format.</span></span>
2. <span data-ttu-id="e2733-113">Passer en revue les configurations de format nécessaires pour générer, envoyer et recevoir des réponses concernant les factures électroniques.</span><span class="sxs-lookup"><span data-stu-id="e2733-113">Review the format configurations that are required to generate, submit, and receive responses about electronic invoices.</span></span>
3. <span data-ttu-id="e2733-114">Configurer les événements prenant en charge les scénarios d’envoi de factures électroniques.</span><span class="sxs-lookup"><span data-stu-id="e2733-114">Configure the events that support the electronic invoice submission scenarios.</span></span>
4. <span data-ttu-id="e2733-115">Publier la fonctionnalité de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="e2733-115">Publish the e-Invoicing feature.</span></span>

> [!NOTE]
> <span data-ttu-id="e2733-116">La « Fonctionnalité de facturation électronique » est le nom générique de la ressource configurée et publiée pour utiliser le serveur complémentaire de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="e2733-116">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing add-on server.</span></span> <span data-ttu-id="e2733-117">Dans ce cas, l’exportation des factures électroniques client est la fonctionnalité de facturation électronique que vous allez paramétrer.</span><span class="sxs-lookup"><span data-stu-id="e2733-117">In this case, the export of customer electronic invoices is the e-Invoicing feature that you will set up.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="e2733-118">Importer la fonctionnalité de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="e2733-118">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="e2733-119">Connectez-vous à votre compte RCS.</span><span class="sxs-lookup"><span data-stu-id="e2733-119">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="e2733-120">Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="e2733-120">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="e2733-121">Sur la page **Fonctionnalités de facturation électronique**, sélectionnez **Importer** pour importer la fonctionnalité de facturation électronique à partir du référentiel global.</span><span class="sxs-lookup"><span data-stu-id="e2733-121">On the **e-Invoicing Features** page, select **Import** to import the e-Invoicing feature from the Global repository.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e2733-122">Si vous ne voyez pas la liste des fonctionnalités disponibles, sélectionnez **Synchroniser**.</span><span class="sxs-lookup"><span data-stu-id="e2733-122">If you don't see the list of available features, select **Synchronize**.</span></span> 

4. <span data-ttu-id="e2733-123">Sélectionnez la fonctionnalité **Exportation de factures électroniques (IT)**, puis sélectionnez **Importer**.</span><span class="sxs-lookup"><span data-stu-id="e2733-123">Select the **e-Invoices Export (IT)** feature, and then select **Import**.</span></span>

![Importation de la fonctionnalité Exportation de factures électroniques (IT)](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

<span data-ttu-id="e2733-125">Lorsque vous importez la fonctionnalité **Exportation de factures électroniques (IT)** à partir du référentiel global, tous les paramètres décrits dans les sections suivantes sont également importés.</span><span class="sxs-lookup"><span data-stu-id="e2733-125">When you import the **e-Invoices Export (IT)** feature from the Global repository, all the settings that are described in the next sections are also imported.</span></span>

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a><span data-ttu-id="e2733-126">Créer une nouvelle version de la fonctionnalité Exportation de factures électroniques (IT)</span><span class="sxs-lookup"><span data-stu-id="e2733-126">Create a new version of the e-Invoices Export (IT) feature</span></span>

1. <span data-ttu-id="e2733-127">Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Versions**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e2733-127">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span> 

    ![Ajout d’une nouvelle version de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    <span data-ttu-id="e2733-129">Ensuite, vous allez configurer les formats d’états électroniques (ER) associés à la fonctionnalité de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="e2733-129">Next, you will configure the Electronic reporting (ER) formats that are associated with the e-Invoicing feature.</span></span>

2. <span data-ttu-id="e2733-130">Dans l’onglet **Configurations**, sélectionnez **Ajouter** pour gérer les versions de configuration.</span><span class="sxs-lookup"><span data-stu-id="e2733-130">On the **Configurations** tab, select **Add** to manage the configuration versions.</span></span>

    ![Gestion des versions de configuration de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    <span data-ttu-id="e2733-132">Dans cette étape, vous ajoutez et configurez les formats ER de différents fichiers utilisés pour exporter des factures électroniques italiennes.</span><span class="sxs-lookup"><span data-stu-id="e2733-132">In this step, you're adding and configuring the ER formats of different files that are used to export Italian e-invoices.</span></span> <span data-ttu-id="e2733-133">Pour les factures électroniques FatturaPA italiennes, utilisez les configurations standard suivantes ou les configurations personnalisées réelles que vous utilisez pour la facturation électronique :</span><span class="sxs-lookup"><span data-stu-id="e2733-133">For Italian FatturaPA e-invoices, use either the following standard configurations or the actual customized configurations that you use for e-invoicing:</span></span>

    - <span data-ttu-id="e2733-134">Facture client (IT)</span><span class="sxs-lookup"><span data-stu-id="e2733-134">Sales invoice (IT)</span></span>
    - <span data-ttu-id="e2733-135">Facture de projet (IT)</span><span class="sxs-lookup"><span data-stu-id="e2733-135">Project invoice (IT)</span></span>

    <span data-ttu-id="e2733-136">Lorsque vous créez une fonctionnalité de facturation électronique dérivée d’une autre fonctionnalité de facturation électronique, tous les formats ER sont hérités de la fonctionnalité d’origine.</span><span class="sxs-lookup"><span data-stu-id="e2733-136">When you create an e-Invoicing feature that is derived from another e-Invoicing feature, all ER formats are inherited from the original feature.</span></span>

3. <span data-ttu-id="e2733-137">Sélectionnez une configuration de format de fichier ER spécifique.</span><span class="sxs-lookup"><span data-stu-id="e2733-137">Select a specific ER format file configuration.</span></span>
4. <span data-ttu-id="e2733-138">Sélectionnez **Modifier** ou **Afficher** pour ouvrir la page **Concepteur de formats**.</span><span class="sxs-lookup"><span data-stu-id="e2733-138">Select **Edit** or **View** to open the **Format designer** page.</span></span>

    ![Ouverture de la page Concepteur de formats](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. <span data-ttu-id="e2733-140">Utilisez la page **Concepteur de formats** pour modifier ou afficher les configurations de format de fichier ER.</span><span class="sxs-lookup"><span data-stu-id="e2733-140">Use the **Format designer** page to edit and view the ER format file configurations.</span></span>

    ![Page Concepteur de formats](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="e2733-142">Gérer les paramétrages de la fonctionnalité de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="e2733-142">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="e2733-143">Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Paramétrages**, sélectionnez **Ajouter**, **Supprimer** ou **Modifier** pour gérer les paramétrages de la fonctionnalité de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="e2733-143">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add**, **Delete**, or **Edit** to manage the e-Invoicing feature setups.</span></span>

![Gestion des paramétrages de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

<span data-ttu-id="e2733-145">Dans cette étape, vous configurez les événements applicables aux factures électroniques, notamment la génération des fichiers de sortie XML au format **FatturaPA** et la signature numérique (si nécessaire).</span><span class="sxs-lookup"><span data-stu-id="e2733-145">In this step, you configure the events that are applicable to electronic invoices, including generation of the XML output files in **FatturaPA** format and digital signing (if required).</span></span>

### <a name="configure-the-sales-invoice-feature-setup"></a><span data-ttu-id="e2733-146">Configurer le paramétrage de la fonctionnalité Facture client</span><span class="sxs-lookup"><span data-stu-id="e2733-146">Configure the Sales invoice feature setup</span></span>

1. <span data-ttu-id="e2733-147">Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Paramétrages**, dans la colonne **Paramétrage de fonctionnalité**, sélectionnez **Facture client**.</span><span class="sxs-lookup"><span data-stu-id="e2733-147">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Sales invoice**.</span></span>
2. <span data-ttu-id="e2733-148">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e2733-148">Select **Edit**.</span></span>
3. <span data-ttu-id="e2733-149">Sur la page **Paramétrage de version de fonctionnalité**, sélectionnez l’onglet **Actions** pour gérer la liste des actions.</span><span class="sxs-lookup"><span data-stu-id="e2733-149">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span> <span data-ttu-id="e2733-150">Les actions définissent une liste d’opérations qui doivent être exécutées dans un ordre séquentiel pour permettre l’exécution complète de l’événement.</span><span class="sxs-lookup"><span data-stu-id="e2733-150">Actions define a list of operations that must be run in sequential order to accomplish full execution of the event.</span></span>

    ![Onglet Actions](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | <span data-ttu-id="e2733-152">ID action</span><span class="sxs-lookup"><span data-stu-id="e2733-152">Action ID</span></span> | <span data-ttu-id="e2733-153">Nom de l’action</span><span class="sxs-lookup"><span data-stu-id="e2733-153">Action name</span></span>        | <span data-ttu-id="e2733-154">Description de l’action</span><span class="sxs-lookup"><span data-stu-id="e2733-154">Action description</span></span>                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | <span data-ttu-id="e2733-155">1</span><span class="sxs-lookup"><span data-stu-id="e2733-155">1</span></span>         | <span data-ttu-id="e2733-156">Transformer le document</span><span class="sxs-lookup"><span data-stu-id="e2733-156">Transform document</span></span> | <span data-ttu-id="e2733-157">Créez le fichier XML de la facture électronique au format **FatturaPA**.</span><span class="sxs-lookup"><span data-stu-id="e2733-157">Create the e-invoice XML file in **FatturaPA** format.</span></span> |
    | <span data-ttu-id="e2733-158">2</span><span class="sxs-lookup"><span data-stu-id="e2733-158">2</span></span>         | <span data-ttu-id="e2733-159">Signer le document</span><span class="sxs-lookup"><span data-stu-id="e2733-159">Sign document</span></span>      | <span data-ttu-id="e2733-160">Appliquez une certificat numérique au fichier XML.</span><span class="sxs-lookup"><span data-stu-id="e2733-160">Apply a digital signature to the XML file.</span></span>             |

4. <span data-ttu-id="e2733-161">Sélectionnez l’onglet **Règles d’applicabilité** pour afficher et gérer les règles d’applicabilité.</span><span class="sxs-lookup"><span data-stu-id="e2733-161">Select the **Applicability rules** tab to view and maintain the applicability rules.</span></span> <span data-ttu-id="e2733-162">Les règles d’applicabilité définissent le contexte d’exécution de l’action.</span><span class="sxs-lookup"><span data-stu-id="e2733-162">Applicability rules define the context where the action will be run.</span></span>

    ![Onglet Règles d’applicabilité](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. <span data-ttu-id="e2733-164">Sélectionnez l’onglet **Variables** pour afficher et gérer les variables.</span><span class="sxs-lookup"><span data-stu-id="e2733-164">Select the **Variables** tab to view and maintain the variables.</span></span>

    ![Onglet Variables](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. <span data-ttu-id="e2733-166">Définissez les variables publiques nécessaires pour exécuter les actions.</span><span class="sxs-lookup"><span data-stu-id="e2733-166">Define the public variables that are required to run the actions.</span></span>

### <a name="configure-the-project-invoice-feature-setup"></a><span data-ttu-id="e2733-167">Configurer le paramétrage de la fonctionnalité Facture de projet</span><span class="sxs-lookup"><span data-stu-id="e2733-167">Configure the Project invoice feature setup</span></span> 

<span data-ttu-id="e2733-168">Les étapes et les paramètres nécessaires pour configurer le paramétrage de la fonctionnalité **Facture de projet** sont très similaires à ceux du paramétrage de la fonctionnalité **Facture client**.</span><span class="sxs-lookup"><span data-stu-id="e2733-168">The steps and settings that are required to configure the **Project invoice** feature setup are very similar to the steps and settings for the **Sales invoice** feature setup.</span></span> <span data-ttu-id="e2733-169">Lorsque vous utilisez des factures de projet, consultez les procédures pour les factures client.</span><span class="sxs-lookup"><span data-stu-id="e2733-169">When you work with project invoices, see the procedures for sales invoices.</span></span>

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a><span data-ttu-id="e2733-170">Attribuer la fonctionnalité de facturation électronique à l’environnement</span><span class="sxs-lookup"><span data-stu-id="e2733-170">Assign the e-Invoicing feature to the environment</span></span>

1. <span data-ttu-id="e2733-171">Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Environnements**, sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="e2733-171">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="e2733-172">Dans le champ **Environnement**, sélectionnez l’environnement.</span><span class="sxs-lookup"><span data-stu-id="e2733-172">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="e2733-173">Dans le champ **Date d’effet**, sélectionnez la date à laquelle l’environnement doit prendre effet.</span><span class="sxs-lookup"><span data-stu-id="e2733-173">In the **Effective from** field, select the date when the environment should become effective.</span></span>
4. <span data-ttu-id="e2733-174">Sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="e2733-174">Select **Enable**.</span></span> 

![Activation de l’environnement de facturation électronique](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a><span data-ttu-id="e2733-176">Publier la fonctionnalité de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="e2733-176">Publish the e-invoicing feature</span></span>

<span data-ttu-id="e2733-177">Vous pouvez publier la fonctionnalité de facturation électronique en modifiant le statut de la version en **Terminé** ou **Publié**.</span><span class="sxs-lookup"><span data-stu-id="e2733-177">You can publish the e-Invoicing feature by changing the version status to **Completed** or **Published**.</span></span>

### <a name="change-the-version-status-to-completed"></a><span data-ttu-id="e2733-178">Modifier le statut de la version en Terminé</span><span class="sxs-lookup"><span data-stu-id="e2733-178">Change the version status to Completed</span></span>

1. <span data-ttu-id="e2733-179">Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Versions**, sélectionnez la version de la fonctionnalité de facturation électronique présentant le statut **Brouillon**.</span><span class="sxs-lookup"><span data-stu-id="e2733-179">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="e2733-180">Sélectionnez **Modifier le statut \> Terminé**.</span><span class="sxs-lookup"><span data-stu-id="e2733-180">Select **Change status \> Complete**.</span></span> 

### <a name="change-the-version-status-to-published"></a><span data-ttu-id="e2733-181">Modifier le statut de la version en Publié</span><span class="sxs-lookup"><span data-stu-id="e2733-181">Change the version status to Published</span></span> 

1. <span data-ttu-id="e2733-182">Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Versions**, sélectionnez la version de la fonctionnalité de facturation électronique présentant le statut **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="e2733-182">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Completed**.</span></span>
2. <span data-ttu-id="e2733-183">Sélectionnez **Modifier le statut \> Publier**.</span><span class="sxs-lookup"><span data-stu-id="e2733-183">Select **Change status \> Publish**.</span></span>

![Modification du statut de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance"></a><span data-ttu-id="e2733-185">Paramétrer l’intégration du module complémentaire de facturation électronique dans Finance</span><span class="sxs-lookup"><span data-stu-id="e2733-185">Set up the Electronic invoicing add-on integration in Finance</span></span>

<span data-ttu-id="e2733-186">Lors du paramétrage de Finance, vous effectuerez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="e2733-186">During the setup of Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="e2733-187">Importer le modèle de données ER, le mappage du modèle de données ER et les configurations de contexte pour les factures électroniques FatturaPA.</span><span class="sxs-lookup"><span data-stu-id="e2733-187">Import the ER data model, the ER data model mapping, and the context configurations for FatturaPA e-invoices.</span></span>
2. <span data-ttu-id="e2733-188">Configurer le certificat nécessaire pour signer numériquement les factures électroniques italiennes.</span><span class="sxs-lookup"><span data-stu-id="e2733-188">Configure the certificate that is required to digitally sign Italian e-invoices.</span></span>

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a><span data-ttu-id="e2733-189">Importer le modèle de données ER, le mappage du modèle de données et les formats</span><span class="sxs-lookup"><span data-stu-id="e2733-189">Import the ER data model, data model mapping, and formats</span></span>

1. <span data-ttu-id="e2733-190">Dans l’espace de travail **États électroniques**, vérifiez que le fournisseur de configuration **Service de documents commerciaux** est défini sur **Actif**.</span><span class="sxs-lookup"><span data-stu-id="e2733-190">In the **Electronic reporting** workspace, verify that the **Business Document Service** configuration provider is set to **Active**.</span></span>
2. <span data-ttu-id="e2733-191">Sélectionnez **Référentiels**.</span><span class="sxs-lookup"><span data-stu-id="e2733-191">Select **Repositories**.</span></span>
3. <span data-ttu-id="e2733-192">Sélectionnez **Ressource globale \> Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="e2733-192">Select **Global resource \> Open**.</span></span>
4. <span data-ttu-id="e2733-193">Importez **Modèle de facture**, **Mappage du modèle de facture** et **Modèle de contexte de facture client**.</span><span class="sxs-lookup"><span data-stu-id="e2733-193">Import **Invoice model**, **Invoice model mapping**, and **Customer invoice context model**.</span></span>

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a><span data-ttu-id="e2733-194">Activer la fonctionnalité d’exportation de factures électroniques client pour l’Italie</span><span class="sxs-lookup"><span data-stu-id="e2733-194">Turn on the feature for exporting customer electronic invoices for Italy</span></span>

1. <span data-ttu-id="e2733-195">Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.</span><span class="sxs-lookup"><span data-stu-id="e2733-195">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="e2733-196">Dans l’onglet **Fonctionnalités**, cochez la case **Activé** dans la ligne de la référence de fonctionnalité **IT00036**.</span><span class="sxs-lookup"><span data-stu-id="e2733-196">On the **Features** tab, select the **Enabled** check box in the row for feature reference **IT00036**.</span></span>

![Activation de la fonctionnalité FatturaPA](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a><span data-ttu-id="e2733-198">Configurer des documents électroniques</span><span class="sxs-lookup"><span data-stu-id="e2733-198">Configure electronic documents</span></span>

1. <span data-ttu-id="e2733-199">Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.</span><span class="sxs-lookup"><span data-stu-id="e2733-199">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="e2733-200">Dans l’onglet **Document électronique**, sélectionnez **Ajouter** et entrez les tables nécessaires pour générer des factures électroniques italiennes :</span><span class="sxs-lookup"><span data-stu-id="e2733-200">On the **Electronic document** tab, select **Add**, and enter the tables that are required to generate Italian e-invoices:</span></span>

    - <span data-ttu-id="e2733-201">**Nom de la table :** Journal des factures client</span><span class="sxs-lookup"><span data-stu-id="e2733-201">**Table name:** Customer invoice journal</span></span>
    - <span data-ttu-id="e2733-202">**Nom de la table :** Facture de projet</span><span class="sxs-lookup"><span data-stu-id="e2733-202">**Table name:** Project invoice</span></span>

3. <span data-ttu-id="e2733-203">Pour chaque table, définissez un contexte de document associé :</span><span class="sxs-lookup"><span data-stu-id="e2733-203">For each table, define a related document context:</span></span>

    - <span data-ttu-id="e2733-204">Pour **Journal des factures client**, sélectionnez **Contexte de la facture client**.</span><span class="sxs-lookup"><span data-stu-id="e2733-204">For **Customer invoice journal**, select **Customer invoice context**.</span></span>
    - <span data-ttu-id="e2733-205">Pour **Facture de projet**, sélectionnez **Contexte de la facture de projet**.</span><span class="sxs-lookup"><span data-stu-id="e2733-205">For **Project invoice**, select **Project invoice context**.</span></span>

![Configuration des types de réponse](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a><span data-ttu-id="e2733-207">Traitement de facture électronique</span><span class="sxs-lookup"><span data-stu-id="e2733-207">Electronic invoice processing</span></span>

<span data-ttu-id="e2733-208">Lors du traitement dans Finance, vous effectuerez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="e2733-208">During processing in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="e2733-209">Générer des factures électroniques italiennes via le module complémentaire de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="e2733-209">Generate Italian e-invoices through the Electronic invoicing add-on</span></span>
2. <span data-ttu-id="e2733-210">Afficher les journaux d’exécution et passer en revue les résultats du traitement</span><span class="sxs-lookup"><span data-stu-id="e2733-210">View the execution logs and review the results of processing</span></span>

### <a name="generate-electronic-invoices"></a><span data-ttu-id="e2733-211">Générer des factures électroniques</span><span class="sxs-lookup"><span data-stu-id="e2733-211">Generate electronic invoices</span></span>

<span data-ttu-id="e2733-212">Après avoir activé la fonctionnalité **Intégration du module complémentaire de facturation électronique configurable** et activé la fonctionnalité **IT00036**, l’ancien processus Finance de génération de factures électroniques italiennes ne peut plus être utilisé.</span><span class="sxs-lookup"><span data-stu-id="e2733-212">After you turn on the **Configurable Electronic invoicing add-on integration** feature and activate the **IT00036** feature, the old Finance process for generating Italian e-invoices can no longer be used.</span></span> <span data-ttu-id="e2733-213">Il est remplacé par un nouveau processus appelé **Envoyer des documents électroniques**.</span><span class="sxs-lookup"><span data-stu-id="e2733-213">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

<span data-ttu-id="e2733-214">Vous pouvez envoyer les documents manuellement, en fonction de votre demande de documents de facture électronique.</span><span class="sxs-lookup"><span data-stu-id="e2733-214">You can submit the documents manually, based on your demand for e-invoice documents.</span></span>

> [!NOTE]
> <span data-ttu-id="e2733-215">Avant de continuer, vérifiez que la configuration nécessaire pour les factures électroniques italiennes a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="e2733-215">Before you continue, verify that the setup that is required for Italian e-invoices was completed.</span></span> <span data-ttu-id="e2733-216">Pour plus d’informations, voir [Factures électroniques client](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices).</span><span class="sxs-lookup"><span data-stu-id="e2733-216">For more information, see [Customer electronic invoices](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices).</span></span> <span data-ttu-id="e2733-217">Notez que certaines des étapes de configuration décrites dans cette rubrique peuvent ne pas être disponibles en raison de l’activation du module complémentaire de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="e2733-217">Be aware that some of the setup steps that are described in that topic might be unavailable because of Electronic invoicing add-on activation.</span></span>

1. <span data-ttu-id="e2733-218">Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Envoyer des documents électroniques**.</span><span class="sxs-lookup"><span data-stu-id="e2733-218">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="e2733-219">Pour le premier envoi d’un document, définissez l’option **Envoyer de nouveau les documents** sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="e2733-219">For the first submission of any document, set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="e2733-220">Si vous devez envoyer à nouveau un document via le service, définissez cette option sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="e2733-220">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="e2733-221">Dans le raccourci **Enregistrements à inclure**, sélectionnez **Filtrer** pour ouvrir la boîte de dialogue **Recherche** dans laquelle vous pouvez créer une requête pour sélectionner des documents pour envoi.</span><span class="sxs-lookup"><span data-stu-id="e2733-221">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>

![Boîte de dialogue Envoyer des documents électroniques](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a><span data-ttu-id="e2733-223">Requête de filtre</span><span class="sxs-lookup"><span data-stu-id="e2733-223">Filter query</span></span>

1. <span data-ttu-id="e2733-224">Dans la boîte de dialogue **Recherche**, configurez les conditions de filtrage des factures client et des factures de projet, ou laissez les conditions vides pour inclure toutes les factures non envoyées.</span><span class="sxs-lookup"><span data-stu-id="e2733-224">In the **Inquiry** dialog box, configure the filtering conditions for both sales invoices and project invoices, or leave the conditions blank to include all unsubmitted invoices.</span></span>

    ![Configuration des critères de filtrage de l’envoi](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. <span data-ttu-id="e2733-226">Cliquez sur **OK** pour fermer la boîte de dialogue **Recherche**.</span><span class="sxs-lookup"><span data-stu-id="e2733-226">Select **OK** to close the **Inquiry** dialog box.</span></span>
3. <span data-ttu-id="e2733-227">Cliquez sur **OK** pour envoyer les documents sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="e2733-227">Select **OK** submit the selected documents.</span></span>

> <span data-ttu-id="e2733-228">![REMARQUE] Lors de votre première tentative d’envoi d’un document via le service, vous serez invité à confirmer la connexion avec le module complémentaire de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="e2733-228">![NOTE] During your first attempt to submit a document through the service, you will be prompted to confirm the connection with the Electronic invoicing add-on.</span></span> <span data-ttu-id="e2733-229">Sélectionnez **Cliquez ici pour vous connecter au service d’envoi de document électronique**.</span><span class="sxs-lookup"><span data-stu-id="e2733-229">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

#### <a name="view-submission-logs"></a><span data-ttu-id="e2733-230">Afficher les journaux d’envoi</span><span class="sxs-lookup"><span data-stu-id="e2733-230">View submission logs</span></span>

<span data-ttu-id="e2733-231">Vous pouvez afficher les journaux d’envoi pour tous les documents envoyés.</span><span class="sxs-lookup"><span data-stu-id="e2733-231">You can view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="e2733-232">Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Journal d’envoi de documents électroniques**.</span><span class="sxs-lookup"><span data-stu-id="e2733-232">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="e2733-233">Dans le champ **Type de document**, sélectionnez **Journal des factures client** ou **Facture de projet** pour filtrer les documents électroniques requis.</span><span class="sxs-lookup"><span data-stu-id="e2733-233">In the **Document type** field, select **Customer invoice journal** or **Project invoice** to filter for the required electronic documents.</span></span>

    ![Sélection d’un type de document pour afficher les journaux d’envoi](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    <span data-ttu-id="e2733-235">La valeur affichée dans la colonne **Statut d’envoi** représente le statut du processus d’envoi.</span><span class="sxs-lookup"><span data-stu-id="e2733-235">The value that is shown in the **Submission status** column represents the status of the submission process.</span></span> <span data-ttu-id="e2733-236">Elle indique si le processus a été exécuté comme configuré et si une action supplémentaire est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e2733-236">It indicates whether the process ran as configured and whether additional action is required.</span></span>

3. <span data-ttu-id="e2733-237">Dans le volet Actions, sélectionnez **Recherches \> Détails de l’envoi** pour afficher les détails des journaux d’exécution de l’envoi.</span><span class="sxs-lookup"><span data-stu-id="e2733-237">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Affichage des détails du journal d’envoi](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. <span data-ttu-id="e2733-239">Dans le raccourci **Actions de traitement**, vous pouvez afficher le journal d’exécution des actions configurées dans la version de fonctionnalité paramétrée dans RCS.</span><span class="sxs-lookup"><span data-stu-id="e2733-239">On the **Processing actions** FastTab, you can view the execution log for the actions that are configured in the feature version that was set up in RCS.</span></span> <span data-ttu-id="e2733-240">La colonne **Statut** indique si l’exécution de l’action a réussi.</span><span class="sxs-lookup"><span data-stu-id="e2733-240">The **Status** column shows whether the action was successfully run.</span></span>
5. <span data-ttu-id="e2733-241">Dans le raccourci **Fichiers d’action**, vous pouvez afficher les fichiers intermédiaires générés lors de l’exécution des actions.</span><span class="sxs-lookup"><span data-stu-id="e2733-241">On the **Action files** FastTab, you can view the intermediate files that were generated during execution of the actions.</span></span> <span data-ttu-id="e2733-242">Vous pouvez sélectionner **Afficher** pour télécharger le fichier XML de sortie au format **FatturaPA** et afficher son contenu.</span><span class="sxs-lookup"><span data-stu-id="e2733-242">You can select **View** to download the output XML file in **FatturaPA** format and view its content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e2733-243">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="e2733-243">Related topics</span></span>

- [<span data-ttu-id="e2733-244">Présentation du module complémentaire de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="e2733-244">Electronic invoicing add-on overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="e2733-245">Démarrage du module complémentaire de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="e2733-245">Get started with the Electronic invoicing add-on</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="e2733-246">Paramétrer le module complémentaire de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="e2733-246">Set up the Electronic invoicing add-on</span></span>](e-invoicing-setup.md)
