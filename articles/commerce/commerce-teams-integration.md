---
title: Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams
description: Cette rubrique présente une vue d’ensemble de l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3b7872757815d4eec0393e8b1c8c6ff5467e9473
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842660"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a><span data-ttu-id="3c100-103">Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c100-103">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="3c100-104">Cette rubrique présente une vue d’ensemble de l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3c100-104">This topic presents an overview of Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="3c100-105">Dynamics 365 Commerce s’intègre à Teams pour aider les clients et leurs employés à améliorer leur productivité en synchronisant la gestion des tâches entre les deux applications.</span><span class="sxs-lookup"><span data-stu-id="3c100-105">Dynamics 365 Commerce is integrating with Teams to help customers and their employees improve productivity by synchronizing task management between the two applications.</span></span> <span data-ttu-id="3c100-106">La gestion transparente des tâches fournie par l’intégration de Commerce et Teams permet aux directeurs de magasin et aux employés de créer des listes de tâches, d’attribuer des tâches à plusieurs magasins et de suivre le statut des tâches dans les différents magasins, à partir de l’une ou l’autre application.</span><span class="sxs-lookup"><span data-stu-id="3c100-106">The seamless task management that Commerce and Teams integration provides lets store managers and employees create task lists, assign tasks to multiple stores, and track the status of tasks across stores, from either application.</span></span>

<span data-ttu-id="3c100-107">L’intégration de Commerce et Teams est disponible à partir de la version Commerce 10.0.18.</span><span class="sxs-lookup"><span data-stu-id="3c100-107">Commerce and Teams integration is available as of the Commerce version 10.0.18 release.</span></span>

## <a name="key-features"></a><span data-ttu-id="3c100-108">Fonctions principales</span><span class="sxs-lookup"><span data-stu-id="3c100-108">Key features</span></span>

<span data-ttu-id="3c100-109">Voici quelques-unes des principales fonctionnalités offertes par l’intégrité de Commerce et Microsoft Teams :</span><span class="sxs-lookup"><span data-stu-id="3c100-109">Here are some of the key features that the Commerce and Microsoft Teams integration provides:</span></span>

- <span data-ttu-id="3c100-110">Configurez Teams en tirant parti des informations bien définies de Commerce, telles que la structure organisationnelle et les informations sur les magasins, les employés, les autorisations et le contexte commercial.</span><span class="sxs-lookup"><span data-stu-id="3c100-110">Provision Teams by taking advantage of well-defined information from Commerce, such as the organizational structure and information about stores, workers, permissions, and business context.</span></span>
- <span data-ttu-id="3c100-111">Synchronisez facilement les changements en cours (par exemple, l’ajout de nouveaux magasins ou l’embauche de nouveaux employés) entre Commerce et Teams, mais gardez Commerce comme source principale des données de structure organisationnelle.</span><span class="sxs-lookup"><span data-stu-id="3c100-111">Easily synchronize ongoing changes (for example, the addition of new stores or hiring of new employees) between Commerce and Teams, but keep Commerce as the master source of organizational structure data.</span></span>
- <span data-ttu-id="3c100-112">Intégrez la gestion des tâches entre Commerce et Teams pour aider les employés de magasin, les directeurs de magasin, les directeurs régionaux et les responsables de la communication à gérer les tâches à partir de l’une ou l’autre des applications.</span><span class="sxs-lookup"><span data-stu-id="3c100-112">Integrate task management between Commerce and Teams to help store workers, store managers, regional managers, and communications managers handle task management from either application.</span></span>

## <a name="prerequisites-for-using-integration-features"></a><span data-ttu-id="3c100-113">Conditions préalables à l’utilisation des fonctionnalités d’intégration</span><span class="sxs-lookup"><span data-stu-id="3c100-113">Prerequisites for using integration features</span></span>

<span data-ttu-id="3c100-114">Les conditions préalables suivantes doivent être en place avant de pouvoir commencer à utiliser les fonctionnalités d’intégration de Microsoft Teams :</span><span class="sxs-lookup"><span data-stu-id="3c100-114">The following prerequisites must be in place before you can start to use Microsoft Teams integration features:</span></span>

- <span data-ttu-id="3c100-115">Licence Microsoft 365 Business Standard (Cette licence inclut Teams.)</span><span class="sxs-lookup"><span data-stu-id="3c100-115">Microsoft 365 Business Standard License (This license includes Teams.)</span></span>
- <span data-ttu-id="3c100-116">Comptes Azure Active Directory(Azure AD) pour tous les directeurs et employés de magasin</span><span class="sxs-lookup"><span data-stu-id="3c100-116">Azure Active Directory (Azure AD) accounts for all store managers and workers</span></span>
- <span data-ttu-id="3c100-117">Systèmes de point de vente (PDV) configurés avec l’authentification Azure AD</span><span class="sxs-lookup"><span data-stu-id="3c100-117">Point of sale (POS) systems that are configured with Azure AD authentication</span></span>

## <a name="conceptual-architecture"></a><span data-ttu-id="3c100-118">Architecture conceptuelle</span><span class="sxs-lookup"><span data-stu-id="3c100-118">Conceptual architecture</span></span>

<span data-ttu-id="3c100-119">L’illustration suivante montre l’architecture conceptuelle de l’intégration de Dynamics 365 Commerce et Microsoft Teams, en prenant un magasin de San Francisco comme exemple.</span><span class="sxs-lookup"><span data-stu-id="3c100-119">The following illustration shows the conceptual architecture of Dynamics 365 Commerce and Microsoft Teams integration, using a San Francisco store as an example.</span></span> <span data-ttu-id="3c100-120">Teams et l’application de PDV Commerce utilisent Microsoft Planner comme référentiel afin que les tâches publiées à partir de Teams apparaissent dans l’application de PDV et que les tâches ponctuelles créées par les directeurs de magasin dans l’application de PDV apparaissent dans Teams, ce qui se traduit par une expérience de gestion des tâches cohérente entre les applications.</span><span class="sxs-lookup"><span data-stu-id="3c100-120">Both Teams and the Commerce POS application use Microsoft Planner as a repository so that tasks published from Teams appear in the POS application and ad hoc tasks created by store managers in the POS application appear in Teams, resulting in a seamless task management experience between the applications.</span></span>    

![Architecture de l’intégration de Commerce et Teams](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a><span data-ttu-id="3c100-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3c100-122">Additional resources</span></span>

[<span data-ttu-id="3c100-123">Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c100-123">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="3c100-124">Configuration de Microsoft Teams à partir de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3c100-124">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="3c100-125">Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3c100-125">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="3c100-126">Gérer les rôles utilisateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c100-126">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="3c100-127">Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c100-127">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="3c100-128">FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c100-128">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
