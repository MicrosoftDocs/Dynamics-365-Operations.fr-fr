---
title: "Configuration requise pour les déploiements Cloud"
description: "Cette rubrique indique la configuration requise pour la version actuelle de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition pour des déploiements cloud."
author: sericks007
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 83637b4b2ccc01950e68569b3b8bee1a7cd69855
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="system-requirements-for-cloud-deployments"></a><span data-ttu-id="2d720-103">Configuration requise pour les déploiements Cloud</span><span class="sxs-lookup"><span data-stu-id="2d720-103">System requirements for cloud deployments</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2d720-104">Cette rubrique indique la configuration requise pour la version actuelle de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition pour des déploiements cloud.</span><span class="sxs-lookup"><span data-stu-id="2d720-104">This topic lists the system requirements for the current version of Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, for cloud deployments.</span></span> <span data-ttu-id="2d720-105">Avant d'installer Finance and Operations, si nécessaire, vérifiez que le système que vous utilisez répond ou excède la configuration minimale requise pour le réseau, le matériel et les logiciels.</span><span class="sxs-lookup"><span data-stu-id="2d720-105">Before you install Finance and Operations, when this step is appropriate, verify that the system that you're working with meets or exceeds the minimum network, hardware, and software requirements.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="2d720-106">Navigateurs Web pris en charge</span><span class="sxs-lookup"><span data-stu-id="2d720-106">Supported web browsers</span></span>
<span data-ttu-id="2d720-107">L'application Web peut s'exécuter dans n'importe lequel des navigateurs Web suivants qui s'exécutent sur les systèmes d'exploitation spécifiés :</span><span class="sxs-lookup"><span data-stu-id="2d720-107">The web application can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="2d720-108">Microsoft Edge (dernière version publique disponible) sur Windows 10</span><span class="sxs-lookup"><span data-stu-id="2d720-108">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="2d720-109">Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7</span><span class="sxs-lookup"><span data-stu-id="2d720-109">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="2d720-110">Google Chrome (dernière version publique disponible) sur Windows 10, Windows 8.1, Windows 8, Windows 7, ou Google Nexus 10 tablette</span><span class="sxs-lookup"><span data-stu-id="2d720-110">Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet</span></span>
-   <span data-ttu-id="2d720-111">Apple Safari (dernière version publique disponible) sur Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra), ou iPad Apple</span><span class="sxs-lookup"><span data-stu-id="2d720-111">Apple Safari (latest publicly available version) on Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) or 10.12 (Sierra), or Apple iPad</span></span>

<span data-ttu-id="2d720-112">Pour trouver la dernière version pour chaque navigateur Web, accédez au site Internet du fournisseur logiciel.</span><span class="sxs-lookup"><span data-stu-id="2d720-112">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> -   <span data-ttu-id="2d720-113">Vous devez installer une extension Chrome préliminaire pour permettre à l'enregistreur de tâches d'effectuer des captures d'écran et de les inclure dans les documents Microsoft Word générés.</span><span class="sxs-lookup"><span data-stu-id="2d720-113">You must install a pre-release Chrome extension to enable Task Recorder to capture screenshots and include them in Microsoft Word documents that are generated.</span></span> <!---For instructions about how to install the extension, see [Screenshot Extension setup](../../dev-itpro/user-interface/task-recorder).-->
> -   <span data-ttu-id="2d720-114">L'éditeur de workflow démarre en tant qu'application ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="2d720-114">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="2d720-115">Seuls Microsoft Edge et Internet Explorer (dans une version prise en charge de Microsoft Windows) prennent en charge les applications ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="2d720-115">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="2d720-116">L'application ClickOnce d'éditeur de workflow nécessite un système d'exploitation compatible 64 bits.</span><span class="sxs-lookup"><span data-stu-id="2d720-116">The Workflow Editor ClickOnce application requires a 64-bit-compatible operating system.</span></span>
> -   <span data-ttu-id="2d720-117">Le Concepteur de rapports pour les États financiers démarre en tant qu'application ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="2d720-117">The Report Designer for Financial reporting is started as a ClickOnce application.</span></span> <span data-ttu-id="2d720-118">Il nécessite un système d'exploitation compatible 64 bits.</span><span class="sxs-lookup"><span data-stu-id="2d720-118">It requires a 64-bit-compatible operating system.</span></span> <span data-ttu-id="2d720-119">Si vous utilisez Chrome, vous devez installer une extension ClickOnce pour télécharger le client Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2d720-119">If you’re using Chrome, you must install a ClickOnce extension to download the Report Designer client.</span></span> <span data-ttu-id="2d720-120">Si vous utilisez Chrome en mode incognito, vérifiez que l'extension ClickOnce est également activée pour le mode incognito.</span><span class="sxs-lookup"><span data-stu-id="2d720-120">If you use Chrome in Incognito mode, make sure that the ClickOnce extension is also enabled for Incognito mode.</span></span>
> -   <span data-ttu-id="2d720-121">Pour afficher un aperçu des fichiers PDF, nous vous recommandons d'utiliser des navigateurs tels que Microsoft Edge (dernière version disponible) sous Windows 10, ou Google Chrome (dernière version disponible) sous Windows 10, Windows 8,1, Windows 8, Windows 7, ou sur la tablette Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="2d720-121">To preview PDF files, we recommend that you use browsers such as Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>

