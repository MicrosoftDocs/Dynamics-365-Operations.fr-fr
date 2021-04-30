---
title: Interface utilisateur de style Microsoft Office dans la gestion des documents commerciaux
description: Cette rubrique explique comment utiliser la nouvelle interface utilisateur dans la fonctionnalité de gestion des documents commerciaux de l’infrastructure de gestion des états électroniques (ER).
author: v-anamir
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e6c5081f71a18dfac83b7aea950395436b42f50e
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881034"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a><span data-ttu-id="6e587-103">Interface utilisateur de style Microsoft Office dans la gestion des documents commerciaux</span><span class="sxs-lookup"><span data-stu-id="6e587-103">Microsoft Office-style user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6e587-104">La gestion des documents commerciaux permet aux utilisateurs professionnels de modifier des modèles de document commercial à l’aide d’un service Microsoft 365 ou de l’application de bureau Microsoft Office appropriée.</span><span class="sxs-lookup"><span data-stu-id="6e587-104">Business document management lets business users edit business document templates by using a Microsoft 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="6e587-105">Les modifications peuvent inclure des modifications de conception ou de nouveaux déploiements, ou les utilisateurs peuvent ajouter des espaces réservés pour inclure des données supplémentaires sans avoir à modifier le code source.</span><span class="sxs-lookup"><span data-stu-id="6e587-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="6e587-106">Pour plus d’informations sur l’utilisation de la gestion des documents commerciaux, consultez [Vue d’ensemble de la gestion de document commercial](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="6e587-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="6e587-107">La nouvelle interface utilisateur (UI) est plus claire et plus confortable à utiliser.</span><span class="sxs-lookup"><span data-stu-id="6e587-107">The new user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="6e587-108">La zone **Document commercial** affiche uniquement les modèles disponibles pour le fournisseur actuel.</span><span class="sxs-lookup"><span data-stu-id="6e587-108">The **Business document** area shows only the templates that are available for the current provider.</span></span> <span data-ttu-id="6e587-109">Dans l'interface utilisateur précédente, l'onglet **Modèle** répertoriait tous les modèles disponibles pour tous les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="6e587-109">In the previous UI, the **Template** tab listed all the templates that were available for any providers.</span></span> <span data-ttu-id="6e587-110">Elle présentait également tous les modèles créés et modifiés par tous les utilisateurs ayant le même rôle.</span><span class="sxs-lookup"><span data-stu-id="6e587-110">It also showed all the templates that were created and edited by any user who had the same role.</span></span>

<span data-ttu-id="6e587-111">Vous pouvez utiliser le bouton **Nouveau document** pour créer et modifier un modèle dans une configuration au format de gestion des états électroniques d'un autre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6e587-111">You can use the **New document** button to create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="6e587-112">Dans l’exemple de cette rubrique, le fournisseur est Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e587-112">In the example in this topic, the provider is Microsoft.</span></span> <span data-ttu-id="6e587-113">Vous pouvez également créer un modèle en chargeant votre propre modèle au format Excel.</span><span class="sxs-lookup"><span data-stu-id="6e587-113">Alternatively, you can create a template by uploading your own template in Excel format.</span></span>


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

