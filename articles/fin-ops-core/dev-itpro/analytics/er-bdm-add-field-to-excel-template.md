---
title: Ajouter de nouveaux champs à un modèle de document commercial dans Microsoft Excel
description: Cette rubrique fournit des informations sur l’ajout de nouveaux champs à un modèle de document commercial dans Microsoft Excel à l’aide de la fonction de gestion de documents commerciaux.
author: NickSelin
ms.date: 11/15/2019
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
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 991fe4ea56a2726c5df835cfc90a390cef2d5df5
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751128"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a><span data-ttu-id="ded28-103">Ajouter de nouveaux champs à un modèle de document commercial dans Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="ded28-103">Add new fields to a business document template in Microsoft Excel</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ded28-104">Vous pouvez ajouter de nouveaux champs à un modèle utilisé pour générer des documents commerciaux dans le format Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="ded28-104">You can add new fields to a template that is used to generate business documents in Microsoft Excel format.</span></span> <span data-ttu-id="ded28-105">Ces champs peuvent être ajoutés comme espaces réservés qui sont utilisés pour compléter les documents générés avec les informations requises depuis l’application.</span><span class="sxs-lookup"><span data-stu-id="ded28-105">These fields can be added as placeholders that are used to fill generated documents with required information from the application.</span></span> <span data-ttu-id="ded28-106">Pour chaque champ que vous ajoutez, vous pouvez également préciser un lien vers les sources de données afin de préciser quelles données d’application seront saisies dans le champ lorsque le modèle est utilisé pour générer des documents commerciaux.</span><span class="sxs-lookup"><span data-stu-id="ded28-106">For every field that you add, you can also specify a binding to the data sources, to specify what application data will be entered in the field when the template is used to generate business documents.</span></span>

<span data-ttu-id="ded28-107">Pour en savoir plus sur cette fonctionnalité, exécutez l’exemple décrit dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ded28-107">To learn more about this feature, complete the example in this topic.</span></span> <span data-ttu-id="ded28-108">Cet exemple présente comment mettre à jour un modèle pour compléter les champs dans les formulaires de facture financière qui sont générés.</span><span class="sxs-lookup"><span data-stu-id="ded28-108">This example shows how to update a template to fill in the fields in free text invoice forms that are generated.</span></span>

## <a name="configure-business-document-management-to-edit-templates"></a><span data-ttu-id="ded28-109">Configurer le module Gestion de document commercial pour modifier les modèles</span><span class="sxs-lookup"><span data-stu-id="ded28-109">Configure Business document management to edit templates</span></span>

<span data-ttu-id="ded28-110">Comme le module Gestion de document commercial repose sur la structure [Vue d’ensemble de la gestion des états électroniques](general-electronic-reporting.md), vous devez configurer les paramètres des états électroniques et du module Gestion de document commercial avant de pouvoir commencer à utiliser ce dernier.</span><span class="sxs-lookup"><span data-stu-id="ded28-110">Because Business document management (BDM) is built on top of the [Electronic reporting (ER) overview](general-electronic-reporting.md) framework, you must configure the required ER and BDM parameters before you can start to work with BDM.</span></span>

1.  <span data-ttu-id="ded28-111">Connectez-vous à l’instance de Microsoft Dynamics 365 Finance en tant qu’administrateur système.</span><span class="sxs-lookup"><span data-stu-id="ded28-111">Sign in to the instance of Microsoft Dynamics 365 Finance as the system administrator.</span></span>
2.  <span data-ttu-id="ded28-112">Suivez les étapes suivantes de l’exemple de la rubrique [Vue d’ensemble du module Gestion de document commercial](er-business-document-management.md) :</span><span class="sxs-lookup"><span data-stu-id="ded28-112">Complete the following steps of the example in the [Business document management overview](er-business-document-management.md) topic:</span></span>

    1.  <span data-ttu-id="ded28-113">Configurez les paramètres de gestion des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="ded28-113">Configure ER parameters.</span></span>
    2.  <span data-ttu-id="ded28-114">Activez le module Gestion de document commercial.</span><span class="sxs-lookup"><span data-stu-id="ded28-114">Turn on BDM.</span></span>

