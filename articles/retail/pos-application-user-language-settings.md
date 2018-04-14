---
title: "Paramètres de langue d'application et d'utilisateur de PDV"
description: "Cette rubrique décrit la modification des paramètres de langue dans Retail Modern POS (MPOS) et Cloud POS."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 8c265332b132f51e948fff9e6feffee94c38ff07
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="pos-application-and-user-language-settings"></a><span data-ttu-id="744e5-103">Paramètres de langue d'application et d'utilisateur de PDV</span><span class="sxs-lookup"><span data-stu-id="744e5-103">POS application and user language settings</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="744e5-104">Cette rubrique décrit la modification des paramètres de langue dans Retail Modern POS (MPOS) et Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="744e5-104">This topic describes how to change language settings in Retail Modern POS (MPOS) and Cloud POS.</span></span>

## <a name="overview"></a><span data-ttu-id="744e5-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="744e5-105">Overview</span></span>
<span data-ttu-id="744e5-106">Retail Modern POS (MPOS) et Cloud POS prennent en charge les environnements dans lesquels les paramètres de langue et les traductions peuvent varier entre le magasin et les paramètres d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="744e5-106">Retail Modern POS (MPOS) and Cloud POS support environments where language settings and translations can vary between the store and user settings.</span></span> <span data-ttu-id="744e5-107">Par exemple, le magasin peut être situé dans une région où l'anglais est la langue la plus parlée par les clients, mais certains collaborateurs préfèrent utiliser l'application avec des traductions françaises.</span><span class="sxs-lookup"><span data-stu-id="744e5-107">For example, the store could be located in a region where English is most common for their customers, but some workers prefer to use the application with French translations.</span></span>

## <a name="data-language"></a><span data-ttu-id="744e5-108">Langue des données</span><span class="sxs-lookup"><span data-stu-id="744e5-108">Data language</span></span>
<span data-ttu-id="744e5-109">Quels que soient les paramètres de l'utilisateur, MPOS et Cloud POS emploieront toujours les paramètres de langue des magasins pour déterminer les traductions utilisées pour les données.</span><span class="sxs-lookup"><span data-stu-id="744e5-109">Regardless of the user’s settings, MPOS and Cloud POS will always use the store's language settings to determine the translations used for data.</span></span> <span data-ttu-id="744e5-110">Cela permet d'assurer à tous les utilisateurs et les clients une expérience cohérente.</span><span class="sxs-lookup"><span data-stu-id="744e5-110">This will ensure that all users and customers will have a consistent experience.</span></span>  <span data-ttu-id="744e5-111">Les exemples de données sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="744e5-111">Examples of data include:</span></span>

-   <span data-ttu-id="744e5-112">Produits</span><span class="sxs-lookup"><span data-stu-id="744e5-112">Products</span></span>
-   <span data-ttu-id="744e5-113">Attributs et valeurs</span><span class="sxs-lookup"><span data-stu-id="744e5-113">Attributes and values</span></span>
-   <span data-ttu-id="744e5-114">Noms de catégorie</span><span class="sxs-lookup"><span data-stu-id="744e5-114">Category names</span></span>
-   <span data-ttu-id="744e5-115">Reçus de transaction imprimés ou envoyés par courrier électronique</span><span class="sxs-lookup"><span data-stu-id="744e5-115">Printed or emailed transaction receipts</span></span>
-   <span data-ttu-id="744e5-116">Noms de mode de paiement</span><span class="sxs-lookup"><span data-stu-id="744e5-116">Payment method names</span></span>
-   <span data-ttu-id="744e5-117">Messages d'affichage de ligne</span><span class="sxs-lookup"><span data-stu-id="744e5-117">Line display messages</span></span>

<span data-ttu-id="744e5-118">La langue du magasin est également utilisée pour l'écran de connexion principal du PDV, puisque l'utilisateur n'est pas connu avant de se connecter.</span><span class="sxs-lookup"><span data-stu-id="744e5-118">The store’s language will also be used for the main POS login screen, since the user is not known before logging in.</span></span> <span data-ttu-id="744e5-119">Si une traduction dans la langue du magasin n'est pas disponible, le PDV reviendra à la langue de la société.</span><span class="sxs-lookup"><span data-stu-id="744e5-119">If a translation is not available for the store’s language, the POS will revert to the company’s language.</span></span>

### <a name="configuring-the-stores-language-setting"></a><span data-ttu-id="744e5-120">Configuration du paramètre de langue du magasin</span><span class="sxs-lookup"><span data-stu-id="744e5-120">Configuring the store’s language setting</span></span>

<span data-ttu-id="744e5-121">Le paramètre de langue du magasin est défini à partir de **Tous les magasins de vente au détail** sur la page **Magasin de vente au détail** sous **Général &gt; Paramètres régionaux &gt; Langue.</span><span class="sxs-lookup"><span data-stu-id="744e5-121">The store’s language setting is set from **All retail stores** on the **Retail Store** page under **General &gt; Regional Settings &gt; Language.</span></span> <span data-ttu-id="744e5-122">** Utilisez le menu déroulant pour choisir la langue de chaque magasin.</span><span class="sxs-lookup"><span data-stu-id="744e5-122">**Use the drop down to choose the language for each store.</span></span>

