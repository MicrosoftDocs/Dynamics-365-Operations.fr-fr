---
title: Réutiliser les configurations ER avec des modèles Excel pour générer des rapports au format Word
description: Cette rubrique décrit comment les formats d’état conçus pour générer des états sous forme de classeurs Excel peuvent être configurés pour générer des états sous forme de documents Word.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 413be634e80b87781444e1c1445c78691f4b4b0b
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944290"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a><span data-ttu-id="796ce-103">Réutiliser les configurations ER avec des modèles Excel pour générer des rapports au format Word</span><span class="sxs-lookup"><span data-stu-id="796ce-103">Reuse ER configurations with Excel templates to generate reports in Word format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="796ce-104">Pour générer les rapports comme documents Microsoft Word, vous pouvez [configurer](../er-design-configuration-word.md) un nouveau [format](../general-electronic-reporting.md#FormatComponentOutbound) de [gestion des états électroniques](../general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="796ce-104">To generate reports as Microsoft Word documents, you can [configure](../er-design-configuration-word.md) a new [Electronic reporting (ER)](../general-electronic-reporting.md) [format](../general-electronic-reporting.md#FormatComponentOutbound).</span></span> <span data-ttu-id="796ce-105">Vous pouvez également réutiliser un format de gestion des états électroniques qui a été conçu à l’origine pour générer des états sous forme de classeurs Excel.</span><span class="sxs-lookup"><span data-stu-id="796ce-105">Alternatively, you can reuse an ER format that was originally designed to generate reports as Excel workbooks.</span></span> <span data-ttu-id="796ce-106">Dans ce cas, vous devez remplacer le modèle Excel par un modèle Word.</span><span class="sxs-lookup"><span data-stu-id="796ce-106">In this case, you must replace the Excel template with a Word template.</span></span>

<span data-ttu-id="796ce-107">Les procédures suivantes montrent comment un utilisateur ayant le rôle d’administrateur système ou le rôle de développeur d’états électroniques peut configurer un format de gestion des états électroniques pour générer des rapports sous forme de fichiers Word en réutilisant un format de gestion des états électroniques conçu pour générer des rapports sous forme de fichiers Excel.</span><span class="sxs-lookup"><span data-stu-id="796ce-107">The following procedures show how a user in either the System administrator role or the Electronic reporting developer role can configure an ER format to generate reports as Word files by reusing an ER format that was designed to generate reports as Excel files.</span></span>

<span data-ttu-id="796ce-108">Ces procédures peuvent être effectuées dans la société GBSI.</span><span class="sxs-lookup"><span data-stu-id="796ce-108">These procedures can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="796ce-109">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="796ce-109">Prerequisites</span></span>

