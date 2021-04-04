---
title: Améliorations des résultats de suivi des rapports de gestion des états électroniques générés et comparaisons avec les valeurs de référence
description: Cette rubrique décrit les améliorations apportées à la fonctionnalité de référence pour la gestion des états électroniques dans Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (juin 2019).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 1579a0bb0dcf21ae16a54969e57ca88301041076
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568947"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a><span data-ttu-id="a9b0b-103">Améliorations des résultats de suivi des rapports de gestion des états électroniques générés et comparaisons avec les valeurs de référence</span><span class="sxs-lookup"><span data-stu-id="a9b0b-103">Improvements in tracing the results of generated ER reports and comparing them with baseline values</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a9b0b-104">Cette rubrique décrit le premier ensemble d’améliorations apportées à la fonction de référence de la structure de génération d’états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="a9b0b-104">This topic describes the first set of improvements that have been made to the baseline feature of the Electronic reporting (ER) framework.</span></span> <span data-ttu-id="a9b0b-105">Ces améliorations sont disponibles dans Microsoft Dynamics 365 for Finance and Operations 10.0.3 (juin 2019) et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-105">These improvements are available in Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (June 2019) and later.</span></span>

## <a name="automate-the-setting-of-baseline-rules"></a><span data-ttu-id="a9b0b-106">Automatisation du paramétrage des règles de référence</span><span class="sxs-lookup"><span data-stu-id="a9b0b-106">Automate the setting of baseline rules</span></span>

<span data-ttu-id="a9b0b-107">La rubrique [Suivre les résultats de rapport généré et les comparer avec des valeurs de base](er-trace-reports-compare-baseline.md) explique comment configurer la structure ER pour collecter les informations sur les exécutions de format ER et évaluer les résultats de ces exécutions.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-107">The [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic explains how to configure the ER framework to collect information about ER format executions and evaluate the results of those executions.</span></span> <span data-ttu-id="a9b0b-108">L’exemple de cette rubrique présente les étapes à accomplir.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-108">The example in this topic shows the steps that must be completed.</span></span>

<span data-ttu-id="a9b0b-109">En voici quelques-unes :</span><span class="sxs-lookup"><span data-stu-id="a9b0b-109">Here are some of the steps:</span></span>

- <span data-ttu-id="a9b0b-110">Exécutez un format ER pour générer un fichier de sortie, et enregistrez le fichier localement.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-110">Run an ER format to generate an outbound file, and store the file locally.</span></span>
- <span data-ttu-id="a9b0b-111">Ajoutez le fichier enregistré localement comme pièce jointe à la référence ajoutée à un format ER.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-111">Add the locally stored file as an attachment of the baseline that was added for an ER format.</span></span>
- <span data-ttu-id="a9b0b-112">Configurez la règle de référence pour la référence ajoutée.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-112">Configure the baseline rule for the added baseline.</span></span> <span data-ttu-id="a9b0b-113">Cette configuration inclut les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a9b0b-113">This configuration includes the following steps:</span></span>

    - <span data-ttu-id="a9b0b-114">Spécifiez un élément de format ER utilisé pour générer un fichier de sortie.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-114">Specify an ER format element that is used to generate an outbound file.</span></span>
    - <span data-ttu-id="a9b0b-115">Sélectionnez la pièce jointe qui renvoie au fichier de sortie généré.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-115">Select the attachment that refers to the generated outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="a9b0b-116">Ces étapes doivent être effectuées manuellement, même si les fonctionnalités ER permettent de les automatiser.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-116">These steps must be done manually, even though the new ER capabilities enable them to be automated.</span></span> <span data-ttu-id="a9b0b-117">Pour en savoir plus sur cette fonction, réalisez l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-117">To learn more about this feature, complete the following example.</span></span>

## <a name="example-automate-the-setting-of-baseline-rules"></a><span data-ttu-id="a9b0b-118">Exemple : Automatisation du paramétrage des règles de référence</span><span class="sxs-lookup"><span data-stu-id="a9b0b-118">Example: Automate the setting of baseline rules</span></span>

<span data-ttu-id="a9b0b-119">Pour accomplir les étapes de cet exemple, vous devez d’abord réaliser les étapes de la rubrique [Suivre les résultats de rapport généré et les comparer avec des valeurs de base](er-trace-reports-compare-baseline.md), jusqu’à la section « Ajouter une nouvelle référence à un format ER défini ».</span><span class="sxs-lookup"><span data-stu-id="a9b0b-119">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, up through the "Add a new baseline for a designed ER format" section.</span></span>