## <a name="user-interface-language"></a><span data-ttu-id="744e5-123">Langue de l'interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="744e5-123">User interface language</span></span>
<span data-ttu-id="744e5-124">Le paramètre de langue de l'utilisateur du PDV détermine les traductions utilisées dans l'interface utilisateur de l'application.</span><span class="sxs-lookup"><span data-stu-id="744e5-124">The POS user’s language setting determines the translations used in the application user interface.</span></span> <span data-ttu-id="744e5-125">Cela inclut tous les noms, menus et listes qui ne sont pas considérés comme des données.</span><span class="sxs-lookup"><span data-stu-id="744e5-125">This includes all labels, menus, and lists that are not considered data.</span></span> <span data-ttu-id="744e5-126">Une exception est le texte affiché dans les groupes de boutons du PDV.</span><span class="sxs-lookup"><span data-stu-id="744e5-126">One exception is the text that is displayed on POS button grids.</span></span> <span data-ttu-id="744e5-127">Elles ne prennent pas en charge les traductions, donc elles affichent toujours le texte tel que défini sous le bouton.</span><span class="sxs-lookup"><span data-stu-id="744e5-127">The button grids don't support translations, so they will always show the text as defined on the button.</span></span> <span data-ttu-id="744e5-128">Afin de prendre en charge les boutons traduits, vous devez copier et conserver des grilles de bouton distinctes et les affecter aux utilisateurs concernés.</span><span class="sxs-lookup"><span data-stu-id="744e5-128">In order to support translated buttons, you'll have to copy and maintain separate button grids and assign them to the users as appropriate.</span></span>

### <a name="configuring-the-users-language-setting"></a><span data-ttu-id="744e5-129">Configuration du paramètre de langue de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="744e5-129">Configuring the user’s language setting</span></span>

<span data-ttu-id="744e5-130">Le paramètre de langue de l'utilisateur du PDV est défini à partir de **Tous les collaborateurs** dans la page **Collaborateur** sous **Vente au détail &gt; Langue**.</span><span class="sxs-lookup"><span data-stu-id="744e5-130">The POS user’s language setting is set from **All workers** on the **Worker** page under **Retail &gt; Language**.</span></span>  <span data-ttu-id="744e5-131">Il n'est pas défini dans l'onglet principal Profil. Ce paramètre n'est pas utilisé par le PDV.</span><span class="sxs-lookup"><span data-stu-id="744e5-131">It is not set on the main Profile tab.  This setting is not used by POS.</span></span> <span data-ttu-id="744e5-132">Si la langue de l'utilisateur n'est pas définie ou si elle est définie sur une langue dans laquelle les traductions ne sont pas disponibles, le PDV reviendra à la langue du magasin.</span><span class="sxs-lookup"><span data-stu-id="744e5-132">If the user’s language is not set or it is set to a language where translations are not available, the POS will revert to the store’s language.</span></span>  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| <span data-ttu-id="744e5-133">** **</span><span class="sxs-lookup"><span data-stu-id="744e5-133">** **</span></span>       | <span data-ttu-id="744e5-134">**Langue de l'interface utilisateur** ** **</span><span class="sxs-lookup"><span data-stu-id="744e5-134">**UI language** ** **</span></span>      | <span data-ttu-id="744e5-135">**Langue des données (produits, formats d'accusé de réception, vue de ligne, etc.).**</span><span class="sxs-lookup"><span data-stu-id="744e5-135">**Data language (products, receipt formats, line display, etc.)**</span></span> |
| <span data-ttu-id="744e5-136">**Société**</span><span class="sxs-lookup"><span data-stu-id="744e5-136">**Company**</span></span> | <span data-ttu-id="744e5-137">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="744e5-137">Default</span></span>                    | <span data-ttu-id="744e5-138">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="744e5-138">Default</span></span>                                                           |
| <span data-ttu-id="744e5-139">**Magasin**</span><span class="sxs-lookup"><span data-stu-id="744e5-139">**Store**</span></span>   | <span data-ttu-id="744e5-140">Remplace la société</span><span class="sxs-lookup"><span data-stu-id="744e5-140">Overrides company</span></span>          | <span data-ttu-id="744e5-141">Remplace la société</span><span class="sxs-lookup"><span data-stu-id="744e5-141">Overrides company</span></span>                                                 |
| <span data-ttu-id="744e5-142">**Utilisateur**</span><span class="sxs-lookup"><span data-stu-id="744e5-142">**User**</span></span>    | <span data-ttu-id="744e5-143">Remplace le magasin ou la société</span><span class="sxs-lookup"><span data-stu-id="744e5-143">Overrides store or company</span></span> | <span data-ttu-id="744e5-144">Jamais</span><span class="sxs-lookup"><span data-stu-id="744e5-144">Never</span></span>                                                             |






