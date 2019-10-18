---
title: Configuration du système Talent et politique de mise à jour
description: Cette rubrique répertorie les besoins pour Dynamics 365 Talent. Elle décrit également la stratégie de mise à jour.
author: andreabichsel
manager: AnnBe
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: b8bf44fc76be968b0b04fd894c39b4c19fd374ce
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024158"
---
# <a name="talent-system-requirements-and-update-policy"></a><span data-ttu-id="9fb9a-104">Configuration du système Talent et politique de mise à jour</span><span class="sxs-lookup"><span data-stu-id="9fb9a-104">Talent system requirements and update policy</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9fb9a-105">Cette rubrique décrit les besoins pour Microsoft Dynamics 365 Talent, y compris Attract, Onboard et Core HR.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-105">This topic describes requirements for Microsoft Dynamics 365 Talent, including Attract, Onboard, and Core HR.</span></span> <span data-ttu-id="9fb9a-106">Elle décrit également les pays et régions où Talent est disponible, et fournit des informations sur les langues et la localisation des données pour Talent.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-106">It also outlines the countries and regions where Talent is available, plus information about languages and localization for Talent data.</span></span> <span data-ttu-id="9fb9a-107">En outre, cette rubrique fournit la stratégie de mise à jour de Talent.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-107">In additions, this topic provides the update policy for Talent.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="9fb9a-108">Navigateurs Web pris en charge</span><span class="sxs-lookup"><span data-stu-id="9fb9a-108">Supported web browsers</span></span>

<span data-ttu-id="9fb9a-109">Microsoft Dynamics 365 Talent peut s'exécuter dans n'importe lequel des navigateurs Web suivants qui s'exécutent sur les systèmes d'exploitation spécifiés :</span><span class="sxs-lookup"><span data-stu-id="9fb9a-109">Microsoft Dynamics 365 Talent can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="9fb9a-110">Microsoft Edge (dernière version publique disponible) sur Windows 10</span><span class="sxs-lookup"><span data-stu-id="9fb9a-110">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="9fb9a-111">Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7</span><span class="sxs-lookup"><span data-stu-id="9fb9a-111">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="9fb9a-112">Google Chrome (dernière version publique disponible)</span><span class="sxs-lookup"><span data-stu-id="9fb9a-112">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="9fb9a-113">Apple Safari (dernière version publique disponible)</span><span class="sxs-lookup"><span data-stu-id="9fb9a-113">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="9fb9a-114">Pour trouver la dernière version pour chaque navigateur Web, accédez au site Internet du fournisseur logiciel.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-114">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="9fb9a-115">Pour capturer des images générées à partir de l'enregistreur de tâches et les inclure dans les documents Microsoft Word, vous devez avoir une extension Chrome installée.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-115">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="9fb9a-116">L'éditeur de workflow démarre en tant qu'application ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-116">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="9fb9a-117">Seuls Microsoft Edge et Internet Explorer (sur une version prise en charge Microsoft Windows) prennent en charge les applications de ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-117">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="9fb9a-118">L'application ClickOnce d'éditeur de workflow nécessite un système d'exploitation compatible 64 bits.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-118">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="9fb9a-119">Pour afficher un aperçu des fichiers PDF, nous vous recommandons d'utiliser des navigateurs tels que Microsoft Edge (dernière version disponible) sous Windows 10, ou Google Chrome (dernière version disponible) sous Windows 10, Windows 8,1, Windows 8, Windows 7, ou sur la tablette Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-119">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="9fb9a-120">Exigences réseau</span><span class="sxs-lookup"><span data-stu-id="9fb9a-120">Network requirements</span></span>
> * <span data-ttu-id="9fb9a-121">Dynamics 365 Talent est conçu pour les réseaux ayant une latence inférieure à 250 à 300 millisecondes (ms) ou moins.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-121">Dynamics 365 Talent is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="9fb9a-122">Cette latence est la latence entre un client de navigateur et le centre de données Microsoft Azure qui héberge Talent.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-122">This is the latency from a browser client to the Microsoft Azure data center that hosts Talent.</span></span> <span data-ttu-id="9fb9a-123">Nous vous recommandons de tester la latence du réseau à l'adresse [www.azurespeed.com](https://www.azurespeed.com "Test de latence Azure").</span><span class="sxs-lookup"><span data-stu-id="9fb9a-123">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="9fb9a-124">La bande passante requise pour Talent dépend de votre scénario.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-124">Bandwidth requirements for Talent depend on your scenario.</span></span> <span data-ttu-id="9fb9a-125">La plupart des scénarios habituels nécessitent une bande passante de plus de 50 kilo-octets par seconde (KBps).</span><span class="sxs-lookup"><span data-stu-id="9fb9a-125">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="9fb9a-126">Ne calculez pas la bande passante d'un emplacement client nécessaire en multipliant le nombre d'utilisateurs par la bande passante minimale requise.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-126">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="9fb9a-127">Il est très difficile de calculer l'utilisation simultanée d'un emplacement donné.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-127">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="9fb9a-128">Pour les clients qui s'inquiètent des besoins de bande passante, utilisez une version d'évaluation de Talent.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-128">For customers who are concerned about bandwidth requirements, use a trial version of Talent.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="9fb9a-129">Applications Microsoft Office prises en charge</span><span class="sxs-lookup"><span data-stu-id="9fb9a-129">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="9fb9a-130">Pour exécuter les compléments Microsoft Excel et Word, vous devez disposer de Microsoft Office 2016 pour Windows ou Mac.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-130">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="9fb9a-131">Pour plus de détails sur les exigences en matière de versions, voir [Dépannage de l'intégration d'Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Dépannage de l'intégration d'Office").</span><span class="sxs-lookup"><span data-stu-id="9fb9a-131">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="9fb9a-132">Pour afficher les documents qui sont générés par la fonctionnalité Exporter vers Excel ou Exporter vers Word, vous devez disposer de Microsoft Office 2007 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-132">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="regional-availability-languages-and-localization"></a><span data-ttu-id="9fb9a-133">Disponibilité, langues et localisation régionales</span><span class="sxs-lookup"><span data-stu-id="9fb9a-133">Regional availability, languages, and localization</span></span>

