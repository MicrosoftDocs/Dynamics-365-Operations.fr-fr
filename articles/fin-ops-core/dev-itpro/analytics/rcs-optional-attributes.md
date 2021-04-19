---
title: Importer les fichiers au format XML avec des attributs facultatifs
description: Cette rubrique fournit des informations sur la conception des formats ER qui spécifient les attributs XML permettant d’analyser les documents électroniques entrants au format XML.
author: NickSelin
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
ms.openlocfilehash: cd5add18f2f1588cef02afae052d29dc1a28face
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748267"
---
# <a name="import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="a6e1d-103">Importer les fichiers au format XML avec des attributs facultatifs</span><span class="sxs-lookup"><span data-stu-id="a6e1d-103">Import files in XML format with optional attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a6e1d-104">Vous pouvez créer des formats de gestion des états électroniques pour analyser les documents électroniques entrants au format XML.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents in XML format.</span></span> <span data-ttu-id="a6e1d-105">Certains attributs des éléments XML peuvent être spécifiés comme facultatifs dans le format ER conçu.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-105">Certain attributes of XML elements can be specified in designed ER format as optional.</span></span> <span data-ttu-id="a6e1d-106">Cela vous permet de gérer correctement les fichiers entrants avec ou sans attributs XML.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-106">It will allow you to handle incoming files with and without such XML attributes properly.</span></span> <span data-ttu-id="a6e1d-107">Vous pouvez ensuite utiliser le contenu de ces fichiers pour mettre à jour les données d’application.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-107">You can then use the content from these files to update application data.</span></span>

<span data-ttu-id="a6e1d-108">Pour en savoir plus sur cette fonction, suivez les étapes de la rubrique [(RCS) Importer les fichiers au format XML avec des attributs facultatifs](tasks/import-files-xml-format-optional-attributes.md), qui fait partie du processus métier 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677).</span><span class="sxs-lookup"><span data-stu-id="a6e1d-108">To learn more about this feature, complete the steps in the topic, [(RCS) Import files in XML format with optional attributes](tasks/import-files-xml-format-optional-attributes.md), which is part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process.</span></span> <span data-ttu-id="a6e1d-109">Vous pouvez télécharger ce guide de tâches et les fichiers exemples associés à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="a6e1d-109">You can download this task guide and associated sample files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>


| <span data-ttu-id="a6e1d-110">Description du contenu</span><span class="sxs-lookup"><span data-stu-id="a6e1d-110">Content description</span></span>       | <span data-ttu-id="a6e1d-111">Fichier</span><span class="sxs-lookup"><span data-stu-id="a6e1d-111">File</span></span>                                                         |
|---------------------------|--------------------------------------------------------------|
| <span data-ttu-id="a6e1d-112">Fichier exemple au format XML</span><span class="sxs-lookup"><span data-stu-id="a6e1d-112">Sample file in XML format</span></span> | <span data-ttu-id="a6e1d-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span><span class="sxs-lookup"><span data-stu-id="a6e1d-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span></span>     |
| <span data-ttu-id="a6e1d-114">Guide des tâches</span><span class="sxs-lookup"><span data-stu-id="a6e1d-114">Task guide</span></span>                | <span data-ttu-id="a6e1d-115">RCS Importer les fichiers au format XML avec des attributs facultatifs .axtr</span><span class="sxs-lookup"><span data-stu-id="a6e1d-115">RCS Import files in XML format with optional attributes.axtr</span></span> |


<span data-ttu-id="a6e1d-116">Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d’états électroniques peut concevoir une configuration de format ER pour importer des fichiers au format XML contenant des attributs facultatifs.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-116">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="a6e1d-117">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de cette procédure, [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="a6e1d-117">To complete these steps, you must first complete the steps in the procedure, [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="a6e1d-118">Avant de commencer, chargez et enregistrez localement le fichier IncomingDocumentToLearnHowToHandleOptionalAttributes.xml à partir du centre de téléchargement Microsoft (https://go.microsoft.com/fwlink/?linkid=874684 ).</span><span class="sxs-lookup"><span data-stu-id="a6e1d-118">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from Microsoft Download Center (https://go.microsoft.com/fwlink/?linkid=874684 ).</span></span>

