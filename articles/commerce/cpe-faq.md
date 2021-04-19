---
title: FAQ des environnements d’évaluation Dynamics 365 Commerce
description: Cette rubrique fournit des réponses aux questions fréquemment posées sur l’environnement d’évaluation Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e42618a522f5ad551f608605300c30b5ffb8e299
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795929"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a><span data-ttu-id="642cc-103">FAQ des environnements d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="642cc-103">Dynamics 365 Commerce evaluation environment FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="642cc-104">Cette rubrique fournit des réponses aux questions fréquemment posées sur l’environnement d’évaluation Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="642cc-104">This topic provides answers to frequently asked questions about the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="642cc-105">**Pouvons-nous utiliser l’environnement d’évaluation Commerce comme vitrine de commerce électronique pour les clients qui implémentent actuellement Retail ?**</span><span class="sxs-lookup"><span data-stu-id="642cc-105">**Can we use the Commerce evaluation environment as an e-Commerce storefront for customers that currently implement Retail?**</span></span>

<span data-ttu-id="642cc-106">N°</span><span class="sxs-lookup"><span data-stu-id="642cc-106">No.</span></span> <span data-ttu-id="642cc-107">L’environnement d’évaluation Commerce est uniquement destiné à l’évaluation.</span><span class="sxs-lookup"><span data-stu-id="642cc-107">The Commerce evaluation environment is only for evaluation.</span></span> <span data-ttu-id="642cc-108">Si vous avez besoin d’un environnement pour un client qui implémente Retail, contactez Microsoft.</span><span class="sxs-lookup"><span data-stu-id="642cc-108">If you require an environment for a customer that implements Retail, contact Microsoft.</span></span>

<span data-ttu-id="642cc-109">**L’environnement d’évaluation Commerce peut-il être utilisé pour fournir les fonctionnalités de commerce électronique s’appuyant sur une application/un environnement existant qui implémente Retail ?**</span><span class="sxs-lookup"><span data-stu-id="642cc-109">**Can the Commerce evaluation environment be used to provision the e-Commerce features on top of an existing application/environment that implements Retail?**</span></span>

<span data-ttu-id="642cc-110">Non (généralement).</span><span class="sxs-lookup"><span data-stu-id="642cc-110">No (mostly).</span></span> <span data-ttu-id="642cc-111">Les composants de la version d’évaluation Commerce sont disponibles uniquement pour les environnements qui correspondent aux configurations spécifiées dans le guide des conditions préalables et de la mise en service.</span><span class="sxs-lookup"><span data-stu-id="642cc-111">The Commerce evaluation components are available only to environments that match the configurations that are specified in the prerequisites and provisioning guide.</span></span> <span data-ttu-id="642cc-112">En outre, les données de démonstration de base requises ne seront pas disponibles dans les environnements qui ont été déployés avec une version initiale antérieure à la version 10.0.8.</span><span class="sxs-lookup"><span data-stu-id="642cc-112">Additionally, the required base demo data won't be available in environments that were deployed with an initial release that is earlier than 10.0.8.</span></span> 

<span data-ttu-id="642cc-113">**Quels sont les coûts impliqués dans le déploiement de l’environnement d’évaluation Commerce sur Microsoft Azure via Microsoft Dynamics Lifecycle Services (LCS) ?**</span><span class="sxs-lookup"><span data-stu-id="642cc-113">**What costs are involved in deploying the Commerce evaluation environment on Microsoft Azure via Microsoft Dynamics Lifecycle Services (LCS)?**</span></span>

