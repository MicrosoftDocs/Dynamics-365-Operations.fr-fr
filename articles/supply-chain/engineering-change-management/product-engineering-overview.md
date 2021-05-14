---
title: Présentation de la gestion des modifications d’ingénierie
description: Cette rubrique fournit une vue d’ensemble de la gestion des modifications techniques, qui vous aide à planifier et à gérer la gestion des versions des produits et à gérer les cycles de vie des produits et les modifications techniques.
author: t-benebo
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d7c0839ffbea80904ca12d1cba7ba9880f721cdd
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947518"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="49f00-103">Présentation de la gestion des modifications d’ingénierie</span><span class="sxs-lookup"><span data-stu-id="49f00-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="49f00-104">Résumé de la fonction</span><span class="sxs-lookup"><span data-stu-id="49f00-104">Feature summary</span></span>

<span data-ttu-id="49f00-105">Les fabricants d’aujourd’hui ont besoin d’une solide gestion des données produit, d’un contrôle de version et d’une gestion des changements d’ingénierie pour réussir dans un monde où les cycles de vie des produits diminuent constamment, les exigences de qualité et de fiabilité accrues et une attention accrue à la sécurité des produits.</span><span class="sxs-lookup"><span data-stu-id="49f00-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="49f00-106">La gestion des changements d’ingénierie apporte structure et discipline au processus de gestion des données produit et permet aux produits d’être définis, publiés et révisés de manière contrôlée et prise en charge par des workflows.</span><span class="sxs-lookup"><span data-stu-id="49f00-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="49f00-107"> Grâce aux versions de produit et à la gestion des modifications techniques, vous pouvez documenter, évaluer l’impact et appliquer les modifications techniques tout au long du cycle de vie d’un produit.</span><span class="sxs-lookup"><span data-stu-id="49f00-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="49f00-108">La gestion des modifications techniques, qui vous aide à planifier et à gérer la gestion des versions des produits et à gérer les cycles de vie des produits et les modifications techniques.</span><span class="sxs-lookup"><span data-stu-id="49f00-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="49f00-109">Voici une liste de ses principales caractéristiques :</span><span class="sxs-lookup"><span data-stu-id="49f00-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="49f00-110">Gestion des versions du produit</span><span class="sxs-lookup"><span data-stu-id="49f00-110">Product versioning</span></span>
- <span data-ttu-id="49f00-111">Fonctionnalité de lancement de produit améliorée qui vous permet de conserver les données de base du produit dans une seule entité juridique (la société d’ingénierie) et de publier le produit lancé entièrement configuré dans d’autres entités juridiques</span><span class="sxs-lookup"><span data-stu-id="49f00-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="49f00-112">Règles de validation de la saisie des informations requises avant l’activation d’une version de produit (contrôles de disponibilité)</span><span class="sxs-lookup"><span data-stu-id="49f00-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="49f00-113">Gestion améliorée du cycle de vie des produits grâce à un contrôle précis du moment où un produit lancé peut être utilisé dans des processus d’entreprise spécifiques</span><span class="sxs-lookup"><span data-stu-id="49f00-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="49f00-114">Demandes de modification technique prises en charge par les workflows</span><span class="sxs-lookup"><span data-stu-id="49f00-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="49f00-115">Ordres de modification technique pris en charge par les workflows</span><span class="sxs-lookup"><span data-stu-id="49f00-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="49f00-116">La vidéo précédente ([Capacités de gestion du changement dans Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) est incluse dans la [playlist Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.</span><span class="sxs-lookup"><span data-stu-id="49f00-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a><span data-ttu-id="49f00-117">Activez la gestion des modifications techniques et les fonctionnalités de dimension de version pour votre système</span><span class="sxs-lookup"><span data-stu-id="49f00-117">Turn on the engineering change management and version dimension features for your system</span></span>

