---
title: L'annulation du rapport comme terminé crée une transaction en cours inattendue
description: L'annulation du reporting comme terminé avec marquage crée une transaction en cours où la quantité contrepassée a les mêmes dimensions de stock que la transaction contrepassée.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ea9044a9008e766c7fc92f98e27cfb91076f5b44
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026519"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a><span data-ttu-id="e4152-103">L'annulation du rapport comme terminé crée une transaction en cours inattendue</span><span class="sxs-lookup"><span data-stu-id="e4152-103">Reversal of reporting as finished creates an unexpected open transaction</span></span>

<span data-ttu-id="e4152-104">Numéro de la base de connaissances : 4612469</span><span class="sxs-lookup"><span data-stu-id="e4152-104">KB number: 4612469</span></span>

## <a name="symptoms"></a><span data-ttu-id="e4152-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="e4152-105">Symptoms</span></span>

<span data-ttu-id="e4152-106">Si vous annulez le reporting comme terminé avec marquage, le système crée une transaction en cours dans laquelle la quantité contrepassée a les mêmes dimensions de stock que la transaction qui a été contrepassée.</span><span class="sxs-lookup"><span data-stu-id="e4152-106">If you reverse reporting as finished that has marking, the system creates an open transaction where the reversed quantity has the same inventory dimensions as the transaction that was reversed.</span></span>

## <a name="resolution"></a><span data-ttu-id="e4152-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="e4152-107">Resolution</span></span>

<span data-ttu-id="e4152-108">Lorsque vous annulez une opération d'état comme terminé, la dimension de stock est initialisée à partir du journal de production.</span><span class="sxs-lookup"><span data-stu-id="e4152-108">When you reverse a report-as-finished operation, the inventory dimension is initialized from the production journal.</span></span> <span data-ttu-id="e4152-109">Par conséquent, il obtient le numéro de lot.</span><span class="sxs-lookup"><span data-stu-id="e4152-109">Therefore, it gets the batch number.</span></span> <span data-ttu-id="e4152-110">En raison du marquage, les transactions de commande client hériteront du numéro de lot.</span><span class="sxs-lookup"><span data-stu-id="e4152-110">Because of marking, the sales order transactions will inherit the batch number.</span></span>

<span data-ttu-id="e4152-111">La dimension peut être réinitialisée lorsque le rapport terminé est validé.</span><span class="sxs-lookup"><span data-stu-id="e4152-111">The dimension can be reset when the reporting as finished is posted.</span></span>
