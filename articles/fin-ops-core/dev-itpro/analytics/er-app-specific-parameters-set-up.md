---
title: Définir les paramètres d'un format de gestion des états électroniques par entité juridique
description: Cette rubrique explique comment vous pouvez définir les paramètres d'un format gestion des états électroniques par entité juridique.
author: NickSelin
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: ca837026f18034cddb34d7a2d5a62002ed69106a
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042755"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a><span data-ttu-id="102e1-103">Définir les paramètres d'un format de gestion des états électroniques par entité juridique</span><span class="sxs-lookup"><span data-stu-id="102e1-103">Set up the parameters of an ER format per legal entity</span></span>

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="102e1-104">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="102e1-104">Prerequisites</span></span>

<span data-ttu-id="102e1-105">Pour effectuer cette procédure, vous devez suivre les étapes de la rubrique [Configurer les formats de gestion des états électroniques pour utiliser les paramètres spécifiés par entité juridique](er-app-specific-parameters-configure-format.md).</span><span class="sxs-lookup"><span data-stu-id="102e1-105">To complete these steps, you must first complete the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span>

<span data-ttu-id="102e1-106">Pour terminer les exemples de cette rubrique, vous devez avoir accès à Microsoft Dynamics 365 Finance (Finance) pour un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="102e1-106">To complete the examples in this topic, you must have access to Microsoft Dynamics 365 Finance (Finance) for one of the following roles:</span></span>

- <span data-ttu-id="102e1-107">Développeur d'états électroniques</span><span class="sxs-lookup"><span data-stu-id="102e1-107">Electronic reporting developer</span></span>
- <span data-ttu-id="102e1-108">Consultant fonctionnel des états électroniques</span><span class="sxs-lookup"><span data-stu-id="102e1-108">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="102e1-109">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="102e1-109">System administrator</span></span>

## <a name="import-er-configurations"></a><span data-ttu-id="102e1-110">Importer les configurations ER</span><span class="sxs-lookup"><span data-stu-id="102e1-110">Import ER configurations</span></span>