### <a name="supported-web-browsers-for-retail-cloud-pos"></a><span data-ttu-id="2d720-122">Navigateurs Web pris en charge pour Retail Cloud POS</span><span class="sxs-lookup"><span data-stu-id="2d720-122">Supported web browsers for Retail Cloud POS</span></span>

<span data-ttu-id="2d720-123">Retail Cloud POS peut s'exécuter dans n'importe lequel des navigateurs Web suivants qui s'exécutent sur les systèmes d'exploitation spécifiés :</span><span class="sxs-lookup"><span data-stu-id="2d720-123">Retail Cloud POS can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="2d720-124">Microsoft Edge (dernière version publique disponible) sur Windows 10</span><span class="sxs-lookup"><span data-stu-id="2d720-124">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="2d720-125">Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7</span><span class="sxs-lookup"><span data-stu-id="2d720-125">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="2d720-126">Chrome (dernière version publique disponible) sous Windows 10, Windows 8,1 ou Windows 7</span><span class="sxs-lookup"><span data-stu-id="2d720-126">Chrome (latest publicly available version) on Windows 10, Windows 8.1, or Windows 7</span></span>

## <a name="network-requirements"></a><span data-ttu-id="2d720-127">Exigences réseau</span><span class="sxs-lookup"><span data-stu-id="2d720-127">Network requirements</span></span>
-   <span data-ttu-id="2d720-128">Finance and Operations est conçu pour les réseaux ayant une latence de 250 à 300 millisecondes (ms) ou moins.</span><span class="sxs-lookup"><span data-stu-id="2d720-128">Finance and Operations is designed for networks that have a latency of 250–300 milliseconds (ms) or less.</span></span> <span data-ttu-id="2d720-129">C'est la latence entre un client de navigateur et le centre de données Microsoft Azure qui héberge Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2d720-129">This latency is the latency from a browser client to the Microsoft Azure datacenter that hosts Finance and Operations.</span></span> <span data-ttu-id="2d720-130">Nous vous recommandons de tester la latence du réseau à l'adresse <http://www.azurespeed.com>.</span><span class="sxs-lookup"><span data-stu-id="2d720-130">We recommend that you test network latency at <http://www.azurespeed.com>.</span></span>
-   <span data-ttu-id="2d720-131">Les besoins en bande passante pour Finance and Operations dépendent de votre scénario.</span><span class="sxs-lookup"><span data-stu-id="2d720-131">Bandwidth requirements for Finance and Operations depend on your scenario.</span></span> <span data-ttu-id="2d720-132">La plupart des scénarios habituels nécessitent une bande passante de plus de 50 kilo-octets par seconde (KBps).</span><span class="sxs-lookup"><span data-stu-id="2d720-132">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span> <span data-ttu-id="2d720-133">Toutefois, une bande passante plus conséquente est recommandée pour les scénarios qui ont des exigences de charge utile élevées, tels que les scénarios impliquant des espaces de travail ou une personnalisation étendue.</span><span class="sxs-lookup"><span data-stu-id="2d720-133">However, we recommend more bandwidth for scenarios that have high payload requirements, such as scenarios that involve workspaces or extensive customization.</span></span>

