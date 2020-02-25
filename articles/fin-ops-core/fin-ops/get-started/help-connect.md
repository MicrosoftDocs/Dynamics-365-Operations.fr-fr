---
title: Connexion au système d'aide
description: Cette rubrique décrit les composants du système d'aide pour les applications Finance and Operations, explique comment les connecter entre eux et résume la création de l'aide personnalisée.
author: margoc
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4427388d75c1aef40a978ce35c831d5b714f2562
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006170"
---
# <a name="connect-the-help-system"></a><span data-ttu-id="832b4-103">Connexion au système d'aide</span><span class="sxs-lookup"><span data-stu-id="832b4-103">Connect the Help system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="832b4-104">Cette rubrique décrit les composants du système d'aide des applications Finance and Operations, par exemple Dynamics 365 Finance, Supply Chain Management, Commerce, et Human Resources.</span><span class="sxs-lookup"><span data-stu-id="832b4-104">This topic describes the components of the Help system for Finance and Operations apps, such as Dynamics 365 Finance, Supply Chain Management, Commerce, and Human Resources.</span></span> <span data-ttu-id="832b4-105">Elle fournit une vue d'ensemble de la procédure de connexion de ces composants et une synthèse de la création de l'aide personnalisée.</span><span class="sxs-lookup"><span data-stu-id="832b4-105">It provides an overview of how to connect these components and a summary of how to create custom help.</span></span>

## <a name="help-architecture"></a><span data-ttu-id="832b4-106">Architecture de l'aide</span><span class="sxs-lookup"><span data-stu-id="832b4-106">Help architecture</span></span>

<span data-ttu-id="832b4-107">La figure suivante illustre les parties du système d'aide.</span><span class="sxs-lookup"><span data-stu-id="832b4-107">The following illustration shows the parts of the Help system.</span></span> <span data-ttu-id="832b4-108">Le système d'aide intégré au produit extrait des articles du site https://docs.microsoft.com, ainsi que les guides de tâche enregistrés dans le Concepteur de processus d'entreprise de Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="832b4-108">The in-product Help system pulls articles from https://docs.microsoft.com, as well as task guides stored in Business Process Modeler in Lifecycle Services (LCS).</span></span>

> [!NOTE]
> <span data-ttu-id="832b4-109">Les fonctionnalités indiquées dans le schéma avec un astérisque (\*) sont planifiées, mais ne sont pas encore disponibles.</span><span class="sxs-lookup"><span data-stu-id="832b4-109">The features listed in the diagram with an asterisk (\*) are planned, but are not available yet.</span></span>

