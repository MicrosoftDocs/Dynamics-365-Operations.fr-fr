---
title: "Étendre les fonctionnalités de Microsoft Dynamics 365 for Talent"
description: "Si vous avez créé des applications Microsoft PowerApps, vous pouvez démarrer ces applications à partir des liens contenus dans Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: Talent
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: cfd3b475b113fdab4ceeb3e636fea6c9134ab982
ms.openlocfilehash: 0ab829803634871c9060daa381bd02d7d2bbdf42
ms.contentlocale: fr-fr
ms.lasthandoff: 12/01/2017

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a><span data-ttu-id="cf801-103">Étendre les fonctionnalités de Microsoft Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="cf801-103">Extend the functionality of Microsoft Dynamics 365 for Talent</span></span>
<span data-ttu-id="cf801-104">Si vous avez créé des applications Microsoft PowerApps, vous pouvez démarrer ces applications à partir des liens contenus dans Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="cf801-104">If you’ve created any Microsoft PowerApps, you can start those applications from links within Microsoft Dynamics 365 for Talent.</span></span> <span data-ttu-id="cf801-105">Pour paramétrer l'accès à vos applications, vous devrez configurer certaines informations de Talent sur une page de configuration que vous pouvez ouvrir à partir de l'espace de travail **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="cf801-105">To set up access to your applications, you’ll need to set up some information in Talent on a configuration page that you can open from the **System administration** workspace.</span></span>

## <a name="configuring-embedded-powerapps-within-talent"></a><span data-ttu-id="cf801-106">Configuration des applications PowerApps incorporées dans Talent</span><span class="sxs-lookup"><span data-stu-id="cf801-106">Configuring embedded PowerApps within Talent</span></span>
<span data-ttu-id="cf801-107">Utilisez la page **Définir les applications Microsoft PowerApps incorporées** pour configurer les pages Talent pour démarrer les applications PowerApps.</span><span class="sxs-lookup"><span data-stu-id="cf801-107">Use the **Set embedded Microsoft PowerApps** page to configure Talent pages to start PowerApps applications.</span></span> <span data-ttu-id="cf801-108">Pour ouvrir la page **Définir les applications Microsoft PowerApps incorporées**, ouvrez l'espace de travail **Administration du système**, puis ouvrez l'onglet **Liens**. Sélectionnez **Microsoft PowerApps** dans le groupe **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="cf801-108">To open the **Set embedded Microsoft PowerApps** page, open the **System administration** workspace and then open the **Links** tab. Select **Microsoft PowerApps** from the **Setup** group.</span></span> 

<span data-ttu-id="cf801-109">Les informations suivantes sont saisies ou définies sur cette page :</span><span class="sxs-lookup"><span data-stu-id="cf801-109">The following information is entered or set on this page:</span></span> 

