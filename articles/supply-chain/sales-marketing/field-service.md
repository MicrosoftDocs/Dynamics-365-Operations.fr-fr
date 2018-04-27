---
title: "Intégration à Microsoft Dynamics 365 for Field Service"
description: "Cette rubrique fournit une vue d'ensemble de l'intégration à Microsoft Dynamics 365 for Field Service"
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: d32a4e376770fc73c79b94924d5ae062d201d84a
ms.openlocfilehash: a224962152e80293f6cf3425dea74d73a283e31a
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2018

---


# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a><span data-ttu-id="cda47-103">Intégration à Microsoft Dynamics 365 for Field Service</span><span class="sxs-lookup"><span data-stu-id="cda47-103">Integration with Microsoft Dynamics 365 for Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cda47-104">Microsoft Dynamics 365 for Finance and Operations active la synchronisation des processus d'entreprise entre Finance and Operations et Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="cda47-104">Microsoft Dynamics 365 for Finance and Operations enables synchronization of business processes between Finance and Operations and Microsoft Dynamics 365 for Field Service.</span></span> <span data-ttu-id="cda47-105">Les scénarios d'intégration sont configurés à l'aide de modèles d'intégrateur de données extensibles et de Common Data Service (CDS) pour activer la synchronisation des processus d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="cda47-105">The integration scenarios are configured by using extensible Data integrator templates and the Common Data Service (CDS) to enable the synchronization of business processes.</span></span>

<span data-ttu-id="cda47-106">[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="cda47-106">[![Synchronization of business processes between Finance and Operations and Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span></span>

<span data-ttu-id="cda47-107">La première phase de l'intégration entre Field Service et Finance and Operations porte sur l'activation des ordres d'exécution et des accords dans Field Service à facturer en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cda47-107">The first phase  of the integration between Field Service and Finance and Operations is focused on enabling work orders and agreements in Field Service to be invoiced in Finance and Operations.</span></span> <span data-ttu-id="cda47-108">Le flux pris en charge commence dans Field Service, où les informations des ordres d'exécution sont synchronisées dans Finance and Operations comme commandes client.</span><span class="sxs-lookup"><span data-stu-id="cda47-108">The supported flow starts in Field Service, where information from work orders is synchronized to Finance and Operations as sales orders.</span></span> <span data-ttu-id="cda47-109">Dans Finance and Operations, des commandes client sont facturées pour générer des documents de facture.</span><span class="sxs-lookup"><span data-stu-id="cda47-109">In Finance and Operations, the sales orders are invoiced to generate invoice documents.</span></span> <span data-ttu-id="cda47-110">De plus, les informations des factures d'accord Field Service sont synchronisées sur Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cda47-110">In addition, the information from Field Service agreement invoices is synchronized to Finance and Operations.</span></span> <span data-ttu-id="cda47-111">L'intégrateur de données Microsoft Dynamics 365 synchronise les données à l'aide de projets personnalisables.</span><span class="sxs-lookup"><span data-stu-id="cda47-111">The Microsoft Dynamics 365 Data integrator synchronizes data by using customizable projects.</span></span> <span data-ttu-id="cda47-112">Les modèles standard peuvent être utilisés pour créer des projets d'intégration personnalisés dans lesquels des champs standard et personnalisés supplémentaires, ainsi que des entités, peuvent être mis en correspondance pour ajuster l'intégration et satisfaire aux besoins spécifiques.</span><span class="sxs-lookup"><span data-stu-id="cda47-112">Standard templates can be used to create custom integration projects where additional standard and custom fields, and also entities, can be mapped to adjust the integration and meet specific requirements.</span></span>

<span data-ttu-id="cda47-113">La première phase de l'intégration entre Field Service et Finance and Operations active la synchronisation des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="cda47-113">The first phase of the integration between Field Service and Finance and Operations enables synchronization of the following items:</span></span>

- [<span data-ttu-id="cda47-114">Produits de Finance and Operations sur des produits de Field Service incluant des informations sur le type de produit</span><span class="sxs-lookup"><span data-stu-id="cda47-114">Products in Finance and Operations to products in Field Service that include Product Type information</span></span>](field-service-product.md)
- [<span data-ttu-id="cda47-115">Des ordres d'exécution Field Service sur des commandes client Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cda47-115">Work orders in Field Service to sales orders in Finance and Operations</span></span>](field-service-work-order.md)
- [<span data-ttu-id="cda47-116">Des factures Field Service en factures financières Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cda47-116">Invoices in Field Service to free text invoices in Finance and Operations</span></span>](field-service-invoice.md)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="cda47-117">Configuration requise pour Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cda47-117">System requirements for Finance and Operations</span></span>
<span data-ttu-id="cda47-118">L'intégration Field Service prend en charge les versions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cda47-118">Field Service integration supports the following versions:</span></span>

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a><span data-ttu-id="cda47-119">Dynamics 365 for Finance and Operations, version 8.0 (avril 2018) ou versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="cda47-119">Dynamics 365 for Finance and Operations version 8.0 (April 2018) or later</span></span>

- <span data-ttu-id="cda47-120">Dynamics 365 for Finance and Operations version 8.0 (avril 2018) a été publié en avril 2018 et a pour numéro de version de l'application 8.0.30.8020 avec Platform Update 15 (7.0.4841.35234).</span><span class="sxs-lookup"><span data-stu-id="cda47-120">Dynamics 365 for Finance and Operations version 8.0 (April 2018) was released in April 2018 and has an application build number 8.0.30.8020 with Platform Update 15 (7.0.4841.35234).</span></span> 

## <a name="system-requirements-for-field-service"></a><span data-ttu-id="cda47-121">Configuration requise pour Field Service</span><span class="sxs-lookup"><span data-stu-id="cda47-121">System requirements for Field Service</span></span>
<span data-ttu-id="cda47-122">Pour utiliser la solution d'intégration Field Service, vous devez installer les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="cda47-122">To use the Field Service integration solution, you must install the following components:</span></span>

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a><span data-ttu-id="cda47-123">Microsoft Dynamics 365 for Field Service 9.0 ou versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="cda47-123">Microsoft Dynamics 365 for Field Service 9.0 or later</span></span>

- <span data-ttu-id="cda47-124">Dynamics 365 for Field Service version 1612 (9.0.1.733) (DB 9.0.1.733) en ligne ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="cda47-124">Dynamics 365 for Field Service version 1612 (9.0.1.733) (DB 9.0.1.733) online or a later version.</span></span>
- <span data-ttu-id="cda47-125">Solution Prospect en disponibilités pour Dynamics 365, version 1.15.0.1 or ultérieure.</span><span class="sxs-lookup"><span data-stu-id="cda47-125">Prospect to Cash (P2C) solution for Dynamics 365, version 1.15.0.1 or a later version.</span></span> <span data-ttu-id="cda47-126">La solution est disponible pour le téléchargement depuis [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span><span class="sxs-lookup"><span data-stu-id="cda47-126">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span></span>
- <span data-ttu-id="cda47-127">Solution d'intégration Field Service pour Dynamics 365 version 1.0.0.0 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="cda47-127">Field Service integration solution for Dynamics 365, version 1.0.0.0 or a later version.</span></span> <span data-ttu-id="cda47-128">La solution est disponible pour le téléchargement depuis AppSource.</span><span class="sxs-lookup"><span data-stu-id="cda47-128">The solution is available for download from AppSource.</span></span> <span data-ttu-id="cda47-129">**(EN ATTENTE DE LANCEMENT)**</span><span class="sxs-lookup"><span data-stu-id="cda47-129">**(PENDING RELEASE)**</span></span>