<span data-ttu-id="6e587-114">LA vidéo [Créer un nouveau document commercial à l'aide de la gestion des documents commerciaux](https://youtu.be/gAIYl-mM_pw) (ci-dessus) est incluse dans la [playlist Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.</span><span class="sxs-lookup"><span data-stu-id="6e587-114">The [Create a new business document using Business document management](https://youtu.be/gAIYl-mM_pw) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="6e587-115">Rendre disponible la nouvelle interface utilisateur de document dans la gestion des documents commerciaux</span><span class="sxs-lookup"><span data-stu-id="6e587-115">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="6e587-116">Pour commencer à utiliser la nouvelle interface utilisateur de document dans la gestion des documents commerciaux, vous devez activer la fonctionnalité **Expérience d’interface utilisateur de type bureau pour la gestion des documents commerciaux** dans l’espace de travail **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="6e587-116">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="6e587-117">Suivez ces étapes pour activer cette fonctionnalité pour toutes les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="6e587-117">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="6e587-118">Dans l’espace de travail **Gestion des fonctionnalités**, dans l’onglet **Tout**, sélectionnez la fonctionnalité **Expérience d’interface utilisateur de type bureau pour la gestion des documents commerciaux** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="6e587-118">In the **Feature management** workspace, on the **All** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="6e587-119">Sélectionnez **Activer maintenant** pour activer la fonctionnalité sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6e587-119">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="6e587-120">Actualisez la page pour accéder à la nouvelle fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="6e587-120">Refresh the page to access the new feature.</span></span>

## <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="6e587-121">Modifier des modèles qui sont détenus par d’autres fournisseurs</span><span class="sxs-lookup"><span data-stu-id="6e587-121">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="6e587-122">Dans l’espace de travail **Gestion des documents commerciaux**, sélectionnez **Nouveau document**.</span><span class="sxs-lookup"><span data-stu-id="6e587-122">In the **Business document management** workspace, select **New document**.</span></span>

    ![Espace de travail du module Gestion de document commercial](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="6e587-124">Dans l'onglet **Sélectionner**, choisissez le document à utiliser comme modèle, puis sélectionnez **Créer un document**.</span><span class="sxs-lookup"><span data-stu-id="6e587-124">On the **Select** tab, select the document to use as a template, and then select **Create document**.</span></span>

    ![Boîte de dialogue Documents commerciaux](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="6e587-126">Dans la nouvelle boîte de dialogue, dans le champ **Titre**, modifiez le titre selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6e587-126">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="6e587-127">Le texte du titre est utilisé pour nommer la nouvelle mconfiguration du format ER qui est automatiquement créée.</span><span class="sxs-lookup"><span data-stu-id="6e587-127">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="6e587-128">La version temporaire de cette configuration (**Copie d’État FTI client (GER)**) qui contient le modèle modifié et sera automatiquement utilisée pour exécuter ce format ER pour l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="6e587-128">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="6e587-129">Le modèle d’origine de la configuration du format ER de base sera utilisé pour exécuter ce format ER pour tout autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6e587-129">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="6e587-130">Dans le champ **Nom**, modifiez le nom de la première révision du modèle modifiable qui sera automatiquement créé.</span><span class="sxs-lookup"><span data-stu-id="6e587-130">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="6e587-131">Dans le champ **Commentaire**, mettez à jour les remarques de la révision du modèle modifiable qui sera créée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="6e587-131">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="6e587-132">Cliquez sur **OK** pour confirmer le début du processus de modification.</span><span class="sxs-lookup"><span data-stu-id="6e587-132">Select **OK** to confirm the start of the editing process.</span></span>

    ![Boîte de dialogue de création de document](./media/BDM_overview_new_template3.png)

<span data-ttu-id="6e587-134">Le bouton **Nouveau document** est utilisé pour créer et modifier un modèle dans une configuration au format ER fournie par un autre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6e587-134">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="6e587-135">Dans cet exemple, le fournisseur est Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e587-135">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="6e587-136">Lorsque vous sélectionnez **Nouveau document**, vous pouvez voir tous les modèles qui sont détenus par les fournisseurs actuels et autres fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="6e587-136">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="6e587-137">Après que vous avez sélectionné le modèle, il est ouvert pour modification.</span><span class="sxs-lookup"><span data-stu-id="6e587-137">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="6e587-138">Le modèle modifié est ensuite stocké dans une nouvelle configuration de format ER qui est automatiquement générée.</span><span class="sxs-lookup"><span data-stu-id="6e587-138">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a><span data-ttu-id="6e587-139">Charger un modèle qui utilise un format Excel existant</span><span class="sxs-lookup"><span data-stu-id="6e587-139">Upload a template that uses an existing Excel format</span></span>
<span data-ttu-id="6e587-140">Suivez ces étapes pour fournir les informations requises avant de charger un modèle.</span><span class="sxs-lookup"><span data-stu-id="6e587-140">Follow these steps to provide required information before you upload a template.</span></span>

1. <span data-ttu-id="6e587-141">Dans l’espace de travail **Gestion des documents commerciaux**, sélectionnez **Nouveau document**.</span><span class="sxs-lookup"><span data-stu-id="6e587-141">In the **Business document management** workspace, select **New document**.</span></span>

    ![Espace de travail du module Gestion de document commercial](./media/BDM_overview_new_template1.png)
    
2. <span data-ttu-id="6e587-143">Sur la page **Créer un nouveau modèle**, sur l'onglet **Charger**, sur l'onglet **Modèle**, sélectionnez **Parcourir** pour rechercher et sélectionner le fichier Excel que vous souhaitez utiliser comme modèle.</span><span class="sxs-lookup"><span data-stu-id="6e587-143">On the **Create a new template** page, on the **Upload** tab, on the **Template** tab, select **Browse** to find and select the Excel file that you want to use as a template.</span></span> <span data-ttu-id="6e587-144">Dans la section **Modèle**, les champs **Titre** et **Description** sont automatiquement remplis.</span><span class="sxs-lookup"><span data-stu-id="6e587-144">In the **Template** section, the **Title** and **Description** fields are automatically filled in.</span></span> <span data-ttu-id="6e587-145">Ils spécifient le nom et la description de la nouvelle configuration de format ER qui est automatiquement créée.</span><span class="sxs-lookup"><span data-stu-id="6e587-145">They specify the name and description of the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="6e587-146">Vous pouvez modifier ces champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6e587-146">You can edit these fields as you require.</span></span>
3. <span data-ttu-id="6e587-147">Dans la section **Type de document**, dans le champ **Nom**, indiquez le type de document commercial.</span><span class="sxs-lookup"><span data-stu-id="6e587-147">In the **Document Type** section, in the **Name** field, specify the type of business document.</span></span> <span data-ttu-id="6e587-148">Cette valeur sera utilisée pour rechercher la source de données correcte (c'est-à-dire la configuration du modèle ER).</span><span class="sxs-lookup"><span data-stu-id="6e587-148">This value will be used to search the correct data source (that is, the ER model configuration).</span></span>

    ![Onglet Modèle](./media/BDM_overview_new_UI_import_21.jpg)

4. <span data-ttu-id="6e587-150">Dans l'onglet **Source de données**, sur le raccourci **Filtre**, sélectionnez **Appliquer le filtre**.</span><span class="sxs-lookup"><span data-stu-id="6e587-150">On the **Data source** tab, on the **Filter** FastTab, select **Apply filter**.</span></span> <span data-ttu-id="6e587-151">Dans la section **Source de données**, le champ **Nom** est automatiquement rempli, ou vous pouvez sélectionner manuellement une valeur.</span><span class="sxs-lookup"><span data-stu-id="6e587-151">In the **Data source** section, the **Name** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="6e587-152">Vous pouvez utiliser le filtre pour rechercher le nom de source de données approprié par nom, description, code pays/région et type de document commercial.</span><span class="sxs-lookup"><span data-stu-id="6e587-152">You can use the filter to search for the appropriate data source name by name, description, country/region code, and business document type.</span></span>

    ![Onglet Source de données](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > <span data-ttu-id="6e587-154">Le raccourci **Filtre** est utilisé pour rechercher la source de données correcte (c'est-à-dire la configuration du modèle ER).</span><span class="sxs-lookup"><span data-stu-id="6e587-154">The **Filter** FastTab is used to search the correct data source (that is, the ER model configuration).</span></span> <span data-ttu-id="6e587-155">Vous pouvez modifier tous les champs de filtre pour trouver la source de données la plus appropriée pour le document que vous chargez.</span><span class="sxs-lookup"><span data-stu-id="6e587-155">You can edit all filter fields to find the most appropriate data source for the document that you're uploading.</span></span>
    > 
    > <span data-ttu-id="6e587-156">Les conditions du raccourci **Filtre** sont utilisées comme conditions **OU**.</span><span class="sxs-lookup"><span data-stu-id="6e587-156">The conditions on the **Filter** FastTab are used as **OR** conditions.</span></span>
    
5. <span data-ttu-id="6e587-157">Dans l’onglet **Mise en correspondance**, sélectionnez **Détection automatique**.</span><span class="sxs-lookup"><span data-stu-id="6e587-157">On the **Mapping** tab, select **Auto detect**.</span></span> <span data-ttu-id="6e587-158">Le champ **Définition racine** est automatiquement rempli, ou vous pouvez sélectionner manuellement une valeur.</span><span class="sxs-lookup"><span data-stu-id="6e587-158">The **Root definition** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="6e587-159">Cet onglet affiche la mise en correspondance finale des éléments provenant du modèle-maquette et du modèle.</span><span class="sxs-lookup"><span data-stu-id="6e587-159">This tab shows the end mapping for the elements from the template and the model.</span></span>

    ![Onglet Mise en correspondance](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > <span data-ttu-id="6e587-161">Le mappage de la section **Structure du modèle** utilise la correspondance complète des étiquettes ou des descriptions de la source de données dans la langue de l'utilisateur, et dans le nom de la cellule dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="6e587-161">The mapping in the **Template structure** section uses the full match of the labels or descriptions in the data source in the user's language, and in the cell name in the template.</span></span>

6. <span data-ttu-id="6e587-162">Sélectionnez **Créer un document** pour confirmer que vous souhaitez créer un modèle et démarrer le processus d'édition.</span><span class="sxs-lookup"><span data-stu-id="6e587-162">Select **Create document** to confirm that you want to create a template and start the editing process.</span></span>

<span data-ttu-id="6e587-163">Pour plus d’informations, voir [Vue d’ensemble de la gestion de document commercial](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="6e587-163">For more information, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="6e587-164">S'il n'y a pas de fournisseur dans la Gestion des états électroniques, vous pouvez en créer un.</span><span class="sxs-lookup"><span data-stu-id="6e587-164">If there isn't a provider in Electronic reporting, you can create one.</span></span> <span data-ttu-id="6e587-165">S'il n'y a pas de fournisseur actif, vous pouvez choisir d'en activer un.</span><span class="sxs-lookup"><span data-stu-id="6e587-165">If there's no active provider, you can select to activate one.</span></span>

- <span data-ttu-id="6e587-166">Pour créer un fournisseur, modifiez le nom du fournisseur dans le champ **Nom**, mettez à jour l'adresse Internet du nouveau fournisseur dans le champ **Adresse Internet** et sélectionnez **OK** pour confirmer.</span><span class="sxs-lookup"><span data-stu-id="6e587-166">To create a provider, change the name of the provider in the **Name** field, update the internet address of the new provider in the **Internet address** field, and select **OK** to confirm.</span></span>

    ![Créer un nouveau fournisseur dans BDM](./media/bdm_create_provider.png)
    
- <span data-ttu-id="6e587-168">Pour activer le fournisseur existant, choisissez le nom du fournisseur dans le champ **Fournisseur de configuration** et sélectionnez **OK** pour définir le fournisseur comme actif.</span><span class="sxs-lookup"><span data-stu-id="6e587-168">To activate existing provider, choose the name of the provider in the **Configuration provider** field, and select **OK** to set provider as active.</span></span>

    ![Activer un fournisseur dans BDM](./media/bdm_choose_provider.png)

> [!NOTE]
> <span data-ttu-id="6e587-170">Chaque modèle BDM fait référence au fournisseur en tant que l’auteur de la configuration.</span><span class="sxs-lookup"><span data-stu-id="6e587-170">Each BDM template refers to the provider as the author of the configuration.</span></span> <span data-ttu-id="6e587-171">c'est pourquoi un fournisseur actif est requis pour le modèle.</span><span class="sxs-lookup"><span data-stu-id="6e587-171">This is why an active provider is required for the template.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
