---
title: Vue d'ensemble de la gestion des entrepôts
description: Utilisez la gestion des entrepôts pour surveiller et automatiser les processus d'entrepôt.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 17e4429dbf3f7e5d6c737c365f0351d5c588fcd2
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204583"
---
# <a name="warehouse-management-overview"></a><span data-ttu-id="2932f-103">Vue d'ensemble de gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="2932f-103">Warehouse management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2932f-104">Le module Gestion des entrepôts vous permet de gérer les processus d'entrepôt dans les sociétés de fabrication, distribution, et vente au détail.</span><span class="sxs-lookup"><span data-stu-id="2932f-104">The Warehouse management module lets you manage warehouse processes in manufacturing, distribution, and retail companies.</span></span> <span data-ttu-id="2932f-105">Ce module offre un large éventail de fonctions pour prendre en charge les entrepôts à un niveau optimal, à tout moment.</span><span class="sxs-lookup"><span data-stu-id="2932f-105">This module has a wide range of features to support the warehouse facility at an optimal level, at any time.</span></span> <span data-ttu-id="2932f-106">Le module Gestion des entrepôts intègre entièrement d'autres processus métier, tels que le transport, la fabrication, le contrôle de la qualité, les achats, le transfert, les ventes et les retours.</span><span class="sxs-lookup"><span data-stu-id="2932f-106">Warehouse management is fully integrated with other business processes such as transportation, manufacturing, quality control, purchase, transfer, sales, and returns.</span></span>

## <a name="get-started"></a><span data-ttu-id="2932f-107">Mise en route</span><span class="sxs-lookup"><span data-stu-id="2932f-107">Get started</span></span>
<span data-ttu-id="2932f-108">Pour commencer à travailler avec le module Gestion des entrepôts, vous devez effectuer le paramétrage des paramètres généraux d'entrepôt pour prendre en charge les processus métiers de votre société.</span><span class="sxs-lookup"><span data-stu-id="2932f-108">To start working with Warehouse management, you need to complete the setup of the general warehouse parameters to support the business processes of you company.</span></span>

- <span data-ttu-id="2932f-109">Accédez à la page **Paramètres de gestion des entrepôts** sous **Gestion des entrepôts** > **Paramétrage** pour configurer les paramètres d'entrepôt généraux.</span><span class="sxs-lookup"><span data-stu-id="2932f-109">Go to the **Warehouse management parameters** page under **Warehouse management** > **Setup** to set up general warehouse parameters.</span></span>

<span data-ttu-id="2932f-110">Vous devez configurer les composants pour les workflows d'entrée et de sortie des processus d'entrepôt en fonction des besoins de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="2932f-110">You must configure components for inbound and outbound warehouse process workflows according to business requirements.</span></span> <span data-ttu-id="2932f-111">Les composants les plus importants que vous devez configurer sont les modèles de vague, les modèles de travail, les pools de travail et les directives d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="2932f-111">The most important components that you must configure are wave templates, work templates, work pools, and location directives.</span></span>

