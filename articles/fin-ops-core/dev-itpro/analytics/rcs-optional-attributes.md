---
title: Importer les fichiers au format XML avec des attributs facultatifs
description: Cette rubrique fournit des informations sur la conception des formats ER qui spécifient les attributs XML permettant d’analyser les documents électroniques entrants au format XML.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 399f19197a729c11eaff94d708c837caef0d366d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562950"
---
# <a name="import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="dc5dc-103">Importer les fichiers au format XML avec des attributs facultatifs</span><span class="sxs-lookup"><span data-stu-id="dc5dc-103">Import files in XML format with optional attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dc5dc-104">Vous pouvez créer des formats de gestion des états électroniques pour analyser les documents électroniques entrants au format XML.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents in XML format.</span></span> <span data-ttu-id="dc5dc-105">Certains attributs des éléments XML peuvent être spécifiés comme facultatifs dans le format ER conçu.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-105">Certain attributes of XML elements can be specified in designed ER format as optional.</span></span> <span data-ttu-id="dc5dc-106">Cela vous permet de gérer correctement les fichiers entrants avec ou sans attributs XML.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-106">It will allow you to handle incoming files with and without such XML attributes properly.</span></span> <span data-ttu-id="dc5dc-107">Vous pouvez ensuite utiliser le contenu de ces fichiers pour mettre à jour les données d’application.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-107">You can then use the content from these files to update application data.</span></span>

<span data-ttu-id="dc5dc-108">Pour en savoir plus sur cette fonction, suivez les étapes de la rubrique [(RCS) Importer les fichiers au format XML avec des attributs facultatifs](tasks/import-files-xml-format-optional-attributes.md), qui fait partie du processus métier 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677).</span><span class="sxs-lookup"><span data-stu-id="dc5dc-108">To learn more about this feature, complete the steps in the topic, [(RCS) Import files in XML format with optional attributes](tasks/import-files-xml-format-optional-attributes.md), which is part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process.</span></span> <span data-ttu-id="dc5dc-109">Vous pouvez télécharger ce guide de tâches et les fichiers exemples associés à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="dc5dc-109">You can download this task guide and associated sample files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>


| <span data-ttu-id="dc5dc-110">Description du contenu</span><span class="sxs-lookup"><span data-stu-id="dc5dc-110">Content description</span></span>       | <span data-ttu-id="dc5dc-111">Fichier</span><span class="sxs-lookup"><span data-stu-id="dc5dc-111">File</span></span>                                                         |
|---------------------------|--------------------------------------------------------------|
| <span data-ttu-id="dc5dc-112">Fichier exemple au format XML</span><span class="sxs-lookup"><span data-stu-id="dc5dc-112">Sample file in XML format</span></span> | <span data-ttu-id="dc5dc-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span><span class="sxs-lookup"><span data-stu-id="dc5dc-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span></span>     |
| <span data-ttu-id="dc5dc-114">Guide des tâches</span><span class="sxs-lookup"><span data-stu-id="dc5dc-114">Task guide</span></span>                | <span data-ttu-id="dc5dc-115">RCS Importer les fichiers au format XML avec des attributs facultatifs .axtr</span><span class="sxs-lookup"><span data-stu-id="dc5dc-115">RCS Import files in XML format with optional attributes.axtr</span></span> |


<span data-ttu-id="dc5dc-116">Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d’états électroniques peut concevoir une configuration de format ER pour importer des fichiers au format XML contenant des attributs facultatifs.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-116">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="dc5dc-117">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de cette procédure, [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="dc5dc-117">To complete these steps, you must first complete the steps in the procedure, [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="dc5dc-118">Avant de commencer, chargez et enregistrez localement le fichier IncomingDocumentToLearnHowToHandleOptionalAttributes.xml à partir du centre de téléchargement Microsoft (https://go.microsoft.com/fwlink/?linkid=874684 ).</span><span class="sxs-lookup"><span data-stu-id="dc5dc-118">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from Microsoft Download Center (https://go.microsoft.com/fwlink/?linkid=874684 ).</span></span>

