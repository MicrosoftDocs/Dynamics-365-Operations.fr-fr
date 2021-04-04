---
title: Mettre à jour la structure d’un modèle de document commercial
description: Cette rubrique explique comment mettre à jour la structure d’un modèle de document commercial à l’aide de la fonctionnalité de gestion des documents commerciaux.
author: NickSelin
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 09813115544701ea3fffb6be06114bcdd63c0ba0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570446"
---
# <a name="update-the-structure-of-a-business-document-template"></a><span data-ttu-id="b4241-103">Mettre à jour la structure d’un modèle de document commercial</span><span class="sxs-lookup"><span data-stu-id="b4241-103">Update the structure of a business document template</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b4241-104">Dans le volet **Structure du modèle** de l’éditeur de modèles [Gestion des documents commerciaux](er-business-document-management.md), vous pouvez modifier un modèle de document commercial en [ajoutant de nouveaux champs](er-bdm-add-field-to-excel-template.md) à un modèle dans Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="b4241-104">In the **Template structure** pane of the [Business document management](er-business-document-management.md) template editor, you can modify a business document template by [adding new fields](er-bdm-add-field-to-excel-template.md) to a template in Microsoft Excel.</span></span> <span data-ttu-id="b4241-105">La structure du modèle est ensuite automatiquement mise à jour dans Dynamics 365 Finance, afin qu’il reflète les modifications que vous avez apportées au volet **Structure du modèle**.</span><span class="sxs-lookup"><span data-stu-id="b4241-105">The structure of the template is then automatically updated in Dynamics 365 Finance, so that it reflects the changes that you made in the **Template structure** pane.</span></span>

<span data-ttu-id="b4241-106">Vous pouvez également modifier un modèle en utilisant la fonctionnalité en ligne Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4241-106">You can also modify a template by using Office 365 online functionality.</span></span> <span data-ttu-id="b4241-107">Par exemple, vous pouvez ajouter un nouvel élément nommé, tel qu’une image ou une forme, à la feuille de calcul modifiable.</span><span class="sxs-lookup"><span data-stu-id="b4241-107">For example, you can add a new named item, such as a picture or shape, to the editable worksheet.</span></span> <span data-ttu-id="b4241-108">Dans ce cas, la structure du modèle n’est pas automatiquement mise à jour dans Finance et l’élément que vous avez ajouté n’apparaît pas dans la **Structure du modèle**.</span><span class="sxs-lookup"><span data-stu-id="b4241-108">In this case, the structure of the template isn't automatically updated in Finance, and the item that you added doesn't appear in the **Template structure** pane.</span></span> <span data-ttu-id="b4241-109">Mettez à jour manuellement la structure du modèle dans Finance en sélectionnant **Mettre à jour la structure** sur la page de l’éditeur de modèles.</span><span class="sxs-lookup"><span data-stu-id="b4241-109">Manually update the template structure in Finance by selecting **Update structure** on the template editor page.</span></span>

<span data-ttu-id="b4241-110">Pour plus d’informations sur cette fonction, réalisez l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="b4241-110">For more information about this feature, complete the following example.</span></span>

## <a name="example-update-the-structure-of-a-business-document-template"></a><span data-ttu-id="b4241-111">Exemple : Mettre à jour la structure d’un modèle de document commercial</span><span class="sxs-lookup"><span data-stu-id="b4241-111">Example: Update the structure of a business document template</span></span>

<span data-ttu-id="b4241-112">Cet exemple montre comment un administrateur système peut mettre à jour la structure d’un modèle de document commercial dans Finance une fois le modèle modifié dans Office Online.</span><span class="sxs-lookup"><span data-stu-id="b4241-112">This example shows how a system administrator can update the structure of a business document template in Finance after the template is modified in Office Online.</span></span> <span data-ttu-id="b4241-113">Les sections suivantes expliquent les étapes impliquées.</span><span class="sxs-lookup"><span data-stu-id="b4241-113">The following sections explain the steps that are involved.</span></span>

