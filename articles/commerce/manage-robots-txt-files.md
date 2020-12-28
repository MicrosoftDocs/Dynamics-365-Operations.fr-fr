---
title: Gérer les fichiers robots.txt
description: Cette rubrique décrit comment gérer les fichiers robots.txt dans Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 07/02/2020
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
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: ad87594b9c20d0c2b53e8d4e7c1170a78babe74b
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517450"
---
# <a name="manage-robotstxt-files"></a><span data-ttu-id="2a9ec-103">Gérer les fichiers robots.txt</span><span class="sxs-lookup"><span data-stu-id="2a9ec-103">Manage robots.txt files</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="2a9ec-104">Cette rubrique décrit comment gérer les fichiers robots.txt dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-104">This topic describes how to manage robots.txt files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2a9ec-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="2a9ec-105">Overview</span></span>

<span data-ttu-id="2a9ec-106">La norme d'exclusion des bots, ou robots.txt, est une norme que les sites web utilisent pour communiquer avec les bots web.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-106">The robots exclusion standard, or robots.txt, is a standard that websites use to communicate with web robots.</span></span> <span data-ttu-id="2a9ec-107">Elle indique aux bots web les zones d'un site web qui ne doivent pas être visitées.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-107">It instructs web robots about any areas of a website that should not be visited.</span></span> <span data-ttu-id="2a9ec-108">Les bots sont souvent utilisés par les moteurs de recherche pour indexer les sites web.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-108">Robots are often used by search engines to index websites.</span></span>

<span data-ttu-id="2a9ec-109">Pour exclure des bots d'un serveur, vous créez un fichier sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-109">To exclude robots from a server, you create a file on the server.</span></span> <span data-ttu-id="2a9ec-110">Dans ce fichier, vous spécifiez une stratégie d'accès pour les bots.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-110">In this file, you specify an access policy for robots.</span></span> <span data-ttu-id="2a9ec-111">Le fichier doit être accessible via HTTP à l'URL locale **/robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-111">The file must be accessible via HTTP at the local URL **/robots.txt**.</span></span> <span data-ttu-id="2a9ec-112">Le fichier robots.txt aide les moteurs de recherche à indexer le contenu de votre site.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-112">The robots.txt file helps search engines index the content on your site.</span></span>

<span data-ttu-id="2a9ec-113">Dynamics 365 Commerce vous permet de télécharger un fichier robots.txt pour votre domaine.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-113">Dynamics 365 Commerce lets you upload a robots.txt file for your domain.</span></span> <span data-ttu-id="2a9ec-114">Pour chaque domaine de votre environnement Commerce, vous pouvez télécharger un fichier robots.txt et l'associer à ce domaine.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-114">For each domain in your Commerce environment, you can upload one robots.txt file and associate it with that domain.</span></span>

<span data-ttu-id="2a9ec-115">Pour plus d'informations sur le fichier robots.txt, visitez [Les pages de bots web](https://www.robotstxt.org/).</span><span class="sxs-lookup"><span data-stu-id="2a9ec-115">For more information about the robots.txt file, visit [The Web Robots Pages](https://www.robotstxt.org/).</span></span>

## <a name="upload-a-robotstxt-file"></a><span data-ttu-id="2a9ec-116">Charger un fichier robots.txt</span><span class="sxs-lookup"><span data-stu-id="2a9ec-116">Upload a robots.txt file</span></span>

