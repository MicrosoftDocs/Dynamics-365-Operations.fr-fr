---
title: Gérer les fichiers robots.txt
description: Cette rubrique décrit comment gérer les fichiers robots.txt dans Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: brishoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: e472f3612bd6860e7262bb128035f2aed3b39372
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946010"
---
# <a name="manage-robotstxt-files"></a><span data-ttu-id="ca0de-103">Gérer les fichiers robots.txt</span><span class="sxs-lookup"><span data-stu-id="ca0de-103">Manage robots.txt files</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="ca0de-104">Cette rubrique décrit comment gérer les fichiers robots.txt dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca0de-104">This topic describes how to manage robots.txt files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ca0de-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="ca0de-105">Overview</span></span>

<span data-ttu-id="ca0de-106">La norme d'exclusion des bots, ou robots.txt, est une norme que les sites web utilisent pour communiquer avec les bots web.</span><span class="sxs-lookup"><span data-stu-id="ca0de-106">The robots exclusion standard, or robots.txt, is a standard that websites use to communicate with web robots.</span></span> <span data-ttu-id="ca0de-107">Elle indique aux bots web les zones d'un site web qui ne doivent pas être visitées.</span><span class="sxs-lookup"><span data-stu-id="ca0de-107">It instructs web robots about any areas of a website that should not be visited.</span></span> <span data-ttu-id="ca0de-108">Les bots sont souvent utilisés par les moteurs de recherche pour indexer les sites web.</span><span class="sxs-lookup"><span data-stu-id="ca0de-108">Robots are often used by search engines to index websites.</span></span>

<span data-ttu-id="ca0de-109">Pour exclure des bots d'un serveur, vous créez un fichier sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="ca0de-109">To exclude robots from a server, you create a file on the server.</span></span> <span data-ttu-id="ca0de-110">Dans ce fichier, vous spécifiez une stratégie d'accès pour les bots.</span><span class="sxs-lookup"><span data-stu-id="ca0de-110">In this file, you specify an access policy for robots.</span></span> <span data-ttu-id="ca0de-111">Le fichier doit être accessible via HTTP à l'URL locale **/robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="ca0de-111">The file must be accessible via HTTP at the local URL **/robots.txt**.</span></span> <span data-ttu-id="ca0de-112">Le fichier robots.txt aide les moteurs de recherche à indexer le contenu de votre site.</span><span class="sxs-lookup"><span data-stu-id="ca0de-112">The robots.txt file helps search engines index the content on your site.</span></span>

<span data-ttu-id="ca0de-113">Dynamics 365 Commerce vous permet de télécharger un fichier robots.txt pour votre domaine.</span><span class="sxs-lookup"><span data-stu-id="ca0de-113">Dynamics 365 Commerce lets you upload a robots.txt file for your domain.</span></span> <span data-ttu-id="ca0de-114">Pour chaque domaine de votre environnement Commerce, vous pouvez télécharger un fichier robots.txt et l'associer à ce domaine.</span><span class="sxs-lookup"><span data-stu-id="ca0de-114">For each domain in your Commerce environment, you can upload one robots.txt file and associate it with that domain.</span></span>

<span data-ttu-id="ca0de-115">Pour plus d'informations sur le fichier robots.txt, visitez [Les pages de bots web](https://www.robotstxt.org/).</span><span class="sxs-lookup"><span data-stu-id="ca0de-115">For more information about the robots.txt file, visit [The Web Robots Pages](https://www.robotstxt.org/).</span></span>

## <a name="upload-a-robotstxt-file"></a><span data-ttu-id="ca0de-116">Charger un fichier robots.txt</span><span class="sxs-lookup"><span data-stu-id="ca0de-116">Upload a robots.txt file</span></span>