<span data-ttu-id="642cc-114">Un environnement de démonstration du siège Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce traditionnel (machine virtuelle \[VM\]) sera hébergé dans votre abonnement Azure.</span><span class="sxs-lookup"><span data-stu-id="642cc-114">A traditional Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce headquarters demo environment (virtual machine \[VM\]) will be hosted in your Azure subscription.</span></span> <span data-ttu-id="642cc-115">Vous pouvez utiliser le [Calculateur de tarification Azure](https://azure.microsoft.com/pricing/calculator/) pour estimer ce coût.</span><span class="sxs-lookup"><span data-stu-id="642cc-115">You can use the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/) to estimate this cost.</span></span>

<span data-ttu-id="642cc-116">D’autres composants tels que Commerce Scale Unit, le générateur de site Commerce et votre site de commerce électronique seront disponibles sous forme de logiciel en tant que service (SaaS) et seront hébergés par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="642cc-116">Other components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site will be available as software as a service (SaaS) and hosted by Microsoft.</span></span>

<span data-ttu-id="642cc-117">**Quelles zones géographiques Azure sont actuellement prises en charge pour l’environnement d’évaluation de Commerce ?**</span><span class="sxs-lookup"><span data-stu-id="642cc-117">**Which Azure geographies are currently supported for the Commerce evaluation environment?**</span></span>

<span data-ttu-id="642cc-118">L’environnement d’évaluation de Commerce ne peut être déployé que dans la zone géographique de l’Amérique du Nord.</span><span class="sxs-lookup"><span data-stu-id="642cc-118">The Commerce evaluation environment can be deployed only in the North America geography.</span></span>

<span data-ttu-id="642cc-119">**Existe-t-il un disque dur virtuel téléchargeable doté de l’option complète de machine virtuelle OneBox ?**</span><span class="sxs-lookup"><span data-stu-id="642cc-119">**Is there a downloadable virtual hard disk (VHD) that has the complete OneBox virtual machine (VM) option?**</span></span>

<span data-ttu-id="642cc-120">Dynamics 365 Commerce et Commerce Scale Unit sont entièrement des logiciels en tant que service (SaaS) et doivent être hébergés dans le cloud.</span><span class="sxs-lookup"><span data-stu-id="642cc-120">Dynamics 365 Commerce and Commerce Scale Unit are completely software as a service (SaaS) and must be cloud-hosted.</span></span>

<span data-ttu-id="642cc-121">**Pendant combien de temps l’environnement d’évaluation de Commerce peut-il être utilisé ?**</span><span class="sxs-lookup"><span data-stu-id="642cc-121">**How long can the Commerce evaluation environment be used?**</span></span>

<span data-ttu-id="642cc-122">L’environnement d’évaluation de Commerce est assorti d’une limite d’utilisation de 30 jours à compter de la date à laquelle les composants SaaS tels que Commerce Scale Unit, le générateur de site Commerce et votre site de commerce électronique sont fournis.</span><span class="sxs-lookup"><span data-stu-id="642cc-122">The Commerce evaluation environment has a 30-day time limit from the date when SaaS components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site are provisioned.</span></span>

<span data-ttu-id="642cc-123">**Puis-je prolonger la durée limite de mon environnement d’évaluation Commerce ?**</span><span class="sxs-lookup"><span data-stu-id="642cc-123">**Can I extend the time limit for my Commerce evaluation environment?**</span></span>

<span data-ttu-id="642cc-124">La prolongation du délai est une exception à la norme et est envisagée au cas par cas.</span><span class="sxs-lookup"><span data-stu-id="642cc-124">Extension of the time limit is an exception to the norm and is considered on a case-by-case basis.</span></span> <span data-ttu-id="642cc-125">Contactez votre partenaire Microsoft pour obtenir de l’aide.</span><span class="sxs-lookup"><span data-stu-id="642cc-125">You should reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="642cc-126">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="642cc-126">Additional resources</span></span>

[<span data-ttu-id="642cc-127">Vue d’ensemble d’un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="642cc-127">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="642cc-128">Mettre en service un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="642cc-128">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="642cc-129">Configurer un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="642cc-129">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="642cc-130">Configurer le BOPIS dans un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="642cc-130">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="642cc-131">Configurer des fonctionnalités facultatives pour un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="642cc-131">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]