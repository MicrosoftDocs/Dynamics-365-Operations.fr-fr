---
title: Présentation de la gestion des modifications d’ingénierie
description: Cette rubrique fournit une vue d'ensemble de la gestion des modifications techniques, qui vous aide à planifier et à gérer la gestion des versions des produits et à gérer les cycles de vie des produits et les modifications techniques.
author: t-benebo
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: b081cd8d56217b8cf76db824c29482d453fc9ea3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001946"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="9cd75-103">Présentation de la gestion des modifications d’ingénierie</span><span class="sxs-lookup"><span data-stu-id="9cd75-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="9cd75-104">Résumé de la fonction</span><span class="sxs-lookup"><span data-stu-id="9cd75-104">Feature summary</span></span>

<span data-ttu-id="9cd75-105">Les fabricants d'aujourd'hui ont besoin d'une solide gestion des données produit, d'un contrôle de version et d'une gestion des changements d'ingénierie pour réussir dans un monde où les cycles de vie des produits diminuent constamment, les exigences de qualité et de fiabilité accrues et une attention accrue à la sécurité des produits.</span><span class="sxs-lookup"><span data-stu-id="9cd75-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="9cd75-106">La gestion des changements d'ingénierie apporte structure et discipline au processus de gestion des données produit et permet aux produits d'être définis, publiés et révisés de manière contrôlée et prise en charge par des workflows.</span><span class="sxs-lookup"><span data-stu-id="9cd75-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="9cd75-107"> Grâce aux versions de produit et à la gestion des modifications techniques, vous pouvez documenter, évaluer l'impact et appliquer les modifications techniques tout au long du cycle de vie d'un produit.</span><span class="sxs-lookup"><span data-stu-id="9cd75-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="9cd75-108">La gestion des modifications techniques, qui vous aide à planifier et à gérer la gestion des versions des produits et à gérer les cycles de vie des produits et les modifications techniques.</span><span class="sxs-lookup"><span data-stu-id="9cd75-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="9cd75-109">Voici une liste de ses principales caractéristiques :</span><span class="sxs-lookup"><span data-stu-id="9cd75-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="9cd75-110">Gestion des versions du produit</span><span class="sxs-lookup"><span data-stu-id="9cd75-110">Product versioning</span></span>
- <span data-ttu-id="9cd75-111">Fonctionnalité de lancement de produit améliorée qui vous permet de conserver les données de base du produit dans une seule entité juridique (la société d'ingénierie) et de publier le produit lancé entièrement configuré dans d'autres entités juridiques</span><span class="sxs-lookup"><span data-stu-id="9cd75-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="9cd75-112">Règles de validation de la saisie des informations requises avant l'activation d'une version de produit (contrôles de disponibilité)</span><span class="sxs-lookup"><span data-stu-id="9cd75-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="9cd75-113">Gestion améliorée du cycle de vie des produits grâce à un contrôle précis du moment où un produit lancé peut être utilisé dans des processus d'entreprise spécifiques</span><span class="sxs-lookup"><span data-stu-id="9cd75-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="9cd75-114">Demandes de modification technique prises en charge par les workflows</span><span class="sxs-lookup"><span data-stu-id="9cd75-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="9cd75-115">Ordres de modification technique pris en charge par les workflows</span><span class="sxs-lookup"><span data-stu-id="9cd75-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="9cd75-116">La vidéo précédente ([Capacités de gestion du changement dans Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) est incluse dans la [playlist Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.</span><span class="sxs-lookup"><span data-stu-id="9cd75-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-engineering-change-management-for-your-system"></a><span data-ttu-id="9cd75-117">Activez la gestion des modifications techniques pour votre système</span><span class="sxs-lookup"><span data-stu-id="9cd75-117">Turn on engineering change management for your system</span></span>

<span data-ttu-id="9cd75-118">Commencez par activer la gestion des modifications techniques en suivant ces étapes.</span><span class="sxs-lookup"><span data-stu-id="9cd75-118">First, turn on engineering change management by following these steps.</span></span>

1. <span data-ttu-id="9cd75-119">Accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9cd75-119">Go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
1. <span data-ttu-id="9cd75-120">Rechercher des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="9cd75-120">Check for updates.</span></span>
1. <span data-ttu-id="9cd75-121">Activez la fonctionnalité nommée **Gestion des modifications d’ingénierie**.</span><span class="sxs-lookup"><span data-stu-id="9cd75-121">Turn on the feature that is named **Engineering Change Management**.</span></span>

<span data-ttu-id="9cd75-122">Ensuite, activez la clé de configuration **Gestion du changement d'ingénierie** en suivant ces étapes.</span><span class="sxs-lookup"><span data-stu-id="9cd75-122">Next, turn on the **Engineering Change Management** configuration key by following these steps.</span></span>

1. <span data-ttu-id="9cd75-123">Mettez votre système en mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="9cd75-123">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="9cd75-124">Accédez à **Administration système \> Paramétrage \> Configuration des licences**.</span><span class="sxs-lookup"><span data-stu-id="9cd75-124">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="9cd75-125">Développez le nœud **Commerce**, et cochez la case **Gestion du changement d'ingénierie**.</span><span class="sxs-lookup"><span data-stu-id="9cd75-125">Expand the **Trade** node, and select the **Engineering Change Management** check box.</span></span>
1. <span data-ttu-id="9cd75-126">Désactiver le mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="9cd75-126">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
