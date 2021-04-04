---
title: Supprimer les contrôles de contenu Word dans les rapports générés
description: Cette rubrique explique comment configurer un format d’état électronique (ER) pour générer des états en tant que fichiers Microsoft Word dans lesquels les contrôles de contenu sont supprimés.
author: NickSelin
manager: AnnBe
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 81ad25514154dd8982aa4f849f0b2bfeb85270f7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562116"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a><span data-ttu-id="87082-103">Supprimer les contrôles de contenu Word dans les rapports générés</span><span class="sxs-lookup"><span data-stu-id="87082-103">Suppress Word content controls in generated reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87082-104">Pour générer des états en tant que documents Microsoft Word, vous devez concevoir un modèle pour les états sous forme de document Word.</span><span class="sxs-lookup"><span data-stu-id="87082-104">To generate reports as Microsoft Word documents, you must design a template for the reports as a Word document.</span></span> <span data-ttu-id="87082-105">Ce modèle doit contenir des contrôles de contenu Word en tant qu’espaces réservés pour les données qui seront renseignées au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="87082-105">This template must contain Word content controls as placeholders for data that will be filled in at runtime.</span></span> <span data-ttu-id="87082-106">Pour utiliser le document Word créé comme modèle pour vos états, vous pouvez [configurer](er-design-configuration-word.md) une nouvelle [solution](er-quick-start1-new-solution.md) de [gestion des états électroniques](general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="87082-106">To use the Word document that is created as a template for your reports, you can [configure](er-design-configuration-word.md) a new [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md).</span></span> <span data-ttu-id="87082-107">La solution doit inclure une [configuration](general-electronic-reporting.md#Configuration) de gestion des états électroniques qui contient un composant de [format](general-electronic-reporting.md#FormatComponentOutbound) de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="87082-107">The solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="87082-108">Ce format ER doit être configuré pour utiliser le modèle conçu pour la génération d’états.</span><span class="sxs-lookup"><span data-stu-id="87082-108">This ER format must be configured to use the designed template for report generation.</span></span>

<span data-ttu-id="87082-109">Dans la version 10.0.6 et les versions ultérieures de Dynamics 365 Finance, vous pouvez configurer des formules dans votre format ER pour supprimer certains contrôles de contenu Word dans les documents générés.</span><span class="sxs-lookup"><span data-stu-id="87082-109">In version 10.0.6 and later of Dynamics 365 Finance, you can configure formulas in your ER format to suppress some Word content controls in generated documents.</span></span>

<span data-ttu-id="87082-110">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de consultant fonctionnel des états électroniques peut configurer un format ER qui génère des états sous forme de fichiers Word et supprime certains des contrôles de contenu dans les rapports générés qui ont été configurés à l’aide d’un modèle Word.</span><span class="sxs-lookup"><span data-stu-id="87082-110">The following steps explain how a user who is assigned to the System administrator or Electronic reporting functional consultant role can configure an ER format that generates reports as Word files and suppresses some of the content controls in the generated reports that have been configured by using a Word template.</span></span>

<span data-ttu-id="87082-111">Ces étapes peuvent être effectuées dans la société GBSI.</span><span class="sxs-lookup"><span data-stu-id="87082-111">These steps can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="87082-112">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="87082-112">Prerequisites</span></span>

<span data-ttu-id="87082-113">Pour réaliser ces étapes, vous devez d’abord effectuer les étapes des guides de tâche suivants :</span><span class="sxs-lookup"><span data-stu-id="87082-113">To complete these steps, you must first complete the steps in the following task guides:</span></span>

- [<span data-ttu-id="87082-114">Concevoir une configuration pour générer des états au format OPENXML</span><span class="sxs-lookup"><span data-stu-id="87082-114">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="87082-115">Réutiliser les configurations des états électroniques avec des modèles Excel pour générer des rapports au format Word</span><span class="sxs-lookup"><span data-stu-id="87082-115">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)

<span data-ttu-id="87082-116">Lorsque vous avez terminé les étapes de ces guides de tâches, les éléments suivants sont préparés :</span><span class="sxs-lookup"><span data-stu-id="87082-116">When you complete the steps of these task guides, the following items are prepared:</span></span>

- <span data-ttu-id="87082-117">Un format ER **Exemple d’état sur les feuilles de calcul** configuré pour générer un document au format Word</span><span class="sxs-lookup"><span data-stu-id="87082-117">A **Sample worksheet report** ER format that is configured to generate a document in Word format</span></span>
- <span data-ttu-id="87082-118">Une version [Brouillon](general-electronic-reporting.md#component-versioning) du format ER **Exemple d’état sur les feuilles de calcul** marqué comme **Exécutable**</span><span class="sxs-lookup"><span data-stu-id="87082-118">A [draft](general-electronic-reporting.md#component-versioning) version of the **Sample worksheet report** ER format that is marked as **Runnable**</span></span>
- <span data-ttu-id="87082-119">Un mode de paiement **Électronique** configuré pour utiliser le format ER **Exemple d’état sur les feuilles de calcul** pour le traitement des paiements fournisseur</span><span class="sxs-lookup"><span data-stu-id="87082-119">An **Electronic** method of payments that is configured to use the **Sample worksheet report** ER format for vendor payment processing</span></span>

<span data-ttu-id="87082-120">Vous devez également télécharger et enregistrer le modèle suivant pour l’exemple d’état :</span><span class="sxs-lookup"><span data-stu-id="87082-120">You must also download and save the following template for the sample report:</span></span>

- [<span data-ttu-id="87082-121">Modèle lié 2 d’état de paiement (SampleVendPaymDocReportBounded2.docx)</span><span class="sxs-lookup"><span data-stu-id="87082-121">Bounded Template 2 of Payment Report (SampleVendPaymDocReportBounded2.docx)</span></span>](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a><span data-ttu-id="87082-122">Consulter le modèle Word téléchargé</span><span class="sxs-lookup"><span data-stu-id="87082-122">Review the downloaded Word template</span></span>

1. <span data-ttu-id="87082-123">Dans l’application de bureau Word, ouvrez le fichier de modèle **SampleVendPaymDocReportBounded2.docx** que vous avez téléchargé précédemment.</span><span class="sxs-lookup"><span data-stu-id="87082-123">In the Word desktop application, open the **SampleVendPaymDocReportBounded2.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="87082-124">Vérifiez que le fichier de modèle contient une section récapitulative qui affiche les montants de paiement totaux pour chaque code devise rencontré dans les paiements traités.</span><span class="sxs-lookup"><span data-stu-id="87082-124">Verify that the template file contains a summary section that shows the total payment amounts for every currency code that has been met in the processed payments.</span></span>

    - <span data-ttu-id="87082-125">La section récapitulative se trouve dans un tableau distinct du document Word.</span><span class="sxs-lookup"><span data-stu-id="87082-125">The summary section resides in a separate table of the Word document.</span></span>
    - <span data-ttu-id="87082-126">La première ligne de ce tableau contient les en-têtes des colonnes du tableau comme en-tête de section.</span><span class="sxs-lookup"><span data-stu-id="87082-126">The first row of this table holds the table columns headings as the section header.</span></span>
    - <span data-ttu-id="87082-127">La deuxième ligne de ce tableau contient le contrôle de contenu répétitif en tant que détails de la section.</span><span class="sxs-lookup"><span data-stu-id="87082-127">The second row of this table holds the repeating content control as the section details.</span></span>
    - <span data-ttu-id="87082-128">Ce contrôle de contenu est mappé sur le champ **SummaryLines** de la partie XML personnalisée **État**.</span><span class="sxs-lookup"><span data-stu-id="87082-128">This content control is mapped to the **SummaryLines** field of the **Report** custom XML part.</span></span>
    - <span data-ttu-id="87082-129">Sur la base de ce mappage, le contrôle de contenu est associé à l’élément **SummaryLines** du format ER modifiable.</span><span class="sxs-lookup"><span data-stu-id="87082-129">Based on this mapping, the content control is associated with the **SummaryLines** element of the editable ER format.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87082-130">Le contrôle de contenu répétitif est balisé par la clé **SummaryLines** qui correspond au champ de la partie XML personnalisée à laquelle elle a été mappée.</span><span class="sxs-lookup"><span data-stu-id="87082-130">The repeating content control is tagged by the **SummaryLines** key that matches the field of the custom XML part that it has been mapped to.</span></span>

    ![Disposition du modèle Word](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="87082-132">Sélectionnez la configuration d’états électroniques existante</span><span class="sxs-lookup"><span data-stu-id="87082-132">Select the existing ER report configuration</span></span>

<span data-ttu-id="87082-133">Pour les étapes suivantes, vous réutiliserez la configuration ER existante que vous avez configurée lorsque vous avez effectué les étapes des guides de tâches mentionnés précédemment.</span><span class="sxs-lookup"><span data-stu-id="87082-133">For the following steps, you will reuse the existing ER configuration that you configured when you completed the steps in the previously mentioned task guides.</span></span>

1. <span data-ttu-id="87082-134">Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="87082-134">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87082-135">Sélectionnez **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="87082-135">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="87082-136">Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle de paiement**, puis sélectionnez **Exemple d’état sur les feuilles de calcul**.</span><span class="sxs-lookup"><span data-stu-id="87082-136">On the **Configurations** page, in the configuration tree, expand **Payment model**, and select **Sample worksheet report**.</span></span>
4. <span data-ttu-id="87082-137">Sélectionnez **Concepteur** pour modifier la version brouillon du format ER sélectionné.</span><span class="sxs-lookup"><span data-stu-id="87082-137">Select **Designer** to edit the draft version of the selected ER format.</span></span>

## <a name="replace-the-current-template-with-the-new-template"></a><span data-ttu-id="87082-138">Remplacer le modèle actuel par le nouveau modèle</span><span class="sxs-lookup"><span data-stu-id="87082-138">Replace the current template with the new template</span></span>

<span data-ttu-id="87082-139">Actuellement, le fichier SampleVendPaymDocReportBounded.docx est utilisé comme modèle pour générer la sortie au format Word.</span><span class="sxs-lookup"><span data-stu-id="87082-139">Currently, the SampleVendPaymDocReportBounded.docx file is used as a template to generate the output in Word format.</span></span> <span data-ttu-id="87082-140">Dans les étapes suivantes, vous remplacerez ce modèle Word par le nouveau modèle Word, SampleVendPaymDocReportBounded2.docx, que vous avez téléchargé précédemment.</span><span class="sxs-lookup"><span data-stu-id="87082-140">In the following steps, you will replace this Word template with the new Word template, SampleVendPaymDocReportBounded2.docx, that you downloaded earlier.</span></span>

1. <span data-ttu-id="87082-141">Dans la page **Concepteur de formats**, sélectionnez **Documents joints**.</span><span class="sxs-lookup"><span data-stu-id="87082-141">On the **Format designer** page, select **Attachments**.</span></span>
2. <span data-ttu-id="87082-142">Sur la page **Documents joints**, sélectionnez **Supprimer** pour supprimer le modèle existant.</span><span class="sxs-lookup"><span data-stu-id="87082-142">On the **Attachments** page, select **Delete** to remove the existing template.</span></span>
3. <span data-ttu-id="87082-143">Sélectionnez **Oui** pour confirmer la suppression.</span><span class="sxs-lookup"><span data-stu-id="87082-143">Select **Yes** to confirm the deletion.</span></span>
4. <span data-ttu-id="87082-144">Sélectionnez **Nouveau** \> **Fichier**.</span><span class="sxs-lookup"><span data-stu-id="87082-144">Select **New** \> **File**.</span></span>
5. <span data-ttu-id="87082-145">Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **SampleVendPaymDocReportBounded2.docx** que vous avez téléchargé précédemment.</span><span class="sxs-lookup"><span data-stu-id="87082-145">Select **Browse**, and browse to and select the **SampleVendPaymDocReportBounded2.docx** file that you downloaded earlier.</span></span>
6. <span data-ttu-id="87082-146">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87082-146">Select **OK**.</span></span>
7. <span data-ttu-id="87082-147">Fermez la page **Pièces jointes**.</span><span class="sxs-lookup"><span data-stu-id="87082-147">Close the **Attachments** page.</span></span>
8. <span data-ttu-id="87082-148">Sur la page **Concepteur de format**, dans le champ **Modèle**, entrez ou sélectionnez le fichier **SampleVendPaymDocReportBounded2.docx**.</span><span class="sxs-lookup"><span data-stu-id="87082-148">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReportBounded2.docx** file.</span></span>

## <a name="run-the-format-to-create-word-output"></a><span data-ttu-id="87082-149">Exécuter le format pour créer une sortie Word</span><span class="sxs-lookup"><span data-stu-id="87082-149">Run the format to create Word output</span></span>

1. <span data-ttu-id="87082-150">Accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements**.</span><span class="sxs-lookup"><span data-stu-id="87082-150">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="87082-151">Sur la page **Paiements fournisseur**, sur l’onglet **Liste**, sélectionnez tous les paiements.</span><span class="sxs-lookup"><span data-stu-id="87082-151">On the **Vendor payments** page, on the **List** tab, select all the payments.</span></span>
3. <span data-ttu-id="87082-152">Sélectionnez **Statut de paiement** \> **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="87082-152">Select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="87082-153">Sélectionnez **Générer des paiements**.</span><span class="sxs-lookup"><span data-stu-id="87082-153">Select **Generate payments**.</span></span>
5. <span data-ttu-id="87082-154">Dans le champ **Mode de paiement**, sélectionnez **Électronique**.</span><span class="sxs-lookup"><span data-stu-id="87082-154">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="87082-155">Dans le champ **Compte bancaire**, sélectionnez **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="87082-155">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="87082-156">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87082-156">Select **OK**.</span></span>
8. <span data-ttu-id="87082-157">Dans la boîte de dialogue **Paramètres de génération d’états électroniques**, sélectionnez **OK** et analysez la sortie générée.</span><span class="sxs-lookup"><span data-stu-id="87082-157">In the **Electronic report parameters** dialog box, select **OK**, and analyze the generated output.</span></span>

    ![Paiements pour traitement sur la page Paiements fournisseur](./media/er-design-configuration-word-suppress-controls-image2.gif)

    <span data-ttu-id="87082-159">La sortie est présentée au format Word et contient la section récapitulative.</span><span class="sxs-lookup"><span data-stu-id="87082-159">The output is presented in Word format and contains the summary section.</span></span>

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a><span data-ttu-id="87082-160">Configurer le format modifiable pour supprimer la section récapitulative</span><span class="sxs-lookup"><span data-stu-id="87082-160">Configure the editable format to suppress the summary section</span></span>

<span data-ttu-id="87082-161">Si vous souhaitez supprimer la section récapitulative dans un document généré, sur la base de la demande d’un utilisateur qui exécute ce format ER, vous devez modifier le format ER modifiable.</span><span class="sxs-lookup"><span data-stu-id="87082-161">If you want to suppress the summary section in a generated document, based on the request of a user who runs this ER format, you must modify the editable ER format.</span></span>

1. <span data-ttu-id="87082-162">Accédez à **Administration d’organisation** \> **Espaces de travail** \> **Gestion des états électroniques** et ouvrez la version brouillon du format ER à modifier.</span><span class="sxs-lookup"><span data-stu-id="87082-162">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**, and open the draft version of the ER format for editing.</span></span>
2. <span data-ttu-id="87082-163">Sélectionnez **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="87082-163">Select **Reporting configurations**.</span></span> 
3. <span data-ttu-id="87082-164">Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle de paiement** \> **Exemple d’état sur les feuilles de calcul**.</span><span class="sxs-lookup"><span data-stu-id="87082-164">On the **Configurations** page, in the configuration tree, expand **Payment model** \> **Sample worksheet report**.</span></span>
4. <span data-ttu-id="87082-165">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="87082-165">Select **Designer**.</span></span>
5. <span data-ttu-id="87082-166">Sur la page **Concepteur de formats**, développez **Word** et sélectionnez **SummaryLines**.</span><span class="sxs-lookup"><span data-stu-id="87082-166">On the **Format designer** page, expand **Word**, and select **SummaryLines**.</span></span>
6. <span data-ttu-id="87082-167">Sur l’onglet **Mappage**, ajoutez une nouvelle source de données pour demander à l’utilisateur, au moment de l’exécution, si la section récapitulative doit être supprimée :</span><span class="sxs-lookup"><span data-stu-id="87082-167">On the **Mapping** tab, add a new data source to ask the user, at runtime, whether the summary section should be suppressed:</span></span>

    1. <span data-ttu-id="87082-168">Sélectionnez **Ajoutez racine**.</span><span class="sxs-lookup"><span data-stu-id="87082-168">Select **Add root**.</span></span>
    2. <span data-ttu-id="87082-169">Dans la boîte de dialogue **Ajouter une source de données**, sélectionnez **Général\Paramètre d’entrée utilisateur** pour ouvrir la boîte de dialogue **Propriétés de la source de données « Paramètre d’entrée utilisateur »**.</span><span class="sxs-lookup"><span data-stu-id="87082-169">In the **Add data source** dialog box, select **General\User input parameter** to open the **'User input parameter' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="87082-170">Dans le champ **Nom**, entrez **uipSuppress**.</span><span class="sxs-lookup"><span data-stu-id="87082-170">In the **Name** field, enter **uipSuppress**.</span></span>
    4. <span data-ttu-id="87082-171">Dans le champ **Libellé**, entrez **Supprimer la section récapitulative**.</span><span class="sxs-lookup"><span data-stu-id="87082-171">In the **Label** field, enter **Suppress summary section**.</span></span>
    5. <span data-ttu-id="87082-172">Dans le champ **Nom du type de données des opérations**, sélectionnez ou entrez **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="87082-172">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="87082-173">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87082-173">Select **OK**.</span></span>

7. <span data-ttu-id="87082-174">Ajoutez une nouvelle source de données du type d’énumération d’application **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="87082-174">Add a new data source of the **NoYes** application enumeration type:</span></span>

    1. <span data-ttu-id="87082-175">Sélectionnez **Ajoutez racine**.</span><span class="sxs-lookup"><span data-stu-id="87082-175">Select **Add root**.</span></span>
    2. <span data-ttu-id="87082-176">Dans la boîte de dialogue **Ajouter une source de données**, sélectionnez **Dynamics 365 for Operations\Énumération** pour ouvrir la boite de dialogue **Propriétés de la source de données « Enumération »**.</span><span class="sxs-lookup"><span data-stu-id="87082-176">In the **Add data source** dialog box, select **Dynamics 365 for Operations\Enumeration** to open the **'Enumeration' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="87082-177">Dans le champ **Nom**, entrez **enumNoYes**.</span><span class="sxs-lookup"><span data-stu-id="87082-177">In the **Name** field, enter **enumNoYes**.</span></span>
    4. <span data-ttu-id="87082-178">Dans le champ **Libellé**, entrez **Supprimer les options**.</span><span class="sxs-lookup"><span data-stu-id="87082-178">In the **Label** field, enter **Suppress options**.</span></span>
    5. <span data-ttu-id="87082-179">Dans le champ **Nom du type de données des opérations**, sélectionnez ou entrez **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="87082-179">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="87082-180">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87082-180">Select **OK**.</span></span>

8. <span data-ttu-id="87082-181">Pour l’élément de format **SummaryLines** sélectionné, configurez la formule pour spécifier quand le contrôle de contenu Word associé à l’élément de format sélectionné doit être supprimé :</span><span class="sxs-lookup"><span data-stu-id="87082-181">For the selected **SummaryLines** format element, configure the formula to specify when the Word content control that is associated with the selected format element should be suppressed:</span></span>

    1. <span data-ttu-id="87082-182">Sur l’onglet **Mappage**, dans la section **Supprimé**, sélectionnez **Modifier** pour ouvrir la page **[Concepteur de formule](general-electronic-reporting-formula-designer.md)**.</span><span class="sxs-lookup"><span data-stu-id="87082-182">On the **Mapping** tab, in the **Removed** section, select **Edit** to open the **[Formula designer](general-electronic-reporting-formula-designer.md)** page.</span></span>
    2. <span data-ttu-id="87082-183">Dans le champ **Formule**, entrez la formule `uipSuppress = enumNoYes.Yes`.</span><span class="sxs-lookup"><span data-stu-id="87082-183">In the **Formula** field, enter the formula `uipSuppress = enumNoYes.Yes`.</span></span>
    3. <span data-ttu-id="87082-184">Sélectionnez **Enregistrer** et fermez la page du **Concepteur de formule**.</span><span class="sxs-lookup"><span data-stu-id="87082-184">Select **Save**, and close the **Formula designer** page.</span></span>

        > [!NOTE]
        > <span data-ttu-id="87082-185">Cette formule sera appliquée à un document généré **après l’exécution de tous les autres éléments de format**.</span><span class="sxs-lookup"><span data-stu-id="87082-185">This formula will be applied to a generated document **after all other format elements are run**.</span></span> <span data-ttu-id="87082-186">Pour appliquer cette formule, un contrôle de contenu Word référencé en tant qu’élément de format pour lequel la formule est configurée (**SummaryLines** dans ce cas) se trouve dans un document généré.</span><span class="sxs-lookup"><span data-stu-id="87082-186">To apply this formula, a Word content control that is tagged as a format element that the formula is configured for (**SummaryLines** in this case) is found in a generated document.</span></span> <span data-ttu-id="87082-187">Ce contrôle de contenu est ensuite complètement supprimé, ainsi que la ligne du tableau Word qui le contient.</span><span class="sxs-lookup"><span data-stu-id="87082-187">That content control is then completely removed, together with the row in the Word table that holds it.</span></span> <span data-ttu-id="87082-188">La ligne de détails de la section récapitulative est supprimée du document généré.</span><span class="sxs-lookup"><span data-stu-id="87082-188">The details row of the summary section is removed from the generated document.</span></span>
        >
        > <span data-ttu-id="87082-189">Au moment de la conception, vous pouvez configurer la formule **Supprimé** pour un élément de format, même si aucun contrôle de contenu dans le modèle Word que vous utilisez n’a de balise correspondant au nom d’un élément de format pour lequel la propriété **Supprimé** est configurée.</span><span class="sxs-lookup"><span data-stu-id="87082-189">At design time, you might configure the **Removed** formula for a format element, even though no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span> <span data-ttu-id="87082-190">Lorsque vous validez le format au moment de la conception, vous recevez un [avertissement](er-components-inspections.md#i14) à propos de cette incohérence.</span><span class="sxs-lookup"><span data-stu-id="87082-190">When you validate the format at design time, you receive a [warning](er-components-inspections.md#i14) about this inconsistency.</span></span>
        >
        > <span data-ttu-id="87082-191">Au moment de l’exécution, une exception est levée si aucun contrôle de contenu dans le modèle Word que vous utilisez n’a de balise correspondant au nom d’un élément de format pour lequel la propriété **Supprimé** est configurée.</span><span class="sxs-lookup"><span data-stu-id="87082-191">At runtime, an exception is thrown if no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span>

    4. <span data-ttu-id="87082-192">Sur l’onglet **Mappage**, dans la section **Supprimé**, définissez l’option **Avec parent** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="87082-192">On the **Mapping** tab, in the **Removed** section, set the **With parent** option to **Yes**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="87082-193">Vous devez définir cette option sur **Oui** pour supprimer l’ensemble du tableau Word en tant qu’objet parent de la ligne contenant les détails de la section récapitulative.</span><span class="sxs-lookup"><span data-stu-id="87082-193">You must set this option to **Yes** to remove the whole Word table as the parent object of the row that holds the summary section details.</span></span> <span data-ttu-id="87082-194">Si vous définissez cette option sur **Non**, la ligne d’en-tête de section reste dans le document généré.</span><span class="sxs-lookup"><span data-stu-id="87082-194">If you set this option to **No**, the section header row remains in the generated document.</span></span>

9. <span data-ttu-id="87082-195">Sélectionnez **Enregistrer** pour enregistrer les modifications dans le format modifiable.</span><span class="sxs-lookup"><span data-stu-id="87082-195">Select **Save** to save your changes to the editable format.</span></span>

    ![Sortie générée au format Word](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a><span data-ttu-id="87082-197">Exécuter le format modifié pour créer une sortie Word</span><span class="sxs-lookup"><span data-stu-id="87082-197">Run the modified format to create Word output</span></span>

1. <span data-ttu-id="87082-198">Accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements**.</span><span class="sxs-lookup"><span data-stu-id="87082-198">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="87082-199">Sélectionnez le journal des paiements que vous avez créé, puis sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="87082-199">Select the payment journal that you created, and then select **Lines**.</span></span>
3. <span data-ttu-id="87082-200">Sur la page **Paiements fournisseur**, sélectionnez toutes les lignes, puis sélectionnez **Statut de paiement** \> **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="87082-200">On the **Vendor payments** page, select all the rows, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="87082-201">Sélectionnez **Générer des paiements**.</span><span class="sxs-lookup"><span data-stu-id="87082-201">Select **Generate payments**.</span></span>
5. <span data-ttu-id="87082-202">Dans le champ **Mode de paiement**, sélectionnez **Électronique**.</span><span class="sxs-lookup"><span data-stu-id="87082-202">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="87082-203">Dans le champ **Compte bancaire**, sélectionnez **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="87082-203">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="87082-204">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87082-204">Select **OK**.</span></span>
8. <span data-ttu-id="87082-205">Dans la boîte de dialogue **Paramètres de génération d’états électroniques**, dans le champ **Supprimer la section récapitulative**, sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="87082-205">In the **Electronic report parameters** dialog box, in the **Suppress summary section** field, select **Yes**.</span></span>
9. <span data-ttu-id="87082-206">Sélectionnez **OK** et analysez la sortie générée.</span><span class="sxs-lookup"><span data-stu-id="87082-206">Select **OK**, and analyze the generated output.</span></span>

    ![Sortie générée au format Word](./media/er-design-configuration-word-suppress-controls-image4.gif)

    <span data-ttu-id="87082-208">Notez que la sortie ne contient pas la section récapitulative, car elle a été supprimée.</span><span class="sxs-lookup"><span data-stu-id="87082-208">Notice that the output doesn't contain the summary section, because it has been suppressed.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="87082-209">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="87082-209">Additional resources</span></span>

- [<span data-ttu-id="87082-210">Concevoir une configuration pour générer des états au format OPENXML</span><span class="sxs-lookup"><span data-stu-id="87082-210">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="87082-211">Concevoir une configuration des états électroniques pour générer des états au format Word</span><span class="sxs-lookup"><span data-stu-id="87082-211">Design a new ER configuration to generate reports in Word format</span></span>](er-design-configuration-word.md)
- [<span data-ttu-id="87082-212">Réutiliser les configurations des états électroniques avec des modèles Excel pour générer des rapports au format Word</span><span class="sxs-lookup"><span data-stu-id="87082-212">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)
- [<span data-ttu-id="87082-213">Inspectez le composant ER configuré pour éviter les problèmes d’exécution</span><span class="sxs-lookup"><span data-stu-id="87082-213">Inspect the configured ER component to prevent runtime issues</span></span>](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]