<span data-ttu-id="2d720-134">De manière générale, Finance and Operations est optimisé pour Internet.</span><span class="sxs-lookup"><span data-stu-id="2d720-134">In general, Finance and Operations is optimized for the internet.</span></span> <span data-ttu-id="2d720-135">Le nombre d'allers-retours entre le client Web et le centre de données Azure est très faible et la charge utile entière est compressée.</span><span class="sxs-lookup"><span data-stu-id="2d720-135">The number of round trips from a browser client to the Azure datacenter is very small, and the whole payload is compressed.</span></span> 

> [!WARNING]
> <span data-ttu-id="2d720-136">Ne calculez pas la bande passante d'un emplacement client nécessaire en multipliant le nombre d'utilisateurs par la bande passante minimale requise.</span><span class="sxs-lookup"><span data-stu-id="2d720-136">Don't calculate bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="2d720-137">Il est très difficile de calculer l'utilisation simultanée d'un emplacement donné.</span><span class="sxs-lookup"><span data-stu-id="2d720-137">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="2d720-138">Les clients qui s'inquiètent des besoins de bande passante doivent utiliser une version d'aperçu de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2d720-138">Customers who are concerned about bandwidth requirements should use a preview version of Finance and Operations.</span></span>

## <a name="net-framework-requirements"></a><span data-ttu-id="2d720-139">Exigences.NET Framework</span><span class="sxs-lookup"><span data-stu-id="2d720-139">.NET Framework requirements</span></span>
<span data-ttu-id="2d720-140">Finance and Operations requiert la version Microsoft .NET Framework 4.6.2 pour toutes les applications ClickOnce, telles que l'agent d'acheminement de document.</span><span class="sxs-lookup"><span data-stu-id="2d720-140">Finance and Operations requires the Microsoft .NET Framework version 4.6.2 for all ClickOnce applications, such as the document routing agent.</span></span> <span data-ttu-id="2d720-141">Pour obtenir les instructions d'installation, voir [Installation de .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="2d720-141">For installation instructions, see [Installing the .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="2d720-142">Applications Microsoft Office prises en charge</span><span class="sxs-lookup"><span data-stu-id="2d720-142">Supported Microsoft Office applications</span></span>
<span data-ttu-id="2d720-143">Les applications suivantes Microsoft Office sont prises en charge dans les déploiements dans le cloud et sur site de Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="2d720-143">The following Microsoft Office applications are supported in cloud and on-premises deployments of Finance and Operations:</span></span>

-   <span data-ttu-id="2d720-144">Pour exécuter les compléments Microsoft Excel et Word, vous devez disposer de Microsoft Office 2016 pour Windows ou Mac.</span><span class="sxs-lookup"><span data-stu-id="2d720-144">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="2d720-145">Pour plus d'informations sur les exigences en matière de versions, voir [Dépannage de l'intégration d'Office](../../dev-itpro/office-integration/office-integration-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="2d720-145">For more information about version requirements, see [Office integration troubleshooting](../../dev-itpro/office-integration/office-integration-troubleshooting.md).</span></span>
-   <span data-ttu-id="2d720-146">Pour afficher les documents qui sont générés par la fonctionnalité Exporter vers Excel ou Exporter vers Word, vous devez disposer de Microsoft Office 2007 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="2d720-146">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="retail-modern-pos-requirements"></a><span data-ttu-id="2d720-147">Exigences de Retail Modern POS</span><span class="sxs-lookup"><span data-stu-id="2d720-147">Retail Modern POS requirements</span></span>