- [<span data-ttu-id="2932f-112">Vue d'ensemble de configuration de l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="2932f-112">Warehouse configuration overview</span></span>](warehouse-configuration.md)
- [<span data-ttu-id="2932f-113">Contrôler le travail d'entrepôt à l'aide de modèles de travail et d'instructions d'emplacement</span><span class="sxs-lookup"><span data-stu-id="2932f-113">Control warehouse work by using work templates and location directives</span></span>](control-warehouse-location-directives.md)
- [<span data-ttu-id="2932f-114">Configuration des appareils mobiles pour le travail d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="2932f-114">Set up mobile devices for warehouse work</span></span>](configure-mobile-devices-warehouse.md)
- [<span data-ttu-id="2932f-115">Paramétrer une instruction d'emplacement pour le rangement des commandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="2932f-115">Set up a location directive for purchase order put-away</span></span>](../transportation/tasks/set-up-location-directive-purchase-order-put-away.md)
- [<span data-ttu-id="2932f-116">Définir un modèle de travail pour les commandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="2932f-116">Set up a work template for purchase orders</span></span>](./tasks/set-up-work-template-purchase-orders.md)

## <a name="warehouse-management-processes"></a><span data-ttu-id="2932f-117">Processus de gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="2932f-117">Warehouse management processes</span></span>
- <span data-ttu-id="2932f-118">Prise en charge intégrée des documents sources pour les commandes, les retours, les ordres de transfert, les ordres de fabrication et le kanban</span><span class="sxs-lookup"><span data-stu-id="2932f-118">Integrated support for source documents for sales orders, returns, transfer orders, production orders, and kanban</span></span>  
- <span data-ttu-id="2932f-119">Prise en charge flexible des workflows de matières entrants et sortants en fonction des requêtes</span><span class="sxs-lookup"><span data-stu-id="2932f-119">Flexible, inbound and outbound material workflow support based on queries</span></span>
- <span data-ttu-id="2932f-120">Intégration complète avec les offres de fabrication et de transport</span><span class="sxs-lookup"><span data-stu-id="2932f-120">Full integration with the Manufacturing and Transportation offerings</span></span>
- <span data-ttu-id="2932f-121">Contrôle total des limites de stockage et du volume de l'emplacement</span><span class="sxs-lookup"><span data-stu-id="2932f-121">Full control of location stocking limits and location volumetrics</span></span>
- <span data-ttu-id="2932f-122">Propriétés de stock contrôlées par statut du stock</span><span class="sxs-lookup"><span data-stu-id="2932f-122">Inventory properties controlled by inventory status</span></span>
- <span data-ttu-id="2932f-123">Prise en charge complète des articles de lot et des articles de série</span><span class="sxs-lookup"><span data-stu-id="2932f-123">Full batch and serial item support</span></span>
- <span data-ttu-id="2932f-124">Diverses capacités de réception d'articles</span><span class="sxs-lookup"><span data-stu-id="2932f-124">Various item receiving capabilities</span></span>
- <span data-ttu-id="2932f-125">Plusieurs stratégies de prélèvement</span><span class="sxs-lookup"><span data-stu-id="2932f-125">Multiple picking strategies</span></span>
- <span data-ttu-id="2932f-126">Support prêt à l'emploi pour la prochaine génération de scanners de codes à barres</span><span class="sxs-lookup"><span data-stu-id="2932f-126">Out-of-the-box support for the next generation of barcode scanners</span></span>
- <span data-ttu-id="2932f-127">Types de palette/conteneur pour les processus d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="2932f-127">Pallet/container types for warehouse processes</span></span>
- <span data-ttu-id="2932f-128">Fonctions de comptabilité avancées</span><span class="sxs-lookup"><span data-stu-id="2932f-128">Advanced counting capabilities</span></span>
- <span data-ttu-id="2932f-129">Impression et acheminement des étiquettes grâce à la prise en charge Zebra ZPL</span><span class="sxs-lookup"><span data-stu-id="2932f-129">Label printing and label routing with Zebra ZPL support</span></span>
- <span data-ttu-id="2932f-130">Intégration de Business Intelligence dans Power BI</span><span class="sxs-lookup"><span data-stu-id="2932f-130">Business intelligence integration into Power BI</span></span>
- <span data-ttu-id="2932f-131">Mouvements manuels et automatiques du stock</span><span class="sxs-lookup"><span data-stu-id="2932f-131">Manual and automatic movement of inventory</span></span>
- <span data-ttu-id="2932f-132">Contrôle de qualité entièrement intégré (QMS)</span><span class="sxs-lookup"><span data-stu-id="2932f-132">Fully-integrated quality control (QMS)</span></span>
- <span data-ttu-id="2932f-133">Traçabilité complète de la manutention de matériel par les collaborateurs</span><span class="sxs-lookup"><span data-stu-id="2932f-133">Full traceability of workers' material handling</span></span>
- <span data-ttu-id="2932f-134">Traitement de vagues sortant</span><span class="sxs-lookup"><span data-stu-id="2932f-134">Outbound wave processing</span></span>
- <span data-ttu-id="2932f-135">Prise en charge de l'emballage manuel et de la mise en conteneur automatique</span><span class="sxs-lookup"><span data-stu-id="2932f-135">Manual packing and automatic containerization support</span></span>
- <span data-ttu-id="2932f-136">Prélèvement de groupement</span><span class="sxs-lookup"><span data-stu-id="2932f-136">Cluster picking</span></span>
- <span data-ttu-id="2932f-137">Cross-docking simple</span><span class="sxs-lookup"><span data-stu-id="2932f-137">Simple cross docking</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2932f-138">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2932f-138">Additional resources</span></span>
### <a name="whats-new-and-in-development"></a><span data-ttu-id="2932f-139">Nouveautés et développements</span><span class="sxs-lookup"><span data-stu-id="2932f-139">What's new and in development</span></span>
<span data-ttu-id="2932f-140">Accédez au [Calendrier de lancement de Microsoft Dynamics 365](https://roadmap.dynamics.com/) pour découvrir les nouvelles fonctions qui ont été lancées ou qui sont en développement.</span><span class="sxs-lookup"><span data-stu-id="2932f-140">Go to the [Microsoft Dynamics 365 Roadmap](https://roadmap.dynamics.com/) to see what new features have been released and what new features are in development.</span></span>

### <a name="blogs"></a><span data-ttu-id="2932f-141">Blogs</span><span class="sxs-lookup"><span data-stu-id="2932f-141">Blogs</span></span>
<span data-ttu-id="2932f-142">Vous trouverez des avis, des actualités et d'autres informations concernant la gestion des entrepôts et d'autres solutions sur le [blog de Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog).</span><span class="sxs-lookup"><span data-stu-id="2932f-142">You can find opinions, news, and other information about Warehouse management and other solutions on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog).</span></span>


 

