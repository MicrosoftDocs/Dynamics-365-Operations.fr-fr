---
title: "Options de génération d'états dans Talent"
description: "Cette rubrique explique comment résoudre le problème où un client souhaite personnaliser des états Microsoft Dynamics 365 for Talent ou créer des états."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 2007e6adec7255b0b3abda7490c2103a8583393f
ms.contentlocale: fr-fr
ms.lasthandoff: 12/04/2018

---

# <a name="reporting-options-in-talent"></a><span data-ttu-id="36ad3-103">Options de génération d'états dans Talent</span><span class="sxs-lookup"><span data-stu-id="36ad3-103">Reporting options in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="36ad3-104">**Détails de l'environnement**</span><span class="sxs-lookup"><span data-stu-id="36ad3-104">**Environment details**</span></span>

<span data-ttu-id="36ad3-105">Ce problème s'applique à tous les environnements.</span><span class="sxs-lookup"><span data-stu-id="36ad3-105">This issue applies to all environments.</span></span>

<span data-ttu-id="36ad3-106">**Symptôme**</span><span class="sxs-lookup"><span data-stu-id="36ad3-106">**Symptom**</span></span>

<span data-ttu-id="36ad3-107">Le client souhaite personnaliser des états Microsoft Dynamics 365 for Talent ou créer des états.</span><span class="sxs-lookup"><span data-stu-id="36ad3-107">The customer wants to customize Microsoft Dynamics 365 for Talent reports or create new reports.</span></span>

<span data-ttu-id="36ad3-108">**Problème**</span><span class="sxs-lookup"><span data-stu-id="36ad3-108">**Issue**</span></span>

<span data-ttu-id="36ad3-109">L'utilisateur ne peut pas personnaliser les états Microsoft Power BI intégrés.</span><span class="sxs-lookup"><span data-stu-id="36ad3-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="36ad3-110">**Solution**</span><span class="sxs-lookup"><span data-stu-id="36ad3-110">**Solution**</span></span>

- <span data-ttu-id="36ad3-111">Les données Core HR qui arrivent dans Common Data Service pour les applications peuvent être déclarées via le connecteur CDS PowerApps sur Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="36ad3-111">The Core HR data that flows to Common Data Service for Apps can be reported on via the PowerApps CDS connector to Power BI Desktop.</span></span> <span data-ttu-id="36ad3-112">Notez que Common Data Service pour les applications contient un sous-ensemble de données Core HR.</span><span class="sxs-lookup"><span data-stu-id="36ad3-112">Note that Common Data Service for Apps contains a subset of Core HR data.</span></span> <span data-ttu-id="36ad3-113">Pour plus d'informations sur Power BI et les tableaux de bord, voir [Créer des états et les tableaux de bord Power BI avec Common Data Service PowerApps](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="36ad3-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="36ad3-114">La gestion des états électroniques (ER) est disponible pour certains états dans Talent.</span><span class="sxs-lookup"><span data-stu-id="36ad3-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="36ad3-115">Les personnalisations effectuées par les clients peuvent être réalisées via les options de configuration d'ER.</span><span class="sxs-lookup"><span data-stu-id="36ad3-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="36ad3-116">Les données peuvent être exportées vers Microsoft Excel ou Microsoft Word à l'aide de différentes entités de données fournies par Talent via l'intégration à Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="36ad3-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="36ad3-117">**Solution à long terme**</span><span class="sxs-lookup"><span data-stu-id="36ad3-117">**Long-term solution**</span></span>

<span data-ttu-id="36ad3-118">Des options Power BI supplémentaires seront disponibles, et des données et entités supplémentaires feront partie de Common Data Service pour les applications.</span><span class="sxs-lookup"><span data-stu-id="36ad3-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service for Apps.</span></span>