> [!NOTE]
> <span data-ttu-id="2d720-148">Si Retail Modern POS utilise une base de données hors connexion, l'ordinateur doit respecter toutes les configurations requises pour Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2d720-148">If Retail Modern POS will use an offline database, the computer must meet all system requirements for Microsoft SQL Server.</span></span> <span data-ttu-id="2d720-149">Une base de données hors connexion Retail Modern POS fonctionnera sur Microsoft SQL Server 2012 avec Service Pack 3 ou une version ultérieure, Microsoft SQL Server 2014 avec Service Pack 2 ou une version ultérieure et Microsoft SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="2d720-149">A Retail Modern POS offline database will work on Microsoft SQL Server 2012 with Service Pack 3 or later, Microsoft SQL Server 2014 with Service Pack 2 or later, and Microsoft SQL Server 2016.</span></span> <span data-ttu-id="2d720-150">Il est recommandé d'utiliser systématiquement la dernière version disponible, et d'installer tous les Service Packs les plus récents.</span><span class="sxs-lookup"><span data-stu-id="2d720-150">We recommend that you always use the latest version that is available, and that you install all the latest service packs.</span></span>

### <a name="supported-operating-systems"></a><span data-ttu-id="2d720-151">Systèmes d'exploitation pris en charge</span><span class="sxs-lookup"><span data-stu-id="2d720-151">Supported operating systems</span></span>

-   <span data-ttu-id="2d720-152">Retail Modern POS est une application 32 bits, mais elle fonctionne aussi bien sur les architectures x86 ou x64.</span><span class="sxs-lookup"><span data-stu-id="2d720-152">Retail Modern POS is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="2d720-153">Retail Modern POS est pris en charge uniquement sous les éditions Windows 10 Pro, Enterprise et Enterprise LTSB (Long Term Servicing Branch).</span><span class="sxs-lookup"><span data-stu-id="2d720-153">Retail Modern POS is supported only on Windows 10 Pro, Enterprise, and Enterprise Long Term Servicing Branch (LTSB) editions.</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="2d720-154">Configuration système minimale</span><span class="sxs-lookup"><span data-stu-id="2d720-154">Minimum system requirements</span></span>

-   <span data-ttu-id="2d720-155">La résolution minimale prise en charge est 1280 × 1024.</span><span class="sxs-lookup"><span data-stu-id="2d720-155">The minimum supported resolution is 1,280 × 1,024.</span></span>
-   <span data-ttu-id="2d720-156">L'ordinateur sur lequel est exécuté Retail Modern POS doit avoir la configuration minimale suivante :</span><span class="sxs-lookup"><span data-stu-id="2d720-156">The computer that Retail Modern POS runs on must meet these requirements:</span></span>

    -   <span data-ttu-id="2d720-157">Il doit disposer au moins d'un processeur double-cœur fonctionnant à une fréquence d'au moins 2 GHz.</span><span class="sxs-lookup"><span data-stu-id="2d720-157">It must have, at a minimum, a dual-core processor that runs at no less than 2 gigahertz (GHz).</span></span>
    -   <span data-ttu-id="2d720-158">Il doit avoir au minimum 3 giga-octets (Go) de mémoire RAM.</span><span class="sxs-lookup"><span data-stu-id="2d720-158">It must have, at a minimum, 3 gigabytes (GB) of random-access memory (RAM).</span></span>
    -   <span data-ttu-id="2d720-159">Il doit avoir accès à Internet.</span><span class="sxs-lookup"><span data-stu-id="2d720-159">It must have internet access.</span></span>

## <a name="retail-hardware-station-requirements"></a><span data-ttu-id="2d720-160">Exigences de la station matérielle Retail</span><span class="sxs-lookup"><span data-stu-id="2d720-160">Retail hardware station requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="2d720-161">Systèmes d'exploitation pris en charge</span><span class="sxs-lookup"><span data-stu-id="2d720-161">Supported operating systems</span></span>

