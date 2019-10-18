---
title: (RCS) Importer les fichiers au format XML avec des attributs facultatifs
description: Cette rubrique fournit des informations sur la manière dont un utilisateur peut créer une configuration de format ER pour importer des fichiers au format XML contenant des attributs facultatifs.
author: NickSelin
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1290598d8dbd5b72d679ccf3e642e75b6dc3215
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182184"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="b245c-103">(RCS) Importer les fichiers au format XML avec des attributs facultatifs</span><span class="sxs-lookup"><span data-stu-id="b245c-103">(RCS) Import files in XML format with optional attributes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b245c-104">Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut concevoir une configuration de format ER pour importer des fichiers au format XML contenant des attributs facultatifs.</span><span class="sxs-lookup"><span data-stu-id="b245c-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="b245c-105">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="b245c-105">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="b245c-106">Avant de commencer, chargez et enregistrez localement le fichier IncomingDocumentToLearnHowToHandleOptionalAttributes.xml à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="b245c-106">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

1.  <span data-ttu-id="b245c-107">Accédez à **Tous les espaces de travail** > **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="b245c-107">Go to **All workspaces** > **Electronic reporting**.</span></span>
2.  <span data-ttu-id="b245c-108">Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**.</span><span class="sxs-lookup"><span data-stu-id="b245c-108">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="b245c-109">Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure [Créer un fournisseur de configuration et le marquer comme actif](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="b245c-109">If you don’t see this configuration provider, complete the steps in the procedure [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3.  <span data-ttu-id="b245c-110">Cliquez sur **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="b245c-110">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="b245c-111">Créer une configuration de modèle de données</span><span class="sxs-lookup"><span data-stu-id="b245c-111">Create a new data model configuration</span></span>
1.  <span data-ttu-id="b245c-112">Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b245c-112">Click **Create configuration** to open the drop dialog.</span></span>
2.  <span data-ttu-id="b245c-113">Dans le champ **Nom**, tapez « Modèle d'importation d'un fichier XML ».</span><span class="sxs-lookup"><span data-stu-id="b245c-113">In the **Name** field, type 'Model to import xml file'.</span></span>
3.  <span data-ttu-id="b245c-114">Cliquez sur **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="b245c-114">Click **Create configuration**.</span></span>
4.  <span data-ttu-id="b245c-115">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="b245c-115">Click **Designer**.</span></span>
5.  <span data-ttu-id="b245c-116">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b245c-116">Click **New** to open the drop dialog.</span></span>
6.  <span data-ttu-id="b245c-117">Dans le champ **Nom**, tapez « Racine ».</span><span class="sxs-lookup"><span data-stu-id="b245c-117">In the **Name** field, type 'Root'.</span></span>
7.  <span data-ttu-id="b245c-118">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b245c-118">Click **Add**.</span></span>
8.  <span data-ttu-id="b245c-119">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b245c-119">Click **New** to open the drop dialog.</span></span>
9.  <span data-ttu-id="b245c-120">Dans le champ **Nom**, tapez « Liste ».</span><span class="sxs-lookup"><span data-stu-id="b245c-120">In the **Name** field, type 'List'.</span></span>
10. <span data-ttu-id="b245c-121">Dans le champ **Type d'article**, sélectionnez **Liste d'enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="b245c-121">In the **Item type** field, select **Record list**.</span></span>
11. <span data-ttu-id="b245c-122">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b245c-122">Click **Add**.</span></span>
12. <span data-ttu-id="b245c-123">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b245c-123">Click **New** to open the drop dialog.</span></span>
13. <span data-ttu-id="b245c-124">Dans le champ **Nom**, tapez « Code ».</span><span class="sxs-lookup"><span data-stu-id="b245c-124">In the **Name** field, type 'Code'.</span></span>
14. <span data-ttu-id="b245c-125">Dans le champ **Type d'article**, sélectionnez **Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="b245c-125">In the **Item type** field, select **String**.</span></span>
15. <span data-ttu-id="b245c-126">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b245c-126">Click **Add**.</span></span>
16. <span data-ttu-id="b245c-127">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b245c-127">Click **Save**.</span></span>
17. <span data-ttu-id="b245c-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b245c-128">Close the page.</span></span>
18. <span data-ttu-id="b245c-129">Cliquez sur **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="b245c-129">Click **Change status**.</span></span>
19. <span data-ttu-id="b245c-130">Cliquez sur **Terminé.**</span><span class="sxs-lookup"><span data-stu-id="b245c-130">Click **Complete**.</span></span>
20. <span data-ttu-id="b245c-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b245c-131">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="b245c-132">Créer un format pour l'importation de données</span><span class="sxs-lookup"><span data-stu-id="b245c-132">Create a format for data import</span></span>
1.  <span data-ttu-id="b245c-133">Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b245c-133">Click **Create configuration** to open the drop dialog.</span></span>
2.  <span data-ttu-id="b245c-134">Dans le champ **Nouveau**, entrez « Format basé sur le modèle de données Modèle d'importation d'un fichier XML ».</span><span class="sxs-lookup"><span data-stu-id="b245c-134">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3.  <span data-ttu-id="b245c-135">Dans le champ **Nom**, tapez « Format d'importation d'un fichier XML ».</span><span class="sxs-lookup"><span data-stu-id="b245c-135">In the **Name** field, type 'Format to import xml file'.</span></span>
4.  <span data-ttu-id="b245c-136">Sélectionnez **Oui** dans le champ **Prend en charge l'importation de données**.</span><span class="sxs-lookup"><span data-stu-id="b245c-136">Select **Yes** in the **Supports data import** field.</span></span>
5.  <span data-ttu-id="b245c-137">Cliquez sur **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="b245c-137">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="b245c-138">Concevoir un format pour analyser le fichier entrant au format xml</span><span class="sxs-lookup"><span data-stu-id="b245c-138">Design a format to parse incoming file in xml format</span></span>
1.  <span data-ttu-id="b245c-139">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="b245c-139">Click **Designer**.</span></span>
2.  <span data-ttu-id="b245c-140">Cliquez sur **Ajouter racine** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b245c-140">Click **Add root** to open the drop dialog.</span></span>
3.  <span data-ttu-id="b245c-141">Dans l'arborescence, sélectionnez **XML\Élément**.</span><span class="sxs-lookup"><span data-stu-id="b245c-141">In the tree, select **XML\Element**.</span></span>
4.  <span data-ttu-id="b245c-142">Dans le champ **Nom**, tapez « Racine ».</span><span class="sxs-lookup"><span data-stu-id="b245c-142">In the **Name** field, type 'root'.</span></span>
5.  <span data-ttu-id="b245c-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b245c-143">Click **OK**.</span></span>
6.  <span data-ttu-id="b245c-144">Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b245c-144">Click **Add** to open the drop dialog.</span></span>
7.  <span data-ttu-id="b245c-145">Dans l'arborescence, sélectionnez **XML\Élément**.</span><span class="sxs-lookup"><span data-stu-id="b245c-145">In the tree, select **XML\Element**.</span></span>
8.  <span data-ttu-id="b245c-146">Dans le champ **Nom**, tapez « Document ».</span><span class="sxs-lookup"><span data-stu-id="b245c-146">In the **Name** field, type 'document'.</span></span>
9.  <span data-ttu-id="b245c-147">Dans le champ **Multiplicité**, sélectionnez **Un plusieurs**.</span><span class="sxs-lookup"><span data-stu-id="b245c-147">In the **Multiplicity** field, select **One many**.</span></span>
10. <span data-ttu-id="b245c-148">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b245c-148">Click **OK**.</span></span>
11. <span data-ttu-id="b245c-149">Dans l'arborescence, sélectionnez **racine\document**.</span><span class="sxs-lookup"><span data-stu-id="b245c-149">In the tree, select **root\document**.</span></span>
12. <span data-ttu-id="b245c-150">Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b245c-150">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="b245c-151">Dans l'arborescence, sélectionnez **XML\Attribut**.</span><span class="sxs-lookup"><span data-stu-id="b245c-151">In the tree, select **XML\Attribute**.</span></span>
14. <span data-ttu-id="b245c-152">Dans le champ **Nom**, tapez « ID ».</span><span class="sxs-lookup"><span data-stu-id="b245c-152">In the **Name** field, type 'ID'.</span></span>
15. <span data-ttu-id="b245c-153">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b245c-153">Click **OK**.</span></span>
16. <span data-ttu-id="b245c-154">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b245c-154">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="b245c-155">Concevoir une mise en correspondance de format pour enregistrer les informations analysées dans le modèle de données</span><span class="sxs-lookup"><span data-stu-id="b245c-155">Design a format mapping to save parsed information to data model</span></span>
1. <span data-ttu-id="b245c-156">Cliquez sur **Mettre en correspondance avec le modèle**.</span><span class="sxs-lookup"><span data-stu-id="b245c-156">Click **Map format to model**.</span></span>
2. <span data-ttu-id="b245c-157">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b245c-157">Click **New**.</span></span>
3. <span data-ttu-id="b245c-158">Saisissez ou sélectionnez une valeur dans le champ **Définition**.</span><span class="sxs-lookup"><span data-stu-id="b245c-158">In the **Definition** field, enter or select a value.</span></span>
4. <span data-ttu-id="b245c-159">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b245c-159">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b245c-160">Dans le champ **Nom**, tapez « Mise en correspondance ».</span><span class="sxs-lookup"><span data-stu-id="b245c-160">In the **Name** field, type 'Mapping'.</span></span>
6. <span data-ttu-id="b245c-161">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b245c-161">Click **Save**.</span></span>
7. <span data-ttu-id="b245c-162">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="b245c-162">Click **Designer**.</span></span>
8. <span data-ttu-id="b245c-163">Dans l'arborescence, développez **Format**.</span><span class="sxs-lookup"><span data-stu-id="b245c-163">In the tree, expand **format**.</span></span>
9. <span data-ttu-id="b245c-164">Dans l'arborescence, développez **format\racine : Élément XML (racine)**.</span><span class="sxs-lookup"><span data-stu-id="b245c-164">In the tree, expand **format\root: XML Element(root)**.</span></span>
10. <span data-ttu-id="b245c-165">Dans l'arborescence, sélectionnez \**format\racine : Élément XML (racine)\document : Élément XML 1.*</span><span class="sxs-lookup"><span data-stu-id="b245c-165">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="b245c-166">(document)\*\*.</span><span class="sxs-lookup"><span data-stu-id="b245c-166">(document)\*\*.</span></span>
11. <span data-ttu-id="b245c-167">Cliquez sur **Lier**.</span><span class="sxs-lookup"><span data-stu-id="b245c-167">Click **Bind**.</span></span>
12. <span data-ttu-id="b245c-168">Dans l'arborescence, développez \**format\racine : Élément XML (racine)\document : Élément XML 1.*</span><span class="sxs-lookup"><span data-stu-id="b245c-168">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="b245c-169">(document)\*\*.</span><span class="sxs-lookup"><span data-stu-id="b245c-169">(document)\*\*.</span></span>
13. <span data-ttu-id="b245c-170">Dans l'arborescence, sélectionnez \**format\racine : Élément XML (racine)\document : Élément XML 1.*</span><span class="sxs-lookup"><span data-stu-id="b245c-170">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="b245c-171">(document)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="b245c-171">(document)\id\*\*.</span></span>
14. <span data-ttu-id="b245c-172">Dans l'arborescence, développez **Liste = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="b245c-172">In the tree, expand **List = format.root.document**.</span></span>
15. <span data-ttu-id="b245c-173">Dans l'arborescence, sélectionnez **Liste = format.root.document\Code**.</span><span class="sxs-lookup"><span data-stu-id="b245c-173">In the tree, select **List = format.root.document\Code**.</span></span>
16. <span data-ttu-id="b245c-174">Cliquez sur **Lier**.</span><span class="sxs-lookup"><span data-stu-id="b245c-174">Click **Bind**.</span></span>
17. <span data-ttu-id="b245c-175">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b245c-175">Click **Save**.</span></span>
18. <span data-ttu-id="b245c-176">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b245c-176">Close the page.</span></span>
 
## <a name="run-format-mapping"></a><span data-ttu-id="b245c-177">Exécuter la mise en correspondance des formats</span><span class="sxs-lookup"><span data-stu-id="b245c-177">Run format mapping</span></span>
1. <span data-ttu-id="b245c-178">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b245c-178">Click **Run**.</span></span>
2. <span data-ttu-id="b245c-179">Cliquez sur **Parcourir** et sélectionnez le fichier **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="b245c-179">Click **Browse** and select **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="b245c-180">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b245c-180">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="b245c-181">Le fichier sélectionné n'a pas été importé car la conception de format suppose l'existence de l'attribut « identification » pour l'élément « document », mais le fichier importé ne contient aucun tel attribut.</span><span class="sxs-lookup"><span data-stu-id="b245c-181">The selected file has not been imported as the format design assumes the existence of ‘id’ attribute for the ‘document’ element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="b245c-182">Modifier la structure de format pour gérer l'attribut xml comme facultatif</span><span class="sxs-lookup"><span data-stu-id="b245c-182">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="b245c-183">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b245c-183">Close the page.</span></span>
2. <span data-ttu-id="b245c-184">Dans l'arborescence, développez **racine\document**.</span><span class="sxs-lookup"><span data-stu-id="b245c-184">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="b245c-185">Dans l'arborescence, sélectionnez **racine\document\id**.</span><span class="sxs-lookup"><span data-stu-id="b245c-185">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="b245c-186">Dans le champ **Chaîne vide pour l'attribut absent**, sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b245c-186">Select **Yes** in the **Empty string for missing attribute** field.</span></span>
5. <span data-ttu-id="b245c-187">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b245c-187">Click **Save**.</span></span>
 
## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="b245c-188">Exécuter la mise en correspondance des formats avec les modifications des tests</span><span class="sxs-lookup"><span data-stu-id="b245c-188">Run format mapping to test changes</span></span>
1. <span data-ttu-id="b245c-189">Cliquez sur **Mettre en correspondance avec le modèle**.</span><span class="sxs-lookup"><span data-stu-id="b245c-189">Click **Map format to model**.</span></span>
2. <span data-ttu-id="b245c-190">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b245c-190">Click **Run**.</span></span>
3. <span data-ttu-id="b245c-191">Cliquez sur **Parcourir** et sélectionnez le fichier **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="b245c-191">Click **Browse** and select the **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** file.</span></span>
4. <span data-ttu-id="b245c-192">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b245c-192">Click **OK**.</span></span>
5. <span data-ttu-id="b245c-193">Examinez le fichier généré.</span><span class="sxs-lookup"><span data-stu-id="b245c-193">Review the generated file.</span></span> 

> [!NOTE]
> <span data-ttu-id="b245c-194">Le même fichier a été importé car la conception de format considère désormais l'attribut « identification » de l'élément « document » comme facultatif.</span><span class="sxs-lookup"><span data-stu-id="b245c-194">The same file has been imported as the format design now consider the ‘id’ attribute for the ‘document’ element as optional.</span></span>
