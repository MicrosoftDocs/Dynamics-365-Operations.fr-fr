---
title: Il n'y a pas de valeur de date de début dans l'onglet Prix actifs de la page Prix de l'article
description: Il n'y a pas de valeur de date de début dans l'onglet Prix actifs de la page Prix de l'article.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dd13f6a3e5ce3c894e96f420358d337f2e43dba
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026522"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a><span data-ttu-id="64dd1-103">Il n'y a pas de valeur de date de début dans l'onglet Prix actifs de la page Prix de l'article</span><span class="sxs-lookup"><span data-stu-id="64dd1-103">There is no From date value on the Active prices tab of the Item price page</span></span>

<span data-ttu-id="64dd1-104">Numéro de la base de connaissances : 4613548</span><span class="sxs-lookup"><span data-stu-id="64dd1-104">KB number: 4613548</span></span>

## <a name="symptoms"></a><span data-ttu-id="64dd1-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="64dd1-105">Symptoms</span></span>

<span data-ttu-id="64dd1-106">Il n'y a pas de valeur **Date de début** dans l'onglet **Prix actifs** de la page **Prix de l'article**.</span><span class="sxs-lookup"><span data-stu-id="64dd1-106">There is no **From date** value on the **Active prices** tab of the **Item price** page.</span></span>

## <a name="resolution"></a><span data-ttu-id="64dd1-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="64dd1-107">Resolution</span></span>

<span data-ttu-id="64dd1-108">La valeur **Date de début** (date d'effet) qui est définie sur le prix en attente n'est pas transférée au prix actif.</span><span class="sxs-lookup"><span data-stu-id="64dd1-108">The **From date** value (effective date) that is set on the pending price isn't transferred to the active price.</span></span>

<span data-ttu-id="64dd1-109">La première fois qu’un enregistrement de coûts d’articles est saisi, il est doté du statut *En attente* et une date d’effet choisie.</span><span class="sxs-lookup"><span data-stu-id="64dd1-109">When an item cost record is first entered, it has a status of *Pending* and an intended effective date.</span></span> <span data-ttu-id="64dd1-110">Lorsque vous activez l’enregistrement des coûts d’articles, le statut est mis à jour sur *Actif*, et la date d’effet est mise à jour sur la date d’activation.</span><span class="sxs-lookup"><span data-stu-id="64dd1-110">When you activate the item cost record, the status is updated to *Active*, and the effective date is updated to the activation date.</span></span> <span data-ttu-id="64dd1-111">Par conséquent, la date d'activation du prix actif est toujours la date réelle de l'activation.</span><span class="sxs-lookup"><span data-stu-id="64dd1-111">Therefore, the active price's activation date is always the actual date of the activation.</span></span>

<span data-ttu-id="64dd1-112">Pour plus d’informations, voir [Vue d’ensemble des versions d’évaluation des coûts](../../cost-management/costing-versions.md).</span><span class="sxs-lookup"><span data-stu-id="64dd1-112">For more information, see [Costing versions overview](../../cost-management/costing-versions.md).</span></span>