-   <span data-ttu-id="2d720-162">La station matérielle Retail est une application 32 bits, mais elle fonctionne aussi bien sur les architectures x86 ou x64.</span><span class="sxs-lookup"><span data-stu-id="2d720-162">Retail hardware station is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="2d720-163">La station matérielle Retail est prise en charge sur les systèmes d'exploitation suivants :</span><span class="sxs-lookup"><span data-stu-id="2d720-163">Retail hardware station is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="2d720-164">Windows 7 éditions Professional, Enterprise et Ultimate</span><span class="sxs-lookup"><span data-stu-id="2d720-164">Windows 7 Professional, Enterprise, and Ultimate editions</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="2d720-165">Windows 7 est pris en charge uniquement si Internet Explorer 11 est manuellement installé sur le système.</span><span class="sxs-lookup"><span data-stu-id="2d720-165">Windows 7 is supported only if Internet Explorer 11 is manually installed on the system.</span></span>

    -   <span data-ttu-id="2d720-166">Windows 8.1 Update 1 éditions Professional, Enterprise et Embedded</span><span class="sxs-lookup"><span data-stu-id="2d720-166">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="2d720-167">Windows 10 éditions Pro, Enterprise et Enterprise LTSB</span><span class="sxs-lookup"><span data-stu-id="2d720-167">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="2d720-168">Configuration système minimale</span><span class="sxs-lookup"><span data-stu-id="2d720-168">Minimum system requirements</span></span>

<span data-ttu-id="2d720-169">L'ordinateur doit répondre à tous exigences système pour installer et utiliser les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2d720-169">The computer must meet all system requirements for installing and using the following items:</span></span>

-   <span data-ttu-id="2d720-170">Services Internet (IIS)</span><span class="sxs-lookup"><span data-stu-id="2d720-170">Internet Information Services (IIS)</span></span>
-   <span data-ttu-id="2d720-171">matériel tiers</span><span class="sxs-lookup"><span data-stu-id="2d720-171">Third-party hardware</span></span>

## <a name="retail-store-scale-unit-requirements"></a><span data-ttu-id="2d720-172">Exigences de l'unité d'échelle de magasin de vente au détail</span><span class="sxs-lookup"><span data-stu-id="2d720-172">Retail Store Scale Unit requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="2d720-173">Systèmes d'exploitation pris en charge</span><span class="sxs-lookup"><span data-stu-id="2d720-173">Supported operating systems</span></span>

-   <span data-ttu-id="2d720-174">L'unité d'échelle Retail Store est une application 32 bits, mais elle fonctionne aussi bien sur les architectures x86 ou x64.</span><span class="sxs-lookup"><span data-stu-id="2d720-174">Retail Store Scale Unit is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="2d720-175">L'unité d'échelle Retail Store est prise en charge sur les systèmes d'exploitation suivants :</span><span class="sxs-lookup"><span data-stu-id="2d720-175">Retail Store Scale Unit is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="2d720-176">Windows 7 éditions Professional, Enterprise et Ultimate</span><span class="sxs-lookup"><span data-stu-id="2d720-176">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="2d720-177">Windows 8.1 Update 1 éditions Professional, Enterprise et Embedded</span><span class="sxs-lookup"><span data-stu-id="2d720-177">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="2d720-178">Windows 10 éditions Pro, Enterprise et Enterprise LTSB</span><span class="sxs-lookup"><span data-stu-id="2d720-178">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="2d720-179">Configuration système minimale</span><span class="sxs-lookup"><span data-stu-id="2d720-179">Minimum system requirements</span></span>

-   <span data-ttu-id="2d720-180">4 Go de mémoire vive (RAM)</span><span class="sxs-lookup"><span data-stu-id="2d720-180">4 GB of RAM</span></span>
-   <span data-ttu-id="2d720-181">Vitesse de pointe du processeur de 1,6 GHz par cœur (deux cœurs au minimum.)</span><span class="sxs-lookup"><span data-stu-id="2d720-181">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="2d720-182">Au moins 10 Go d'espace libre (la base de données des canaux peut nécessiter un espace volumineux.)</span><span class="sxs-lookup"><span data-stu-id="2d720-182">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

### <a name="recommended-system-requirements"></a><span data-ttu-id="2d720-183">Configuration système recommandée</span><span class="sxs-lookup"><span data-stu-id="2d720-183">Recommended system requirements</span></span>