<span data-ttu-id="49f00-118">Avant de pouvoir utiliser la gestion des modifications techniques, vous devez activer la fonctionnalité *Gestion du changement d’ingénierie* et sa clé de configuration.</span><span class="sxs-lookup"><span data-stu-id="49f00-118">Before you can use engineering change management, you must enable both the *Engineering Change Management* feature and its configuration key.</span></span> <span data-ttu-id="49f00-119">Si vous souhaitez également suivre la dimension de version des produits dans les transactions (facultatif), vous devez également activer la fonctionnalité *Dimension de la version du produit* et sa clé de configuration.</span><span class="sxs-lookup"><span data-stu-id="49f00-119">If you also want to track the version dimension of products in transactions (optional), then you must also enable the *Product version dimension* feature and its configuration key.</span></span>

<span data-ttu-id="49f00-120">Commencez par activer les fonctionnalités en suivant ces étapes.</span><span class="sxs-lookup"><span data-stu-id="49f00-120">First, turn on the features by following these steps.</span></span>

1. <span data-ttu-id="49f00-121">Accédez à l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="49f00-121">Go to the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace.</span></span>
1. <span data-ttu-id="49f00-122">Rechercher des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="49f00-122">Check for updates.</span></span>
1. <span data-ttu-id="49f00-123">Activez la fonctionnalité nommée **Gestion des modifications d’ingénierie**.</span><span class="sxs-lookup"><span data-stu-id="49f00-123">Turn on the feature that is named **Engineering Change Management**.</span></span>
1. <span data-ttu-id="49f00-124">Si vous souhaitez l’utiliser, activez également la fonctionnalité nommée **Version de dimension de produit**.</span><span class="sxs-lookup"><span data-stu-id="49f00-124">If you want to use it, then also turn on the feature that is named **Product dimension version**.</span></span>

<span data-ttu-id="49f00-125">Ensuite, activez les clés de configuration en suivant ces étapes.</span><span class="sxs-lookup"><span data-stu-id="49f00-125">Next, turn on the configuration keys by following these steps.</span></span>

1. <span data-ttu-id="49f00-126">Mettez votre système en mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="49f00-126">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="49f00-127">Accédez à **Administration système \> Paramétrage \> Configuration des licences**.</span><span class="sxs-lookup"><span data-stu-id="49f00-127">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="49f00-128">Développez le nœud **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="49f00-128">Expand the **Trade** node.</span></span>
1. <span data-ttu-id="49f00-129">Activez la clé de configuration de la fonction principale en activant la case à cocher **Gestion du changement technologique**.</span><span class="sxs-lookup"><span data-stu-id="49f00-129">Enable the configuration key for the main feature by selecting the **Engineering Change Management** check box.</span></span> <span data-ttu-id="49f00-130">(Il n'est pas nécessaire de développer le nœud, sauf si vous souhaitez également désactiver l'une de ses sous-fonctionnalités ou les deux.)</span><span class="sxs-lookup"><span data-stu-id="49f00-130">(It isn't necessary to expand the node unless you also want to disable one or both of its sub-features.)</span></span>
1. <span data-ttu-id="49f00-131">Si vous souhaitez également utiliser la dimension de la version, cochez **Dimension du produit – Version**.</span><span class="sxs-lookup"><span data-stu-id="49f00-131">If you also want to use the version dimension, then select the **Product dimension - Version** check box.</span></span> <span data-ttu-id="49f00-132">(Cette case à cocher se trouve plus bas dans la liste, elle n'est pas imbriquée sous le nœud **Gestion du changement technologique**.)</span><span class="sxs-lookup"><span data-stu-id="49f00-132">(This check box is further down the list, not nested under the **Engineering Change Management** node.)</span></span>
1. <span data-ttu-id="49f00-133">Désactiver le mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="49f00-133">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49f00-134">À partir d'avril 2022, les clés de licence pour **Gestion du changement technologique** et **Dimension du produit – Version** seront activées par défaut pour toutes les nouvelles installations, mais vous pourrez toujours les désactiver si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="49f00-134">Starting in April 2022, the license keys for both **Engineering Change Management** and **Product dimension - Version** will be enabled by default for all new installations, but you will still be able to disable them if needed.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