### <a name="review-added-baseline"></a><span data-ttu-id="a9b0b-120">Examiner la référence ajoutée</span><span class="sxs-lookup"><span data-stu-id="a9b0b-120">Review added baseline</span></span>

1. <span data-ttu-id="a9b0b-121">Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-121">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="a9b0b-122">Sélectionnez **Références**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-122">Select **Baselines**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a9b0b-123">Le bouton **Références** du volet Actions n’est disponible que lorsque le paramètre utilisateur ER **Exécuter en mode de débogage** est activé pour la société en cours.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-123">The **Baselines** button on the Action Pane is available only when the **Run in debug mode** ER user parameter is turned on for the current company.</span></span>

<span data-ttu-id="a9b0b-124">La référence a été ajoutée pour le format **Format pour l’apprentissage des références ER** sélectionné, mais les règles de la référence n’ont pas encore été ajoutées à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-124">The baseline has been added for the selected **Format to learn ER baselines** format, but the baseline rules haven't yet been added for this baseline.</span></span>

<span data-ttu-id="a9b0b-125">![Page Références de base du format de gestion des états électroniques, aucune règle configurée](media/GER-BaselineSample-AddBaseline2.PNG "Capture d’écran de la page Références de base de la gestion des états électroniques")</span><span class="sxs-lookup"><span data-stu-id="a9b0b-125">![Electronic reporting format baselines page, no rules yet](media/GER-BaselineSample-AddBaseline2.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="a9b0b-126">Établir une nouvelle règle de référence</span><span class="sxs-lookup"><span data-stu-id="a9b0b-126">Make a new baseline rule</span></span>

1. <span data-ttu-id="a9b0b-127">Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-127">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="a9b0b-128">Dans l’arborescence, développez **Modèle d’apprentissage des références ER**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-128">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="a9b0b-129">Dans l’arborescence, sélectionnez **Modèle d’apprentissage des références ER\\Format pour l’apprentissage des références ER**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-129">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="a9b0b-130">Dans l’organisateur **Versions**, sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-130">On the **Versions** FastTab, select **Run**.</span></span>
5. <span data-ttu-id="a9b0b-131">Dans le champ **Entrer l’identifiant**, entrez **1**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-131">In the **Enter Id** field, enter **1**.</span></span>
6. <span data-ttu-id="a9b0b-132">Définissez l’option **Créer des fichiers de référence** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-132">Set the **Make baseline files** option to **Yes**.</span></span>
7. <span data-ttu-id="a9b0b-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-133">Select **OK**.</span></span>
8. <span data-ttu-id="a9b0b-134">Sélectionnez **Références**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-134">Select **Baselines**.</span></span>

    <span data-ttu-id="a9b0b-135">![Références de base de la gestion des états électroniques, références de base sélectionnées](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Capture d’écran de la page Références de base de la gestion des états électroniques")</span><span class="sxs-lookup"><span data-stu-id="a9b0b-135">![Electronic reporting format baselines page, baselines selected](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

    <span data-ttu-id="a9b0b-136">Le fichier de sortie généré a été associé automatiquement à la référence du format ER exécuté.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-136">The generated outbound file has been automatically attached to the baseline of the executed ER format.</span></span> <span data-ttu-id="a9b0b-137">La règle de référence a été ajoutée automatiquement à cette référence. Elle contient également la référence au fichier joint.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-137">The baseline rule has been automatically added to this baseline and also contains the reference to the attached file.</span></span>

9. <span data-ttu-id="a9b0b-138">Dans le champ **Nom**, entrez **Base de référence 1**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-138">In the **Name** field, enter **Baseline 1**.</span></span>
10. <span data-ttu-id="a9b0b-139">Dans le champ **Masque du nom de fichier**, entrez **.xml**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-139">In the **File name mask** field, enter **.xml**.</span></span>
11. <span data-ttu-id="a9b0b-140">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-140">Select **Save**.</span></span>

### <a name="run-the-format"></a><span data-ttu-id="a9b0b-141">Exécuter le format</span><span class="sxs-lookup"><span data-stu-id="a9b0b-141">Run the format</span></span>

<span data-ttu-id="a9b0b-142">Vous êtes maintenant prêt à accomplir les étapes restantes de l’exemple de la rubrique [Suivre les résultats de rapport généré et les comparer avec des valeurs de base](er-trace-reports-compare-baseline.md), en commençant par la section « Exécuter le format ER défini et examiner le fichier journal pour analyser les résultats ».</span><span class="sxs-lookup"><span data-stu-id="a9b0b-142">You're now ready to complete the remaining steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, starting from the "Run the designed ER format and review the log to analyze the results" section.</span></span>

> [!NOTE]
> <span data-ttu-id="a9b0b-143">Lorsque vous supprimez la règle de référence automatiquement ajoutée dans l’organisateur **Références**, la pièce jointe référencée n’est pas automatiquement supprimée.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-143">When you delete the automatically added baseline rule on the **Baselines** FastTab, the referenced attachment isn't automatically deleted.</span></span>

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="a9b0b-144">Configurez la référence de sorte qu’elle ignore les éléments qui changent en permanence de la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-144">Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="a9b0b-145">Lorsqu’un format ER a été conçu pour contenir des informations qui changent lors de l’exécution du format, celui-ci doit utiliser la fonction de référence ER pour comparer les résultats obtenus avec les valeurs de référence.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-145">When an ER format has been designed to contain information that is changed when the format is run, the format must be required to use the ER baseline feature to compare the generated results with baseline values.</span></span> <span data-ttu-id="a9b0b-146">Par exemple, les informations peuvent être la date et l’heure du traitement, ou l’identificateur unique d’un document généré dans différents formats (identificateur global unique \[GUID\], etc.).</span><span class="sxs-lookup"><span data-stu-id="a9b0b-146">For example, the information might be the processing date and time or the unique identifier of a generated document in different formats (globally unique identifier \[GUID\], and so on).</span></span> <span data-ttu-id="a9b0b-147">Les nouvelles fonctionnalités ER permettent de configurer la règle de référence de manière à ce qu’elle ignore les éléments variables d’un format ER lorsque le format est exécuté dans le but de comparer les valeurs de référence avec celles de l’exécution du format.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-147">The new ER capabilities let you configure the baseline rule so that it ignores changeable elements of an ER format when the format is run with the purpose of comparing baseline values with the results of the format's execution.</span></span> <span data-ttu-id="a9b0b-148">Pour en savoir plus sur cette fonction, réalisez l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-148">To learn more about this feature, complete the following example.</span></span>

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="a9b0b-149">Exemple : Configurer la référence de sorte qu’elle ignore les éléments qui changent en permanence de la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-149">Example: Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="a9b0b-150">Pour accomplir les étapes de cet exemple, vous devez d’abord réaliser les étapes de la rubrique [Suivre les résultats de rapport généré et les comparer avec des valeurs de base](er-trace-reports-compare-baseline.md).</span><span class="sxs-lookup"><span data-stu-id="a9b0b-150">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic.</span></span>

### <a name="modify-a-configured-er-format"></a><span data-ttu-id="a9b0b-151">Modifier un format ER configuré</span><span class="sxs-lookup"><span data-stu-id="a9b0b-151">Modify a configured ER format</span></span>

1. <span data-ttu-id="a9b0b-152">Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-152">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="a9b0b-153">Dans l’arborescence, développez **Modèle d’apprentissage des références ER**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-153">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="a9b0b-154">Dans l’arborescence, sélectionnez **Modèle d’apprentissage des références ER\\Format pour l’apprentissage des références ER**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-154">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="a9b0b-155">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-155">Select **Designer**.</span></span>
5. <span data-ttu-id="a9b0b-156">Dans l’arborescence, sélectionnez **Résultat\\Document**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-156">In the tree, select **Output\\Document**.</span></span>
6. <span data-ttu-id="a9b0b-157">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-157">Select **Add**.</span></span>
7. <span data-ttu-id="a9b0b-158">Dans la boîte de dialogue déroulante, dans l’arborescence, sélectionnez **XML\\Attribut**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-158">In the drop-down dialog box, in the tree, select **XML\\Attribute**.</span></span>
8. <span data-ttu-id="a9b0b-159">Dans le champ **Nom**, entrez **ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-159">In the **Name** field, enter **ProcessingDateTime**.</span></span>
9. <span data-ttu-id="a9b0b-160">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-160">Select **OK**.</span></span>
10. <span data-ttu-id="a9b0b-161">Dans l’onglet **Mise en correspondance**, dans l’arborescence, sélectionnez **Résultat\\Document\\ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-161">On the **Mapping** tab, in the tree, select **Output\\Document\\ProcessingDateTime**.</span></span>
11. <span data-ttu-id="a9b0b-162">Sélectionnez **Modifier la formule**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-162">Select **Edit formula**.</span></span>
12. <span data-ttu-id="a9b0b-163">Dans le champ **Formule**, entrez l’expression suivante : **DATETIMEFORMAT(NOW(), "O")**</span><span class="sxs-lookup"><span data-stu-id="a9b0b-163">In the **Formula** field, enter the following expression: **DATETIMEFORMAT(NOW(), "O")**</span></span>
13. <span data-ttu-id="a9b0b-164">Sélectionnez **Enregistrer**, puis sélectionnez **Test**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-164">Select **Save**, and then select **Test**.</span></span>
14. <span data-ttu-id="a9b0b-165">Sélectionnez **Test** de nouveau pour tester à nouveau l’expression configurée.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-165">Select **Test** again to retest the configured expression.</span></span>

    <span data-ttu-id="a9b0b-166">![Page Concepteur de formule](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Capture d’écran de la page Concepteur de formule")</span><span class="sxs-lookup"><span data-stu-id="a9b0b-166">![Formula designer page](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Screenshot of the Formula designer page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="a9b0b-167">L’onglet **Résultat du test** indique que l’expression configurée retourne une valeur différente de date et d’heure chaque fois qu’elle a été appelée.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-167">The **Test result** tab shows that the configured expression returns a different date and time value whenever it's called.</span></span>

15. <span data-ttu-id="a9b0b-168">Fermez la page du **Concepteur de formule**, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-168">Close the **Formula designer** page, and then select **Save**.</span></span>

    <span data-ttu-id="a9b0b-169">![Page Concepteur de formats](media/GER-BaselineSample-FormatMappingDesign2.PNG "Capture d’écran de la page Concepteur de format")</span><span class="sxs-lookup"><span data-stu-id="a9b0b-169">![Format designer page](media/GER-BaselineSample-FormatMappingDesign2.PNG "Screenshot of the Format designer page")</span></span>

16. <span data-ttu-id="a9b0b-170">Fermez la page **Concepteur de format**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-170">Close the **Format designer** page.</span></span>

### <a name="remove-an-existing-baseline-rule"></a><span data-ttu-id="a9b0b-171">Supprimer une règle de référence existante</span><span class="sxs-lookup"><span data-stu-id="a9b0b-171">Remove an existing baseline rule</span></span>

1. <span data-ttu-id="a9b0b-172">Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-172">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="a9b0b-173">Sélectionnez **Références**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-173">Select **Baselines**.</span></span>
3. <span data-ttu-id="a9b0b-174">Dans la liste des références, sélectionnez celle qui a été configurée pour le format **Format pour l’apprentissage des références ER**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-174">In the list of baselines, select the baseline that is configured for the **Format to learn ER baselines** format.</span></span>
4. <span data-ttu-id="a9b0b-175">Dans l’organisateur **Références**, sélectionnez **Supprimer** pour supprimer la règle de référence que vous avez définie précédemment.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-175">On the **Baselines** FastTab, select **Delete** to remove the baseline rule that you configured earlier.</span></span>

<span data-ttu-id="a9b0b-176">![Page Références de base du format de gestion des états électroniques, supprimée](media/GER-BaselineSample-AddBaseline3.PNG "Capture d’écran de la page Références de base de la gestion des états électroniques")</span><span class="sxs-lookup"><span data-stu-id="a9b0b-176">![Electronic reporting format baselines page, deleted](media/GER-BaselineSample-AddBaseline3.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="define-replacements-for-bindings-of-designed-er-format"></a><span data-ttu-id="a9b0b-177">Définir les substitutions de liaisons du format ER défini</span><span class="sxs-lookup"><span data-stu-id="a9b0b-177">Define replacements for bindings of designed ER format</span></span>

1. <span data-ttu-id="a9b0b-178">Dans la page **Configurations**, sous l’organisateur **Remplacements**, sélectionnez **Sélectionner des composants**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-178">On the **Configurations** page, on the **Replacements** FastTab, select **Select components**.</span></span>
2. <span data-ttu-id="a9b0b-179">Dans l’arborescence des composants de format, développez **Résultat**, développez **Résultat\\Document**, puis activez la case à cocher pour **Résultat\\Document\\ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-179">In the format components tree, expand **Output**, expand **Output\\Document**, and then select the check box for **Output\\Document\\ProcessingDateTime**.</span></span>
3. <span data-ttu-id="a9b0b-180">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-180">Select **OK**.</span></span>

<span data-ttu-id="a9b0b-181">![Page Références de base du format de gestion des états électroniques, composants](media/GER-BaselineSample-AddBaseline4.PNG "Capture d’écran de la page Références de base de la gestion des états électroniques")</span><span class="sxs-lookup"><span data-stu-id="a9b0b-181">![Electronic reporting format baselines page, components](media/GER-BaselineSample-AddBaseline4.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

<span data-ttu-id="a9b0b-182">Le composant du format ER sélectionné a été ajouté à la liste des composants dans l’organisateur **Remplacements**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-182">The selected ER format component has been added to the list of components on the **Replacements** FastTab.</span></span> <span data-ttu-id="a9b0b-183">Lorsque le format ER de référence est exécuté en mode de débogage, la liaison du format pour chaque composant est remplacée par la liaison affichée dans la colonne **Liaison**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-183">When the base ER format is run in debug mode, the format's binding for each component will be replaced by the binding that is shown in the **Binding** column.</span></span> <span data-ttu-id="a9b0b-184">Pour modifier la liaison par défaut pour un composant répertorié dans l’organisateur **Remplacements**, sélectionnez **Éditer**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-184">To change the default binding for a component that is listed on the **Replacements** FastTab, select **Edit**.</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="a9b0b-185">Établir une nouvelle règle de référence</span><span class="sxs-lookup"><span data-stu-id="a9b0b-185">Make a new baseline rule</span></span>

<span data-ttu-id="a9b0b-186">Suivez les étapes de la section « Exemple :Automatisation du paramétrage des règles de référence » plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-186">Follow the steps in the "Example: Automate the setting of baseline rules" section earlier in this topic.</span></span> <span data-ttu-id="a9b0b-187">Une notification vous indique que le fichier de sortie a été généré à l’aide des paramètres de référence, et qu’un remplacement forcé des liaisons du format a eu lieu.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-187">A notification warns you that the outbound file has been generated by using baseline settings, and that a forced replacement of the format bindings has occurred.</span></span>

<span data-ttu-id="a9b0b-188">![Notification sur la page Configurations](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Capture d’écran de la notification sur la page Configurations")</span><span class="sxs-lookup"><span data-stu-id="a9b0b-188">![Notification on the Configurations page](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Screenshot of the notification on the Configurations page")</span></span>

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a><span data-ttu-id="a9b0b-189">Supprimer les avertissements concernant le remplacement des liaisons de format</span><span class="sxs-lookup"><span data-stu-id="a9b0b-189">Suppress warnings about the replacement of format bindings</span></span>

<span data-ttu-id="a9b0b-190">En définissant des paramètres ER spécifiques, vous pouvez supprimer les notifications qui avertissent du remplacement des liaisons du format.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-190">By setting specific ER parameters, you can suppress notifications that warn about the replacement of format bindings.</span></span> <span data-ttu-id="a9b0b-191">Cette opération peut être utile lorsque les liaisons de format sont remplacées en mode sans assistance à l’aide de Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-191">This suppression can be useful when format bindings are replaced in an unattended mode by using the Regression Suite Automation Tool.</span></span> <span data-ttu-id="a9b0b-192">Dans ce cas, l’avertissement peut être considéré comme un échec du scénario de test exécuté.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-192">In this case, the warning can be considered a failure of the test case that is running.</span></span>

1. <span data-ttu-id="a9b0b-193">Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, sélectionnez **Paramètres utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-193">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, select **User parameters**.</span></span>
2. <span data-ttu-id="a9b0b-194">Définissez l’option **Supprimer les avertissements relatifs à la référence** sur **Oui**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-194">Set the **Suppress baseline warnings** option to **Yes**, and then select **OK**.</span></span>

### <a name="review-the-generated-baseline-file"></a><span data-ttu-id="a9b0b-195">Examiner le fichier de référence généré</span><span class="sxs-lookup"><span data-stu-id="a9b0b-195">Review the generated baseline file</span></span>

1. <span data-ttu-id="a9b0b-196">Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-196">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="a9b0b-197">Sélectionnez **Références**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-197">Select **Baselines**.</span></span>
3. <span data-ttu-id="a9b0b-198">Sélectionnez **Pièces jointes**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-198">Select **Attachments**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="a9b0b-199">Le fichier généré contient le texte de la date et de l’heure du traitement (**« # »**) à partir de la liaison qui a été configurée dans la règle de référence ajoutée, et non à partir de la liaison du format.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-199">The generated file contains the processing date and time text (**"#"**) from the binding that was configured in the added baseline rule, not from the format's binding.</span></span>
    
4. <span data-ttu-id="a9b0b-200">Fermez la page **Pièces jointes**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-200">Close the **Attachments** page.</span></span>

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a><span data-ttu-id="a9b0b-201">Exécutez le format ER conçu et consultez le journal pour analyser les résultats</span><span class="sxs-lookup"><span data-stu-id="a9b0b-201">Run the designed ER format and review the log to analyze the results</span></span>

1. <span data-ttu-id="a9b0b-202">Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-202">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="a9b0b-203">Dans l’arborescence, développez **Modèle d’apprentissage des références ER**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-203">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="a9b0b-204">Dans l’arborescence, sélectionnez **Modèle d’apprentissage des références ER\\Format pour l’apprentissage des références ER**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-204">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="a9b0b-205">Dans l’organisateur **Versions**, sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-205">On the **Versions** FastTab select **Run**.</span></span>
5. <span data-ttu-id="a9b0b-206">Dans le champ **Entrer l’identifiant**, entrez **1**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-206">In the **Enter Id** field, type **1**.</span></span>
6. <span data-ttu-id="a9b0b-207">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-207">Select **OK**.</span></span>
7. <span data-ttu-id="a9b0b-208">Accédez à **Administration d’organisation** \> **États électroniques** \> **Journaux de débogage des configurations**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-208">Go to **Organization administration** \> **Electronic reporting** \> **Configuration debug logs**.</span></span>

<span data-ttu-id="a9b0b-209">Le journal d’exécution contient des informations sur le résultat de la comparaison du fichier généré avec la base de référence configurée.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-209">The execution log contains information about the results of the comparison of the generated file with the configured baseline.</span></span> <span data-ttu-id="a9b0b-210">Le journal indique que le fichier généré et la référence sont égaux, même si le format exécuté contient la liaison permettant d’entrer une valeur de date et d’heure changeant en permanence dans le fichier de sortie.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-210">The log indicates that the generated file and the baseline are equal, even though the executed format contains the binding to enter a constantly changing date and time value in the outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="a9b0b-211">Bien que le fichier de sortie ait été généré à l’aide de paramètres de référence qui forcent le remplacement des liaisons du format, vous ne recevez aucun avertissement concernant ce remplacement.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-211">Although the outbound file has been generated by using baseline settings that force the replacement of the format's bindings, you don't receive any warnings about the replacement.</span></span>

## <a name="exchange-baseline-settings-between-environments"></a><span data-ttu-id="a9b0b-212">Échanger les paramètres de référence entre environnements</span><span class="sxs-lookup"><span data-stu-id="a9b0b-212">Exchange baseline settings between environments</span></span>

### <a name="export-baseline-settings"></a><span data-ttu-id="a9b0b-213">Exporter les paramètres de référence</span><span class="sxs-lookup"><span data-stu-id="a9b0b-213">Export baseline settings</span></span>

<span data-ttu-id="a9b0b-214">Les nouvelles fonctionnalités ER vous permettent d’exporter les paramètres de référence pour le format ER sélectionné à partir de l’environnement actuel et de les enregistrer sous la forme de fichiers XML.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-214">The new ER capabilities let you export baseline settings for the selected ER format from the current environment and store them as XML files.</span></span> 

<span data-ttu-id="a9b0b-215">Pour exporter les paramètres de référence, dans la page **Références de format de la génération d’états électroniques**, sélectionnez **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-215">To export baseline settings, on the **Electronic reporting format baselines** page, select **Export**.</span></span>

### <a name="import-baseline-settings"></a><span data-ttu-id="a9b0b-216">Importer les paramètres de base</span><span class="sxs-lookup"><span data-stu-id="a9b0b-216">Import baseline settings</span></span>

<span data-ttu-id="a9b0b-217">Les paramètres de référence exportés peuvent être importés dans un autre environnement.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-217">Exported baseline settings can be imported into a different environment.</span></span> <span data-ttu-id="a9b0b-218">L’environnement doit d’abord être importé en tant que format ER.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-218">The environment must first be imported as an ER format.</span></span> <span data-ttu-id="a9b0b-219">Vous pouvez ensuite importer les paramètres de référence.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-219">You can then import the baseline settings.</span></span>

<span data-ttu-id="a9b0b-220">Pour importer les paramètres de référence à partir d’un fichier XML enregistré localement, dans la page **Références de format de la génération d’états électroniques**, sélectionnez **Importer**, puis sélectionnez **Parcourir** pour sélectionner le fichier XML.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-220">To import baseline settings from a locally stored XML file, on the **Electronic reporting format baselines** page, select **Import**, and then select **Browse** to select the XML file.</span></span>

<span data-ttu-id="a9b0b-221">![Boîte de dialogue Importer les paramètres de base](media/GER-BaselineSample-ImportBaseline1.PNG "Capture d’écran de la boîte de dialogue Importer les paramètres de base")</span><span class="sxs-lookup"><span data-stu-id="a9b0b-221">![Import baseline settings dialog box](media/GER-BaselineSample-ImportBaseline1.PNG "Screenshot of the Import baseline settings dialog box")</span></span>

<span data-ttu-id="a9b0b-222">Pour importer des paramètres de référence à partir d’un fichier XML stocké sur le serveur Microsoft SharePoint, en fonction des paramètres de gestion des documents et du type de document sélectionné, dans la page **Références de format de la génération d’états électroniques**, sélectionnez **Importer à partir d’une source**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-222">To import baseline settings from an XML file that is stored on the Microsoft SharePoint Server, based on the current Document management settings and the selected document type, on the **Electronic reporting format baselines** page, select **Import from source**.</span></span> <span data-ttu-id="a9b0b-223">Sélectionnez ensuite le type de document et le fichier XML.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-223">Then select the document type and the XML file.</span></span> <span data-ttu-id="a9b0b-224">Type de document requis pour accéder au dossier SharePoint doit être configuré à l’avance.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-224">The required document type to access the SharePoint folder must be configured in advance.</span></span>

<span data-ttu-id="a9b0b-225">![Boîte de dialogue Importer à partir de la source](media/GER-BaselineSample-ImportBaseline2.PNG "Capture d’écran de la boîte de dialogue Importer à partir de la source")</span><span class="sxs-lookup"><span data-stu-id="a9b0b-225">![Import from source dialog box](media/GER-BaselineSample-ImportBaseline2.PNG "Screenshot of the Import from source dialog box")</span></span>

> [!NOTE]
> <span data-ttu-id="a9b0b-226">Vous pouvez utiliser l’enregistreur de tâches pour enregistrer les étapes de sélection du type de document requis et du nom du fichier dans la boîte de dialogue **Importer à partir d’une source**.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-226">You can use Task recorder to record the steps for selecting the required document type and the file name in the **Import from source** dialog box.</span></span> <span data-ttu-id="a9b0b-227">De cette manière, vous pouvez conserver les paramètres de référence requis sur le serveur SharePoint et les importer automatiquement en les lisant dans un enregistrement de tâche au moment de l’exécution des tests automatisés à l’aide de Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="a9b0b-227">In this way, you can keep required baseline settings on SharePoint Server and then automatically import them by playing a task recording when you run automated tests by using the Regression Suite Automation Tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a9b0b-228">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a9b0b-228">Additional resources</span></span>

- [<span data-ttu-id="a9b0b-229">Suivre les résultats de rapport généré et les comparer avec des valeurs de base</span><span class="sxs-lookup"><span data-stu-id="a9b0b-229">Trace generated report results and compare them with baseline values</span></span>](er-trace-reports-compare-baseline.md)
- [<span data-ttu-id="a9b0b-230">Ressources de l’enregistreur de tâches</span><span class="sxs-lookup"><span data-stu-id="a9b0b-230">Task recorder resources</span></span>](../user-interface/task-recorder.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]