1. <span data-ttu-id="dc5dc-119">Accédez à **Administration d’organisation** > **Espaces de travail** > **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-119">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span>
2. <span data-ttu-id="dc5dc-120">Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-120">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="dc5dc-121">Si ce fournisseur de configuration ne s’affiche pas, effectuez les étapes de la rubrique [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="dc5dc-121">If you don't see this configuration provider, complete the steps in the topic, [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="dc5dc-122">Cliquez sur **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-122">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="dc5dc-123">Créer une configuration de modèle de données</span><span class="sxs-lookup"><span data-stu-id="dc5dc-123">Create a new data model configuration</span></span>
1. <span data-ttu-id="dc5dc-124">Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-124">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="dc5dc-125">Dans le champ **Nom**, tapez « Modèle d’importation d’un fichier XML ».</span><span class="sxs-lookup"><span data-stu-id="dc5dc-125">In the **Name** field, type 'Model to import xml file'.</span></span>
3. <span data-ttu-id="dc5dc-126">Cliquez sur **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-126">Click **Create configuration**.</span></span>
4. <span data-ttu-id="dc5dc-127">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-127">Click **Designer**.</span></span>
5. <span data-ttu-id="dc5dc-128">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-128">Click **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="dc5dc-129">Dans le champ **Nom**, tapez « Racine ».</span><span class="sxs-lookup"><span data-stu-id="dc5dc-129">In the **Name** field, type 'Root'.</span></span>
7. <span data-ttu-id="dc5dc-130">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-130">Click **Add**.</span></span>
8. <span data-ttu-id="dc5dc-131">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-131">Click **New** to open the drop dialog.</span></span>
9. <span data-ttu-id="dc5dc-132">Dans le champ **Nom**, tapez « Liste ».</span><span class="sxs-lookup"><span data-stu-id="dc5dc-132">In the **Name** field, type 'List'.</span></span>
10.    <span data-ttu-id="dc5dc-133">Dans le champ **Type d’article**, sélectionnez **Liste d’enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-133">In the **Item type** field, select **Record list**.</span></span>
11.    <span data-ttu-id="dc5dc-134">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-134">Click **Add**.</span></span>
12.    <span data-ttu-id="dc5dc-135">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-135">Click **New** to open the drop dialog.</span></span>
13.    <span data-ttu-id="dc5dc-136">Dans le champ **Nom**, tapez « Code ».</span><span class="sxs-lookup"><span data-stu-id="dc5dc-136">In the **Name** field, type 'Code'.</span></span>
14.    <span data-ttu-id="dc5dc-137">Dans le champ **Type d’article**, sélectionnez **Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-137">In the **Item type** field, select **String**.</span></span>
15.    <span data-ttu-id="dc5dc-138">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-138">Click **Add**.</span></span>
16.    <span data-ttu-id="dc5dc-139">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-139">Click **Save**.</span></span>
17.    <span data-ttu-id="dc5dc-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-140">Close the page.</span></span>
18.    <span data-ttu-id="dc5dc-141">Cliquez sur **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-141">Click **Change status**.</span></span>
19.    <span data-ttu-id="dc5dc-142">Cliquez sur **Terminé.**</span><span class="sxs-lookup"><span data-stu-id="dc5dc-142">Click **Complete**.</span></span>
20.    <span data-ttu-id="dc5dc-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-143">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="dc5dc-144">Créer un format pour l’importation de données</span><span class="sxs-lookup"><span data-stu-id="dc5dc-144">Create a format for data import</span></span>
1. <span data-ttu-id="dc5dc-145">Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-145">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="dc5dc-146">Dans le champ **Nouveau**, entrez « Format basé sur le modèle de données Modèle d’importation d’un fichier XML ».</span><span class="sxs-lookup"><span data-stu-id="dc5dc-146">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3. <span data-ttu-id="dc5dc-147">Dans le champ **Nom**, tapez « Format d’importation d’un fichier XML ».</span><span class="sxs-lookup"><span data-stu-id="dc5dc-147">In the **Nam** e field, type 'Format to import xml file'.</span></span> 
4. <span data-ttu-id="dc5dc-148">Sélectionnez **Oui** dans le champ **Prend en charge l’importation de données**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-148">Select **Yes** in the **Supports data import** field.</span></span>
5. <span data-ttu-id="dc5dc-149">Cliquez sur **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-149">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="dc5dc-150">Concevoir un format pour analyser le fichier entrant au format xml</span><span class="sxs-lookup"><span data-stu-id="dc5dc-150">Design a format to parse incoming file in xml format</span></span>
1. <span data-ttu-id="dc5dc-151">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-151">Click **Designer**.</span></span>
2. <span data-ttu-id="dc5dc-152">Cliquez sur **Ajouter racine** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-152">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="dc5dc-153">Dans l’arborescence, sélectionnez **XML\Élément**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-153">In the tree, select **XML\Element**.</span></span>
4. <span data-ttu-id="dc5dc-154">Dans le champ **Nom**, tapez « Racine ».</span><span class="sxs-lookup"><span data-stu-id="dc5dc-154">In the **Name** field, type 'root'.</span></span>
5. <span data-ttu-id="dc5dc-155">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-155">Click **OK**.</span></span>
6. <span data-ttu-id="dc5dc-156">Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-156">Click **Add** to open the drop dialog.</span></span>
7. <span data-ttu-id="dc5dc-157">Dans l’arborescence, sélectionnez **XML\Élément**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-157">In the tree, select **XML\Element**.</span></span>
8. <span data-ttu-id="dc5dc-158">Dans le champ **Nom**, tapez « Document ».</span><span class="sxs-lookup"><span data-stu-id="dc5dc-158">In the **Name** field, type 'document'.</span></span>
9. <span data-ttu-id="dc5dc-159">Dans le champ **Multiplicité**, sélectionnez **Un plusieurs**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-159">In the **Multiplicity** field, select **One many**.</span></span>
10.    <span data-ttu-id="dc5dc-160">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-160">Click **OK**.</span></span>
11.    <span data-ttu-id="dc5dc-161">Dans l’arborescence, sélectionnez **racine\document**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-161">In the tree, select **root\document**.</span></span>
12.    <span data-ttu-id="dc5dc-162">Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-162">Click **Add** to open the drop dialog.</span></span>
13.    <span data-ttu-id="dc5dc-163">Dans l’arborescence, sélectionnez **XML\Attribut**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-163">In the tree, select **XML\Attribute**.</span></span>
14.    <span data-ttu-id="dc5dc-164">Dans le champ **Nom**, tapez « id ».</span><span class="sxs-lookup"><span data-stu-id="dc5dc-164">In the **Name** field, type 'id'.</span></span>
15.    <span data-ttu-id="dc5dc-165">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-165">Click **OK**.</span></span>
16.    <span data-ttu-id="dc5dc-166">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-166">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="dc5dc-167">Concevoir une mise en correspondance de format pour enregistrer les informations analysées dans le modèle de données</span><span class="sxs-lookup"><span data-stu-id="dc5dc-167">Design a format mapping to save parsed information to data model</span></span>
1.    <span data-ttu-id="dc5dc-168">Cliquez sur **Mettre en correspondance avec le modèle**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-168">Click **Map format to model**.</span></span>
2.    <span data-ttu-id="dc5dc-169">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-169">Click **New**.</span></span>
3.    <span data-ttu-id="dc5dc-170">Saisissez ou sélectionnez une valeur dans le champ **Définition**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-170">In the **Definition** field, enter or select a value.</span></span>
4.    <span data-ttu-id="dc5dc-171">Dans le champ **Nom**, tapez « Mise en correspondance ».</span><span class="sxs-lookup"><span data-stu-id="dc5dc-171">In the **Name** field, type 'Mapping'.</span></span>
5.    <span data-ttu-id="dc5dc-172">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-172">Click **Save**.</span></span>
6.    <span data-ttu-id="dc5dc-173">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-173">Click **Designer**.</span></span>
7.    <span data-ttu-id="dc5dc-174">Dans l’arborescence, développez **Format**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-174">In the tree, expand **format**.</span></span>
8.    <span data-ttu-id="dc5dc-175">Dans l’arborescence, développez **format\racine : Élément XML (racine)**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-175">In the tree, expand **format\root: XML Element(root)**.</span></span>
9.    <span data-ttu-id="dc5dc-176">Dans l’arborescence, sélectionnez \**format\racine : Élément XML (racine)\document : Élément XML 1.*</span><span class="sxs-lookup"><span data-stu-id="dc5dc-176">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="dc5dc-177">(document)\*\*.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-177">(document)\*\*.</span></span>
10.    <span data-ttu-id="dc5dc-178">Cliquez sur **Lier**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-178">Click **Bind**.</span></span>
11.    <span data-ttu-id="dc5dc-179">Dans l’arborescence, développez \**format\racine : Élément XML (racine)\document : Élément XML 1.*</span><span class="sxs-lookup"><span data-stu-id="dc5dc-179">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="dc5dc-180">(document)\*\*.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-180">(document)\*\*.</span></span>
12.    <span data-ttu-id="dc5dc-181">Dans l’arborescence, sélectionnez \**format\racine : Élément XML (racine)\document : Élément XML 1.*</span><span class="sxs-lookup"><span data-stu-id="dc5dc-181">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="dc5dc-182">(document)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-182">(document)\id\*\*.</span></span>
13.    <span data-ttu-id="dc5dc-183">Dans l’arborescence, développez **Liste = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-183">In the tree, expand **List = format.root.document**.</span></span>
14.    <span data-ttu-id="dc5dc-184">Dans l’arborescence, sélectionnez **Liste = format.root.document\Code**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-184">In the tree, select **List = format.root.document\Code**.</span></span>
15.    <span data-ttu-id="dc5dc-185">Cliquez sur **Lier**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-185">Click **Bind**.</span></span>
16.    <span data-ttu-id="dc5dc-186">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-186">Click **Save**.</span></span>
17.    <span data-ttu-id="dc5dc-187">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-187">Close the page.</span></span>