-   <span data-ttu-id="2d720-184">6 Go de mémoire vive (RAM)</span><span class="sxs-lookup"><span data-stu-id="2d720-184">6 GB of RAM</span></span>
-   <span data-ttu-id="2d720-185">Vitesse de pointe du processeur de 2,4 GHz i7 (ou équivalent) par cœur (quatre cœurs recommandés.)</span><span class="sxs-lookup"><span data-stu-id="2d720-185">2.4 GHz i7 (or equivalent) peak CPU speed per core (Four cores are recommended.)</span></span>
-   <span data-ttu-id="2d720-186">Au moins 10 Go d'espace libre (la base de données des canaux peut nécessiter un espace volumineux.)</span><span class="sxs-lookup"><span data-stu-id="2d720-186">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="connector-requirements"></a><span data-ttu-id="2d720-187">Connecteur requis</span><span class="sxs-lookup"><span data-stu-id="2d720-187">Connector requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="2d720-188">Systèmes d'exploitation pris en charge</span><span class="sxs-lookup"><span data-stu-id="2d720-188">Supported operating systems</span></span>

-   <span data-ttu-id="2d720-189">Le connecteur pour Microsoft Dynamics AX a deux programmes d'installation distincts, un pour le service Async Server Connector et un pour le service Real-time Service pour Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="2d720-189">The Connector for Microsoft Dynamics AX has two separate installers, one for Async Server Connector service and one for Real-time service for Dynamics AX 2012 R3.</span></span>
-   <span data-ttu-id="2d720-190">Les deux composants sont des applications 32 bits, mais ils fonctionnent aussi bien sur les architectures x86 ou x64.</span><span class="sxs-lookup"><span data-stu-id="2d720-190">Both components are 32-bit applications, but they will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="2d720-191">Les deux composants sont pris en charge sur les systèmes d'exploitation suivants :</span><span class="sxs-lookup"><span data-stu-id="2d720-191">Both components are supported on the following operating systems:</span></span>

    -   <span data-ttu-id="2d720-192">Windows 7 éditions Professional, Enterprise et Ultimate</span><span class="sxs-lookup"><span data-stu-id="2d720-192">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="2d720-193">Windows 8.1 Update 1 éditions Professional, Enterprise et Embedded</span><span class="sxs-lookup"><span data-stu-id="2d720-193">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="2d720-194">Windows 10 éditions Pro, Enterprise et Enterprise LTSB</span><span class="sxs-lookup"><span data-stu-id="2d720-194">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>
    -   <span data-ttu-id="2d720-195">Microsoft Windows Server 2012 R2 et Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="2d720-195">Microsoft Windows Server 2012 R2 and Microsoft Windows Server 2016</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="2d720-196">Configuration système minimale</span><span class="sxs-lookup"><span data-stu-id="2d720-196">Minimum system requirements</span></span>
-   <span data-ttu-id="2d720-197">2 Go de RAM (4 Go de RAM sont recommandés)</span><span class="sxs-lookup"><span data-stu-id="2d720-197">2 GB of RAM (4 GB of RAM are recommended.)</span></span>
-   <span data-ttu-id="2d720-198">Vitesse de pointe du processeur de 1,6 GHz par cœur (deux cœurs au minimum.)</span><span class="sxs-lookup"><span data-stu-id="2d720-198">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="2d720-199">Au moins 10 Go d'espace libre (la base de données des canaux peut nécessiter un espace volumineux.)</span><span class="sxs-lookup"><span data-stu-id="2d720-199">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="requirements-for-development-on-local-vms"></a><span data-ttu-id="2d720-200">Exigences pour le développement sur les ordinateurs virtuels locaux</span><span class="sxs-lookup"><span data-stu-id="2d720-200">Requirements for development on local VMs</span></span>
<span data-ttu-id="2d720-201">Pour plus d'informations sur les exigences associées au développement sur les ordinateurs virtuels locaux, voir [Ordinateurs virtuels sur site](../../dev-itpro/dev-tools/access-instances.md).</span><span class="sxs-lookup"><span data-stu-id="2d720-201">For information about the requirements for development on local virtual machines (VMs), see [VM running on-premises](../../dev-itpro/dev-tools/access-instances.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="2d720-202">Voir également :</span><span class="sxs-lookup"><span data-stu-id="2d720-202">See also</span></span>

[<span data-ttu-id="2d720-203">Obtenir une copie d'évaluation de Dynamics 365 for Finance and Operations, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="2d720-203">Get an evaluation copy of Dynamics 365 for Finance and Operations, Enterprise edition</span></span>](../../dev-itpro/dev-tools/get-evaluation-copy.md)