<span data-ttu-id="ded28-115">Vous pouvez maintenant commencer à utiliser le module Gestion de document commercial pour modifier les modèles de document commercial.</span><span class="sxs-lookup"><span data-stu-id="ded28-115">You can now start to use BDM to edit business document templates.</span></span>

## <a name="import-er-solutions-that-contain-a-template"></a><span data-ttu-id="ded28-116">Importez les solutions de gestion des états électroniques qui contiennent un modèle.</span><span class="sxs-lookup"><span data-stu-id="ded28-116">Import ER solutions that contain a template</span></span>

<span data-ttu-id="ded28-117">L’exemple de cette procédure utilise la solution de gestion des états électroniques publiée officiellement.</span><span class="sxs-lookup"><span data-stu-id="ded28-117">The example in this procedure uses the officially published ER solution.</span></span> <span data-ttu-id="ded28-118">Vous devez importer les configurations de gestion des états électroniques de cette solution dans votre instance actuelle de Finance.</span><span class="sxs-lookup"><span data-stu-id="ded28-118">You must import the ER configurations of this solution into your current instance of Finance.</span></span>

<span data-ttu-id="ded28-119">La configuration du format de gestion des états électroniques **Facturation financière (Excel)** de cette solution contient le modèle de document commercial au format Excel qui peut être modifié à l’aide du module Gestion de document commercial.</span><span class="sxs-lookup"><span data-stu-id="ded28-119">The **Free text invoice (Excel)** ER format configuration of this solution contains the business document template in Excel format that can be edited by using BDM.</span></span> <span data-ttu-id="ded28-120">Importez la dernière version de cette configuration du format de gestion des états électroniques depuis Microsoft Dynamics Lifecycle Service (LCS).</span><span class="sxs-lookup"><span data-stu-id="ded28-120">Import the latest version of this ER format configuration from Microsoft Dynamics Lifecycle Service (LCS).</span></span> <span data-ttu-id="ded28-121">Le modèle de données de gestion des états électroniques correspondants et les configurations de mise en correspondance du modèle de gestion des états électroniques seront importés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="ded28-121">The corresponding ER data model and ER model mapping configurations will be imported automatically.</span></span>

