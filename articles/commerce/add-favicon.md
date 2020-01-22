---
title: Ajouter une icône de favori
description: Cette rubrique explique comment ajouter une icône de favori à votre site.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 18e12cbe46650fcf024a56b6de9a8cb2903d2bf8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914570"
---
# <a name="add-a-favicon"></a><span data-ttu-id="f390e-103">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="f390e-103">Add a favicon</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="f390e-104">Cette rubrique explique comment ajouter une icône de favori à votre site.</span><span class="sxs-lookup"><span data-stu-id="f390e-104">This topic explains how to add a favicon to your site.</span></span>

## <a name="overview"></a><span data-ttu-id="f390e-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="f390e-105">Overview</span></span>

<span data-ttu-id="f390e-106">Une icône de favori est un petit fichier graphique affiché sous un onglet du navigateur web, dans la barre d'adresse, dans l'historique de navigation, et dans les signets ou les favoris, entre autres.</span><span class="sxs-lookup"><span data-stu-id="f390e-106">A favicon is a small graphics file that is shown on a web browser tab, in the Address bar, in the browsing history, and in bookmarks or favorites, among other places.</span></span> <span data-ttu-id="f390e-107">Nous vous recommandons d'ajouter une icône de favori à votre site, car elle représente et renforce votre marque, et aide à distinguer votre site d'autres sites que vos clients visitent.</span><span class="sxs-lookup"><span data-stu-id="f390e-107">We recommend that you add a favicon to your site, because it represents and reinforces your brand, and helps distinguish your site from other sites that your customers visit.</span></span>

<span data-ttu-id="f390e-108">Bien que vous puissiez ajouter plusieurs icônes de favori de différentes tailles et types de fichiers à votre site, cette rubrique explique comment ajouter une icône de favori unique.</span><span class="sxs-lookup"><span data-stu-id="f390e-108">Although you can add multiple favicons of various sizes and file types to your site, this topic shows how to add a single favicon.</span></span> <span data-ttu-id="f390e-109">Toutefois, les mêmes processus et emplacement sont utilisés pour ajouter des une icônes de favori.</span><span class="sxs-lookup"><span data-stu-id="f390e-109">However, the same process and location are used to add more favicons.</span></span>

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a><span data-ttu-id="f390e-110">Chargement de l'icône de favori dans la collection d'actifs du site</span><span class="sxs-lookup"><span data-stu-id="f390e-110">Upload a favicon to your site's asset collection</span></span>

<span data-ttu-id="f390e-111">Pour charger l'icône de favori dans la collection d'actifs du site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f390e-111">To upload a favicon to your site's asset collection, follow these steps.</span></span>

1. <span data-ttu-id="f390e-112">Accédez à **Actifs \> Charger \> Charger des actifs**.</span><span class="sxs-lookup"><span data-stu-id="f390e-112">Go to **Assets \> Upload \> Upload assets**.</span></span>
1. <span data-ttu-id="f390e-113">Recherchez et sélectionnez l'icône de favori sur votre système de fichiers local.</span><span class="sxs-lookup"><span data-stu-id="f390e-113">Find and select the favicon on your local file system.</span></span>
1. <span data-ttu-id="f390e-114">Entrez un titre, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="f390e-114">Enter a title, and then select **OK**.</span></span> 
1. <span data-ttu-id="f390e-115">Dans le volet de propriété de droite, copiez l'URL publique de l'icône de favori.</span><span class="sxs-lookup"><span data-stu-id="f390e-115">In the property pane on the right, copy the public URL of the favicon.</span></span>

> [!NOTE]
> <span data-ttu-id="f390e-116">Si vous ne sélectionnez pas l'option **Publier les actifs après chargement**, vous devez retourner à la page **Actifs** et publier manuellement l'icône de favori ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="f390e-116">If you don't select the **Publish assets after upload** option, you must return to **Assets** page and manually publish the favicon later.</span></span>

## <a name="create-the-html-for-the-favicon"></a><span data-ttu-id="f390e-117">Créer l'HTML pour l'icône de favori</span><span class="sxs-lookup"><span data-stu-id="f390e-117">Create the HTML for the favicon</span></span>

<span data-ttu-id="f390e-118">Pour créer le fichier HTML pour l'icône de favori, utilisez l'extrait de code HTML.</span><span class="sxs-lookup"><span data-stu-id="f390e-118">To create the HTML for the favicon, use the following HTML snippet.</span></span> <span data-ttu-id="f390e-119">Pour l'attribut **href**, remplacez **« Public\_URL\_pour\_votre\_icône_de_favori »** par l'URL publique copiée précédemment.</span><span class="sxs-lookup"><span data-stu-id="f390e-119">For the **href** attribute, replace **"Public\_URL\_for\_your\_favicon"** with the public URL that you copied earlier.</span></span>

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="add-the-html-for-the-favicon-to-the-head-element-of-your-pages"></a><span data-ttu-id="f390e-120">Ajoutez l'HTML pour l'icône de favori à l'élément \<en-tête\> de vos pages</span><span class="sxs-lookup"><span data-stu-id="f390e-120">Add the HTML for the favicon to the \<head\> element of your pages</span></span>

<span data-ttu-id="f390e-121">Pour ajouter une icône de favori à votre site, utilisez la même procédure que pour ajouter un type de HTML ou un script à l'élément **\<en-tête\>** des pages de votre site.</span><span class="sxs-lookup"><span data-stu-id="f390e-121">To add a favicon to your site, use the same procedure that is used to add any type of HTML or script to the **\<head\>** element of your site pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f390e-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f390e-122">Additional resources</span></span>

[<span data-ttu-id="f390e-123">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="f390e-123">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="f390e-124">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="f390e-124">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="f390e-125">Utilisation de fichiers de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="f390e-125">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="f390e-126">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="f390e-126">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="f390e-127">Ajouter un avis de droits d'auteur</span><span class="sxs-lookup"><span data-stu-id="f390e-127">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="f390e-128">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="f390e-128">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="f390e-129">Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="f390e-129">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