### <a name="prepare-a-business-document-template-for-editing"></a><span data-ttu-id="b4241-114">Préparer un modèle de document commercial à modifier</span><span class="sxs-lookup"><span data-stu-id="b4241-114">Prepare a business document template for editing</span></span>

<span data-ttu-id="b4241-115">Suivez les procédures suivantes dans [Vue d’ensemble de la gestion des documents commerciaux](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="b4241-115">Complete the following procedures in [Business document management overview](er-business-document-management.md).</span></span>

1. [<span data-ttu-id="b4241-116">Configurer les paramètres de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="b4241-116">Configure ER parameters</span></span>](er-business-document-management.md#configure-er-parameters)
2. [<span data-ttu-id="b4241-117">Importer des solutions d’ER</span><span class="sxs-lookup"><span data-stu-id="b4241-117">Import ER solutions</span></span>](er-business-document-management.md#import-er-solutions)
3. [<span data-ttu-id="b4241-118">Activer le module Gestion de document commercial</span><span class="sxs-lookup"><span data-stu-id="b4241-118">Enable Business document management</span></span>](er-business-document-management.md#enable-business-document-management)
4. [<span data-ttu-id="b4241-119">Configurer les paramètres</span><span class="sxs-lookup"><span data-stu-id="b4241-119">Configure parameters</span></span>](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a><span data-ttu-id="b4241-120">Modifier un modèle de document commercial</span><span class="sxs-lookup"><span data-stu-id="b4241-120">Edit a business document template</span></span>

1. <span data-ttu-id="b4241-121">Dans l’espace de travail **Gestion des documents commerciaux**, sélectionnez **Nouveau document**.</span><span class="sxs-lookup"><span data-stu-id="b4241-121">In the **Business document management** workspace, select **New document**.</span></span>
2. <span data-ttu-id="b4241-122">Sur la page **Créer un modèle**, sélectionnez le modèle **Facture en texte libre (exemple ER) (Excel)**.</span><span class="sxs-lookup"><span data-stu-id="b4241-122">On the **Create a new template** page, select the **Free text invoice (ER sample)(Excel)** template.</span></span>
3. <span data-ttu-id="b4241-123">Sélectionner **Créer un document**.</span><span class="sxs-lookup"><span data-stu-id="b4241-123">Select **Create document**.</span></span>
4. <span data-ttu-id="b4241-124">Dans le champ **Titre**, entrez **Exemple FTI Litware**.</span><span class="sxs-lookup"><span data-stu-id="b4241-124">In the **Title** field, enter **FTI sample Litware**.</span></span>
5. <span data-ttu-id="b4241-125">Sélectionnez **OK** pour créer le modèle.</span><span class="sxs-lookup"><span data-stu-id="b4241-125">Select **OK** to create the new template.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4241-126">Si vous n’êtes pas encore connecté à Office Online vous êtes [dirigé vers la page de connexion Office 365](er-business-document-management.md#frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="b4241-126">If you haven't yet signed in to Office Online, you're [directed to the Office 365 sign-in page](er-business-document-management.md#frequently-asked-questions).</span></span> <span data-ttu-id="b4241-127">Pour revenir à votre environnement Finance, sélectionnez le bouton **Précédent** dans votre navigateur.</span><span class="sxs-lookup"><span data-stu-id="b4241-127">To return to your Finance environment, select the **Back** button in your browser.</span></span>

    <span data-ttu-id="b4241-128">Le nouveau modèle est ouvert pour modification dans le contrôle intégré Excel Online sur la page de l’éditeur de modèle.</span><span class="sxs-lookup"><span data-stu-id="b4241-128">The new template is opened for editing in the Excel Online embedded control on the template editor page.</span></span>

<span data-ttu-id="b4241-129">[![Utilisation de l’espace de travail Gestion des documents commerciaux pour commencer à modifier un modèle de document commercial](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span><span class="sxs-lookup"><span data-stu-id="b4241-129">[![Using the Business document management workspace to start to edit a business document template](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span></span>

### <a name="review-the-current-structure-of-the-editable-template"></a><span data-ttu-id="b4241-130">Examiner la structure actuelle du modèle modifiable</span><span class="sxs-lookup"><span data-stu-id="b4241-130">Review the current structure of the editable template</span></span>

1. <span data-ttu-id="b4241-131">Dans Excel Online, sur le ruban, sur l’onglet **Vue**, dans le groupe **Afficher**, sélectionnez **Quadrillage**.</span><span class="sxs-lookup"><span data-stu-id="b4241-131">In Excel Online, on the ribbon, on the **View** tab, in the **Show** group, select **Gridlines**.</span></span>
2. <span data-ttu-id="b4241-132">Dans le modèle modifiable, sélectionnez le rectangle au-dessus du titre du modèle.</span><span class="sxs-lookup"><span data-stu-id="b4241-132">In the editable template, select the rectangle above the template title.</span></span> <span data-ttu-id="b4241-133">Ce rectangle est une image nommée **rptHeaderCompLogo**.</span><span class="sxs-lookup"><span data-stu-id="b4241-133">This rectangle is a picture that is named **rptHeaderCompLogo**.</span></span>
3. <span data-ttu-id="b4241-134">Si le volet **Structure du modèle** est masqué, sélectionnez **Afficher la structure**.</span><span class="sxs-lookup"><span data-stu-id="b4241-134">If the **Template structure** pane is hidden, select **Show structure**.</span></span>
4. <span data-ttu-id="b4241-135">Dans le volet **Structure du modèle**, développer **Rapport \> Facture d’achat \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="b4241-135">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="b4241-136">Notez que, dans la structure du modèle dans Finance, l’élément **rptHeaderCompLogo** est présenté comme un élément enfant de **Rapport \> Facture d’achat \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="b4241-136">Notice that, in the template structure in Finance, the **rptHeaderCompLogo** item is presented as a child item of **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>

<span data-ttu-id="b4241-137">[![Utilisation de l’espace de travail Gestion des documents commerciaux pour examiner la structure actuelle d’un modèle modifiable](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span><span class="sxs-lookup"><span data-stu-id="b4241-137">[![Using the Business document management workspace to review the current structure of an editable template](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a><span data-ttu-id="b4241-138">Mettre à jour la structure d’un modèle de document commercial en supprimant une image</span><span class="sxs-lookup"><span data-stu-id="b4241-138">Update the structure of a business document template by deleting a picture</span></span>

1. <span data-ttu-id="b4241-139">Dans Excel Online, dans le modèle modifiable, sélectionnez l’image **rptHeaderCompLogo**.</span><span class="sxs-lookup"><span data-stu-id="b4241-139">In Excel Online, in the editable template, select the **rptHeaderCompLogo** picture.</span></span>
2. <span data-ttu-id="b4241-140">Suivez l’une de ces étapes pour supprimer l’image sélectionnée du modèle modifiable :</span><span class="sxs-lookup"><span data-stu-id="b4241-140">Follow one of these steps to delete the selected picture from the editable template:</span></span>

    - <span data-ttu-id="b4241-141">Sélectionnez la touche **Supprimer** de votre clavier.</span><span class="sxs-lookup"><span data-stu-id="b4241-141">Select the **Delete** key on your keyboard.</span></span>
    - <span data-ttu-id="b4241-142">Sélectionnez et maintenez (ou cliquez avec le bouton droit) sur l’image, puis sélectionnez **Couper**.</span><span class="sxs-lookup"><span data-stu-id="b4241-142">Select and hold (or right-click) the picture, and then select **Cut**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4241-143">L’élément **rptHeaderCompLogo** est actuellement toujours présent dans la structure du modèle dans Finance, même si l’image n’est plus incluse dans le modèle Excel.</span><span class="sxs-lookup"><span data-stu-id="b4241-143">The **rptHeaderCompLogo** item is currently still present in the template structure in Finance, even though the picture is no longer included in the Excel template.</span></span>

3. <span data-ttu-id="b4241-144">Sélectionnez **Mettre à jour la structure** pour synchroniser la structure du modèle modifiable dans Excel et Finance.</span><span class="sxs-lookup"><span data-stu-id="b4241-144">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
4. <span data-ttu-id="b4241-145">Dans le volet **Structure du modèle**, développer **Rapport \> Facture d’achat \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="b4241-145">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="b4241-146">Notez que l’élément **rptHeaderCompLogo** n’est plus inclus dans la structure du modèle dans Finance.</span><span class="sxs-lookup"><span data-stu-id="b4241-146">Notice that the **rptHeaderCompLogo** item is no longer included in the template structure in Finance.</span></span>

<span data-ttu-id="b4241-147">[![Utilisation de l’espace de travail Gestion des documents commerciaux pour supprimer une image d’un modèle de document commercial](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span><span class="sxs-lookup"><span data-stu-id="b4241-147">[![Using the Business document management workspace to delete a picture from a business document template](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a><span data-ttu-id="b4241-148">Mettre à jour la structure d’un modèle de document commercial en ajoutant une image</span><span class="sxs-lookup"><span data-stu-id="b4241-148">Update the structure of a business document template by adding a picture</span></span>

1. <span data-ttu-id="b4241-149">Dans Excel Online, sur le ruban, sur l’onglet **Insérer**, dans le groupe **Illustrations**, sélectionnez **Image**.</span><span class="sxs-lookup"><span data-stu-id="b4241-149">In Excel Online, on the ribbon, on the **Insert** tab, in the **Illustrations** group, select **Picture**.</span></span>
2. <span data-ttu-id="b4241-150">Sélectionner **Choisir un fichier**, recherchez l’image que vous souhaitez ajouter, sélectionnez-la, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4241-150">Select **Choose file**, browse to the image that you want to add, select it, and then select **OK**.</span></span>
3. <span data-ttu-id="b4241-151">Sélectionnez **Insérer**.</span><span class="sxs-lookup"><span data-stu-id="b4241-151">Select **Insert**.</span></span>
4. <span data-ttu-id="b4241-152">Déplacez la nouvelle image jusqu’à ce qu’elle soit au bon endroit.</span><span class="sxs-lookup"><span data-stu-id="b4241-152">Move the new picture until it's in the correct place.</span></span> <span data-ttu-id="b4241-153">Par défaut, Excel nomme l’image.</span><span class="sxs-lookup"><span data-stu-id="b4241-153">By default, Excel names the picture.</span></span> <span data-ttu-id="b4241-154">Par exemple, il peut nommer l’image **Image 2**.</span><span class="sxs-lookup"><span data-stu-id="b4241-154">For example, it might name the picture **Picture 2**.</span></span>
5. <span data-ttu-id="b4241-155">Sélectionnez **Mettre à jour la structure** pour synchroniser la structure du modèle modifiable dans Excel et Finance.</span><span class="sxs-lookup"><span data-stu-id="b4241-155">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
6. <span data-ttu-id="b4241-156">Dans le volet **Structure du modèle**, développer **Rapport \> Facture d’achat \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="b4241-156">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
7. <span data-ttu-id="b4241-157">Notez que la nouvelle image est à présent incluse en tant qu’élément dans la structure du modèle dans Finance.</span><span class="sxs-lookup"><span data-stu-id="b4241-157">Notice that the new picture is now included as an item in the template structure in Finance.</span></span>

<span data-ttu-id="b4241-158">[![Utilisation de l’espace de travail Gestion des documents commerciaux pour ajouter une image à un modèle de document commercial](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span><span class="sxs-lookup"><span data-stu-id="b4241-158">[![Using the Business document management workspace to add a picture to a business document template](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span></span>

## <a name="related-links"></a><span data-ttu-id="b4241-159">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="b4241-159">Related links</span></span>

[<span data-ttu-id="b4241-160">Vue d’ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="b4241-160">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="b4241-161">Vue d’ensemble de la gestion de document commercial</span><span class="sxs-lookup"><span data-stu-id="b4241-161">Business document management overview</span></span>](er-business-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]