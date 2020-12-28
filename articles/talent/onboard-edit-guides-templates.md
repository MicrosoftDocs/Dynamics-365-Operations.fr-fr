---
title: Modifier les guides et les modèles d'intégration dans Dynamics 365 Talent - Onboard
description: Cette rubrique explique comment ajouter des activités et d'autres informations aux guides et modèles d'intégration dans Microsoft Dynamics 365 Talent - Onboard.
author: andreabichsel
manager: ''
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 291f7aefac61c26dfab81cfff28c1c6580d46de5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461179"
---
# <a name="edit-onboarding-guides-and-templates"></a><span data-ttu-id="b3e7f-103">Modifier les guides et les modèles d'intégration</span><span class="sxs-lookup"><span data-stu-id="b3e7f-103">Edit onboarding guides and templates</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b3e7f-104">Après avoir créé un guide ou un modèle d'intégration dans Microsoft Dynamics 365 Talent: Onboard, vous devez ajouter une introduction, des activités, des contacts et des ressources.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-104">After you create an onboarding guide or template in Microsoft Dynamics 365 Talent: Onboard, you must add an introduction, activities, contacts, and resources.</span></span> <span data-ttu-id="b3e7f-105">Onboard vous permet d'ajouter du contenu enrichi à vos guides d'intégration, notamment :</span><span class="sxs-lookup"><span data-stu-id="b3e7f-105">Onboard lets you include rich content in your onboarding guides, including:</span></span>

- <span data-ttu-id="b3e7f-106">Vidéos YouTube</span><span class="sxs-lookup"><span data-stu-id="b3e7f-106">YouTube videos</span></span>
- <span data-ttu-id="b3e7f-107">Présentations Microsoft Sway</span><span class="sxs-lookup"><span data-stu-id="b3e7f-107">Microsoft Sway presentations</span></span>
- <span data-ttu-id="b3e7f-108">Applications Microsoft PowerApps</span><span class="sxs-lookup"><span data-stu-id="b3e7f-108">Microsoft PowerApps apps</span></span>
- <span data-ttu-id="b3e7f-109">Vidéos Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="b3e7f-109">Microsoft Stream videos</span></span>
- <span data-ttu-id="b3e7f-110">Formulaires Microsoft Forms</span><span class="sxs-lookup"><span data-stu-id="b3e7f-110">Microsoft Forms forms</span></span>
- <span data-ttu-id="b3e7f-111">Iframes contenant du contenu Web</span><span class="sxs-lookup"><span data-stu-id="b3e7f-111">Iframes that contains web content</span></span>

## <a name="edit-introductions-or-activities-imported-from-a-template"></a><span data-ttu-id="b3e7f-112">Modifier des introductions ou des activités importées à partir d'un modèle</span><span class="sxs-lookup"><span data-stu-id="b3e7f-112">Edit introductions or activities imported from a template</span></span>

<span data-ttu-id="b3e7f-113">Si vous créez un guide d'intégration à partir d'un modèle, ou si vous importez des activités d'un modèle vers un autre, vous remarquerez un bouton **Verrouiller** sur les activités importées.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-113">If you create an onboarding guide from a template, or if you import activities from one template into another, you'll notice a **Lock** button on the imported activities.</span></span> <span data-ttu-id="b3e7f-114">Celles-ci sont appelées des *activités gérées*.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-114">These are called *managed activities*.</span></span>