> - <span data-ttu-id="cf801-110">Nom descriptif ou identificateur de chaque application PowerApps.</span><span class="sxs-lookup"><span data-stu-id="cf801-110">A descriptive name or identifier for each PowerApps application.</span></span>
> - <span data-ttu-id="cf801-111">Identificateur unique (GUID) de chaque application que vous ajoutez à une page Talent.</span><span class="sxs-lookup"><span data-stu-id="cf801-111">A unique identifier (GUID) for each application that you add to a Talent page.</span></span> <span data-ttu-id="cf801-112">L'ID d'application est disponible sur le site PowerApps [powerapps.com](http://powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="cf801-112">The app ID is available on the PowerApps site, [powerapps.com](http://powerapps.com/).</span></span> 
> - <span data-ttu-id="cf801-113">Page à partir de laquelle les utilisateurs peuvent ouvrir une application ou un état.</span><span class="sxs-lookup"><span data-stu-id="cf801-113">The page from which users can open an application or report.</span></span> <span data-ttu-id="cf801-114">Certaines pages Talent prennent en charge les applications PowerApps incorporées et les états Power BI.</span><span class="sxs-lookup"><span data-stu-id="cf801-114">Not all Talent pages support embedded PowerApps and Power BI reports.</span></span> 

 > [!NOTE]
 >  <span data-ttu-id="cf801-115">Entrez le nom interne de la page au lieu du nom complet qui apparaît en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="cf801-115">Enter the internal name of the page, rather than the display name that appears at the top of the page.</span></span> <span data-ttu-id="cf801-116">Pour rechercher le nom interne, ouvrez la page dont vous avez besoin du nom interne, puis cliquez avec le bouton droit n'importe où sur la page.</span><span class="sxs-lookup"><span data-stu-id="cf801-116">To find the internal name, open the page that you need the internal name of, and right-click anywhere on the page.</span></span> <span data-ttu-id="cf801-117">Lorsque le menu s'ouvre, placez votre pointeur sur l'élément **Informations sur l'écran**.</span><span class="sxs-lookup"><span data-stu-id="cf801-117">When the menu opens, hover over the **Form information** item.</span></span> <span data-ttu-id="cf801-118">Le nom d'écran interne s'affiche en regard de l'élément **Informations sur l'écran** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="cf801-118">The internal form name is displayed next to the **Form information** item in the menu.</span></span>
 
> - <span data-ttu-id="cf801-119">Spécifiez le contrôle d'écran à partir duquel l'application peut extraire les données de contexte.</span><span class="sxs-lookup"><span data-stu-id="cf801-119">Specify the form control from which the application can retrieve context data.</span></span> <span data-ttu-id="cf801-120">Par exemple, une application peut utiliser les données concernant un collaborateur.</span><span class="sxs-lookup"><span data-stu-id="cf801-120">For example, an application might use data about a worker.</span></span> <span data-ttu-id="cf801-121">Si vous ouvrez la page **Collaborateur** dans le champ **Contexte**, la page **Collaborateur** s'ouvre lorsque vous démarrez l'application.</span><span class="sxs-lookup"><span data-stu-id="cf801-121">If you enter the **Worker** page in the **Context** field, the **Worker** page will open when you start the application.</span></span> <span data-ttu-id="cf801-122">La saisie de données dans le champ **Contexte** est facultative.</span><span class="sxs-lookup"><span data-stu-id="cf801-122">An entry in the **Context field** is optional.</span></span> 
> - <span data-ttu-id="cf801-123">Définissez la taille de la boîte de dialogue dans laquelle l'application PowerApps s'exécute.</span><span class="sxs-lookup"><span data-stu-id="cf801-123">Set the size of the dialog box on which the PowerApps application will run.</span></span> <span data-ttu-id="cf801-124">Les boîtes de dialogue sont conçues comme « petites » ou « grandes » afin d'optimiser l'interface utilisateur lorsque votre application s'exécute sur un téléphone ou un appareil plus grand, respectivement.</span><span class="sxs-lookup"><span data-stu-id="cf801-124">The dialog boxes are designated as “small” or “large” to optimize the user interface when your application for running on a phone or a larger device, respectively.</span></span> 

<span data-ttu-id="cf801-125">Vous pouvez également spécifier les entités juridiques pour lesquelles une application est disponible, ou vous pouvez la rendre accessible à toutes vos entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="cf801-125">You can also specify which legal entities an application will be available for, or you can make it available to all your legal entities.</span></span> <span data-ttu-id="cf801-126">Par défaut, vos applications PowerApps sont accessibles à toutes les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="cf801-126">By default, your PowerApps applications are available to all legal entities.</span></span>

## <a name="opening-an-application"></a><span data-ttu-id="cf801-127">Ouverture d'une application</span><span class="sxs-lookup"><span data-stu-id="cf801-127">Opening an application</span></span>
<span data-ttu-id="cf801-128">Lorsque vous avez configuré les applications PowerApps incorporées, les liens vers les applications que vous avez spécifiées sont ajoutés aux pages dans Talent.</span><span class="sxs-lookup"><span data-stu-id="cf801-128">When you’ve configured embedded PowerApps applications, links to the applications that you specified will be added to the pages within Talent.</span></span> <span data-ttu-id="cf801-129">Cliquez sur un lien pour ouvrir une application.</span><span class="sxs-lookup"><span data-stu-id="cf801-129">Click a link to open an application.</span></span> 