<span data-ttu-id="ded28-122">Pour plus d’informations sur la manière d’importer des configurations de gestion des états électroniques, voir [Gérer le cycle de vie de la configuration des états électroniques](general-electronic-reporting-manage-configuration-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="ded28-122">For more information about how to import ER configurations, see [Manage the ER configuration lifecycle](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

![Page de bibliothèque d’actifs partagés LCS](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a><span data-ttu-id="ded28-124">Modifiez le modèle de solution de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="ded28-124">Edit the ER solution template</span></span>

1.  <span data-ttu-id="ded28-125">Connectez-vous en tant qu’utilisateur avec accès à l’espace de travail **Gestion de document commercial**.</span><span class="sxs-lookup"><span data-stu-id="ded28-125">Sign in as a user who has access to the **Business document management** workspace.</span></span>
2.  <span data-ttu-id="ded28-126">Ouvrez l’espace de travail du module **Gestion de document commercial**.</span><span class="sxs-lookup"><span data-stu-id="ded28-126">Open the **Business document management** workspace.</span></span>

    ![Espace de travail du module Gestion de document commercial](./media/BDM-AddFldExcel-Workspace.png)

3.  <span data-ttu-id="ded28-128">Dans la grille, sélectionnez le modèle **Facture financière (Excel)**.</span><span class="sxs-lookup"><span data-stu-id="ded28-128">In the grid, select the **Free text invoice (Excel)** template.</span></span>
4.  <span data-ttu-id="ded28-129">Dans le volet droit, sélectionnez **Nouveau modèle** pour créer un modèle basé sur le modèle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ded28-129">In the right pane, select **New template** to create a new template that is based on the selected template.</span></span>
5.  <span data-ttu-id="ded28-130">Dans le champ **Titre**, entrez **Facture financière (Excel) Contoso** comme titre du nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="ded28-130">In the **Title** field, enter **Free text invoice (Excel) Contoso** as the title of the new template.</span></span>
6.  <span data-ttu-id="ded28-131">Cliquez sur **OK** pour confirmer le début du processus de modification.</span><span class="sxs-lookup"><span data-stu-id="ded28-131">Select **OK** to confirm the start of the editing process.</span></span>

<span data-ttu-id="ded28-132">La page Éditeur de modèle BDM s’affiche.</span><span class="sxs-lookup"><span data-stu-id="ded28-132">The BDM template editor page appears.</span></span> <span data-ttu-id="ded28-133">Vous pouvez utiliser Microsoft 365 pour modifier le modèle sélectionné en ligne dans le contrôle incorporé.</span><span class="sxs-lookup"><span data-stu-id="ded28-133">You can use Microsoft 365 to edit the selected template online in the embedded control.</span></span>

![Page Éditeur de modèle BDM](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a><span data-ttu-id="ded28-135">Ajoutez le libellé pour un nouveau champ au modèle</span><span class="sxs-lookup"><span data-stu-id="ded28-135">Add the label for a new field to the template</span></span>

1.  <span data-ttu-id="ded28-136">Sur la page Éditeur de modèle BDM, sur le ruban Excel, sur l’onglet **Afficher**, sélectionnez les cases **En-têtes et grilles de ligne** pour le modèle Excel modifiable.</span><span class="sxs-lookup"><span data-stu-id="ded28-136">On the BDM template editor page, on the Excel ribbon, on the **View** tab, select the **Headings and Gridlines** check boxes for the editable Excel template.</span></span>

    ![Cases à cocher En-têtes et Lignes de grille sélectionnées](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  <span data-ttu-id="ded28-138">Sélectionnez les cellules **E8:F8**.</span><span class="sxs-lookup"><span data-stu-id="ded28-138">Select cells **E8:F8**.</span></span>
3.  <span data-ttu-id="ded28-139">Dans le ruban d’Excel, sur l’onglet **Accueil**, sélectionnez **Fusionner et centrer** pour fusionner les cellules sélectionnées en une cellule fusionnée **E8:F8**.</span><span class="sxs-lookup"><span data-stu-id="ded28-139">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **E8:F8** cell.</span></span>
4.  <span data-ttu-id="ded28-140">Dans la cellule fusionnée **E8:F8**, saisissez **URL**.</span><span class="sxs-lookup"><span data-stu-id="ded28-140">In the merged cell **E8:F8**, enter **URL**.</span></span>
5.  <span data-ttu-id="ded28-141">Sélectionnez la cellule fusionnée **E7:F7**, sélectionnez **Reproduire la mise en forme**, puis sélectionnez la cellule fusionnée **E8:F8** pour la formater de la même manière que la cellule fusionnée **E7:F7**.</span><span class="sxs-lookup"><span data-stu-id="ded28-141">Select merged cell **E7:F7**, select **Format painter**, and then select merged cell **E8:F8** to format it in the same way as merged cell **E7:F7**.</span></span>

    ![Nouveau libellé de champ ajouté au modèle](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a><span data-ttu-id="ded28-143">Formater le modèle pour réserver l’espace pour un nouveau champ</span><span class="sxs-lookup"><span data-stu-id="ded28-143">Format the template to reserve space for a new field</span></span>

1.  <span data-ttu-id="ded28-144">Sur la page Éditeur de modèle BDM, sélectionnez la cellule fusionnée **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="ded28-144">On the BDM template editor page, select merged cell **G8:H8**.</span></span>
2.  <span data-ttu-id="ded28-145">Dans le ruban d’Excel, sur l’onglet **Accueil**, sélectionnez **Fusionner et centrer** pour fusionner les cellules sélectionnées en une cellule fusionnée **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="ded28-145">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **G8:H8** cell.</span></span>
3.  <span data-ttu-id="ded28-146">Sélectionnez la cellule fusionnée **G7:H7**, sélectionnez **Reproduire la mise en forme**, puis sélectionnez la cellule fusionnée **G8:H8** pour la formater de la même manière que la cellule fusionnée **G7:H7**.</span><span class="sxs-lookup"><span data-stu-id="ded28-146">Select merged cell **G7:H7**, select **Format painter**, and then select merged cell **G8:H8** to format it in the same way as merged cell **G7:H7**.</span></span>

    ![Espace réservé pour le nouveau champ](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  <span data-ttu-id="ded28-148">Dans le champ **Nom**, sélectionnez **CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="ded28-148">In the **Name** box field, select **CompanyInfo**.</span></span>

    <span data-ttu-id="ded28-149">La plage **CompanyInfo** du modèle Excel actuel contient tous les champs qui sont utilisés pour remplir l’en-tête d’un état généré avec les détails de la société actuelle en tant que vendeur.</span><span class="sxs-lookup"><span data-stu-id="ded28-149">The **CompanyInfo** range of the current Excel template holds all the fields that are used to fill the header of a generated report with the details of the current company as a seller party.</span></span>

    ![Plage CompanyInfo sélectionnée](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a><span data-ttu-id="ded28-151">Ajouter un nouveau champ au modèle</span><span class="sxs-lookup"><span data-stu-id="ded28-151">Add a new field to the template</span></span>

1.  <span data-ttu-id="ded28-152">Dans la page **Éditeur de modèle BDM**, dans le volet Actions, sélectionnez **Afficher le format**.</span><span class="sxs-lookup"><span data-stu-id="ded28-152">On the **BDM template editor** page, on the Action Pane, select **Show format**.</span></span>
2.  <span data-ttu-id="ded28-153">Dans le volet **Structure de modèle**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ded28-153">In the **Template structure** pane, select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ded28-154">Vous devez ajuster la section du modèle à utiliser comme nouveau champ.</span><span class="sxs-lookup"><span data-stu-id="ded28-154">You must adjust the section of the template that you want to use as a new field.</span></span> <span data-ttu-id="ded28-155">Vous avez déjà apporté cet ajustement en formatant la cellule fusionnée **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="ded28-155">You already made this adjustment by formatting merged cell **G8:H8**.</span></span>

    ![Ajout d’un nouveau champ au modèle](./media/BDM-AddFldExcel-AddCell.png)

3.  <span data-ttu-id="ded28-157">Sélectionnez **Excel\Cellule** pour ajouter un nouveau champ comme cellule dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="ded28-157">Select **Excel\Cell** to add a new field as a cell in the template.</span></span>

    <span data-ttu-id="ded28-158">Vous pouvez sélectionner **Excel\Plage** si vous souhaitez ajouter une plage au modèle.</span><span class="sxs-lookup"><span data-stu-id="ded28-158">You can select **Excel\Range** if you want to add a new range to the template.</span></span> <span data-ttu-id="ded28-159">La plage saisie peut contenir plusieurs cellules.</span><span class="sxs-lookup"><span data-stu-id="ded28-159">The range that is entered can contain multiple cells.</span></span> <span data-ttu-id="ded28-160">Vous pouvez ajouter ces cellules ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="ded28-160">You can add these cells later.</span></span>
    
    <span data-ttu-id="ded28-161">Observez que le composant modèle **CompanyInfo** est automatiquement sélectionné dans le volet **Structure du modèle**, car il s’agit du composant parent le plus approprié dans la structure de modèle actuelle pour le champ que vous ajoutez.</span><span class="sxs-lookup"><span data-stu-id="ded28-161">Notice that the **CompanyInfo** template component, is automatically selected in the **Template structure** pane, because it's the most suitable parent component in the current template structure for the field that you're adding.</span></span>
    
4.  <span data-ttu-id="ded28-162">Dans le champ **Plage Excel**, entrez **CompanyURL_Value**.</span><span class="sxs-lookup"><span data-stu-id="ded28-162">In the **Excel range** field, enter **CompanyURL_Value**.</span></span>
5.  <span data-ttu-id="ded28-163">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ded28-163">Select **OK**.</span></span>

    ![Champ CompanyURL_Value ajouté à la structure de modèle](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  <span data-ttu-id="ded28-165">Dans le volet **Structure du modèle**, sélectionnez le bouton représentant les points de suspension (…), et sélectionnez **Afficher les liaisons**.</span><span class="sxs-lookup"><span data-stu-id="ded28-165">In the **Template structure** pane, select the ellipsis button (...), and then select **Show bindings**.</span></span>

    ![Afficher les liaisons sélectionnées](./media/BDM-AddFldExcel-ShowBindings.png)

    <span data-ttu-id="ded28-167">Le volet **Structure du modèle** affiche maintenant les sources de données disponibles au format de gestion des états électroniques sous-jacents.</span><span class="sxs-lookup"><span data-stu-id="ded28-167">The **Template structure** pane now shows the data sources that are available in the underlying ER format.</span></span>

7.  <span data-ttu-id="ded28-168">Sélectionnez **CompanyInfo_Value** comme le champ que vous prévoyez de lier à une source de données du format de gestion des états électroniques sous-jacents.</span><span class="sxs-lookup"><span data-stu-id="ded28-168">Select **CompanyInfo_Value** as the field that you plan to bind to a data source of the underlying ER format.</span></span>
8.  <span data-ttu-id="ded28-169">Dans la section **Sources de données** du volet **Structure du modèle**, développez **Modèle \> InvoiceBase \> CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="ded28-169">In the **Data sources** section of the **Template structure** pane, expand **Model \> InvoiceBase \> CompanyInfo**.</span></span>
9.  <span data-ttu-id="ded28-170">Sous **CompanyInfo**, sélectionnez l’élément **WebsiteURI**.</span><span class="sxs-lookup"><span data-stu-id="ded28-170">Under **CompanyInfo**, select the **WebsiteURI** item.</span></span>

    ![Élément WebsiteURI sélectionné](./media/BDM-AddFldExcel-BindURL.png)

10. <span data-ttu-id="ded28-172">Sélectionnez **Lier**.</span><span class="sxs-lookup"><span data-stu-id="ded28-172">Select **Bind**.</span></span>
11. <span data-ttu-id="ded28-173">Dans le volet **Structure de modèle**, sélectionnez **Enregistrer**, puis fermez la page Éditeur de modèle BDM.</span><span class="sxs-lookup"><span data-stu-id="ded28-173">In the **Template structure** pane, select **Save**, and then close the BDM template editor page.</span></span>

<span data-ttu-id="ded28-174">Dans l’espace de travail **Gestion de document commercial**, l’onglet **Modèle** dans le volet de droit présente le modèle mis à jour.</span><span class="sxs-lookup"><span data-stu-id="ded28-174">In the **Business document management** workspace, the **Template** tab in the right pane shows the updated template.</span></span> <span data-ttu-id="ded28-175">Dans la grille, notez que le champ **Statut** pour le modèle modifié a été modifié sur **Brouillon**, et le champ **Révision** n’est plus vide.</span><span class="sxs-lookup"><span data-stu-id="ded28-175">In the grid, notice that the **Status** field for the edited template has been changed to **Draft**, and the **Revision** field is no longer blank.</span></span> <span data-ttu-id="ded28-176">Ces modifications indiquent que le processus de modification de ce modèle a commencé.</span><span class="sxs-lookup"><span data-stu-id="ded28-176">These changes indicate that the process of editing this template has been started.</span></span>

![Modèle modifié dans l’espace de travail Gestion de document commercial](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a><span data-ttu-id="ded28-178">Revoir les paramètres de société</span><span class="sxs-lookup"><span data-stu-id="ded28-178">Review company settings</span></span>

1.  <span data-ttu-id="ded28-179">Accédez à **Administration d’organisation \> Organisations \> Entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="ded28-179">Go to **Organization administration \> Organizations \> Legal entities**.</span></span>
2.  <span data-ttu-id="ded28-180">Dans l’organisateur **Informations de contact**, vérifiez que l’URL de la société est entrée.</span><span class="sxs-lookup"><span data-stu-id="ded28-180">On the **Contact information** FastTab, verify that the company URL is entered.</span></span>

![URL de société entrée sur la page Entités juridiques](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a><span data-ttu-id="ded28-182">Générer des documents commerciaux pour tester le modèle mis à jour</span><span class="sxs-lookup"><span data-stu-id="ded28-182">Generate business documents to test the updated template</span></span>

1.  <span data-ttu-id="ded28-183">Dans l’application, modifiez la société **USMF**, puis accédez à **Comptabilité client \> Factures \> Toutes les factures financières**.</span><span class="sxs-lookup"><span data-stu-id="ded28-183">In the application, change the company to **USMF**, and go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>
2.  <span data-ttu-id="ded28-184">Sélectionnez la facture **FTI-00000002**, puis sélectionnez **Gestion de l’impression**.</span><span class="sxs-lookup"><span data-stu-id="ded28-184">Select invoice **FTI-00000002**, and then select **Print management**.</span></span>
3.  <span data-ttu-id="ded28-185">Dans le volet gauche, développez **Module – Comptabilité client \> Documents \> Facture financière**.</span><span class="sxs-lookup"><span data-stu-id="ded28-185">In the left pane, expand **Module - accounts receivable \> Documents \> Free text invoice**.</span></span>
4.  <span data-ttu-id="ded28-186">Sous **Facture financière**, sélectionnez le niveau **Document d’origine** pour préciser le champ des factures à traiter.</span><span class="sxs-lookup"><span data-stu-id="ded28-186">Under **Free text invoice**, select the **Original document** level to specify the scope of invoices for processing.</span></span>
5.  <span data-ttu-id="ded28-187">Dans le volet droit, dans le champ **Format de l’état**, sélectionnez le modèle **Facture financière (Excel) Contoso** pour le niveau spécifié de document.</span><span class="sxs-lookup"><span data-stu-id="ded28-187">In the right pane, in the **Report format** field, select the **Free text invoice (Excel) Contoso** template for the specified document level.</span></span>

    ![Modèle Facture financière (Excel) Contoso sélectionné](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  <span data-ttu-id="ded28-189">Appuyez sur **Échap** pour fermer la page actuelle.</span><span class="sxs-lookup"><span data-stu-id="ded28-189">Press **Esc** to close the current page.</span></span>
7.  <span data-ttu-id="ded28-190">Sélectionnez **Imprimer \> Sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="ded28-190">Select **Print \> Selected**.</span></span>
8.  <span data-ttu-id="ded28-191">Téléchargez le document généré, puis rouvrez-le dans Excel.</span><span class="sxs-lookup"><span data-stu-id="ded28-191">Download the generated document, and open it in Excel.</span></span>

    ![Facture financière dans Excel](./media/BDM-AddFldExcel-PreviewReport.png)

<span data-ttu-id="ded28-193">Le modèle révisé est utilisé pour générer l’état de facture financière pour l’article sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ded28-193">The modified template is used to generate the free text invoice report for the selected item.</span></span> <span data-ttu-id="ded28-194">Pour analyser la manière dont cet état est affecté par les modifications apportées au modèle, vous pouvez exécuter cet état dans une session de l’application immédiatement après avoir modifié le modèle dans une autre session de l’application.</span><span class="sxs-lookup"><span data-stu-id="ded28-194">To analyze how this report is affected by changes that you make to the template, run the report in one application session immediately after you change the template in another application session.</span></span>

## <a name="related-links"></a><span data-ttu-id="ded28-195">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="ded28-195">Related links</span></span>

[<span data-ttu-id="ded28-196">Vue d’ensemble des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="ded28-196">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="ded28-197">Vue d’ensemble de la gestion de document commercial</span><span class="sxs-lookup"><span data-stu-id="ded28-197">Business document management overview</span></span>](er-business-document-management.md)

[<span data-ttu-id="ded28-198">Concevoir une configuration pour générer des états au format OPENXML</span><span class="sxs-lookup"><span data-stu-id="ded28-198">Design a configuration for generating reports in OPENXML format</span></span>](tasks/er-design-reports-openxml-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]