---
title: Le champ Date du dernier test n'est pas mis à jour lorsque plusieurs commandes de qualité sont créées
description: Le champ Date du dernier test n'est pas mis à jour lorsque plusieurs commandes de qualité sont créées.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f796bdaa88d32b1c58dd8a4bca19f0ce4f3943d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026518"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a><span data-ttu-id="53967-103">Le champ Date du dernier test n'est pas mis à jour lorsque plusieurs commandes de qualité sont créées</span><span class="sxs-lookup"><span data-stu-id="53967-103">The Last tested date field isn't updated when multiple quality orders are created</span></span>

<span data-ttu-id="53967-104">Numéro de la base de connaissances : 4612803</span><span class="sxs-lookup"><span data-stu-id="53967-104">KB number: 4612803</span></span>

## <a name="symptoms"></a><span data-ttu-id="53967-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="53967-105">Symptoms</span></span>

<span data-ttu-id="53967-106">Le champ **Date du dernier test** n'est pas mis à jour lorsque plusieurs commandes de qualité sont créées.</span><span class="sxs-lookup"><span data-stu-id="53967-106">The **Last tested date** field isn't updated when multiple quality orders are created.</span></span>

## <a name="resolution"></a><span data-ttu-id="53967-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="53967-107">Resolution</span></span>

<span data-ttu-id="53967-108">Le système se comporte comme prévu.</span><span class="sxs-lookup"><span data-stu-id="53967-108">The system is behaving as designed.</span></span> <span data-ttu-id="53967-109">La dernière date testée n'est pas liée aux commandes de qualité.</span><span class="sxs-lookup"><span data-stu-id="53967-109">The last tested date isn't related to quality orders.</span></span> <span data-ttu-id="53967-110">Il stocke la date à laquelle les produits finis ont été achetés ou fabriqués pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="53967-110">It stores the date when the finished goods were first purchased or manufactured.</span></span> <span data-ttu-id="53967-111">Cette date est utilisée pour calculer la date d'avis de durée de conservation.</span><span class="sxs-lookup"><span data-stu-id="53967-111">This date is used to calculate the shelf life advice date.</span></span>
