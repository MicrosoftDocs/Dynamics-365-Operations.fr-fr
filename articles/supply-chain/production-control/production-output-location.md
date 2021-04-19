---
title: Emplacement de la sortie de production
description: Cette rubrique décrit la hiérarchie utilisée pour identifier l’emplacement de sortie de production.
author: johanhoffmann
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 48b68c36718fa42b7f80e3ffe1f54b7efbbee8bd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814630"
---
# <a name="production-output-location"></a><span data-ttu-id="a78c8-103">Emplacement de la sortie de production</span><span class="sxs-lookup"><span data-stu-id="a78c8-103">Production output location</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a78c8-104">Cette rubrique décrit la hiérarchie utilisée pour identifier l’emplacement de sortie de production.</span><span class="sxs-lookup"><span data-stu-id="a78c8-104">This topic describes the hierarchy that is used to identify the production output location.</span></span>

<span data-ttu-id="a78c8-105">L’emplacement de sortie de production est l’emplacement où un produit fini est d’abord stocké après avoir été produit.</span><span class="sxs-lookup"><span data-stu-id="a78c8-105">The production output location is the location where a finished good is first stored after it's produced.</span></span> <span data-ttu-id="a78c8-106">Généralement, cet emplacement est près du processus de production qui produit le produit fini.</span><span class="sxs-lookup"><span data-stu-id="a78c8-106">Usually, this location is close to the production process that produces the finished good.</span></span> <span data-ttu-id="a78c8-107">L’emplacement de sortie de production est utilisé comme stockage intermédiaire pour le matériel avant qu’il soit déplacé dans la zone d’expédition, à un emplacement de stockage, à un emplacement d’entrée en production pour un processus de production en aval, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="a78c8-107">The production output location is used as intermediate storage for the material before it's moved on to the shipment area, a storage location, a production input location for a downstream production process, and so on.</span></span> 

<span data-ttu-id="a78c8-108">Un emplacement de sortie de production par défaut est paramétré lorsque des produits finis sont signalés sur un ordre de fabrication ou un lot de commandes.</span><span class="sxs-lookup"><span data-stu-id="a78c8-108">A default production output location is set when finished goods are reported on a production order or batch order.</span></span> <span data-ttu-id="a78c8-109">La hiérarchie suivante est utilisée pour identifier cet emplacement de sortie :</span><span class="sxs-lookup"><span data-stu-id="a78c8-109">The following hierarchy is used to identify this output location:</span></span>

1. <span data-ttu-id="a78c8-110">Utilisez l’emplacement de sortie qui est défini dans l’en-tête de l’ordre de fabrication ou du lot de commandes.</span><span class="sxs-lookup"><span data-stu-id="a78c8-110">Use the output location that is defined on the production order or batch order header.</span></span>
2. <span data-ttu-id="a78c8-111">Si aucun emplacement n’est trouvé là, utilisez l’emplacement de sortie défini sur la ressource utilisée par la dernière opération définie dans la gamme de production.</span><span class="sxs-lookup"><span data-stu-id="a78c8-111">If no location is found there, use the output location that is defined on the resource that is used by the last operation that is defined in the production route.</span></span>
3. <span data-ttu-id="a78c8-112">Si aucun emplacement n’est trouvé là, utilisez l’emplacement de sortie défini sur le groupe de ressources utilisé par la ressource pour la dernière opération définie dans la gamme de production.</span><span class="sxs-lookup"><span data-stu-id="a78c8-112">If no location is found there, use the output location that is defined on the resource group that is used by the resource for the last operation that is defined in the production route.</span></span>
4. <span data-ttu-id="a78c8-113">Si aucun entrepôt n’est trouvé là, utilisez l’emplacement de sortie défini dans l’entrepôt qui est défini pour l’ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="a78c8-113">If no location is found there, use the output location that is defined on the warehouse that is defined for the production order.</span></span>

<span data-ttu-id="a78c8-114">Un emplacement de sortie de production par défaut est défini uniquement pour les produits qui sont paramétrés à l’aide des processus d’entrepôt avancés.</span><span class="sxs-lookup"><span data-stu-id="a78c8-114">A default production output location is set only for products that are set up by using advanced warehouse processes.</span></span> <span data-ttu-id="a78c8-115">Lorsque ce type d’article est déclaré terminé, le type de travail en entrepôt **Rangement des produits finis** ou **Rangement des coproduits et des sous-produits** est créé.</span><span class="sxs-lookup"><span data-stu-id="a78c8-115">When this type of item is reported as finished, warehouse work of the **Finished goods put away** or **Co-product and by-product put away** type is created.</span></span> <span data-ttu-id="a78c8-116">Ce type de travail utilise l’emplacement de sortie de production comme emplacement de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="a78c8-116">This type of work uses the production output location as the pick location.</span></span> <span data-ttu-id="a78c8-117">L’emplacement de rangement est déterminé par les instructions sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="a78c8-117">The put-away location is determined by the location directives.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]