<span data-ttu-id="b3e7f-115">[![Activités gérées](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)</span><span class="sxs-lookup"><span data-stu-id="b3e7f-115">[![Managed activities](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)</span></span>

<span data-ttu-id="b3e7f-116">Lorsque vous sélectionnez une activité gérée, le modèle source s'affiche en haut de l'activité.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-116">When you select a managed activity, you can see the source template at the top of the activity.</span></span>

<span data-ttu-id="b3e7f-117">[![Source de l'activité gérée](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)</span><span class="sxs-lookup"><span data-stu-id="b3e7f-117">[![Managed activity source](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)</span></span>

<span data-ttu-id="b3e7f-118">Si vous modifiez une activité dans un modèle, Onboard envoie les modifications à tous les modèles et guides non envoyés basés sur ce modèle.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-118">If you edit an activity in a template, Onboard will push the changes to all templates and unsent guides that are based on that template.</span></span> <span data-ttu-id="b3e7f-119">Si vous sélectionnez un guide non envoyé basé sur un modèle que vous avez modifié, puis vous sélectionnez l'onglet **Activités** dans le guide, une notification de modification de votre guide s'affiche.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-119">If you select an unsent guide based on a template you edited and then select the **Activities** tab in the guide, you will see a notice that your guide has changed.</span></span> <span data-ttu-id="b3e7f-120">Pour ignorer la notification, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-120">To dismiss the notification, select **OK**.</span></span> 

<span data-ttu-id="b3e7f-121">[![Notification de modification](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)</span><span class="sxs-lookup"><span data-stu-id="b3e7f-121">[![Change notification](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)</span></span>

<span data-ttu-id="b3e7f-122">Un point noir s'affiche en regard des activités mises à jour.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-122">You'll see a black dot next to the updated activities.</span></span>

<span data-ttu-id="b3e7f-123">[![Activité modifiée](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)</span><span class="sxs-lookup"><span data-stu-id="b3e7f-123">[![Changed activity](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)</span></span>

<span data-ttu-id="b3e7f-124">Vous ne pouvez pas modifier des activités gérées en dehors du modèle d'origine, sauf pour ajouter un destinataire, une date d'échéance ou d'autres informations dans la section à droite de l'activité.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-124">You can't edit managed activities outside of the original template, except to add an assignee, due date, or other information in the right-hand section of the activity.</span></span>

<span data-ttu-id="b3e7f-125">Si vous souhaitez modifier une activité gérée, ou si une activité ne doit pas recevoir de mises à jour du modèle d'origine, sélectionnez le bouton **Verrouiller** pour cette activité.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-125">If you want to edit a managed activity, or if you don't want an activity to receive updates from the template it came from, select the **Lock** button for that activity.</span></span> <span data-ttu-id="b3e7f-126">Le bouton **Verrouiller** disparaîtra.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-126">The **Lock** button will disappear.</span></span> <span data-ttu-id="b3e7f-127">L'activité ne sera plus gérée par le modèle d'origine, et elle ne recevra plus de mises à jour de ce modèle.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-127">The activity will no longer be managed by the original template, and it will no longer receive updates from that template.</span></span> <span data-ttu-id="b3e7f-128">Les mises à jour apportées à une activité n'affectent pas le modèle d'origine.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-128">Updates you make to an activity do not affect the original template.</span></span>

<span data-ttu-id="b3e7f-129">Si vous supprimez une activité d'un guide et envoyez les modifications du modèle de ce guide, l'activité reste supprimée dans le guide.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-129">If you delete an activity from a guide and push changes from that guide's template, the activity will remain deleted in the guide.</span></span>

> [!NOTE]
> <span data-ttu-id="b3e7f-130">Les contacts et les ressources ne sont pas gérées par les modèles.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-130">Contacts and resources aren't managed by templates.</span></span> <span data-ttu-id="b3e7f-131">En outre, les sections ne sont pas gérées, donc si vous ajoutez ou modifiez une section dans un modèle, les modifications ne sont pas envoyées aux guides ou aux modèles qui utilisent ce modèle.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-131">In addition, sections aren't managed, so if you add or edit a section in a template, the changes won't be pushed to any guides or templates that use that template.</span></span>
> 
> <span data-ttu-id="b3e7f-132">Si vous ajoutez de nouvelles activités à un modèle, les nouvelles activités sont envoyées aux guides et aux modèles basés sur ce modèle, et les nouvelles activités s'affichent en haut.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-132">If you add new activities to a template, the new activities are pushed to guides and templates based on that template, and the new activities display at the top.</span></span>

## <a name="import-activities-from-another-template"></a><span data-ttu-id="b3e7f-133">Importer des activités à partir d'un autre modèle</span><span class="sxs-lookup"><span data-stu-id="b3e7f-133">Import activities from another template</span></span>

<span data-ttu-id="b3e7f-134">Vous pouvez importer des activités d'un ou de plusieurs modèles vers un guide ou un modèle.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-134">You can import activities from one or more templates into a guide or template.</span></span>

1. <span data-ttu-id="b3e7f-135">Sélectionnez le guide ou le modèle à modifier.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-135">Select the guide or template you want to edit.</span></span>

2. <span data-ttu-id="b3e7f-136">Sélectionnez l'onglet **Activités**.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-136">Select the **Activities** tab.</span></span>

3. <span data-ttu-id="b3e7f-137">Sélectionnez l'onglet **Importer** dans la section à droite.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-137">Select the **Import** tab in the section on the right.</span></span>

   <span data-ttu-id="b3e7f-138">[![Importer des activités](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)</span><span class="sxs-lookup"><span data-stu-id="b3e7f-138">[![Import activities](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)</span></span>

4. <span data-ttu-id="b3e7f-139">Pour afficher un aperçu des tâches dans un nouvel onglet de votre navigateur, sélectionnez le bouton **Ouvrir dans un nouvel onglet** sur n'importe quel modèle.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-139">To preview the tasks in a new tab in your browser, select the **Open in new tab** button on any template.</span></span>

   <span data-ttu-id="b3e7f-140">[![Importer des activités](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)</span><span class="sxs-lookup"><span data-stu-id="b3e7f-140">[![Import activities](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)</span></span>

5. <span data-ttu-id="b3e7f-141">Glissez et déplacez le modèle souhaité vers l'emplacement dans votre modèle de guide où vous souhaitez faire apparaître les activités.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-141">Drag and drop the desired template to the place in your guide template where you want the activities to appear.</span></span> <span data-ttu-id="b3e7f-142">Continuez à modifier votre guide ou votre modèle.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-142">Continue editing your guide or template.</span></span>

<span data-ttu-id="b3e7f-143">Les activités importées contiennent un bouton **Verrouiller**, qui indique que ces activités sont gérées par le modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-143">The imported activities will contain a **Lock** button, which indicates those activities are managed by the template you imported from.</span></span> <span data-ttu-id="b3e7f-144">Lorsque vous apportez des modifications au modèle que vous avez importé, ces activités sont mises à jour dans le modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-144">When you make changes to the template you imported, those activities will update in the template you imported them to.</span></span> <span data-ttu-id="b3e7f-145">Toutefois, les modifications ne sont pas envoyées automatiquement aux guides créés à partir du modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-145">However, the changes will not be pushed automatically to any guides created from the template you imported to.</span></span>

## <a name="push-changes-from-a-template-to-other-templates-or-guides"></a><span data-ttu-id="b3e7f-146">Envoyer les modifications d'un modèle vers d'autres modèles ou guides</span><span class="sxs-lookup"><span data-stu-id="b3e7f-146">Push changes from a template to other templates or guides</span></span>

<span data-ttu-id="b3e7f-147">Si vous modifiez un modèle contenant des activités qui sont utilisées dans d'autres modèles ou guides, vous devez envoyer les modifications si vous souhaitez les faire apparaître dans les autres modèles ou guides.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-147">If you edit a template that contains activities that are used in other templates or guides, you must push the changes if you want them to appear in the other templates or guides.</span></span>

<span data-ttu-id="b3e7f-148">Si vous ne savez pas si les activités de votre modèle sont utilisées dans d'autres modèles ou guides, sélectionnez l'onglet **Utilisé dans** pour voir où ces activités apparaissent.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-148">If you're not sure whether your template's activities are used in other templates or guides, select the **Used in** tab to view where those activities appear.</span></span>

   <span data-ttu-id="b3e7f-149">[![Afficher les guides et les modèles dans lesquels les activités sont utilisées](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)</span><span class="sxs-lookup"><span data-stu-id="b3e7f-149">[![View guides and templates activities are used in](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)</span></span>

<span data-ttu-id="b3e7f-150">Pour envoyer vos modifications :</span><span class="sxs-lookup"><span data-stu-id="b3e7f-150">To push your changes:</span></span>

1. <span data-ttu-id="b3e7f-151">Enregistrez vos modifications en sélectionnant le bouton **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-151">Save your changes by selecting the **Save** button.</span></span> <span data-ttu-id="b3e7f-152">Dans le cas contraire, vous serez invité à enregistrer vos modifications dans l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-152">If you don't do this, you'll be prompted to save your changes in the next step.</span></span>

2. <span data-ttu-id="b3e7f-153">Sélectionnez **Envoyer ces modifications**.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-153">Select **Push these changes**.</span></span>

   
## <a name="add-or-edit-an-introduction"></a><span data-ttu-id="b3e7f-154">Ajouter ou modifier une introduction</span><span class="sxs-lookup"><span data-stu-id="b3e7f-154">Add or edit an introduction</span></span>

1. <span data-ttu-id="b3e7f-155">Sous l'onglet **Introduction**, entrez un titre pour votre guide et un message de présentation.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-155">On the **Introduction** tab, enter a title for your guide and an opening message.</span></span> <span data-ttu-id="b3e7f-156">Pour utiliser l'exemple de texte, sélectionnez **Utiliser ce message**.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-156">To use the sample text, select **Use this message**.</span></span>

    <span data-ttu-id="b3e7f-157">[![Onglet Introduction dans un modèle Onboard](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)</span><span class="sxs-lookup"><span data-stu-id="b3e7f-157">[![Introduction tab in an Onboard template](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)</span></span>

2. <span data-ttu-id="b3e7f-158">Utilisez les boutons de mise en forme pour ajouter une légende au texte si nécessaire, ou ajouter des images ou des liens.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-158">Use the formatting buttons to call out text as you require, or to add images or links.</span></span>
3. <span data-ttu-id="b3e7f-159">Sélectionnez **Enregistrer** pour enregistrer votre travail.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-159">Select **Save** to save your work.</span></span>

## <a name="add-or-edit-activities"></a><span data-ttu-id="b3e7f-160">Ajouter ou modifier des activités</span><span class="sxs-lookup"><span data-stu-id="b3e7f-160">Add or edit activities</span></span>

1. <span data-ttu-id="b3e7f-161">Sous l'onglet **Activités**, faites glisser des éléments de la droite vers la zone de modification.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-161">On the **Activities** tab, drag items from the right to the editing area.</span></span>
2. <span data-ttu-id="b3e7f-162">Pour organiser votre guide en sections, faites glisser l'élément **Nouvelle section** vers la zone de modification, puis entrez un nom et une description facultative pour la section.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-162">To organize your guide into sections, drag the **New section** item to the editing area, and enter a name and an optional description for the section.</span></span>

    ![[<span data-ttu-id="b3e7f-163">Ajout d'une nouvelle section à un guide ou modèle d'intégration</span><span class="sxs-lookup"><span data-stu-id="b3e7f-163">Adding a new section to an onboarding guide or template</span></span>](./media/onboard-edit-add-section.png)](./media/onboard-edit-add-section.png)

3. <span data-ttu-id="b3e7f-164">Pour ajouter des activités que votre nouvelle recrue doit effectuer, faites glisser l'élément **Nouvelle activité** vers la zone de modification, puis entrez un nom et une description pour l'activité.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-164">To add activities for your new hire to complete, drag the **New activity** item to the editing area, and enter a name and description for the activity.</span></span>

    ![[<span data-ttu-id="b3e7f-165">Ajout d'une nouvelle activité à un guide ou modèle d'intégration</span><span class="sxs-lookup"><span data-stu-id="b3e7f-165">Adding a new activity to an onboarding guide or template</span></span>](./media/onboard-edit-add-activity.png)](./media/onboard-edit-add-activity.png)

4. <span data-ttu-id="b3e7f-166">Ajouter du contenu enrichi à votre guide d'intégration :</span><span class="sxs-lookup"><span data-stu-id="b3e7f-166">Add rich content to your onboarding guide:</span></span>

    - <span data-ttu-id="b3e7f-167">Pour ajouter une vidéo YouTube, faites glisser l'élément **YouTube** vers la zone de modification, entrez un nom et une description pour l'activité, puis entrez l'URL de la vidéo YouTube.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-167">To add a YouTube video, drag the **YouTube** item to the editing area, enter a name and description for the activity, and enter the URL for the YouTube video.</span></span>
    - <span data-ttu-id="b3e7f-168">Pour ajouter une présentation Sway ou un bulletin d'informations, faites glisser l'élément **Sway** vers la zone de modification, entrez un nom et une description pour l'activité, puis entrez l'URL intégrée de la présentation Sway ou du bulletin d'informations.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-168">To add a Sway presentation or newsletter, drag the **Sway** item to the editing area, enter a name and description for the activity, and enter the embedded URL for the Sway presentation or newsletter.</span></span>
    - <span data-ttu-id="b3e7f-169">Pour ajouter une application Microsoft Power Apps, faites glisser l'élément **Power Apps** vers la zone de modification, entrez un nom et une description pour l'activité, puis sélectionnez l'application Power Apps ou entrez l'ID de l'application Power Apps.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-169">To add a Microsoft Power Apps app, drag the **Power Apps** item to the editing area, enter a name and description for the activity, and either select the Power Apps app or enter the Power Apps app ID.</span></span>
    - <span data-ttu-id="b3e7f-170">Pour ajouter une vidéo Microsoft Stream, faites glisser l'élément **Microsoft Stream** vers la zone de modification, entrez un nom et une description pour l'activité, puis entrez l'URL de la vidéo Microsoft Stream.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-170">To add a Microsoft Stream video, drag the **Microsoft Stream** item to the editing area, enter a name and description for the activity, and enter the URL for the Microsoft Stream video.</span></span>
    - <span data-ttu-id="b3e7f-171">Pour ajouter un formulaire Microsoft Forms, faites glisser l'élément **Microsoft Forms** vers la zone de modification, entrez un nom et une description pour l'activité, entrez l'URL du formulaire Microsoft Forms, puis spécifiez la taille de la zone d'écran.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-171">To add a Microsoft Forms form, drag the **Microsoft Forms** item to the editing area, enter a name and description for the activity, enter the URL for the Microsoft Forms form, and specify the size of the screen area.</span></span>
    - <span data-ttu-id="b3e7f-172">Pour ajouter un iframe contenant du contenu Web, faites glisser l'élément **Contenu Web (iframe)** vers la zone de modification, entrez un nom et une description pour l'activité, entrez l'URL du contenu Web, puis spécifiez la taille de la zone d'écran.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-172">To add an iframe that contains web content, drag the **Web Content (iframe)** item to the editing area, enter a name and description for the activity, enter the URL for the web content, and specify the size of the screen area.</span></span>

    ![[<span data-ttu-id="b3e7f-173">Ajout de contenu enrichi à un guide ou modèle d'intégration</span><span class="sxs-lookup"><span data-stu-id="b3e7f-173">Adding rich content to an onboarding guide or template</span></span>](./media/onboard-edit-add-rich-content.png)](./media/onboard-edit-add-rich-content.png)

2. <span data-ttu-id="b3e7f-174">Facultatif : dans la zone à droite de chaque activité, affectez l'activité à une personne ou un rôle spécifique, ajoutez une date d'échéance et une personne à contacter, puis affectez une couleur de catégorie.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-174">Optional: In the area on the right of each activity, assign the activity to a specific person or role, add a due date and contact person, and assign a category color.</span></span> <span data-ttu-id="b3e7f-175">Lorsque vous affectez une activité à une personne ou un rôle, une tâche est créée pour chaque individu.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-175">When you assign an activity to a person or role, a task is created for each individual.</span></span> <span data-ttu-id="b3e7f-176">Cette tâche apparaît dans le menu **Tâches** d'Onboard.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-176">This task appears on the **Tasks** menu in Onboard.</span></span>

    <span data-ttu-id="b3e7f-177">[![Affectation d'une activité dans un guide ou un modèle d'intégration](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)</span><span class="sxs-lookup"><span data-stu-id="b3e7f-177">[![Assigning an activity in an onboarding guide or template](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)</span></span>

3. <span data-ttu-id="b3e7f-178">Sélectionnez **Enregistrer** pour enregistrer votre travail.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-178">Select **Save** to save your work.</span></span>

<span data-ttu-id="b3e7f-179">Pour supprimer une activité ou une section, sélectionnez le bouton **Supprimer** (le symbole de poubelle) dans le coin supérieur droit de l'activité ou de la section.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-179">To delete an activity or section, select the **Delete** button (the trash can symbol) in the upper-right corner of the activity or section.</span></span>

<span data-ttu-id="b3e7f-180">Pour réorganiser les activités et les sections, faites-les glisser vers un nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-180">To rearrange activities and sections, drag them to a new location.</span></span>

## <a name="add-or-edit-contacts"></a><span data-ttu-id="b3e7f-181">Ajouter ou modifier des contacts</span><span class="sxs-lookup"><span data-stu-id="b3e7f-181">Add or edit contacts</span></span>

<span data-ttu-id="b3e7f-182">Vous pouvez ajouter des personnes à contacter qui peuvent aider votre nouvelle recrue à réussir dès le premier jour.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-182">You can add contact people who can help your new hire succeed from day one.</span></span> <span data-ttu-id="b3e7f-183">Ces contacts peuvent être des recruteurs, des membres de l'équipe, des parrains, des mentors, des administrateurs et du personnel d'assistance informatique.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-183">These contacts can be recruiters, teammates, onboarding buddies, mentors, admins, and IT support staff.</span></span>

1. <span data-ttu-id="b3e7f-184">Sous l'onglet **Contacts**, sélectionnez **Nouveau contact**.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-184">On the **Contacts** tab, select **New contact**.</span></span>
2. <span data-ttu-id="b3e7f-185">Dans la boîte de dialogue **Ajouter un membre de l'équipe**, entrez le nom ou l'adresse e-mail de la personne à contacter, entrez une brève description expliquant comment la personne à contacter peut aider la nouvelle recrue, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-185">In the **Add team member** dialog box, enter the contact person's name or email address, enter a short description that explains how the contact person can help the new hire, and then select **Add**.</span></span> 

    ![[<span data-ttu-id="b3e7f-186">Ajout de contacts à un guide ou modèle d'intégration</span><span class="sxs-lookup"><span data-stu-id="b3e7f-186">Adding contacts to an onboarding guide or template</span></span>](./media/onboard-edit-add-contact.png)](./media/onboard-edit-add-contact.png)

    <span data-ttu-id="b3e7f-187">Vous pouvez également sélectionner un ou plusieurs contacts sous **Suggestions**.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-187">Alternately, you can select one or more contacts under **Suggestions**.</span></span>

3. <span data-ttu-id="b3e7f-188">Sélectionnez **Enregistrer** pour enregistrer votre travail.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-188">Select **Save** to save your work.</span></span>

<span data-ttu-id="b3e7f-189">Pour supprimer un contact, sélectionnez le bouton **Supprimer** (le symbole de poubelle) à droite du contact.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-189">To delete a contact, select the **Delete** button (the trash can symbol) to the right of the contact.</span></span>

<span data-ttu-id="b3e7f-190">Pour modifier un contact, sélectionnez le bouton **Modifier** (le symbole de crayon) à droite du contact.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-190">To edit a contact, select the **Edit** button (the pencil symbol) to the right of the contact.</span></span>

## <a name="add-or-edit-resources"></a><span data-ttu-id="b3e7f-191">Ajouter ou modifier des ressources</span><span class="sxs-lookup"><span data-stu-id="b3e7f-191">Add or edit resources</span></span>

<span data-ttu-id="b3e7f-192">Vous pouvez ajouter des fichiers, cartes et liens utiles à la section **Ressources** de votre guide d'intégration.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-192">You can add useful files, maps, and links to the **Resources** section of your onboarding guide.</span></span>

1. <span data-ttu-id="b3e7f-193">Sous l'onglet **Ressources**, sélectionnez **Nouvelle ressource**.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-193">On the **Resources** tab, select **New resource**.</span></span>
2. <span data-ttu-id="b3e7f-194">Utilisez l'une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="b3e7f-194">Follow one of these steps:</span></span>

    - <span data-ttu-id="b3e7f-195">Pour ajouter un fichier, sélectionner l'onglet **Fichier**, puis faites glisser le fichier vers la zone indiquée.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-195">To add a file, select the **File** tab, and drag the file into the designated area.</span></span> <span data-ttu-id="b3e7f-196">(Sinon, cliquez n'importe où dans cette zone pour rechercher le fichier sur votre ordinateur, ou sélectionnez **Parcourir OneDrive**). Entrez un nom pour le fichier, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-196">(Alternatively, click anywhere in that area to browse for the file on your computer, or select **Browse OneDrive**.) Enter a name for the file, and then select **Add**.</span></span>
    - <span data-ttu-id="b3e7f-197">Pour ajouter un lien, sélectionnez l'onglet **Lien**, entrez un nom et une adresse pour le lien, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-197">To add a link, select the **Link** tab, enter a name and address for the link, and then select **Add**.</span></span>
    - <span data-ttu-id="b3e7f-198">Pour ajouter une carte, sélectionnez l'onglet **Carte**, entrez un nom et une adresse pour la carte, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-198">To add a map, select the **Map** tab, enter a name and address for the map, and then select **Add**.</span></span> <span data-ttu-id="b3e7f-199">Onboard ajoutera une carte de l'adresse que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-199">Onboard will include a map of the address that you specify.</span></span>

    ![[<span data-ttu-id="b3e7f-200">Ajout d'une ressource à un guide ou modèle d'intégration</span><span class="sxs-lookup"><span data-stu-id="b3e7f-200">Adding a resource to an onboarding guide or template</span></span>](./media/onboard-edit-add-resource.png)](./media/onboard-edit-add-resource.png)

3. <span data-ttu-id="b3e7f-201">Sélectionnez **Enregistrer** pour enregistrer votre travail.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-201">Select **Save** to save your work.</span></span>

<span data-ttu-id="b3e7f-202">Pour supprimer une ressource, sélectionnez le bouton **Supprimer** (le symbole de poubelle) à droite de la ressource.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-202">To delete a resource, select the **Delete** button (the trash can symbol) to the right of the resource.</span></span>

<span data-ttu-id="b3e7f-203">Pour modifier une ressource, sélectionnez le bouton **Modifier** (le symbole de crayon) à droite de la ressource.</span><span class="sxs-lookup"><span data-stu-id="b3e7f-203">To edit a contact, select the **Edit** button (the pencil symbol) to the right of the resource.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3e7f-204">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="b3e7f-204">Next steps</span></span>

- [<span data-ttu-id="b3e7f-205">Partager du contenu avec d'autres contributeurs</span><span class="sxs-lookup"><span data-stu-id="b3e7f-205">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="b3e7f-206">Afficher le statut d'intégration des employés et des tâches</span><span class="sxs-lookup"><span data-stu-id="b3e7f-206">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="b3e7f-207">Créer des équipes de recrutement dans Onboard</span><span class="sxs-lookup"><span data-stu-id="b3e7f-207">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="b3e7f-208">Voir également :</span><span class="sxs-lookup"><span data-stu-id="b3e7f-208">See also</span></span>

- [<span data-ttu-id="b3e7f-209">Essayer ou acheter l'application Onboard</span><span class="sxs-lookup"><span data-stu-id="b3e7f-209">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="b3e7f-210">Nouveautés ou modifications dans Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="b3e7f-210">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="b3e7f-211">Programmes de lancement</span><span class="sxs-lookup"><span data-stu-id="b3e7f-211">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="b3e7f-212">Obtenir de l'aide sur Microsoft Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="b3e7f-212">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
