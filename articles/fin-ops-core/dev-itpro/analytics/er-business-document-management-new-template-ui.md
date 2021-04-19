---
title: Nouvelle interface utilisateur de document dans la gestion des documents commerciaux
description: Cette rubrique fournit des informations sur l’utilisation de la nouvelle interface utilisateur de document dans la fonctionnalité de gestion des documents commerciaux de l’infrastructure de gestion des états électroniques.
author: v-anamir
ms.date: 05/12/2019
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
ms.openlocfilehash: 4c430e21e3bf7f1c01c7b60c0bef58fb49c0c601
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748339"
---
# <a name="new-document-user-interface-in-business-document-management"></a><span data-ttu-id="b7085-103">Nouvelle interface utilisateur de document dans la gestion des documents commerciaux</span><span class="sxs-lookup"><span data-stu-id="b7085-103">New document user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b7085-104">La gestion des documents commerciaux permet aux utilisateurs professionnels de modifier des modèles de document commercial à l’aide d’un service Microsoft 365 ou de l’application de bureau Microsoft Office appropriée.</span><span class="sxs-lookup"><span data-stu-id="b7085-104">Business document management lets business users edit business document templates by using a Microsoft 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="b7085-105">Les modifications peuvent inclure des modifications de conception ou de nouveaux déploiements, ou les utilisateurs peuvent ajouter des espaces réservés pour inclure des données supplémentaires sans avoir à modifier le code source.</span><span class="sxs-lookup"><span data-stu-id="b7085-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="b7085-106">Pour plus d’informations sur l’utilisation de la gestion des documents commerciaux, consultez [Vue d’ensemble de la gestion de document commercial](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="b7085-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="b7085-107">La nouvelle interface utilisateur de document (UI) est plus claire et plus confortable à utiliser.</span><span class="sxs-lookup"><span data-stu-id="b7085-107">The new document user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="b7085-108">La zone **Document commercial** affiche uniquement les modèles disponibles pour le fournisseur actuel.</span><span class="sxs-lookup"><span data-stu-id="b7085-108">The **Business document** area shows only the templates that are available for the current provider.</span></span>

<span data-ttu-id="b7085-109">Le bouton **Nouveau document** permet aux utilisateurs de créer et de modifier un modèle dans une configuration au format d’états électroniques (ER) fournie par un autre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b7085-109">The **New document** button lets users create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="b7085-110">Dans l’exemple de cette rubrique, le fournisseur est Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7085-110">In the example in this topic, the provider is Microsoft.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="b7085-111">Rendre disponible la nouvelle interface utilisateur de document dans la gestion des documents commerciaux</span><span class="sxs-lookup"><span data-stu-id="b7085-111">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="b7085-112">Pour commencer à utiliser la nouvelle interface utilisateur de document dans la gestion des documents commerciaux, vous devez activer la fonctionnalité **Expérience d’interface utilisateur de type bureau pour la gestion des documents commerciaux** dans l’espace de travail **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="b7085-112">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="b7085-113">Suivez ces étapes pour activer cette fonctionnalité pour toutes les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="b7085-113">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="b7085-114">Dans l’espace de travail **Gestion des fonctionnalités**, dans l’onglet **Nouveau**, sélectionnez la fonctionnalité **Expérience d’interface utilisateur de type bureau pour la gestion des documents commerciaux** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="b7085-114">In the **Feature management** workspace, on the **New** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="b7085-115">Sélectionnez **Activer maintenant** pour activer la fonctionnalité sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b7085-115">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="b7085-116">Actualisez la page pour accéder à la nouvelle fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="b7085-116">Refresh the page to access the new feature.</span></span>

### <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="b7085-117">Modifier des modèles qui sont détenus par d’autres fournisseurs</span><span class="sxs-lookup"><span data-stu-id="b7085-117">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="b7085-118">Dans l’espace de travail **Gestion des documents commerciaux**, sélectionnez **Nouveau document**.</span><span class="sxs-lookup"><span data-stu-id="b7085-118">In the **Business document management** workspace, select **New document**.</span></span>

    ![Espace de travail du module Gestion de document commercial](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="b7085-120">Dans la boîte de dialogue, choisissez le document à utiliser comme modèle, puis sélectionnez **Créer un document**.</span><span class="sxs-lookup"><span data-stu-id="b7085-120">In the dialog box, select the document to use as a template, and then select **Create document**.</span></span>

    ![Boîte de dialogue Documents commerciaux](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="b7085-122">Dans la nouvelle boîte de dialogue, dans le champ **Titre**, modifiez le titre selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b7085-122">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="b7085-123">Le texte du titre est utilisé pour nommer la nouvelle mconfiguration du format ER qui est automatiquement créée.</span><span class="sxs-lookup"><span data-stu-id="b7085-123">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="b7085-124">La version temporaire de cette configuration (**Copie d’État FTI client (GER)**) qui contient le modèle modifié et sera automatiquement utilisée pour exécuter ce format ER pour l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="b7085-124">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="b7085-125">Le modèle d’origine de la configuration du format ER de base sera utilisé pour exécuter ce format ER pour tout autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b7085-125">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="b7085-126">Dans le champ **Nom**, modifiez le nom de la première révision du modèle modifiable qui sera automatiquement créé.</span><span class="sxs-lookup"><span data-stu-id="b7085-126">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="b7085-127">Dans le champ **Commentaire**, mettez à jour les remarques de la révision du modèle modifiable qui sera créée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="b7085-127">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="b7085-128">Cliquez sur **OK** pour confirmer le début du processus de modification.</span><span class="sxs-lookup"><span data-stu-id="b7085-128">Select **OK** to confirm the start of the editing process.</span></span>

    ![Boîte de dialogue de création de document](./media/BDM_overview_new_template3.png)

<span data-ttu-id="b7085-130">Le bouton **Nouveau document** est utilisé pour créer et modifier un modèle dans une configuration au format ER fournie par un autre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b7085-130">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="b7085-131">Dans cet exemple, le fournisseur est Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7085-131">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="b7085-132">Lorsque vous sélectionnez **Nouveau document**, vous pouvez voir tous les modèles qui sont détenus par les fournisseurs actuels et autres fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="b7085-132">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="b7085-133">Après que vous avez sélectionné le modèle, il est ouvert pour modification.</span><span class="sxs-lookup"><span data-stu-id="b7085-133">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="b7085-134">Le modèle modifié est ensuite stocké dans une nouvelle configuration de format ER qui est automatiquement générée.</span><span class="sxs-lookup"><span data-stu-id="b7085-134">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

<span data-ttu-id="b7085-135">Pour plus d’informations, voir [Vue d’ensemble de la gestion de document commercial](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="b7085-135">For more information, see [Business document management overview](er-business-document-management.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]