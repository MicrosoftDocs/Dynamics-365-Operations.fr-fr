---
title: Une seule étiquette est imprimée pour plusieurs en-têtes de travail sur un seul reçu
description: Une seule étiquette est imprimée pour plusieurs en-têtes de travail sur un seul reçu.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8e11dc918eb3c9085018d15b43819522cc8bebe3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026506"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a><span data-ttu-id="21f77-103">Une seule étiquette est imprimée pour plusieurs en-têtes de travail sur un seul reçu</span><span class="sxs-lookup"><span data-stu-id="21f77-103">Only one label is printed for multiple work headers on a single receipt</span></span>

<span data-ttu-id="21f77-104">Numéro de la base de connaissances : 4614667</span><span class="sxs-lookup"><span data-stu-id="21f77-104">KB number: 4614667</span></span>

## <a name="symptoms"></a><span data-ttu-id="21f77-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="21f77-105">Symptoms</span></span>

<span data-ttu-id="21f77-106">Plusieurs en-têtes de travail sont créés pour le même contenant cible dans le cadre d'un seul événement de réception d'application d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="21f77-106">Multiple work headers are created for the same target license plate as part of a single warehouse app receiving event.</span></span> <span data-ttu-id="21f77-107">Cependant, une seule étiquette de contenant est imprimée lors de la réception du produit.</span><span class="sxs-lookup"><span data-stu-id="21f77-107">However, only one license plate label is printed when the product is received.</span></span>

## <a name="resolution"></a><span data-ttu-id="21f77-108">Résolution</span><span class="sxs-lookup"><span data-stu-id="21f77-108">Resolution</span></span>

<span data-ttu-id="21f77-109">Le système se comporte comme prévu.</span><span class="sxs-lookup"><span data-stu-id="21f77-109">The system is behaving as designed.</span></span>

<span data-ttu-id="21f77-110">Dans la conception actuelle, une seule étiquette de contenant est toujours générée, quel que soit le nombre de combinaisons d'en-tête de travail et de ligne de travail qui existent.</span><span class="sxs-lookup"><span data-stu-id="21f77-110">In the current design, a single license plate label is always generated, regardless of the number of work header and work line combinations that exist.</span></span> <span data-ttu-id="21f77-111">L'étiquette générée comprend les informations pour une seule combinaison.</span><span class="sxs-lookup"><span data-stu-id="21f77-111">The generated label includes the information for only one combination.</span></span>

<span data-ttu-id="21f77-112">Pour contourner ce problème, assurez-vous que la création d'en-tête de travail est toujours mappée à un seul contenant cible.</span><span class="sxs-lookup"><span data-stu-id="21f77-112">To work around this issue, make sure that work header creation is always mapped to just one target license plate.</span></span>