<span data-ttu-id="796ce-110">Pour exécuter ces procédures, vous devez tout d’abord suivre les étapes du guide de tâches [Concevoir une configuration pour générer des états au format OPENXML](er-design-reports-openxml-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="796ce-110">To complete these procedures, you must first follow the steps in the [Design a configuration for generating reports in OPENXML format](er-design-reports-openxml-2016-11.md) task guide.</span></span>

<span data-ttu-id="796ce-111">Vous devez également télécharger et enregistrer localement les modèles suivants pour l’exemple d’état :</span><span class="sxs-lookup"><span data-stu-id="796ce-111">You must also download and locally save the following templates for the sample report:</span></span>

- [<span data-ttu-id="796ce-112">Modèle d’état de paiement (SampleVendPaymDocReport.docx)</span><span class="sxs-lookup"><span data-stu-id="796ce-112">Template of Payment Report (SampleVendPaymDocReport.docx)</span></span>](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [<span data-ttu-id="796ce-113">Modèle lié d’état de paiement (SampleVendPaymDocReportBounded.docx)</span><span class="sxs-lookup"><span data-stu-id="796ce-113">Bounded Template of Payment Report (SampleVendPaymDocReportBounded.docx)</span></span>](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

<span data-ttu-id="796ce-114">Ces procédures concernent une fonctionnalité qui a été ajoutée dans Dynamics 365 for Operations version 1611 (novembre 2016).</span><span class="sxs-lookup"><span data-stu-id="796ce-114">These procedures are for a feature that was added in Dynamics 365 for Operations version 1611 (November 2016).</span></span>

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="796ce-115">Sélectionnez la configuration d’états électroniques existante</span><span class="sxs-lookup"><span data-stu-id="796ce-115">Select the existing ER report configuration</span></span>

1. <span data-ttu-id="796ce-116">Dans Dynamics 365 Finance, accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="796ce-116">In Dynamics 365 Finance, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="796ce-117">Assurez-vous que le fournisseur de la configuration **Litware, Inc.** est sélectionné comme **Actif**.</span><span class="sxs-lookup"><span data-stu-id="796ce-117">Make sure that the **Litware, Inc.** configuration provider is selected as **Active**.</span></span> <span data-ttu-id="796ce-118">Si ce n’est pas le cas, suivez les étapes du guide de tâche [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="796ce-118">If it isn't, follow the steps in the [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) task guide.</span></span>
3. <span data-ttu-id="796ce-119">Sélectionnez **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="796ce-119">Select **Reporting configurations**.</span></span> <span data-ttu-id="796ce-120">Vous réutiliserez la configuration pour la gestion des états électroniques existante conçue pour générer la sortie d’état au format OPENXML.</span><span class="sxs-lookup"><span data-stu-id="796ce-120">You will reuse the existing ER configuration that was designed to generate the report output in OPENXML format.</span></span>
4. <span data-ttu-id="796ce-121">Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de paiement**, puis sélectionnez **Exemple d’état sur les feuilles de calcul**.</span><span class="sxs-lookup"><span data-stu-id="796ce-121">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and select **Sample worksheet report**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="796ce-122">La version provisoire du format pour la gestion des états électroniques sélectionnés peut être modifiée dans l’organisateur **Versions**.</span><span class="sxs-lookup"><span data-stu-id="796ce-122">The draft version of the selected ER format can be edited on the **Versions** FastTab.</span></span>

5. <span data-ttu-id="796ce-123">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="796ce-123">Select **Designer**.</span></span>
6. <span data-ttu-id="796ce-124">Sur la page **Concepteur de format**, notez que le titre de l’élément de format racine indique qu’un modèle Excel est actuellement utilisé.</span><span class="sxs-lookup"><span data-stu-id="796ce-124">On the **Format designer** page, notice that the title of the root format element indicates that an Excel template is currently used.</span></span>

![Sélectionner la configuration existante](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a><span data-ttu-id="796ce-126">Consulter le modèle Word téléchargé</span><span class="sxs-lookup"><span data-stu-id="796ce-126">Review the downloaded Word template</span></span>

1. <span data-ttu-id="796ce-127">Dans l’application de bureau Word, ouvrez le fichier de modèle **SampleVendPaymDocReport.docx** que vous avez téléchargé précédemment.</span><span class="sxs-lookup"><span data-stu-id="796ce-127">In the Word desktop application, open the **SampleVendPaymDocReport.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="796ce-128">Vérifiez que le modèle ne contient que la mise en page du document que vous souhaitez générer comme sortie de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="796ce-128">Verify that the template contains only the layout of the document that you want to generate as ER output.</span></span>

![Disposition du modèle Word dans l’application de bureau](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a><span data-ttu-id="796ce-130">Remplacer le modèle Excel par le modèle Word et ajouter une partie XML personnalisée</span><span class="sxs-lookup"><span data-stu-id="796ce-130">Replace the Excel template with the Word template and add a custom XML part</span></span>

<span data-ttu-id="796ce-131">Actuellement, le document Excel est utilisé comme modèle pour générer la sortie au format OPENXML.</span><span class="sxs-lookup"><span data-stu-id="796ce-131">Currently, the Excel document is used as a template to generate the output in OPENXML format.</span></span> <span data-ttu-id="796ce-132">Vous remplacerez ce modèle par le modèle Word SampleVendPaymDocReport.docx que vous avez téléchargé antérieurement.</span><span class="sxs-lookup"><span data-stu-id="796ce-132">You will replace this template with the SampleVendPaymDocReport.docx Word template file that you downloaded earlier.</span></span> <span data-ttu-id="796ce-133">Vous développerez également le modèle Word en ajoutant une partie XML personnalisée.</span><span class="sxs-lookup"><span data-stu-id="796ce-133">You will also extend the Word template by adding a custom XML part.</span></span>

1. <span data-ttu-id="796ce-134">Dans Finance, sur la page **Concepteur de format**, dans l’onglet **Format**, sélectionnez **Documents joints**.</span><span class="sxs-lookup"><span data-stu-id="796ce-134">In Finance, on the **Format designer** page, on the **Format** tab, select **Attachments**.</span></span>
2. <span data-ttu-id="796ce-135">Sur la page **Documents joints**, sélectionnez **Supprimer** pour supprimer le modèle Excel existant.</span><span class="sxs-lookup"><span data-stu-id="796ce-135">On the **Attachments** page, select **Delete** to remove the existing Excel template.</span></span> <span data-ttu-id="796ce-136">Sélectionnez **Oui** pour confirmer la modification.</span><span class="sxs-lookup"><span data-stu-id="796ce-136">Select **Yes** to confirm the change.</span></span>
3. <span data-ttu-id="796ce-137">Sélectionnez **Nouveau** \> **Fichier**.</span><span class="sxs-lookup"><span data-stu-id="796ce-137">Select **New** \> **File**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="796ce-138">Vous devez sélectionner un type de document qui a été [configuré](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) dans les paramètres de gestion des états électroniques pour stocker les modèles aux formats de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="796ce-138">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

4. <span data-ttu-id="796ce-139">Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **SampleVendPaymDocReport.docx** que vous avez téléchargé précédemment.</span><span class="sxs-lookup"><span data-stu-id="796ce-139">Select **Browse**, and then browse to and select the **SampleVendPaymDocReport.docx** file that you downloaded earlier.</span></span>
5. <span data-ttu-id="796ce-140">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="796ce-140">Select **OK**.</span></span>
6. <span data-ttu-id="796ce-141">Fermez la page **Pièces jointes**.</span><span class="sxs-lookup"><span data-stu-id="796ce-141">Close the **Attachments** page.</span></span>
7. <span data-ttu-id="796ce-142">Sur la page **Concepteur de format**, dans le champ **Modèle**, entrez ou sélectionnez le fichier **SampleVendPaymDocReport.docx** pour utiliser ce modèle Word au lieu du modèle Excel précédemment utilisé.</span><span class="sxs-lookup"><span data-stu-id="796ce-142">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReport.docx** file to use that Word template instead of the Excel template that was previously used.</span></span>
8. <span data-ttu-id="796ce-143">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="796ce-143">Select **Save**.</span></span>

    <span data-ttu-id="796ce-144">Outre les modifications de configuration de stockage, l’action **Enregistrer** met également à jour le modèle Word joint.</span><span class="sxs-lookup"><span data-stu-id="796ce-144">In addition to storing configuration changes, the **Save** action updates the attached Word template.</span></span> <span data-ttu-id="796ce-145">La structure hiérarchique du format conçu est ajoutée au document Word joint en tant que nouvelle partie XML personnalisée nommée **État**.</span><span class="sxs-lookup"><span data-stu-id="796ce-145">The hierarchical structure of the designed format is added to the attached Word document as a new custom XML part that is named **Report**.</span></span> <span data-ttu-id="796ce-146">Le modèle Word joint contient non seulement la mise en page du document que nous souhaitons générer comme sortie de gestion des états électroniques, mais également la structure des données que la gestion des états électroniques renseignera dans ce modèle au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="796ce-146">The attached Word template contains the layout of the document that will be generated as ER output and the structure of data that ER will enter in that template at runtime.</span></span>

9. <span data-ttu-id="796ce-147">Notez que le titre de l’élément de format racine indique qu’un modèle Word est actuellement utilisé.</span><span class="sxs-lookup"><span data-stu-id="796ce-147">Notice that the title of the root format element indicates that a Word template is currently used.</span></span>

    ![Remplacer le modèle Excel par le modèle Word et ajouter une partie XML personnalisée](../media/er-design-configuration-word-2016-11-image03.gif)

10. <span data-ttu-id="796ce-149">Dans l’onglet **Format**, sélectionnez **Pièces jointes**.</span><span class="sxs-lookup"><span data-stu-id="796ce-149">On the **Format** tab, select **Attachments**.</span></span>

<span data-ttu-id="796ce-150">Vous pouvez maintenant mettre en correspondance des éléments de la partie XML personnalisée **État** et des contrôles de contenu du document Word.</span><span class="sxs-lookup"><span data-stu-id="796ce-150">You can now map the elements of the **Report** custom XML part to the content controls of the Word document.</span></span>

<span data-ttu-id="796ce-151">Si vous connaissez bien le processus de conception des documents Word comme formulaires qui contiennent les [contrôles de contenu](/office/client-developer/word/content-controls-in-word) mis en correspondance avec les éléments des [pièces XML personnalisées](/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), exécutez toutes les étapes de la prochaine procédure pour créer le document.</span><span class="sxs-lookup"><span data-stu-id="796ce-151">If you're familiar with the process of designing Word documents as forms that contain [content controls](/office/client-developer/word/content-controls-in-word) that are mapped to elements of [custom XML parts](/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), complete all steps in the next procedure to create the document.</span></span> <span data-ttu-id="796ce-152">Pour plus de détails, voir [Créer des formulaires à remplir ou imprimer dans Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span><span class="sxs-lookup"><span data-stu-id="796ce-152">For more information, see [Create forms that users complete or print in Words](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span></span> <span data-ttu-id="796ce-153">Sinon, passez à la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="796ce-153">Otherwise, skip the next procedure.</span></span>

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a><span data-ttu-id="796ce-154">Obtenir un document Word contenant une partie XML personnalisée et effectuer un mappage de données</span><span class="sxs-lookup"><span data-stu-id="796ce-154">Get a Word document that has a custom XML part and do data mapping</span></span>

1. <span data-ttu-id="796ce-155">Dans Finance, sur la page **Documents joints**, sélectionnez **Ouvrir** pour télécharger le modèle sélectionné depuis Finance et le stocker localement sous forme de document Word.</span><span class="sxs-lookup"><span data-stu-id="796ce-155">In Finance, on the **Attachments** page, select **Open** to download the selected template from Finance and store it locally as a Word document.</span></span>
3. <span data-ttu-id="796ce-156">Dans l’application de bureau Word, ouvrez le document que vous venez de télécharger.</span><span class="sxs-lookup"><span data-stu-id="796ce-156">In the Word desktop application, open the document that you just downloaded.</span></span>
4. <span data-ttu-id="796ce-157">Dans l’onglet **Développeur**, sélectionnez **Volet de mise en correspondance XML**.</span><span class="sxs-lookup"><span data-stu-id="796ce-157">On the **Developer** tab, select **XML Mapping Pane**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="796ce-158">Si l’onglet **Développeur** n’apparaît pas sur le ruban, personnalisez le ruban pour l’ajouter.</span><span class="sxs-lookup"><span data-stu-id="796ce-158">If the **Developer** tab doesn't appear on the ribbon, customize the ribbon to add it.</span></span>

5. <span data-ttu-id="796ce-159">Dans le volet **Mise en correspondance XML**, dans le champ **Partie XML personnalisée**, sélectionnez la partie XML personnalisée **État**.</span><span class="sxs-lookup"><span data-stu-id="796ce-159">In the **XML Mapping** pane, in the **Custom XML Part** field, select the **Report** custom XML part.</span></span>
6. <span data-ttu-id="796ce-160">Mettez en correspondance des éléments de la partie XML personnalisée **État** sélectionnée et des contrôles de contenu du document Word.</span><span class="sxs-lookup"><span data-stu-id="796ce-160">Map the elements of the selected **Report** custom XML part and the content controls of the Word document.</span></span>
7. <span data-ttu-id="796ce-161">Enregistrez le document Word mis à jour localement sous **SampleVendPaymDocReportBounded.docx**.</span><span class="sxs-lookup"><span data-stu-id="796ce-161">Save the updated Word document locally as **SampleVendPaymDocReportBounded.docx**.</span></span>

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="796ce-162">Examiner le modèle Word dans lequel la partie XML personnalisée est mappée aux contrôles de contenu</span><span class="sxs-lookup"><span data-stu-id="796ce-162">Review the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="796ce-163">Dans l’application de bureau Word, ouvrez le fichier de modèle **SampleVendPaymDocReportBounded.docx**.</span><span class="sxs-lookup"><span data-stu-id="796ce-163">In the Word desktop application, open the **SampleVendPaymDocReportBounded.docx** template file.</span></span>
2. <span data-ttu-id="796ce-164">Vérifiez que le modèle contient la mise en page du document que vous souhaitez générer comme sortie de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="796ce-164">Verify that the template contains the layout of the document that you want to generate as ER output.</span></span> <span data-ttu-id="796ce-165">Les contrôles de contenu qui sont utilisés comme espaces réservés pour les données que la gestion des états électroniques entrera dans ce modèle lors de l’exécution sont basés sur les mappages configurés entre les éléments de la partie XML personnalisée **État** et les contrôles de contenu du document Word.</span><span class="sxs-lookup"><span data-stu-id="796ce-165">The content controls that are used as placeholders for data that ER will enter in this template at runtime are based on the mappings that are configured between elements of the **Report** custom XML part and the content controls of the Word document.</span></span>

![Aperçu du modèle Word dans l’application de bureau](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="796ce-167">Charger le modèle Word dans lequel la partie XML personnalisée est mappée aux contrôles de contenu</span><span class="sxs-lookup"><span data-stu-id="796ce-167">Upload the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="796ce-168">Dans Finance, sur la page **Documents joints**, sélectionnez **Supprimer** pour supprimer le modèle Word qui n’a pas de mappage entre les éléments de la partie XML personnalisée **État** et les contrôles de contenu.</span><span class="sxs-lookup"><span data-stu-id="796ce-168">In Finance, on the **Attachments** page, select **Delete** to remove the Word template that has no mappings between elements of the **Report** custom XML part and content controls.</span></span> <span data-ttu-id="796ce-169">Sélectionnez **Oui** pour confirmer la modification.</span><span class="sxs-lookup"><span data-stu-id="796ce-169">Select **Yes** to confirm the change.</span></span>
2. <span data-ttu-id="796ce-170">Sélectionnez **Nouveau** \> **Fichier** pour ajouter un nouveau fichier de modèle contenant des mappages entre les éléments de la partie XML personnalisée **État** et les contrôles de contenu.</span><span class="sxs-lookup"><span data-stu-id="796ce-170">Select **New** \> **File** to add a new template file that contains mappings between elements of the **Report** custom XML part and content controls.</span></span>

    > [!NOTE]
    > <span data-ttu-id="796ce-171">Vous devez sélectionner un type de document qui a été [configuré](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) dans les paramètres de gestion des états électroniques pour stocker les modèles aux formats de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="796ce-171">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

3. <span data-ttu-id="796ce-172">Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **SampleVendPaymDocReportBounded.docx** que vous avez téléchargé ou préparé en suivant la procédure dans la section [Obtenir un Word avec une partie XML personnalisée pour faire le mappage de données](#get-word-doc).</span><span class="sxs-lookup"><span data-stu-id="796ce-172">Select **Browse**, and then browse to and select the **SampleVendPaymDocReportBounded.docx** file that you downloaded or prepared by completing the procedure in the [Get a Word that has a custom XML part to do data mapping](#get-word-doc) section.</span></span>
4. <span data-ttu-id="796ce-173">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="796ce-173">Select **OK**.</span></span>
5. <span data-ttu-id="796ce-174">Fermez la page **Pièces jointes**.</span><span class="sxs-lookup"><span data-stu-id="796ce-174">Close the **Attachments** page.</span></span>
6. <span data-ttu-id="796ce-175">Sur la page **Concepteur de format**, dans le champ **Modèle**, sélectionnez le document que vous venez de télécharger.</span><span class="sxs-lookup"><span data-stu-id="796ce-175">On the **Format designer** page, in the **Template** field, select the document that you just downloaded.</span></span>
7. <span data-ttu-id="796ce-176">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="796ce-176">Select **Save**.</span></span>
8. <span data-ttu-id="796ce-177">Fermez la page **Concepteur de format**.</span><span class="sxs-lookup"><span data-stu-id="796ce-177">Close the **Format designer** page.</span></span>

## <a name="mark-the-configured-format-as-runnable"></a><span data-ttu-id="796ce-178">Marquer le format configuré comme exécutable</span><span class="sxs-lookup"><span data-stu-id="796ce-178">Mark the configured format as runnable</span></span>

<span data-ttu-id="796ce-179">Pour exécuter la version brouillon du format modifiable, vous devez le rendre [exécutable](../er-quick-start2-customize-report.md#MarkFormatRunnable).</span><span class="sxs-lookup"><span data-stu-id="796ce-179">To run the draft version of the editable format, you must make it [runnable](../er-quick-start2-customize-report.md#MarkFormatRunnable).</span></span>

1. <span data-ttu-id="796ce-180">Dans Finance, sur la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="796ce-180">In Finance, on the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
2. <span data-ttu-id="796ce-181">Dans la boîte de dialogue **Paramètres utilisateur**, définissez l’option **Paramètres d’exécution** sur **Oui**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="796ce-181">In the **User parameters** dialog box, set the **Run settings** option to **Yes**, and then select **OK**.</span></span>
3. <span data-ttu-id="796ce-182">Sélectionnez **Modifier** pour rendre la page active modifiable, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="796ce-182">Select **Edit** to make the current page editable, as required.</span></span>
4. <span data-ttu-id="796ce-183">Pour la configuration **Exemple d’état sur les feuilles de calcul** actuellement sélectionnée, définissez l’option **Exécuter le brouillon** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="796ce-183">For the currently selected **Sample worksheet report** configuration, set the **Run Draft** option to **Yes**.</span></span>
5. <span data-ttu-id="796ce-184">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="796ce-184">Select **Save**.</span></span>

## <a name="run-the-format-to-create-output-in-word-format"></a><span data-ttu-id="796ce-185">Exécuter le format pour créer une sortie au format Word</span><span class="sxs-lookup"><span data-stu-id="796ce-185">Run the format to create output in Word format</span></span>

1. <span data-ttu-id="796ce-186">Dans Finance, accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements**.</span><span class="sxs-lookup"><span data-stu-id="796ce-186">In Finance, go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="796ce-187">Dans un journal des paiements que vous avez saisi précédemment, sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="796ce-187">In a payment journal that you entered earlier, select **Lines**.</span></span>
3. <span data-ttu-id="796ce-188">Sur la page **Paiements fournisseur**, sélectionnez toutes les lignes de la grille.</span><span class="sxs-lookup"><span data-stu-id="796ce-188">On the **Vendor payments** page, select all rows in the grid.</span></span>
4. <span data-ttu-id="796ce-189">Sélectionnez **Statut de paiement** \> **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="796ce-189">Select **Payment status** \> **None**.</span></span>

    ![Paiements pour traitement sur la page Paiements fournisseur](../media/er-design-configuration-word-2016-11-image05.png)

5. <span data-ttu-id="796ce-191">Dans le volet Actions, sélectionnez **Générer les paiements**.</span><span class="sxs-lookup"><span data-stu-id="796ce-191">On the Action Pane, select **Generate payments**.</span></span>
6. <span data-ttu-id="796ce-192">Dans la boîte de dialogue qui s’affiche, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="796ce-192">In the dialog box that appears, follow these steps:</span></span>

    1. <span data-ttu-id="796ce-193">Dans le champ **Mode de paiement**, sélectionnez **Électronique**.</span><span class="sxs-lookup"><span data-stu-id="796ce-193">In the **Method of payment** field, select **Electronic**.</span></span>
    2. <span data-ttu-id="796ce-194">Dans le champ **Compte bancaire**, sélectionnez **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="796ce-194">In the **Bank account** field, select **GBSI OPER**.</span></span>
    3. <span data-ttu-id="796ce-195">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="796ce-195">Select **OK**.</span></span>

7. <span data-ttu-id="796ce-196">Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="796ce-196">In the **Electronic report parameters** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="796ce-197">La sortie générée se présente sous le format Word et contient les détails des paiements traités.</span><span class="sxs-lookup"><span data-stu-id="796ce-197">The generated output is presented in Word format and contains the details of the processed payments.</span></span> <span data-ttu-id="796ce-198">Analysez la sortie générée.</span><span class="sxs-lookup"><span data-stu-id="796ce-198">Analyze the generated output.</span></span>

    ![Sortie générée au format Word](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a><span data-ttu-id="796ce-200">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="796ce-200">Additional resources</span></span>

- [<span data-ttu-id="796ce-201">Créer une configuration de gestion des états électroniques pour générer des états au format Word</span><span class="sxs-lookup"><span data-stu-id="796ce-201">Design a new ER configuration to generate reports in Word format</span></span>](../er-design-configuration-word.md)
- [<span data-ttu-id="796ce-202">Intégrer des images et des formes dans les documents que vous générez ER à l’aide de la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="796ce-202">Embed images and shapes in documents that you generate by using ER</span></span>](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