1. <span data-ttu-id="a6e1d-119">Accédez à **Administration d’organisation** > **Espaces de travail** > **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-119">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span>
2. <span data-ttu-id="a6e1d-120">Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-120">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="a6e1d-121">Si ce fournisseur de configuration ne s’affiche pas, effectuez les étapes de la rubrique [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="a6e1d-121">If you don't see this configuration provider, complete the steps in the topic, [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="a6e1d-122">Cliquez sur **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-122">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="a6e1d-123">Créer une configuration de modèle de données</span><span class="sxs-lookup"><span data-stu-id="a6e1d-123">Create a new data model configuration</span></span>
1. <span data-ttu-id="a6e1d-124">Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-124">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="a6e1d-125">Dans le champ **Nom**, tapez « Modèle d’importation d’un fichier XML ».</span><span class="sxs-lookup"><span data-stu-id="a6e1d-125">In the **Name** field, type 'Model to import xml file'.</span></span>
3. <span data-ttu-id="a6e1d-126">Cliquez sur **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-126">Click **Create configuration**.</span></span>
4. <span data-ttu-id="a6e1d-127">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-127">Click **Designer**.</span></span>
5. <span data-ttu-id="a6e1d-128">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-128">Click **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="a6e1d-129">Dans le champ **Nom**, tapez « Racine ».</span><span class="sxs-lookup"><span data-stu-id="a6e1d-129">In the **Name** field, type 'Root'.</span></span>
7. <span data-ttu-id="a6e1d-130">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-130">Click **Add**.</span></span>
8. <span data-ttu-id="a6e1d-131">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-131">Click **New** to open the drop dialog.</span></span>
9. <span data-ttu-id="a6e1d-132">Dans le champ **Nom**, tapez « Liste ».</span><span class="sxs-lookup"><span data-stu-id="a6e1d-132">In the **Name** field, type 'List'.</span></span>
10.    <span data-ttu-id="a6e1d-133">Dans le champ **Type d’article**, sélectionnez **Liste d’enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-133">In the **Item type** field, select **Record list**.</span></span>
11.    <span data-ttu-id="a6e1d-134">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-134">Click **Add**.</span></span>
12.    <span data-ttu-id="a6e1d-135">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-135">Click **New** to open the drop dialog.</span></span>
13.    <span data-ttu-id="a6e1d-136">Dans le champ **Nom**, tapez « Code ».</span><span class="sxs-lookup"><span data-stu-id="a6e1d-136">In the **Name** field, type 'Code'.</span></span>
14.    <span data-ttu-id="a6e1d-137">Dans le champ **Type d’article**, sélectionnez **Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-137">In the **Item type** field, select **String**.</span></span>
15.    <span data-ttu-id="a6e1d-138">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-138">Click **Add**.</span></span>
16.    <span data-ttu-id="a6e1d-139">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-139">Click **Save**.</span></span>
17.    <span data-ttu-id="a6e1d-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-140">Close the page.</span></span>
18.    <span data-ttu-id="a6e1d-141">Cliquez sur **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-141">Click **Change status**.</span></span>
19.    <span data-ttu-id="a6e1d-142">Cliquez sur **Terminé.**</span><span class="sxs-lookup"><span data-stu-id="a6e1d-142">Click **Complete**.</span></span>
20.    <span data-ttu-id="a6e1d-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-143">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="a6e1d-144">Créer un format pour l’importation de données</span><span class="sxs-lookup"><span data-stu-id="a6e1d-144">Create a format for data import</span></span>
1. <span data-ttu-id="a6e1d-145">Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-145">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="a6e1d-146">Dans le champ **Nouveau**, entrez « Format basé sur le modèle de données Modèle d’importation d’un fichier XML ».</span><span class="sxs-lookup"><span data-stu-id="a6e1d-146">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3. <span data-ttu-id="a6e1d-147">Dans le champ **Nom**, tapez « Format d’importation d’un fichier XML ».</span><span class="sxs-lookup"><span data-stu-id="a6e1d-147">In the **Nam** e field, type 'Format to import xml file'.</span></span> 
4. <span data-ttu-id="a6e1d-148">Sélectionnez **Oui** dans le champ **Prend en charge l’importation de données**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-148">Select **Yes** in the **Supports data import** field.</span></span>
5. <span data-ttu-id="a6e1d-149">Cliquez sur **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-149">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="a6e1d-150">Concevoir un format pour analyser le fichier entrant au format xml</span><span class="sxs-lookup"><span data-stu-id="a6e1d-150">Design a format to parse incoming file in xml format</span></span>
1. <span data-ttu-id="a6e1d-151">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-151">Click **Designer**.</span></span>
2. <span data-ttu-id="a6e1d-152">Cliquez sur **Ajouter racine** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-152">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="a6e1d-153">Dans l’arborescence, sélectionnez **XML\Élément**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-153">In the tree, select **XML\Element**.</span></span>
4. <span data-ttu-id="a6e1d-154">Dans le champ **Nom**, tapez « Racine ».</span><span class="sxs-lookup"><span data-stu-id="a6e1d-154">In the **Name** field, type 'root'.</span></span>
5. <span data-ttu-id="a6e1d-155">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-155">Click **OK**.</span></span>
6. <span data-ttu-id="a6e1d-156">Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-156">Click **Add** to open the drop dialog.</span></span>
7. <span data-ttu-id="a6e1d-157">Dans l’arborescence, sélectionnez **XML\Élément**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-157">In the tree, select **XML\Element**.</span></span>
8. <span data-ttu-id="a6e1d-158">Dans le champ **Nom**, tapez « Document ».</span><span class="sxs-lookup"><span data-stu-id="a6e1d-158">In the **Name** field, type 'document'.</span></span>
9. <span data-ttu-id="a6e1d-159">Dans le champ **Multiplicité**, sélectionnez **Un plusieurs**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-159">In the **Multiplicity** field, select **One many**.</span></span>
10.    <span data-ttu-id="a6e1d-160">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-160">Click **OK**.</span></span>
11.    <span data-ttu-id="a6e1d-161">Dans l’arborescence, sélectionnez **racine\document**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-161">In the tree, select **root\document**.</span></span>
12.    <span data-ttu-id="a6e1d-162">Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-162">Click **Add** to open the drop dialog.</span></span>
13.    <span data-ttu-id="a6e1d-163">Dans l’arborescence, sélectionnez **XML\Attribut**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-163">In the tree, select **XML\Attribute**.</span></span>
14.    <span data-ttu-id="a6e1d-164">Dans le champ **Nom**, tapez « id ».</span><span class="sxs-lookup"><span data-stu-id="a6e1d-164">In the **Name** field, type 'id'.</span></span>
15.    <span data-ttu-id="a6e1d-165">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-165">Click **OK**.</span></span>
16.    <span data-ttu-id="a6e1d-166">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-166">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="a6e1d-167">Concevoir une mise en correspondance de format pour enregistrer les informations analysées dans le modèle de données</span><span class="sxs-lookup"><span data-stu-id="a6e1d-167">Design a format mapping to save parsed information to data model</span></span>
1.    <span data-ttu-id="a6e1d-168">Cliquez sur **Mettre en correspondance avec le modèle**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-168">Click **Map format to model**.</span></span>
2.    <span data-ttu-id="a6e1d-169">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-169">Click **New**.</span></span>
3.    <span data-ttu-id="a6e1d-170">Saisissez ou sélectionnez une valeur dans le champ **Définition**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-170">In the **Definition** field, enter or select a value.</span></span>
4.    <span data-ttu-id="a6e1d-171">Dans le champ **Nom**, tapez « Mise en correspondance ».</span><span class="sxs-lookup"><span data-stu-id="a6e1d-171">In the **Name** field, type 'Mapping'.</span></span>
5.    <span data-ttu-id="a6e1d-172">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-172">Click **Save**.</span></span>
6.    <span data-ttu-id="a6e1d-173">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-173">Click **Designer**.</span></span>
7.    <span data-ttu-id="a6e1d-174">Dans l’arborescence, développez **Format**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-174">In the tree, expand **format**.</span></span>
8.    <span data-ttu-id="a6e1d-175">Dans l’arborescence, développez **format\racine : Élément XML (racine)**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-175">In the tree, expand **format\root: XML Element(root)**.</span></span>
9.    <span data-ttu-id="a6e1d-176">Dans l’arborescence, sélectionnez \**format\racine : Élément XML (racine)\document : Élément XML 1.*</span><span class="sxs-lookup"><span data-stu-id="a6e1d-176">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="a6e1d-177">(document)\*\*.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-177">(document)\*\*.</span></span>
10.    <span data-ttu-id="a6e1d-178">Cliquez sur **Lier**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-178">Click **Bind**.</span></span>
11.    <span data-ttu-id="a6e1d-179">Dans l’arborescence, développez \**format\racine : Élément XML (racine)\document : Élément XML 1.*</span><span class="sxs-lookup"><span data-stu-id="a6e1d-179">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="a6e1d-180">(document)\*\*.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-180">(document)\*\*.</span></span>
12.    <span data-ttu-id="a6e1d-181">Dans l’arborescence, sélectionnez \**format\racine : Élément XML (racine)\document : Élément XML 1.*</span><span class="sxs-lookup"><span data-stu-id="a6e1d-181">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="a6e1d-182">(document)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-182">(document)\id\*\*.</span></span>
13.    <span data-ttu-id="a6e1d-183">Dans l’arborescence, développez **Liste = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-183">In the tree, expand **List = format.root.document**.</span></span>
14.    <span data-ttu-id="a6e1d-184">Dans l’arborescence, sélectionnez **Liste = format.root.document\Code**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-184">In the tree, select **List = format.root.document\Code**.</span></span>
15.    <span data-ttu-id="a6e1d-185">Cliquez sur **Lier**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-185">Click **Bind**.</span></span>
16.    <span data-ttu-id="a6e1d-186">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-186">Click **Save**.</span></span>
17.    <span data-ttu-id="a6e1d-187">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-187">Close the page.</span></span>