<span data-ttu-id="9fb9a-134">Vous pouvez télécharger un fichier PDF des pays, régions et langues pris en charge par Talent dans [Disponibilité internationale de Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span><span class="sxs-lookup"><span data-stu-id="9fb9a-134">You can download a PDF file of the countries, regions, and languages Talent supports at [International availability of Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span></span> 

> [!NOTE]
> <span data-ttu-id="9fb9a-135">Bien que l'interface utilisateur soit localisée dans d'autres langues, toutes les données d'utilisateur sont stockées dans la langue dans laquelle elles ont été entrées.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-135">While the user interface is localized into other languages, all user data is stored in the language in which it was entered.</span></span> <span data-ttu-id="9fb9a-136">Vous pouvez créer des e-mails et des modèles dans d'autres langues, mais les données telles que les informations de planification sont uniquement disponibles en anglais à ce stade.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-136">You can create emails and templates in other languages, but data such as scheduling information is only available in English at this time.</span></span>

<span data-ttu-id="9fb9a-137">Si vous êtes développeur et intéressé à créer des personnalisations spécifiques à un pays ou une région, ou à créer une solution pour un pays ou une région actuellement non pris en charge par Microsoft, voir [Globalisation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span><span class="sxs-lookup"><span data-stu-id="9fb9a-137">If you're a developer interested in creating country- or region-specific customizations, or in creating a solution for a country or region not currently supported by Microsoft, see [Globalization](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span></span>

## <a name="update-policy"></a><span data-ttu-id="9fb9a-138">Stratégie de mise à jour</span><span class="sxs-lookup"><span data-stu-id="9fb9a-138">Update policy</span></span>

<span data-ttu-id="9fb9a-139">Talent fait l'objet d'une maintenance dans le cadre d'une offre Cloud.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-139">Talent is serviced as a cloud offering.</span></span> <span data-ttu-id="9fb9a-140">Les mises à jour de Talent sont continues et appliquées automatiquement par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-140">Talent updates are continuous and applied automatically by Microsoft.</span></span>

<span data-ttu-id="9fb9a-141">Les mises à jour sont publiées régulièrement et s'appliqueront à tous les environnements.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-141">Updates are released on a regular cadence and will be made to all environments.</span></span> <span data-ttu-id="9fb9a-142">Talent est pris en charge conformément à la [Stratégie Microsoft Support Lifecycle](https://support.microsoft.com/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), qui fournit des instructions cohérentes et prévisibles pour la disponibilité du support produit.</span><span class="sxs-lookup"><span data-stu-id="9fb9a-142">Talent is supported according to the [Microsoft Support Lifecycle policy](https://support.microsoft.com/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), which provides consistent and predictable guidelines for product support availability.</span></span>