1.  <span data-ttu-id="102e1-111">Connectez-vous à votre environnement.</span><span class="sxs-lookup"><span data-stu-id="102e1-111">Sign in to your environment.</span></span>
2.  <span data-ttu-id="102e1-112">Dans le tableau de bord par défaut, sélectionnez **Gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="102e1-112">On the default dashboard, select **Electronic reporting**.</span></span>
3.  <span data-ttu-id="102e1-113">Sélectionnez **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="102e1-113">Select **Reporting configurations**.</span></span>
4.  <span data-ttu-id="102e1-114">Importez, dans l'instance actuelle de Finance, les configurations exportées depuis RCS lorsque vous exécutez ces étapes dans la rubrique [Configurer les formats de gestion des états électroniques pour utiliser les paramètres qui sont spécifiques par entité juridique](er-app-specific-parameters-configure-format.md).</span><span class="sxs-lookup"><span data-stu-id="102e1-114">Import, into the current instance of Finance, the configurations that you exported from Regulatory Configuration Services (RCS) while you were completing the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span> <span data-ttu-id="102e1-115">Procédez comme suit pour chaque configuration de gestion des états électroniques, dans l'ordre suivant : modèle de données, mise en correspondance de modèle et formats.</span><span class="sxs-lookup"><span data-stu-id="102e1-115">Follow these steps for each Electronic reporting (ER) configuration, in the following order: data model, model mapping, and formats.</span></span>

    1. <span data-ttu-id="102e1-116">Sélectionnez **Échanger \> Charger depuis le fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="102e1-116">Select **Exchange \> Load from XML file**.</span></span>
    2. <span data-ttu-id="102e1-117">Sélectionnez **Parcourir** pour sélectionner le fichier pour la configuration de gestion des états électroniques requise au format XML.</span><span class="sxs-lookup"><span data-stu-id="102e1-117">Select **Browse** to select the file for the required ER configuration in XML format.</span></span>
    3. <span data-ttu-id="102e1-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="102e1-118">Select **OK**.</span></span>
    
    <span data-ttu-id="102e1-119">L'illustration suivante présente les configurations que vous devez avoir lorsque vous avez fini.</span><span class="sxs-lookup"><span data-stu-id="102e1-119">The following illustration shows the configurations that you must have when you've finished.</span></span>

    ![Page Configurations d'ER](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a><span data-ttu-id="102e1-121">Définir les paramètres pour l'entreprise DEMF</span><span class="sxs-lookup"><span data-stu-id="102e1-121">Set up parameters for the DEMF company</span></span>

<span data-ttu-id="102e1-122">Vous pouvez utiliser la structure de gestion des états électroniques pour configurer les paramètres spécifiques à l'application pour un format de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="102e1-122">You can use the ER framework to set up application-specific parameters for an ER format.</span></span>

1.  <span data-ttu-id="102e1-123">Sélectionnez l'entité juridique **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="102e1-123">Select the **DEMF** legal entity.</span></span>
2.  <span data-ttu-id="102e1-124">Dans l'arborescence des configurations, sélectionnez le format **Format pour apprendre comment rechercher les données LE**.</span><span class="sxs-lookup"><span data-stu-id="102e1-124">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
3.  <span data-ttu-id="102e1-125">Dans le volet Actions, sous l'onglet **Configurations**, dans le groupe **Paramètres spécifiques à l'application**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="102e1-125">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>

    ![Page Paramètres spécifiques à l'application de la gestion des états électroniques](./media/GER-AppSpecParms-LookupForm.PNG)
    
    <span data-ttu-id="102e1-127">Sur la page **Paramètres spécifiques à l'application**, vous pouvez configurer les règles pour la source données **Sélecteur** du format **Format pour apprendre comment rechercher les données LE**.</span><span class="sxs-lookup"><span data-stu-id="102e1-127">On the **Application specific parameters** page, you can configure the rules for the **Selector** data source of the **Format to learn how to lookup LE data** format.</span></span>
    
    <span data-ttu-id="102e1-128">Si le format de gestion des états électroniques de base contient plusieurs sources de données de type **Recherche**, vous devez sélectionner la source de données souhaitée dans l'organisateur **Recherches** avant de commencer à configurer l'ensemble de règles pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="102e1-128">If the base ER format will contain several data sources of the **Lookup** type, you must select the desired data source on the **Lookups** FastTab before you can start to configure the set of rules for the data source.</span></span>
    
    <span data-ttu-id="102e1-129">Pour chaque source de données, vous pouvez configurer des règles différentes pour chaque version du format de gestion des états électroniques sélectionné.</span><span class="sxs-lookup"><span data-stu-id="102e1-129">For each data source, you can configure separate rules for each version of the selected ER format.</span></span>
    
    <span data-ttu-id="102e1-130">L'ensemble des règles pour toutes les sources de données de recherche qui sont disponibles dans la version sélectionnée du format de gestion des états électroniques de base constitue les paramètres spécifiques à l'application pour le format de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="102e1-130">The whole set of rules for all lookup data sources that are available in the selected version of the base ER format makes up the application-specific parameters for the ER format.</span></span>

4.  <span data-ttu-id="102e1-131">Sélectionnez la version **1.1.1** du format de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="102e1-131">Select version **1.1.1** of the ER format.</span></span>
5.  <span data-ttu-id="102e1-132">Dans l'organisateur **Conditions**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="102e1-132">On the **Conditions** FastTab, select **Add**.</span></span>
6.  <span data-ttu-id="102e1-133">Dans le champ **Code** du nouvel enregistrement, sélectionnez la flèche du menu déroulant pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="102e1-133">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="102e1-134">La recherche affiche la liste des codes taxe pour la sélection.</span><span class="sxs-lookup"><span data-stu-id="102e1-134">The lookup presents the list of tax codes for selection.</span></span> <span data-ttu-id="102e1-135">Cette liste est renvoyée par la source de données **Model.Data.Tax** qui a été configurée dans le format de gestion des états électroniques de base.</span><span class="sxs-lookup"><span data-stu-id="102e1-135">This list is returned by the **Model.Data.Tax** data source that has been configured in the base ER format.</span></span> <span data-ttu-id="102e1-136">Parce que cette source de données contient le champ **Nom**, le nom de chaque code taxe s'affiche dans la recherche.</span><span class="sxs-lookup"><span data-stu-id="102e1-136">Because this data source contains the **Name** field, the name of each tax code appears in the lookup.</span></span>

    ![Page Paramètres spécifiques à l'application de la gestion des états électroniques](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)
    
7.  <span data-ttu-id="102e1-138">Sélectionnez le code taxe **VAT19**.</span><span class="sxs-lookup"><span data-stu-id="102e1-138">Select the **VAT19** tax code.</span></span>
8.  <span data-ttu-id="102e1-139">Dans le champ **Résultat de la recherche** du nouvel enregistrement, sélectionnez la flèche du menu déroulant pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="102e1-139">In the **Lookup result** field of the new record, select the drop-down arrow to open the lookup.</span></span> <span data-ttu-id="102e1-140">La recherche affiche la liste des valeurs pour l'énumération de format TaxationLevel pour la sélection.</span><span class="sxs-lookup"><span data-stu-id="102e1-140">The lookup presents the list of values for the TaxationLevel format enumeration for selection.</span></span>

    <span data-ttu-id="102e1-141">Notez que, si l'allemand est sélectionné comme langue préférée de l'utilisateur sous lequel vous êtes connecté, les libellés des valeurs dans la recherche seront en allemand, à condition qu'ils aient été traduits au format de gestion des états électroniques de base.</span><span class="sxs-lookup"><span data-stu-id="102e1-141">Note that, if German is selected as the preferred language of the user that you're signed in as, the labels of the values in the lookup will be in German, provided that they have been translated in the base ER format.</span></span> <span data-ttu-id="102e1-142">En outre, si le libellé d'une source de données de recherche a été traduit, ce libellé apparaîtra dans la langue préférée de l'utilisateur dans l'onglet **Recherches**.</span><span class="sxs-lookup"><span data-stu-id="102e1-142">Additionally, if the label of a lookup data source has been translated, that label will appear in the user's preferred language on the **Lookups** tab.</span></span>

    ![Page Paramètres spécifiques à l'application de la gestion des états électroniques](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9.  <span data-ttu-id="102e1-144">Sélectionnez la valeur **Imposition normale**.</span><span class="sxs-lookup"><span data-stu-id="102e1-144">Select the **Regular taxation** value.</span></span>

    <span data-ttu-id="102e1-145">En ajoutant cet enregistrement, vous définissez la règle suivante : dès que la source de données de recherche **Sélecteur** est demandée, et que le code taxe **VAT19** est transmis comme argument, **Imposition normale** sera renvoyée comme le niveau d'imposition demandé.</span><span class="sxs-lookup"><span data-stu-id="102e1-145">By adding this record, you define the following rule: Whenever the **Selector** lookup data source is requested, and the **VAT19** tax code is passed as an argument, **Regular taxation** will be returned as the requested taxation level.</span></span>

10. <span data-ttu-id="102e1-146">Sélectionnez **Ajouter**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="102e1-146">Select **Add**, and then follow these steps:</span></span>

    1. <span data-ttu-id="102e1-147">Dans le champ **Code**, sélectionnez le code taxe **InVAT19**.</span><span class="sxs-lookup"><span data-stu-id="102e1-147">In the **Code** field, select the **InVAT19** tax code.</span></span>
    2. <span data-ttu-id="102e1-148">Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Imposition normale**.</span><span class="sxs-lookup"><span data-stu-id="102e1-148">In the **Lookup result** field, select the **Regular taxation** value.</span></span>
    
11. <span data-ttu-id="102e1-149">Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="102e1-149">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="102e1-150">Dans le champ **Code**, sélectionnez le code taxe **VAT7**.</span><span class="sxs-lookup"><span data-stu-id="102e1-150">In the **Code** field, select the **VAT7** tax code.</span></span>
    2. <span data-ttu-id="102e1-151">Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Imposition réduite**.</span><span class="sxs-lookup"><span data-stu-id="102e1-151">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
12. <span data-ttu-id="102e1-152">Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="102e1-152">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="102e1-153">Dans le champ **Code**, sélectionnez le code taxe **InVAT7**.</span><span class="sxs-lookup"><span data-stu-id="102e1-153">In the **Code** field, select the **InVAT7** tax code.</span></span>
    2. <span data-ttu-id="102e1-154">Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Imposition réduite**.</span><span class="sxs-lookup"><span data-stu-id="102e1-154">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
13. <span data-ttu-id="102e1-155">Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="102e1-155">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="102e1-156">Dans le champ **Code**, sélectionnez le code taxe **THIRD**.</span><span class="sxs-lookup"><span data-stu-id="102e1-156">In the **Code** field, select the **THIRD** tax code.</span></span>
    2. <span data-ttu-id="102e1-157">Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Aucune imposition**.</span><span class="sxs-lookup"><span data-stu-id="102e1-157">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
14. <span data-ttu-id="102e1-158">Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="102e1-158">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="102e1-159">Dans le champ **Code**, sélectionnez le code taxe **InVAT0**.</span><span class="sxs-lookup"><span data-stu-id="102e1-159">In the **Code** field, select the **InVAT0** tax code.</span></span>
    2. <span data-ttu-id="102e1-160">Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Aucune imposition**.</span><span class="sxs-lookup"><span data-stu-id="102e1-160">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
15. <span data-ttu-id="102e1-161">Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="102e1-161">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="102e1-162">Dans le champ **Code**, sélectionnez l'option **\*Non vide\***.</span><span class="sxs-lookup"><span data-stu-id="102e1-162">In the **Code** field, select the **\*Not blank\*** option.</span></span>
    2. <span data-ttu-id="102e1-163">Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Autre**.</span><span class="sxs-lookup"><span data-stu-id="102e1-163">In the **Lookup result** field, select the **Other** value.</span></span>
    
    <span data-ttu-id="102e1-164">En ajoutant ce dernier enregistrement, vous définissez la règle suivante : dès que le code taxe transmis comme argument ne répond plus aux règles précédentes, la source de données de recherche renverra **Autre** comme le niveau d'imposition demandé.</span><span class="sxs-lookup"><span data-stu-id="102e1-164">By adding this last record, you define the following rule: Whenever the tax code that is passed as an argument doesn't satisfy any of the previous rules, the lookup data source will return **Other** as the requested taxation level.</span></span>

    ![Page Paramètres spécifiques à l'application de la gestion des états électroniques](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)
    
16. <span data-ttu-id="102e1-166">Dans le champ **État**, sélectionnez **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="102e1-166">In the **State** field, select **Completed**.</span></span>

    <span data-ttu-id="102e1-167">Lorsque vous exécutez une version de format de gestion des états électroniques avec un état défini sur **Terminé** ou **Partagé**, cet ensemble de règles doit être à l'état **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="102e1-167">When you run an ER format version that has a status of either **Completed** or **Shared**, this set of rules must be in the **Completed** state.</span></span> <span data-ttu-id="102e1-168">Sinon, l'exécution du format de gestion des états électroniques de base est interrompue lorsque le format essaye de charger les données provenant de cet ensemble de règles tandis que la source de données de recherche **Sélecteur** est exécutée.</span><span class="sxs-lookup"><span data-stu-id="102e1-168">Otherwise, execution of the base ER format will be interrupted when the format tries to load data from this set of rules while the **Selector** lookup data source is being run.</span></span>
    
    <span data-ttu-id="102e1-169">Lorsque vous exécutez une version de format de gestion des états électroniques avec un état défini sur **Brouillon**, le format de gestion des états électroniques de base peut accéder à cet ensemble de règles, quel que soit son état.</span><span class="sxs-lookup"><span data-stu-id="102e1-169">When you run an ER format version that has a status of **Draft**, the base ER format can access this set of rules, regardless of its state.</span></span>
    
17. <span data-ttu-id="102e1-170">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="102e1-170">Select **Save**.</span></span>
18. <span data-ttu-id="102e1-171">Fermez la page **Paramètres spécifiques de l'application**.</span><span class="sxs-lookup"><span data-stu-id="102e1-171">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-demf-company"></a><span data-ttu-id="102e1-172">Exécuter le format de gestion des états électroniques dans la société DEMF</span><span class="sxs-lookup"><span data-stu-id="102e1-172">Run the ER format in the DEMF company</span></span>

1.  <span data-ttu-id="102e1-173">Dans l'arborescence des configurations, sélectionnez le format **Format pour apprendre comment rechercher les données LE**.</span><span class="sxs-lookup"><span data-stu-id="102e1-173">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="102e1-174">Dans le volet Actions, sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="102e1-174">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="102e1-175">Dans la boîte de dialogue qui apparaît, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="102e1-175">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="102e1-176">Téléchargez le relevé qui est généré et enregistrez-le localement.</span><span class="sxs-lookup"><span data-stu-id="102e1-176">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="102e1-177">Dans le relevé généré, notez que la synthèse du code taxe **InVAT7** est passée au niveau **Réduite**, et que les synthèses de codes taxe **VAT19** et **InVA19** sont passées au niveau **Normale**.</span><span class="sxs-lookup"><span data-stu-id="102e1-177">In the generated statement, notice that the summary of the **InVAT7** tax code has been put on the **Reduced** level, and the summaries of the **VAT19** and **InVA19** tax codes have been put on the **Regular** level.</span></span> <span data-ttu-id="102e1-178">Ce comportement est déterminé par la configuration dans l'ensemble de règles dépendant de l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="102e1-178">This behavior is determined by the configuration in the legal entity–dependent set of rules.</span></span>
    
5.  <span data-ttu-id="102e1-179">Accédez à **Taxe \> Taxes indirectes \> Taxe \> Codes taxe**.</span><span class="sxs-lookup"><span data-stu-id="102e1-179">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax codes**.</span></span>
6.  <span data-ttu-id="102e1-180">Sélectionnez le code taxe **InVAT7**.</span><span class="sxs-lookup"><span data-stu-id="102e1-180">Select the **InVAT7** tax code.</span></span>
7.  <span data-ttu-id="102e1-181">Dans le volet Actions, sous l'onglet **Code taxe**, au groupe **Recherches**, sélectionnez **Taxe validée** permet d'afficher des informations sur la valeur de taxe et le taux appliqué de taxe par code taxe.</span><span class="sxs-lookup"><span data-stu-id="102e1-181">On the Action Pane, on the **Sales tax code** tab, in the **Inquiries** group, select **Posted sales tax** to view information about the tax value and applied tax rate per tax code.</span></span>

    ![Page de la taxe validée](./media/GER-AppSpecParms-Statement.PNG)

8.  <span data-ttu-id="102e1-183">Fermez la page Taxe validée.</span><span class="sxs-lookup"><span data-stu-id="102e1-183">Close the Posted sales tax page.</span></span>

## <a name="set-up-parameters-for-the-usmf-company"></a><span data-ttu-id="102e1-184">Définir les paramètres pour l'entreprise USMF</span><span class="sxs-lookup"><span data-stu-id="102e1-184">Set up parameters for the USMF company</span></span>

1.  <span data-ttu-id="102e1-185">Sélectionnez l'entité juridique **USMF**.</span><span class="sxs-lookup"><span data-stu-id="102e1-185">Select the **USMF** legal entity.</span></span>
2.  <span data-ttu-id="102e1-186">Accédez à **Administration d'organisation \> États électroniques \> Configurations**.</span><span class="sxs-lookup"><span data-stu-id="102e1-186">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
3.  <span data-ttu-id="102e1-187">Dans l'arborescence des configurations, développez l'article **Modèle pour apprendre les appels paramétrés**, développez l'article **Format pour apprendre les appels paramétrés**, puis sélectionnez le format **Format pour apprendre comment rechercher les données LE**.</span><span class="sxs-lookup"><span data-stu-id="102e1-187">In the configurations tree, expand the **Model to learn parameterized calls** item, expand the **Format to learn parameterized calls** item, and select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="102e1-188">Dans le volet Actions, sous l'onglet **Configurations**, dans le groupe **Paramètres spécifiques à l'application**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="102e1-188">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="102e1-189">Sélectionnez la version **1.1.1** du format de gestion des états électroniques sélectionné.</span><span class="sxs-lookup"><span data-stu-id="102e1-189">Select version **1.1.1** of the selected ER format.</span></span>
6.  <span data-ttu-id="102e1-190">Dans l'organisateur **Conditions**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="102e1-190">On the **Conditions** FastTab, select **Add**.</span></span>
7.  <span data-ttu-id="102e1-191">Dans le champ **Code** du nouvel enregistrement, sélectionnez la flèche du menu déroulant pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="102e1-191">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="102e1-192">La recherche affiche désormais la liste des codes taxe pour la taxe de société **USMF** pour sélection.</span><span class="sxs-lookup"><span data-stu-id="102e1-192">The lookup now presents the list of tax codes for the **USMF** company tax for selection.</span></span>

    ![Page Paramètres spécifiques à l'application de la gestion des états électroniques](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)
    
8.  <span data-ttu-id="102e1-194">Sélectionnez le code taxe **EXEMPT**.</span><span class="sxs-lookup"><span data-stu-id="102e1-194">Select the **EXEMPT** tax code.</span></span>
9.  <span data-ttu-id="102e1-195">Dans le champ **Résultat de la recherche** du nouvel enregistrement, sélectionnez la valeur **Aucune imposition**.</span><span class="sxs-lookup"><span data-stu-id="102e1-195">In the **Lookup resul**t field of the new record, select the **No taxation** value.</span></span>
10. <span data-ttu-id="102e1-196">Sélectionnez à nouveau **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="102e1-196">Select **Add** again.</span></span>
11. <span data-ttu-id="102e1-197">Dans le champ **Code** du nouvel enregistrement, sélectionnez l'option **\*Non vide\***.</span><span class="sxs-lookup"><span data-stu-id="102e1-197">In the **Code** field of the new record, select the **\*Not blank\*** option.</span></span>
12. <span data-ttu-id="102e1-198">Dans le champ **Résultat de la recherche** du nouvel enregistrement, sélectionnez la valeur **Imposition normale**.</span><span class="sxs-lookup"><span data-stu-id="102e1-198">In the **Lookup result** field of the new record, select the **Regular taxation** value.</span></span>
13. <span data-ttu-id="102e1-199">Dans le champ **État**, sélectionnez **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="102e1-199">In the **State** field, select **Completed**.</span></span>
14. <span data-ttu-id="102e1-200">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="102e1-200">Select **Save**.</span></span>

    ![Page Paramètres spécifiques à l'application de la gestion des états électroniques](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)
    
15. <span data-ttu-id="102e1-202">Fermez la page **Paramètres spécifiques de l'application**.</span><span class="sxs-lookup"><span data-stu-id="102e1-202">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-usmf-company"></a><span data-ttu-id="102e1-203">Exécuter le format de gestion des états électroniques dans la société USMF</span><span class="sxs-lookup"><span data-stu-id="102e1-203">Run the ER format in the USMF company</span></span>

1.  <span data-ttu-id="102e1-204">Dans l'arborescence des configurations, sélectionnez le format **Format pour apprendre comment rechercher les données LE**.</span><span class="sxs-lookup"><span data-stu-id="102e1-204">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="102e1-205">Dans le volet Actions, sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="102e1-205">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="102e1-206">Dans la boîte de dialogue qui apparaît, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="102e1-206">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="102e1-207">Téléchargez le relevé qui est généré et enregistrez-le localement.</span><span class="sxs-lookup"><span data-stu-id="102e1-207">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="102e1-208">Dans le relevé généré, notez que vous avez désormais réutilisé le même format de gestion des états électroniques pour une autre entité juridique, mais sans faire d'ajustement au format de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="102e1-208">In the generated statement, notice that you've now reused the same ER format for a different legal entity, but without making any adjustments to the ER format.</span></span>

## <a name="reuse-legal-entitydependent-parameters"></a><span data-ttu-id="102e1-209">Réutiliser les paramètres dépendant de l'entité juridique</span><span class="sxs-lookup"><span data-stu-id="102e1-209">Reuse legal entity–dependent parameters</span></span>

### <a name="export-parameters"></a><span data-ttu-id="102e1-210">Exporter les paramètres</span><span class="sxs-lookup"><span data-stu-id="102e1-210">Export parameters</span></span>

1.  <span data-ttu-id="102e1-211">Allez dans **Administration d'organisation \> Espaces de travail \> États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="102e1-211">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2.  <span data-ttu-id="102e1-212">Sélectionnez **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="102e1-212">Select **Reporting configurations**.</span></span>
3.  <span data-ttu-id="102e1-213">Dans l'arborescence des configurations, sélectionnez le format **Format pour apprendre comment rechercher les données LE**.</span><span class="sxs-lookup"><span data-stu-id="102e1-213">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="102e1-214">Dans le volet Actions, sous l'onglet **Configurations**, dans le groupe **Paramètres spécifiques à l'application**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="102e1-214">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="102e1-215">Sélectionnez la version **1.1.1** du format de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="102e1-215">Select version **1.1.1** of the ER format.</span></span>
6.  <span data-ttu-id="102e1-216">Dans le volet Actions, sélectionnez **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="102e1-216">On the Action Pane, select **Export**.</span></span>
7.  <span data-ttu-id="102e1-217">Téléchargez le fichier qui est généré et enregistrez-le localement.</span><span class="sxs-lookup"><span data-stu-id="102e1-217">Download the file that is generated and store it locally.</span></span>

    <span data-ttu-id="102e1-218">L'ensemble configuré des paramètres spécifiques à l'application est désormais exporté comme fichier XML.</span><span class="sxs-lookup"><span data-stu-id="102e1-218">The configured set of application-specific parameters has now been exported as an XML file.</span></span>

### <a name="import-parameters"></a><span data-ttu-id="102e1-219">Importer les paramètres</span><span class="sxs-lookup"><span data-stu-id="102e1-219">Import parameters</span></span>

1.  <span data-ttu-id="102e1-220">Sélectionnez la version **1.1.2** du format de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="102e1-220">Select version **1.1.2** of the ER format.</span></span>
2.  <span data-ttu-id="102e1-221">Dans la volet Actions, sélectionnez **Importer**.</span><span class="sxs-lookup"><span data-stu-id="102e1-221">On the Action Pane, select **Import**.</span></span>
3.  <span data-ttu-id="102e1-222">Sélectionnez **Oui** pour confirmer que vous souhaitez remplacer les paramètres spécifiques à l'application existants pour cette version de format.</span><span class="sxs-lookup"><span data-stu-id="102e1-222">Select **Yes** to confirm that you want to override the existing application-specific parameters for this format version.</span></span>
4.  <span data-ttu-id="102e1-223">Sélectionnez **Parcourir** pour rechercher le fichier qui contient les paramètres spécifiques à l'application exportés pour la version **1.1.1**.</span><span class="sxs-lookup"><span data-stu-id="102e1-223">Select **Browse** to find the file that contains the exported application-specific parameters for version **1.1.1**.</span></span>
5.  <span data-ttu-id="102e1-224">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="102e1-224">Select **OK**.</span></span>

    <span data-ttu-id="102e1-225">La version **1.1.2** du format de gestion des états électroniques a désormais les mêmes paramètres spécifiques à l'application que vous avez précédemment configurés pour la version **1.1.1**.</span><span class="sxs-lookup"><span data-stu-id="102e1-225">Version **1.1.2** of the ER format now has the same application-specific parameters that you originally configured for version **1.1.1**.</span></span>
    
    <span data-ttu-id="102e1-226">Notez que les paramètres spécifiques à l'application d'un format de gestion des états électroniques dépendent de l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="102e1-226">Note that the application-specific parameters of an ER format are legal entity–dependent.</span></span> <span data-ttu-id="102e1-227">Pour réutiliser les paramètres spécifiques à l'application qui ont été configurés pour une entité juridique dans une autre entité juridique, vous devez les exporter alors que vous êtes connecté à la première entité juridique, puis les importer ensuite après vous être connecté à l'autre entité juridique.</span><span class="sxs-lookup"><span data-stu-id="102e1-227">To reuse the application-specific parameters that were configured for one legal entity in a different legal entity, you must export them while you're signed in to the first legal entity and then import them after you sign in to the other legal entity.</span></span>

    <span data-ttu-id="102e1-228">Vous pouvez également utiliser cette approche pour transférer les paramètres spécifiques à l'application associés à la gestion des états électroniques qui étaient configurés dans une instance de Finance vers une autre instance de Finance.</span><span class="sxs-lookup"><span data-stu-id="102e1-228">You can also use this approach to transfer an ER format related application-specific parameters that were originally configured in one instance of Finance to another instance of Finance.</span></span>

    <span data-ttu-id="102e1-229">Notez que si vous configurez les paramètres spécifiques à l'application pour une version d'un format de gestion des états électroniques et si vous importez une version supérieure du même format dans l'instance actuelle de Finance, les paramètres spécifiques à l'application existants ne seront pas appliqués pour la version importée.</span><span class="sxs-lookup"><span data-stu-id="102e1-229">Be aware that if you configure application-specific parameters for one version of an ER format and import a higher version of the same format into the current Finance instance, the existing application-specific parameters won't be applied for the imported version.</span></span>
    
    <span data-ttu-id="102e1-230">Tenez également compte que, lorsque vous sélectionnez un fichier pour importation, la structure des paramètres spécifiques à l'application de ce fichier est comparée à la structure de la source de données correspondante du type **Recherche** dans le format de gestion des états électroniques sélectionné pour importation.</span><span class="sxs-lookup"><span data-stu-id="102e1-230">Also be aware that, when you select a file for import, the structure of the application-specific parameters in that file is compared with the structure of the corresponding data source of the **Lookup** type in the ER format that is selected for import.</span></span> <span data-ttu-id="102e1-231">L'importation est effectuée lors de la structure de chaque paramètre spécifique à l'application correspond la structure de la source de données correspondante dans le format de gestion des états électroniques sélectionné pour importation.</span><span class="sxs-lookup"><span data-stu-id="102e1-231">The import is done when the structure of each application-specific parameter matches the structure of the corresponding data source in the ER format that is selected for import.</span></span> <span data-ttu-id="102e1-232">Si les structures ne correspondent pas, vous recevez un message d'avertissement informant que l'importation ne peut pas avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="102e1-232">If the structures don't match, you receive a warning message that states that the import can't be done.</span></span> <span data-ttu-id="102e1-233">Si vous forcez l'importation, les paramètres spécifiques à l'application existants pour le format de gestion des états électroniques sélectionné seront effacés et vous devrez les configurer à partir de zéro.</span><span class="sxs-lookup"><span data-stu-id="102e1-233">If you force the import to be done, the existing application-specific parameters for the selected ER format will be cleaned up, and you must set them up from the beginning.</span></span>

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a><span data-ttu-id="102e1-234">Relation entre les paramètres spécifiques à l'application et un format de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="102e1-234">Relationship between application-specific parameters and an ER format</span></span>

<span data-ttu-id="102e1-235">La relation entre un format de gestion des états électroniques et ses paramètres spécifiques à l'application est établie par le code d'identification unique indépendant de l'instance du format de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="102e1-235">The relationship between an ER format and its application-specific parameters is established by the ER format's instance-independent unique identification code.</span></span> <span data-ttu-id="102e1-236">Par conséquent, lorsque vous supprimez un format de gestion des états électroniques de Finance, les paramètres spécifiques à l'application qui sont configurés pour le format de gestion des états électroniques sont conservés dans l'instance actuelle de Finance.</span><span class="sxs-lookup"><span data-stu-id="102e1-236">Therefore, when you remove an ER format from Finance, the application-specific parameters that are configured for the ER format are kept in the current instance of Finance.</span></span> <span data-ttu-id="102e1-237">Ils peuvent être consultés dès que le format de gestion des états électroniques de base est réimporté dans cette instance de Finance.</span><span class="sxs-lookup"><span data-stu-id="102e1-237">They can be accessed whenever the base ER format is reimported into this instance of Finance.</span></span>

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a><span data-ttu-id="102e1-238">Accéder aux paramètres spécifiques à l'application en utilisant la structure de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="102e1-238">Access application-specific parameters by using the ER framework</span></span>

<span data-ttu-id="102e1-239">Dans l'exemple précédent, vous avez accédé aux paramètres spécifiques à l'application d'un format de gestion des états électroniques à l'aide de la structure de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="102e1-239">In the preceding example, you have accessed application-specific parameters of an ER format by using the ER framework.</span></span> <span data-ttu-id="102e1-240">Cette approche ne vous permet pas limiter l'accès aux paramètres spécifiques à l'application d'un format de gestion des états électroniques spécifique.</span><span class="sxs-lookup"><span data-stu-id="102e1-240">This approach doesn't let you restrict access to the application-specific parameters of a specific ER format.</span></span> <span data-ttu-id="102e1-241">Si vous devez appliquer de telles restrictions, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="102e1-241">If you must apply such restrictions, follow these steps.</span></span> 

1.  <span data-ttu-id="102e1-242">Réutilisez un élément de menu **ERSolutionAppSpecificParametersDesigner** existant, ou mettez en œuvre votre propre élément de menu **ERSolutionAppSpecificParametersDesigner**.</span><span class="sxs-lookup"><span data-stu-id="102e1-242">Either reuse an existing **ERSolutionAppSpecificParametersDesigner** menu item, or implement your own **ERSolutionAppSpecificParametersDesigner** menu item.</span></span>

    ![Page Visual Studio](./media/GER-AppSpecParms-LookupForm-Access1.PNG)
    
2.  <span data-ttu-id="102e1-244">Utilisez l'une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="102e1-244">Follow one of these steps:</span></span>

    1.  <span data-ttu-id="102e1-245">Créez un bouton d'option de menu, et liez-le à l'enregistrement correspondant depuis la table **ERSolutionTable** en définissant sa propriété **Source de données** sur **ERSolutionTable**.</span><span class="sxs-lookup"><span data-stu-id="102e1-245">Create a new menu item button, and link it to the corresponding record from the **ERSolutionTable** table by setting its **Data Source** property to **ERSolutionTable**.</span></span>
    
        ![Page Visual Studio](./media/GER-AppSpecParms-LookupForm-Access2.PNG)
        
    2.  <span data-ttu-id="102e1-247">Créez un bouton unique, et remplacez la méthode **Cliqué** comme indiqué dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="102e1-247">Create a simple button, and override the **Clicked** method as shown in the following example.</span></span>
    
        <span data-ttu-id="102e1-248">Grâce à cette approche, vous pouvez spécifier un ID unique de solution (défini à l'aide de la valeur **GUID**) pour autoriser l'accès aux paramètres spécifiques à l'application d'un seul format de gestion des états électroniques spécifique et de copies racines qui en sont dérivées.</span><span class="sxs-lookup"><span data-stu-id="102e1-248">By using this approach, you can specify a unique solution ID (defined via the **GUID** value) to allow access to the application-specific parameters of only a specific ER format and descendant copies that have been derived from it.</span></span>
        
        ```xpp
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a><span data-ttu-id="102e1-249">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="102e1-249">Additional resources</span></span>

[<span data-ttu-id="102e1-250">Concepteur de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="102e1-250">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="102e1-251">Configurer des formats de gestion des états électroniques pour utiliser les paramètres spécifiés par entité juridique</span><span class="sxs-lookup"><span data-stu-id="102e1-251">Configure ER formats to use parameters that are specified per legal entity</span></span>](er-app-specific-parameters-configure-format.md)