<span data-ttu-id="2a9ec-117">Après avoir créé et modifié votre fichier robots.txt conformément à la [norme d'exclusion des bots](https://www.robotstxt.org/orig.html), assurez-vous que le fichier est accessible sur l'ordinateur sur lequel vous utiliserez les outils de création de Commerce.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-117">After you've created and edited your robots.txt file according to the [robots exclusion standard](https://www.robotstxt.org/orig.html), make sure that the file is accessible on the computer where you will use the Commerce authoring tools.</span></span> <span data-ttu-id="2a9ec-118">Le fichier doit être nommé **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-118">The file must be named **robots.txt**.</span></span> <span data-ttu-id="2a9ec-119">Pour de meilleurs résultats, il doit être dans le format indiqué dans la norme.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-119">For best results, it must be in the format that is noted in the standard.</span></span> <span data-ttu-id="2a9ec-120">Chaque client Commerce est responsable de la validation et de la maintenance du contenu de son fichier robots.txt.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-120">Each Commerce customer is responsible for validating and maintaining the contents of its robots.txt file.</span></span> <span data-ttu-id="2a9ec-121">Pour charger un fichier robots.txt, vous devez être connecté à Commerce en tant qu'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-121">To upload a robots.txt file, you must be signed in to Commerce as a system admin.</span></span>

<span data-ttu-id="2a9ec-122">Pour charger un fichier robots.txt sur votre site dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-122">To upload a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="2a9ec-123">Connectez-vous à Commerce en tant qu'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-123">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="2a9ec-124">Dans le volet de navigation de gauche, sélectionnez **Paramètres du client** (à côté du symbole d'engrenage) pour l'agrandir.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-124">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="2a9ec-125">En dessous de **Paramètres client**, sélectionnez **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-125">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="2a9ec-126">Une liste de tous les domaines associés à votre environnement apparaît dans la partie principale de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-126">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="2a9ec-127">Sélectionnez **Gérer** pour charger un fichier robots.txt pour un domaine dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-127">Select **Manage** to upload a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="2a9ec-128">Dans le menu de droite, cliquez sur le bouton **Télécharger** (flèche pointant vers le haut) à côté du domaine associé au fichier robots.txt.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-128">On the menu on the right, select the **Upload** button (the upward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="2a9ec-129">Une boîte de dialogue d'explorateur de fichiers apparaît.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-129">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="2a9ec-130">Dans la boîte de dialogue, recherchez et sélectionnez le fichier robots.txt que vous souhaitez charger pour le domaine associé, puis sélectionnez **Ouvrir** pour terminer le chargement.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-130">In the dialog box, browse to and select the robots.txt file that you want to upload for the associated domain, and then select **Open** to complete the upload.</span></span>

> [!NOTE] 
> <span data-ttu-id="2a9ec-131">Pendant le chargement, Commerce vérifie que le fichier est un fichier texte, mais il ne valide pas le contenu du fichier.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-131">During upload, Commerce verifies that the file is a text file, but it doesn't validate the file's contents.</span></span>

## <a name="download-a-robotstxt-file"></a><span data-ttu-id="2a9ec-132">Télécharger un fichier robots.txt</span><span class="sxs-lookup"><span data-stu-id="2a9ec-132">Download a robots.txt file</span></span>

<span data-ttu-id="2a9ec-133">Pour télécharger un fichier robots.txt sur votre site dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-133">To download a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="2a9ec-134">Connectez-vous à Commerce en tant qu'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-134">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="2a9ec-135">Dans le volet de navigation de gauche, sélectionnez **Paramètres du client** (à côté du symbole d'engrenage) pour l'agrandir.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-135">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="2a9ec-136">En dessous de **Paramètres client**, sélectionnez **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-136">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="2a9ec-137">Une liste de tous les domaines associés à votre environnement apparaît dans la partie principale de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-137">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="2a9ec-138">Sélectionnez **Gérer** pour télécharger un fichier robots.txt pour un domaine dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-138">Select **Manage** to download a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="2a9ec-139">Dans le menu de droite, cliquez sur le bouton **Télécharger** (flèche pointant vers le bas) à côté du domaine associé au fichier robots.txt.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-139">On the menu on the right, select the **Download** button (the downward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="2a9ec-140">Une boîte de dialogue d'explorateur de fichiers apparaît.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-140">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="2a9ec-141">Dans la boîte de dialogue, accédez à l'emplacement souhaité sur votre lecteur local, confirmez ou entrez un nom de fichier, puis sélectionnez **Enregistrer** pour terminer le téléchargement.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-141">In the dialog box, go to the desired location on your local drive, confirm or enter a file name, and then select **Save** to complete the download.</span></span>

> [!NOTE]
> <span data-ttu-id="2a9ec-142">Cette procédure peut être utilisée pour télécharger uniquement les fichiers robots.txt qui ont été précédemment chargés via les outils de création de Commerce.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-142">This procedure can be used to download only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="delete-a-robotstxt-file"></a><span data-ttu-id="2a9ec-143">Supprimer un fichier robots.txt</span><span class="sxs-lookup"><span data-stu-id="2a9ec-143">Delete a robots.txt file</span></span>

<span data-ttu-id="2a9ec-144">Pour supprimer un fichier robots.txt sur votre site dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-144">To delete a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="2a9ec-145">Connectez-vous à Commerce en tant qu'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-145">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="2a9ec-146">Dans le volet de navigation de gauche, sélectionnez **Paramètres du client** (à côté du symbole d'engrenage) pour l'agrandir.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-146">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="2a9ec-147">En dessous de **Paramètres client**, sélectionnez **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-147">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="2a9ec-148">Une liste de tous les domaines associés à votre environnement apparaît dans la partie principale de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-148">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="2a9ec-149">Sélectionnez **Gérer** pour supprimer un fichier robots.txt pour un domaine dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-149">Select **Manage** to delete a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="2a9ec-150">Dans le menu de droite, cliquez sur le bouton **Supprimer** (symbole de corbeille) à côté du domaine associé au fichier robots.txt.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-150">On the menu on the right, select the **Delete** button (the trash can symbol) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="2a9ec-151">Une fenêtre de l'explorateur de fichiers apparaît.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-151">A file browser window appears.</span></span>
6. <span data-ttu-id="2a9ec-152">Dans la fenêtre de l'explorateur de fichiers, recherchez et sélectionnez le fichier robots.txt que vous souhaitez supprimer pour le domaine, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-152">In the file browser window, browse to and select the robots.txt file that you want to delete for the domain, and then select **Open**.</span></span> <span data-ttu-id="2a9ec-153">Une zone de message d'avertissement apparaît.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-153">A warning message box appears.</span></span>
7. <span data-ttu-id="2a9ec-154">Dans la zone de message, sélectionnez **Supprimer** pour confirmer la suppression du fichier robots.txt.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-154">In the message box, select **Delete** to confirm deletion of the robots.txt file.</span></span>

> [!NOTE] 
> <span data-ttu-id="2a9ec-155">Cette procédure peut être utilisée pour supprimer uniquement les fichiers robots.txt qui ont été précédemment chargés via les outils de création de Commerce.</span><span class="sxs-lookup"><span data-stu-id="2a9ec-155">This procedure can be used to delete only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2a9ec-156">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2a9ec-156">Additional resources</span></span>

[<span data-ttu-id="2a9ec-157">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="2a9ec-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="2a9ec-158">Déployer un nouveau client e-commerce</span><span class="sxs-lookup"><span data-stu-id="2a9ec-158">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="2a9ec-159">Créer un site d’e-commerce</span><span class="sxs-lookup"><span data-stu-id="2a9ec-159">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="2a9ec-160">Associer un site Dynamics 365 Commerce avec un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="2a9ec-160">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="2a9ec-161">Importer des redirections d’URL en bloc</span><span class="sxs-lookup"><span data-stu-id="2a9ec-161">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="2a9ec-162">Configurer un client B2C dans Commerce</span><span class="sxs-lookup"><span data-stu-id="2a9ec-162">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="2a9ec-163">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="2a9ec-163">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="2a9ec-164">Configurer plusieurs locataires B2C dans un environnement Commerce</span><span class="sxs-lookup"><span data-stu-id="2a9ec-164">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="2a9ec-165">Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="2a9ec-165">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="2a9ec-166">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="2a9ec-166">Enable location-based store detection</span></span>](enable-store-detection.md)
