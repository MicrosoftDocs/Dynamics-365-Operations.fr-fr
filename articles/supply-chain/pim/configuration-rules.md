---
title: Règles de configuration
description: Cet article fournit des informations générales sur les règles de configuration. Les règles de configuration définissent les relations entre les articles dans une nomenclature (BOM) pour les produits qui utilisent la technologie de configuration basée sur les dimensions.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac3515837df45b65121ebec72a32ac98d740796a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5221869"
---
# <a name="configuration-rules"></a><span data-ttu-id="40e4b-104">Règles de configuration</span><span class="sxs-lookup"><span data-stu-id="40e4b-104">Configuration rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40e4b-105">Cet article fournit des informations générales sur les règles de configuration.</span><span class="sxs-lookup"><span data-stu-id="40e4b-105">This article provides general information about configuration rules.</span></span> <span data-ttu-id="40e4b-106">Les règles de configuration définissent les relations entre les articles dans une nomenclature (BOM) pour les produits qui utilisent la technologie de configuration basée sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="40e4b-106">Configuration rules define relationships between items in a bill of materials (BOM) for products that use the dimension-based configuration technology.</span></span>

<span data-ttu-id="40e4b-107">Les règles de configuration sont disponibles lorsque vous définissez des modèles de configuration basés sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="40e4b-107">Configuration rules are available when you define dimension-based configuration models.</span></span> <span data-ttu-id="40e4b-108">Les règles de configuration sont utilisées pour appliquer ou interdire des combinaisons d’article spécifiques dans une nomenclature.</span><span class="sxs-lookup"><span data-stu-id="40e4b-108">Configuration rules are used to either enforce or prohibit specific item combinations in a bill of materials (BOM).</span></span> <span data-ttu-id="40e4b-109">Une fois qu’une nomenclature a été créée et que les articles appropriés ont été affectés à leurs groupes de configuration respectifs, une ou plusieurs règles de configuration peuvent être définies.</span><span class="sxs-lookup"><span data-stu-id="40e4b-109">After a BOM has been created and the relevant items have been assigned to their respective configuration groups, one or more configuration rules can be defined.</span></span> <span data-ttu-id="40e4b-110">Si deux articles sont liés, l’opérateur **Sélectionner** est utilisé pour assurer l’inclusion.</span><span class="sxs-lookup"><span data-stu-id="40e4b-110">If two items belong together, the **Select** operator is used to ensure inclusion.</span></span> <span data-ttu-id="40e4b-111">Si deux articles s’excluent mutuellement, l’opérateur **Désélectionner** est utilisé pour assurer l’exclusion.</span><span class="sxs-lookup"><span data-stu-id="40e4b-111">If two items are mutually exclusive, the **Deselect** operator is used to ensure exclusion.</span></span>  

<span data-ttu-id="40e4b-112">**Remarque :** ces informations s’appliquent uniquement aux produits génériques qui utilisent la technologie de configuration basée sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="40e4b-112">**Note:** This information applies only to product masters that use the dimension-based configuration technology.</span></span>  

<span data-ttu-id="40e4b-113">Les configurations existantes ne sont pas concernées par les modifications ultérieures apportées aux règles de configuration.</span><span class="sxs-lookup"><span data-stu-id="40e4b-113">Existing configurations aren't affected by subsequent changes to the configuration rules.</span></span> <span data-ttu-id="40e4b-114">Cependant, il est important de définir les règles avant de définir une nouvelle configuration et de les vérifier si vous pensez qu’elles ont été modifiées.</span><span class="sxs-lookup"><span data-stu-id="40e4b-114">However, it's important that you set the rules before you define a new configuration, and that you check the rules if you think they have been changed.</span></span>  

<span data-ttu-id="40e4b-115">**Remarque :** pour la méthode **Sélectionner**, le groupe de configurations déduit, le numéro d’article et la configuration sont automatiquement sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="40e4b-115">**Note:** For the **Select** method, the derived configuration group, item number, and configuration are automatically selected.</span></span> <span data-ttu-id="40e4b-116">Pour la méthode **Désélectionner**, le groupe de configurations déduit, le numéro d’article et la configuration ne peuvent pas être sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="40e4b-116">For the **Deselect** method, the derived configuration group, item number, and configuration can't be selected.</span></span>

<a name="additional-resources"></a><span data-ttu-id="40e4b-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="40e4b-117">Additional resources</span></span>
--------

[<span data-ttu-id="40e4b-118">Vue d’ensemble de la configuration des produits basée sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="40e4b-118">Dimension-based product configuration overview</span></span>](dimension-based-product-configuration.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]