## <a name="run-format-mapping"></a><span data-ttu-id="a6e1d-188">Exécuter la mise en correspondance des formats</span><span class="sxs-lookup"><span data-stu-id="a6e1d-188">Run format mapping</span></span>
1. <span data-ttu-id="a6e1d-189">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-189">Click **Run**.</span></span>
2. <span data-ttu-id="a6e1d-190">Cliquez sur **Parcourir** et sélectionnez le fichier, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-190">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="a6e1d-191">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-191">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="a6e1d-192">Le fichier sélectionné n’a pas été importé car la conception de format suppose l’existence de l’attribut « identification » pour l’élément « document », mais le fichier importé ne contient aucun tel attribut.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-192">The selected file has not been imported as the format design assumes the existence of 'id' attribute for the 'document' element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="a6e1d-193">Modifier la structure de format pour gérer l’attribut xml comme facultatif</span><span class="sxs-lookup"><span data-stu-id="a6e1d-193">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="a6e1d-194">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-194">Close the page.</span></span>
2. <span data-ttu-id="a6e1d-195">Dans l’arborescence, développez **racine\document**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-195">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="a6e1d-196">Dans l’arborescence, sélectionnez **racine\document\id**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-196">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="a6e1d-197">Dans le champ **Chaîne vide pour l’attribut absent**, sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-197">In the **Empty string for missing attribute** field, select **Yes**.</span></span>
5. <span data-ttu-id="a6e1d-198">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-198">Click **Save**.</span></span>

## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="a6e1d-199">Exécuter la mise en correspondance des formats avec les modifications des tests</span><span class="sxs-lookup"><span data-stu-id="a6e1d-199">Run format mapping to test changes</span></span>
1. <span data-ttu-id="a6e1d-200">Cliquez sur **Mettre en correspondance avec le modèle**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-200">Click **Map format to model**.</span></span>
2. <span data-ttu-id="a6e1d-201">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-201">Click **Run**.</span></span>
3. <span data-ttu-id="a6e1d-202">Cliquez sur **Parcourir** et sélectionnez le fichier, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-202">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
4. <span data-ttu-id="a6e1d-203">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-203">Click **OK**.</span></span>
5. <span data-ttu-id="a6e1d-204">Examinez le fichier généré.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-204">Review the generated file.</span></span> <span data-ttu-id="a6e1d-205">Notez que le même fichier a été importé car la conception de format considère désormais l’attribut « identification » de l’élément « document » comme facultatif.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-205">Note that same file has been imported as the format design now consider the 'id' attribute for the 'document' element as optional.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]