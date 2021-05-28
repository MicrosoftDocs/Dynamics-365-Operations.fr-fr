---
title: L'entrepôt dans le journal de la liste de prélèvement n'est pas mis à jour sur une ligne de nomenclature.
description: L'entrepôt dans le journal de la liste de prélèvement n'est pas mis à jour sur une ligne de nomenclature (BOM).
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5d24c0b8538f3894fd1d2a3edb3a6ed8633c9609
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026498"
---
# <a name="the-warehouse-in-the-picking-list-journal-isnt-updated-on-a-bom-line"></a><span data-ttu-id="462cf-103">L'entrepôt dans le journal de la liste de prélèvement n'est pas mis à jour sur une ligne de nomenclature</span><span class="sxs-lookup"><span data-stu-id="462cf-103">The warehouse in the picking list journal isn't updated on a BOM line</span></span>

<span data-ttu-id="462cf-104">Numéro de la base de connaissances : 4614848</span><span class="sxs-lookup"><span data-stu-id="462cf-104">KB number: 4614848</span></span>

## <a name="symptoms"></a><span data-ttu-id="462cf-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="462cf-105">Symptoms</span></span>

<span data-ttu-id="462cf-106">L'entrepôt dans le journal de la liste de prélèvement n'est pas mis à jour sur une ligne de nomenclature (BOM).</span><span class="sxs-lookup"><span data-stu-id="462cf-106">The warehouse in the picking list journal isn't updated on a bill of materials (BOM) line.</span></span>

## <a name="resolution"></a><span data-ttu-id="462cf-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="462cf-107">Resolution</span></span>

<span data-ttu-id="462cf-108">Le système se comporte comme prévu.</span><span class="sxs-lookup"><span data-stu-id="462cf-108">The system is behaving as designed.</span></span> <span data-ttu-id="462cf-109">Si une ligne de journal de liste de prélèvement est créée avec une référence (via l'ID de lot) à une ligne de nomenclature de production, l'entrepôt sur la ligne de nomenclature de production ne sera pas mis à jour si la dimension magasin sur la ligne de journal de liste de prélèvement de production est modifiée ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="462cf-109">If a picking list journal line is created that has a reference (via the lot ID) to a production BOM line, the warehouse on the production BOM line won't be updated if the warehouse dimension on the production picking list journal line is changed later.</span></span>