<span data-ttu-id="832b4-110">[![Architecture de l'aide](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="832b4-110">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>

## <a name="connecting-the-help-system"></a><span data-ttu-id="832b4-111">Connexion au système d'aide</span><span class="sxs-lookup"><span data-stu-id="832b4-111">Connecting the Help system</span></span>

> [!NOTE]
> <span data-ttu-id="832b4-112">L'onglet **Guides de tâche** n'est pas disponible actuellement dans Dynamics 365 Human Resources ou Commerce.</span><span class="sxs-lookup"><span data-stu-id="832b4-112">The **Task guides** tab is currently not available in Dynamics 365 Human Resources or Commerce.</span></span> <span data-ttu-id="832b4-113">Nous œuvrons actuellement pour activer cette fonctionnalité dans une future version.</span><span class="sxs-lookup"><span data-stu-id="832b4-113">We are currently working to enable this functionality in a future release.</span></span> <span data-ttu-id="832b4-114">Les guides des tâches dans l'expérience Mise en route dans Human Resources restent disponibles pour couvrir les fonctionnalités de base.</span><span class="sxs-lookup"><span data-stu-id="832b4-114">The Task guides in the Getting Started experience in Human Resources remain available to cover basic functionality.</span></span> <span data-ttu-id="832b4-115">L'aide concernant la procédure est également disponible sur le site docs.microsoft.com pour Human Resources et Commerce.</span><span class="sxs-lookup"><span data-stu-id="832b4-115">Procedural help is also available on the docs.microsoft.com site for both Human Resources and Commerce.</span></span>

<span data-ttu-id="832b4-116">En utilisant le formulaire **Paramètres système**, les administrateurs système connectent les parties du système d'aide pour une implémentation.</span><span class="sxs-lookup"><span data-stu-id="832b4-116">Using the **System Parameters** page, system administrators connect the pieces of the Help system for an implementation.</span></span>

<span data-ttu-id="832b4-117">[![Écran Paramètres système avec paramètres d'aide](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span><span class="sxs-lookup"><span data-stu-id="832b4-117">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span></span>

<span data-ttu-id="832b4-118">Sur la page **Paramètres système**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="832b4-118">On the **System parameters** page, follow these steps:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="832b4-119">La première fois que vous ouvrez l'onglet **Aide**, vous devez vous connecter à Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="832b4-119">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="832b4-120">Veillez à cliquer sur le lien au milieu de l'écran, attendez la connexion, fermez la boîte de dialogue, puis cliquez sur **OK** pour accéder à l'écran **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="832b4-120">Be sure to click the link in the middle of the form, wait for the connection, close the dialog box, and then click **OK** to get to the **System Parameters** page.</span></span>
>
> <span data-ttu-id="832b4-121">[![Se connecter à LCS](./media/connect-to-lcs-crop-1024x365.png "Se connecter à LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="832b4-121">[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1. <span data-ttu-id="832b4-122">Sélectionnez le projet Lifecycle Services auquel se connecter.</span><span class="sxs-lookup"><span data-stu-id="832b4-122">Select the Lifecycle Services project to connect to.</span></span>
2. <span data-ttu-id="832b4-123">Sélectionnez les bibliothèques BPM (dans le projet sélectionné) à partir desquelles récupérer les enregistrements de tâche.</span><span class="sxs-lookup"><span data-stu-id="832b4-123">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
3. <span data-ttu-id="832b4-124">Sélectionnez l'ordre d'affichage des bibliothèques BPM.</span><span class="sxs-lookup"><span data-stu-id="832b4-124">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="832b4-125">Cela déterminer l'ordre dans lequel les enregistrements de tâche des bibliothèques s'affichent dans le volet **Aide**.</span><span class="sxs-lookup"><span data-stu-id="832b4-125">This determines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="832b4-126">À l'issue de ces étapes, vous pouvez ouvrir le volet **Aide**, puis cliquer sur l'onglet **Guides de tâches**. Vous obtenez désormais les guides de tâches qui s'appliquent à la page sur laquelle vous êtes actuellement dans les applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="832b4-126">After you complete these steps, you can open the **Help** pane and click the **Task guides** tab. You'll now see the task guides that apply to the page that you're currently on in Finance and Operations apps.</span></span> <span data-ttu-id="832b4-127">Si aucun guide de tâche n'est trouvé, vous pouvez entrer des mots clés pour affiner votre recherche.</span><span class="sxs-lookup"><span data-stu-id="832b4-127">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="832b4-128">Affichage des guides de tâches traduits</span><span class="sxs-lookup"><span data-stu-id="832b4-128">Showing translated task guides</span></span>

<span data-ttu-id="832b4-129">Les guides de tâches traduits ont été expédiés pour la première fois dans la Bibliothèque unifiée APQC de mai 2016 et la bibliothèque de mise en route.</span><span class="sxs-lookup"><span data-stu-id="832b4-129">Translated task guides were first shipped in the May 2016 APQC Unified Library, and the Getting Started library.</span></span> <span data-ttu-id="832b4-130">Dans les applications Finance and Operations, pour afficher l'aide du guide de tâche localisé, assurez-vous que vous êtes connecté à la bibliothèque de mai.</span><span class="sxs-lookup"><span data-stu-id="832b4-130">In Finance and Operations apps, to see localized task guide help, make sure that you are connected to the May library.</span></span> <span data-ttu-id="832b4-131">La langue dans laquelle s'affiche un guide de tâche est contrôlée pour chaque utilisateur par les paramètres de langue sous **Options** &gt; **Préférences**.</span><span class="sxs-lookup"><span data-stu-id="832b4-131">The language that a task guide appears in is controlled for each user by the Language settings under **Options** &gt; **Preferences**.</span></span>

> [!NOTE]
> <span data-ttu-id="832b4-132">Bien que de nombreux guides des tâches aient été traduits, le client n’affiche pas les noms des guides des tâches traduits.</span><span class="sxs-lookup"><span data-stu-id="832b4-132">Even though many task guides have been translated, right now the client is not showing the translated task guide names.</span></span> <span data-ttu-id="832b4-133">De plus, seuls les guides des tâches qui ont été publiés en février 2016 sont disponibles pour la traduction dans la bibliothèque de mai à ce stade.</span><span class="sxs-lookup"><span data-stu-id="832b4-133">Also, only the task guides that were released in February 2016 are available in translation in the May library.</span></span> <span data-ttu-id="832b4-134">Nous publierons une bibliothèque mise à jour avec des traductions supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="832b4-134">We will release an updated library with additional translations.</span></span>
>
> - <span data-ttu-id="832b4-135">Si un guide de tâche a été traduit, lorsque vous ouvrez ce guide de tâche, tout le texte du guide de tâche s’affiche dans la langue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="832b4-135">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> - <span data-ttu-id="832b4-136">Si un guide de tâche n'a pas encore été traduit, lorsque vous ouvrez ce guide de tâche, une partie du texte (texte des commandes) s’affiche dans la langue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="832b4-136">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="creating-custom-help"></a><span data-ttu-id="832b4-137">Création d'une aide personnalisée</span><span class="sxs-lookup"><span data-stu-id="832b4-137">Creating custom help</span></span>

<span data-ttu-id="832b4-138">Vous pouvez utiliser des guides de tâche pour créer de l'aide personnalisée, ou connecter un site Web au volet d'aide.</span><span class="sxs-lookup"><span data-stu-id="832b4-138">You can use task guides to create custom help, or connect a website to the Help pane.</span></span>

### <a name="create-custom-help-with-task-guides"></a><span data-ttu-id="832b4-139">Créer une aide personnalisée à l'aide des guides de tâches</span><span class="sxs-lookup"><span data-stu-id="832b4-139">Create custom help with task guides</span></span>

<span data-ttu-id="832b4-140">Vous pouvez créer une aide personnalisée pour votre implémentation de Finance, Supply Chain Management, et pour Commerce en créant des enregistrements de tâche qui reflètent votre implémentation, et en les enregistrant dans une bibliothèque de processus d'entreprise LCS.</span><span class="sxs-lookup"><span data-stu-id="832b4-140">You can create custom help for Finance, Supply Chain Management, and Commerce by creating task recordings that reflect your implementation, and saving them to an LCS Business Process Library.</span></span> <span data-ttu-id="832b4-141">Vous ne pouvez pas créer de guides de tâches personnalisés pour Human Resources.</span><span class="sxs-lookup"><span data-stu-id="832b4-141">You cannot create custom task guides for Human Resources.</span></span>

<span data-ttu-id="832b4-142">Pour les partenaires, si vous faites d'une bibliothèque une bibliothèque d'entreprise et la comprenez dans une solution, elle sera à la disposition de vos clients.</span><span class="sxs-lookup"><span data-stu-id="832b4-142">For partners, if you promote a library to be a corporate library, and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="832b4-143">Vous pouvez également faire une copie de la bibliothèque globale unifiée APQC, puis ouvrir votre copie, ouvrir des enregistrements de tâches à partit de celle-ci et enregistrer les enregistrements avec vos modifications.</span><span class="sxs-lookup"><span data-stu-id="832b4-143">You can also make a copy of the APQC Unified global library, and then open your copy, open task recordings from it, modify them, and save the recordings with your changes.</span></span> <span data-ttu-id="832b4-144">Pour plus d'informations, voir [Ressources de l'enregistreur de tâches](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="832b4-144">For more information, see [Task recorder resources](../../dev-itpro/user-interface/task-recorder.md).</span></span>

### <a name="connect-a-custom-site"></a><span data-ttu-id="832b4-145">Connecter un site personnalisé</span><span class="sxs-lookup"><span data-stu-id="832b4-145">Connect a custom site</span></span>

<span data-ttu-id="832b4-146">Microsoft a fourni un livre blanc et un exemple de code qui expliquent comment créer et connecter un site d'aide personnalisée au volet d'aide.</span><span class="sxs-lookup"><span data-stu-id="832b4-146">Microsoft has provided a white paper and sample code that describe how to create and connect a custom help site to the Help pane.</span></span> <span data-ttu-id="832b4-147">Pour plus d'informations, voir :</span><span class="sxs-lookup"><span data-stu-id="832b4-147">For more information, see:</span></span>

- [<span data-ttu-id="832b4-148">Créer l'aide personnalisée pour Finance and Operations (livre blanc)</span><span class="sxs-lookup"><span data-stu-id="832b4-148">Create Custom Help for Finance and Operations apps (white paper)</span></span>](https://go.microsoft.com/fwlink/?linkid=2041185)
- [<span data-ttu-id="832b4-149">Référentiel GitHub d'aide personnalisée</span><span class="sxs-lookup"><span data-stu-id="832b4-149">Custom help GitHub repository</span></span>](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a><span data-ttu-id="832b4-150">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="832b4-150">Additional resources</span></span>

[<span data-ttu-id="832b4-151">Système d'aide</span><span class="sxs-lookup"><span data-stu-id="832b4-151">Help system</span></span>](help-overview.md)

[<span data-ttu-id="832b4-152">Ressources de l'enregistreur de tâches</span><span class="sxs-lookup"><span data-stu-id="832b4-152">Task recorder resources</span></span>](../../dev-itpro/user-interface/task-recorder.md)

[<span data-ttu-id="832b4-153">Créer une documentation ou une formation à l'aide de l'enregistreur de tâches</span><span class="sxs-lookup"><span data-stu-id="832b4-153">Create documentation or training with Task Recorder</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)
