---
title: "Connexion au système d'aide"
description: "Cette rubrique décrit les composants du système Aide pour Microsoft Dynamics 365 for Finance and Operations, explique comment les connecter entre eux et résume la création de l'aide personnalisée."
author: margoc
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: acb832c422ccb5ddb98d6ddd6b69d2e2c3e11057
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---

# <a name="connect-the-help-system"></a><span data-ttu-id="fe217-103">Connexion au système d'aide</span><span class="sxs-lookup"><span data-stu-id="fe217-103">Connect the Help system</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="fe217-104">Cette rubrique décrit les composants du système d'aide Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fe217-104">This topic describes the components of the Help system for Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="fe217-105">Elle fournit une vue d'ensemble de la procédure de connexion de ces composants et une synthèse de la création de l'aide personnalisée.</span><span class="sxs-lookup"><span data-stu-id="fe217-105">It provides an overview of how to connect these components and a summary of how to create custom help.</span></span> 

## <a name="help-architecture"></a><span data-ttu-id="fe217-106">Architecture de l'aide</span><span class="sxs-lookup"><span data-stu-id="fe217-106">Help architecture</span></span>
<span data-ttu-id="fe217-107">La figure suivante illustre les parties du système d'aide de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fe217-107">The following illustration shows the parts of the Finance and Operations Help system.</span></span> <span data-ttu-id="fe217-108">Le système d'aide intégré au produit extrait des articles du site Finance and Operations sur https://docs.microsoft.com, ainsi que les guides de tâche enregistrés dans le Concepteur de processus d'entreprise de Lifecycle Services (LCS) de Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="fe217-108">The in-product Help system pulls articles from the Finance and Operations site on https://docs.microsoft.com, as well as task guides stored in Business Process Modeler in Lifecycle Services (LCS).</span></span> 
> [!NOTE]
> <span data-ttu-id="fe217-109">Les fonctionnalités indiquées dans le schéma avec un astérisque (\*) sont planifiées, mais ne sont pas encore disponibles.</span><span class="sxs-lookup"><span data-stu-id="fe217-109">The features listed in the diagram with an asterisk (\*) are planned, but are not available yet.</span></span> <span data-ttu-id="fe217-110">[![Architecture de l'aide](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="fe217-110">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>


## <a name="connecting-the-help-system"></a><span data-ttu-id="fe217-111">Connexion au système d'aide</span><span class="sxs-lookup"><span data-stu-id="fe217-111">Connecting the Help system</span></span>
> [!NOTE]
> <span data-ttu-id="fe217-112">L'onglet **Guides de tâches** n'est pas disponible dans Microsoft Dynamics 365 for Talent et Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="fe217-112">The **Task guides** tab is currently not available in Microsoft Dynamics 365 for Talent and Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="fe217-113">Nous œuvrons actuellement pour activer cette fonctionnalité dans une future version.</span><span class="sxs-lookup"><span data-stu-id="fe217-113">We are currently working to enable this functionality in a future release.</span></span> <span data-ttu-id="fe217-114">Les guides des tâches dans l'expérience Mise en route dans Talent restent disponibles pour couvrir les fonctionnalités de base.</span><span class="sxs-lookup"><span data-stu-id="fe217-114">The Task guides in the Getting Started experience in Talent remain available to cover basic functionality.</span></span> <span data-ttu-id="fe217-115">L'aide procédurale est également disponible sur le site docs.microsoft.com ([docs.microsoft.com/dynamics365/operations)](/dynamics365/unified-operations/fin-and-ops/index) pour Retail et Talent.</span><span class="sxs-lookup"><span data-stu-id="fe217-115">Procedural help is also available on the docs.microsoft.com site ([docs.microsoft.com/dynamics365/operations](/dynamics365/unified-operations/fin-and-ops/index)) for both Retail and Talent.</span></span>
 

<span data-ttu-id="fe217-116">En utilisant le formulaire **Paramètres système**, les administrateurs système connectent les parties du système d'aide pour une implémentation.</span><span class="sxs-lookup"><span data-stu-id="fe217-116">Using the **System Parameters** page, system administrators connect the pieces of the Help system for an implementation.</span></span> <span data-ttu-id="fe217-117">[![Écran Paramètres système avec les paramètres d'aide](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Sur la page **Paramètres système**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="fe217-117">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) On the **System parameters** page, follow these steps:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe217-118">La première fois que vous ouvrez l'onglet **Aide**, vous devez vous connecter à Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="fe217-118">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="fe217-119">Veillez à cliquer sur le lien au milieu de l'écran, attendez la connexion, fermez la boîte de dialogue, puis cliquez sur **OK** pour obtenir à la page **Paramètres système**.[![Se connecter à LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="fe217-119">Be sure to click the link in the middle of the form, wait for the connection, close the dialog box, and then click **OK** to get to the **System Parameters** page.[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1.  <span data-ttu-id="fe217-120">Sélectionnez le projet Lifecycle Services auquel se connecter.</span><span class="sxs-lookup"><span data-stu-id="fe217-120">Select the Lifecycle Services project to connect to.</span></span>
2.  <span data-ttu-id="fe217-121">Sélectionnez les bibliothèques BPM (dans le projet sélectionné) à partir desquelles récupérer les enregistrements de tâche.</span><span class="sxs-lookup"><span data-stu-id="fe217-121">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
    - <span data-ttu-id="fe217-122">Pour le contenu Finance and Operations et Microsoft, sélectionnez la bibliothèque unifiée QPC de février 2017 pour Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fe217-122">For Finance and Operations, for Microsoft content, select the February 2017 QPC Unified Library for Microsoft Dynamics 365 for Finance and Operations.</span></span> 
    - <span data-ttu-id="fe217-123">Pour Retail, nous lancerons une bibliothèque en juillet.</span><span class="sxs-lookup"><span data-stu-id="fe217-123">For Retail, we will be releasing a library in July.</span></span> 
    - <span data-ttu-id="fe217-124">Vous n'avez pas besoin de sélectionner une bibliothèque pour Talent - la connexion à la bibliothèque appropriée est établie pour vous.</span><span class="sxs-lookup"><span data-stu-id="fe217-124">You do not need to select a library for Talent—the connection to the correct library is established for you.</span></span> 

3.  <span data-ttu-id="fe217-125">Sélectionnez l'ordre d'affichage des bibliothèques BPM.</span><span class="sxs-lookup"><span data-stu-id="fe217-125">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="fe217-126">Cela déterminer l'ordre dans lequel les enregistrements de tâche des bibliothèques s'affichent dans le volet **Aide**.</span><span class="sxs-lookup"><span data-stu-id="fe217-126">This determines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="fe217-127">Une fois ces étapes accomplies, vous pouvez ouvrir le volet **Aide** puis cliquer sur l'onglet **Guides de tâche**.</span><span class="sxs-lookup"><span data-stu-id="fe217-127">After you complete these steps, you can open the **Help** pane and click the **Task guides** tab.</span></span> <span data-ttu-id="fe217-128">Les guides de tâche qui s'appliquent à la page sur laquelle vous vous trouvez dans Finance and Operations s'affichent.</span><span class="sxs-lookup"><span data-stu-id="fe217-128">You'll now see the task guides that apply to the page that you’re currently on in Finance and Operations.</span></span> <span data-ttu-id="fe217-129">Si aucun guide de tâche n'est trouvé, vous pouvez entrer des mots clés pour affiner votre recherche.</span><span class="sxs-lookup"><span data-stu-id="fe217-129">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="fe217-130">Affichage des guides de tâches traduits</span><span class="sxs-lookup"><span data-stu-id="fe217-130">Showing translated task guides</span></span>

<span data-ttu-id="fe217-131">Les guides de tâches traduits ont été expédiés pour la première fois dans la Bibliothèque unifiée APQC de mai 2016 et la bibliothèque de mise en route.</span><span class="sxs-lookup"><span data-stu-id="fe217-131">Translated task guides were first shipped in the May 2016 APQC Unified Library, and the Getting Started library.</span></span> <span data-ttu-id="fe217-132">Dans Finance and Operations, pour afficher l'aide du guide de tâche localisé, assurez-vous que vous êtes connecté à la bibliothèque de mai.</span><span class="sxs-lookup"><span data-stu-id="fe217-132">In Finance and Operations, to see localized task guide help, make sure that you are connected to the May library.</span></span> <span data-ttu-id="fe217-133">La langue dans laquelle s'affiche un guide de tâche est contrôlée pour chaque utilisateur par les paramètres de langue sous **Options** &gt; **Préférences**.</span><span class="sxs-lookup"><span data-stu-id="fe217-133">The language that a task guide appears in is controlled for each user by the Language settings under **Options** &gt; **Preferences**.</span></span> 

> [!NOTE]
> <span data-ttu-id="fe217-134">Bien que de nombreux guides des tâches aient été traduits, le client Finance and Operations n’affiche pas les noms des guides des tâches traduits.</span><span class="sxs-lookup"><span data-stu-id="fe217-134">Even though many task guides have been translated, right now the Finance and Operations client is not showing the translated task guide names.</span></span> <span data-ttu-id="fe217-135">De plus, seuls les guides des tâches qui ont été publiés en février 2016 sont disponibles pour la traduction dans la bibliothèque de mai à ce stade.</span><span class="sxs-lookup"><span data-stu-id="fe217-135">Also, only the task guides that were released in February 2016 are available in translation in the May library.</span></span> <span data-ttu-id="fe217-136">Nous publierons une bibliothèque mise à jour avec des traductions supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="fe217-136">We will release an updated library with additional translations.</span></span>
> -   <span data-ttu-id="fe217-137">Si un guide de tâche a été traduit, lorsque vous ouvrez ce guide de tâche, tout le texte du guide de tâche s’affiche dans la langue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fe217-137">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> -   <span data-ttu-id="fe217-138">Si un guide de tâche n'a pas encore été traduit, lorsque vous ouvrez ce guide de tâche, une partie du texte (texte des commandes) s’affiche dans la langue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fe217-138">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="creating-custom-help"></a><span data-ttu-id="fe217-139">Création d'une aide personnalisée</span><span class="sxs-lookup"><span data-stu-id="fe217-139">Creating custom help</span></span>
<span data-ttu-id="fe217-140">Vous pouvez créer une aide personnalisée pour votre implémentation de Finance and Operations, et pour Retail en créant des enregistrements de tâche qui reflètent votre implémentation, et en les enregistrant dans une bibliothèque de processus d'entreprise LCS.</span><span class="sxs-lookup"><span data-stu-id="fe217-140">You can create custom help for Finance and Operations, and for Retail by creating task recordings that reflect your implementation, and saving them to an LCS Business Process Library.</span></span> <span data-ttu-id="fe217-141">Vous ne pouvez pas créer de guides de tâche personnalisés pour Talent.</span><span class="sxs-lookup"><span data-stu-id="fe217-141">You cannot create custom task guides for Talent.</span></span> 

<span data-ttu-id="fe217-142">Pour les partenaires, si vous faites d'une bibliothèque une bibliothèque d'entreprise et la comprenez dans une solution, elle sera à la disposition de vos clients.</span><span class="sxs-lookup"><span data-stu-id="fe217-142">For partners, if you promote a library to be a corporate library, and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="fe217-143">Vous pouvez également faire une copie de la bibliothèque globale unifiée APQC, puis ouvrir votre copie, ouvrir des enregistrements de tâches à partit de celle-ci et enregistrer les enregistrements avec vos modifications.</span><span class="sxs-lookup"><span data-stu-id="fe217-143">You can also make a copy of the APQC Unified global library, and then open your copy, open task recordings from it, modify them, and save the recordings with your changes.</span></span> <span data-ttu-id="fe217-144">Pour plus d'informations, consultez [Création d'un enregistrement de tâche pour l'utiliser comme documentation ou formation](../user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="fe217-144">For more information, see [How to create a task recording to use as documentation or training](../user-interface/task-recorder.md).</span></span>

<a name="see-also"></a><span data-ttu-id="fe217-145">Voir également :</span><span class="sxs-lookup"><span data-stu-id="fe217-145">See also</span></span>
--------

[<span data-ttu-id="fe217-146">Vue d'ensemble de l'Aide</span><span class="sxs-lookup"><span data-stu-id="fe217-146">Help overview</span></span>](help-overview.md)

[<span data-ttu-id="fe217-147">Vue d'ensemble de l'enregistreur de tâches</span><span class="sxs-lookup"><span data-stu-id="fe217-147">Task recorder overview</span></span>](../user-interface/task-recorder.md)

[<span data-ttu-id="fe217-148">Procédure de création d'un enregistrement de tâche à utiliser comme documentation ou formation</span><span class="sxs-lookup"><span data-stu-id="fe217-148">How to create a task recording to use as documentation or training</span></span>](../user-interface/task-recorder-training-docs.md)