## <a name="run-format-mapping"></a><span data-ttu-id="dc5dc-188">Exécuter la mise en correspondance des formats</span><span class="sxs-lookup"><span data-stu-id="dc5dc-188">Run format mapping</span></span>
1. <span data-ttu-id="dc5dc-189">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-189">Click **Run**.</span></span>
2. <span data-ttu-id="dc5dc-190">Cliquez sur **Parcourir** et sélectionnez le fichier, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-190">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="dc5dc-191">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-191">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="dc5dc-192">Le fichier sélectionné n’a pas été importé car la conception de format suppose l’existence de l’attribut « identification » pour l’élément « document », mais le fichier importé ne contient aucun tel attribut.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-192">The selected file has not been imported as the format design assumes the existence of 'id' attribute for the 'document' element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="dc5dc-193">Modifier la structure de format pour gérer l’attribut xml comme facultatif</span><span class="sxs-lookup"><span data-stu-id="dc5dc-193">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="dc5dc-194">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-194">Close the page.</span></span>
2. <span data-ttu-id="dc5dc-195">Dans l’arborescence, développez **racine\document**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-195">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="dc5dc-196">Dans l’arborescence, sélectionnez **racine\document\id**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-196">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="dc5dc-197">Dans le champ **Chaîne vide pour l’attribut absent**, sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-197">In the **Empty string for missing attribute** field, select **Yes**.</span></span>
5. <span data-ttu-id="dc5dc-198">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-198">Click **Save**.</span></span>

## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="dc5dc-199">Exécuter la mise en correspondance des formats avec les modifications des tests</span><span class="sxs-lookup"><span data-stu-id="dc5dc-199">Run format mapping to test changes</span></span>
1. <span data-ttu-id="dc5dc-200">Cliquez sur **Mettre en correspondance avec le modèle**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-200">Click **Map format to model**.</span></span>
2. <span data-ttu-id="dc5dc-201">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-201">Click **Run**.</span></span>
3. <span data-ttu-id="dc5dc-202">Cliquez sur **Parcourir** et sélectionnez le fichier, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-202">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
4. <span data-ttu-id="dc5dc-203">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-203">Click **OK**.</span></span>
5. <span data-ttu-id="dc5dc-204">Examinez le fichier généré.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-204">Review the generated file.</span></span> <span data-ttu-id="dc5dc-205">Notez que le même fichier a été importé car la conception de format considère désormais l’attribut « identification » de l’élément « document » comme facultatif.</span><span class="sxs-lookup"><span data-stu-id="dc5dc-205">Note that same file has been imported as the format design now consider the 'id' attribute for the 'document' element as optional.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]