<span data-ttu-id="ca0de-117">Après avoir créé et modifié votre fichier robots.txt conformément à la [norme d'exclusion des bots](https://www.robotstxt.org/orig.html), assurez-vous que le fichier est accessible sur l'ordinateur sur lequel vous utiliserez les outils de création de Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca0de-117">After you've created and edited your robots.txt file according to the [robots exclusion standard](https://www.robotstxt.org/orig.html), make sure that the file is accessible on the computer where you will use the Commerce authoring tools.</span></span> <span data-ttu-id="ca0de-118">Le fichier doit être nommé **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="ca0de-118">The file must be named **robots.txt**.</span></span> <span data-ttu-id="ca0de-119">Pour de meilleurs résultats, il doit être dans le format indiqué dans la norme.</span><span class="sxs-lookup"><span data-stu-id="ca0de-119">For best results, it must be in the format that is noted in the standard.</span></span> <span data-ttu-id="ca0de-120">Chaque client Commerce est responsable de la validation et de la maintenance du contenu de son fichier robots.txt.</span><span class="sxs-lookup"><span data-stu-id="ca0de-120">Each Commerce customer is responsible for validating and maintaining the contents of its robots.txt file.</span></span> <span data-ttu-id="ca0de-121">Pour charger un fichier robots.txt, vous devez être connecté à Commerce en tant qu'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="ca0de-121">To upload a robots.txt file, you must be signed in to Commerce as a system admin.</span></span>

<span data-ttu-id="ca0de-122">Pour charger un fichier robots.txt sur votre site dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ca0de-122">To upload a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="ca0de-123">Connectez-vous à Commerce en tant qu'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="ca0de-123">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="ca0de-124">Dans le volet de navigation de gauche, sélectionnez **Paramètres du client** (à côté du symbole d'engrenage) pour l'agrandir.</span><span class="sxs-lookup"><span data-stu-id="ca0de-124">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="ca0de-125">En dessous de **Paramètres client**, sélectionnez **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="ca0de-125">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="ca0de-126">Une liste de tous les domaines associés à votre environnement apparaît dans la partie principale de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="ca0de-126">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="ca0de-127">Sélectionnez **Gérer** pour charger un fichier robots.txt pour un domaine dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="ca0de-127">Select **Manage** to upload a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="ca0de-128">Dans le menu de droite, cliquez sur le bouton **Télécharger** (flèche pointant vers le haut) à côté du domaine associé au fichier robots.txt.</span><span class="sxs-lookup"><span data-stu-id="ca0de-128">On the menu on the right, select the **Upload** button (the upward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="ca0de-129">Une boîte de dialogue d'explorateur de fichiers apparaît.</span><span class="sxs-lookup"><span data-stu-id="ca0de-129">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="ca0de-130">Dans la boîte de dialogue, recherchez et sélectionnez le fichier robots.txt que vous souhaitez charger pour le domaine associé, puis sélectionnez **Ouvrir** pour terminer le chargement.</span><span class="sxs-lookup"><span data-stu-id="ca0de-130">In the dialog box, browse to and select the robots.txt file that you want to upload for the associated domain, and then select **Open** to complete the upload.</span></span>

> [!NOTE] 
> <span data-ttu-id="ca0de-131">Pendant le chargement, Commerce vérifie que le fichier est un fichier texte, mais il ne valide pas le contenu du fichier.</span><span class="sxs-lookup"><span data-stu-id="ca0de-131">During upload, Commerce verifies that the file is a text file, but it doesn't validate the file's contents.</span></span>

## <a name="download-a-robotstxt-file"></a><span data-ttu-id="ca0de-132">Télécharger un fichier robots.txt</span><span class="sxs-lookup"><span data-stu-id="ca0de-132">Download a robots.txt file</span></span>

<span data-ttu-id="ca0de-133">Pour télécharger un fichier robots.txt sur votre site dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ca0de-133">To download a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="ca0de-134">Connectez-vous à Commerce en tant qu'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="ca0de-134">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="ca0de-135">Dans le volet de navigation de gauche, sélectionnez **Paramètres du client** (à côté du symbole d'engrenage) pour l'agrandir.</span><span class="sxs-lookup"><span data-stu-id="ca0de-135">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="ca0de-136">En dessous de **Paramètres client**, sélectionnez **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="ca0de-136">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="ca0de-137">Une liste de tous les domaines associés à votre environnement apparaît dans la partie principale de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="ca0de-137">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="ca0de-138">Sélectionnez **Gérer** pour télécharger un fichier robots.txt pour un domaine dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="ca0de-138">Select **Manage** to download a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="ca0de-139">Dans le menu de droite, cliquez sur le bouton **Télécharger** (flèche pointant vers le bas) à côté du domaine associé au fichier robots.txt.</span><span class="sxs-lookup"><span data-stu-id="ca0de-139">On the menu on the right, select the **Download** button (the downward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="ca0de-140">Une boîte de dialogue d'explorateur de fichiers apparaît.</span><span class="sxs-lookup"><span data-stu-id="ca0de-140">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="ca0de-141">Dans la boîte de dialogue, accédez à l'emplacement souhaité sur votre lecteur local, confirmez ou entrez un nom de fichier, puis sélectionnez **Enregistrer** pour terminer le téléchargement.</span><span class="sxs-lookup"><span data-stu-id="ca0de-141">In the dialog box, go to the desired location on your local drive, confirm or enter a file name, and then select **Save** to complete the download.</span></span>

> [!NOTE]
> <span data-ttu-id="ca0de-142">Cette procédure peut être utilisée pour télécharger uniquement les fichiers robots.txt qui ont été précédemment chargés via les outils de création de Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca0de-142">This procedure can be used to download only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="delete-a-robotstxt-file"></a><span data-ttu-id="ca0de-143">Supprimer un fichier robots.txt</span><span class="sxs-lookup"><span data-stu-id="ca0de-143">Delete a robots.txt file</span></span>

<span data-ttu-id="ca0de-144">Pour supprimer un fichier robots.txt sur votre site dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ca0de-144">To delete a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="ca0de-145">Connectez-vous à Commerce en tant qu'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="ca0de-145">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="ca0de-146">Dans le volet de navigation de gauche, sélectionnez **Paramètres du client** (à côté du symbole d'engrenage) pour l'agrandir.</span><span class="sxs-lookup"><span data-stu-id="ca0de-146">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="ca0de-147">En dessous de **Paramètres client**, sélectionnez **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="ca0de-147">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="ca0de-148">Une liste de tous les domaines associés à votre environnement apparaît dans la partie principale de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="ca0de-148">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="ca0de-149">Sélectionnez **Gérer** pour supprimer un fichier robots.txt pour un domaine dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="ca0de-149">Select **Manage** to delete a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="ca0de-150">Dans le menu de droite, cliquez sur le bouton **Supprimer** (symbole de corbeille) à côté du domaine associé au fichier robots.txt.</span><span class="sxs-lookup"><span data-stu-id="ca0de-150">On the menu on the right, select the **Delete** button (the trash can symbol) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="ca0de-151">Une fenêtre de l'explorateur de fichiers apparaît.</span><span class="sxs-lookup"><span data-stu-id="ca0de-151">A file browser window appears.</span></span>
6. <span data-ttu-id="ca0de-152">Dans la fenêtre de l'explorateur de fichiers, recherchez et sélectionnez le fichier robots.txt que vous souhaitez supprimer pour le domaine, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="ca0de-152">In the file browser window, browse to and select the robots.txt file that you want to delete for the domain, and then select **Open**.</span></span> <span data-ttu-id="ca0de-153">Une zone de message d'avertissement apparaît.</span><span class="sxs-lookup"><span data-stu-id="ca0de-153">A warning message box appears.</span></span>
7. <span data-ttu-id="ca0de-154">Dans la zone de message, sélectionnez **Supprimer** pour confirmer la suppression du fichier robots.txt.</span><span class="sxs-lookup"><span data-stu-id="ca0de-154">In the message box, select **Delete** to confirm deletion of the robots.txt file.</span></span>

> [!NOTE] 
> <span data-ttu-id="ca0de-155">Cette procédure peut être utilisée pour supprimer uniquement les fichiers robots.txt qui ont été précédemment chargés via les outils de création de Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca0de-155">This procedure can be used to delete only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ca0de-156">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ca0de-156">Additional resources</span></span>

[<span data-ttu-id="ca0de-157">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="ca0de-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="ca0de-158">Déploiement d'un nouveau site de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="ca0de-158">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="ca0de-159">Création d'un site de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="ca0de-159">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="ca0de-160">Association d'un site en ligne avec un canal</span><span class="sxs-lookup"><span data-stu-id="ca0de-160">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="ca0de-161">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="ca0de-161">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="ca0de-162">Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="ca0de-162">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="ca0de-163">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="ca0de-163">Enable location-based store detection</span></span>](enable-store-detection.md)
