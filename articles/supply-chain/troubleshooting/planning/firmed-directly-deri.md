---
title: Les commandes confirmées directement dérivées sont traitées par un flux de travail en révision
description: Les commandes confirmées directement dérivées sont traitées par un flux de travail avec le statut En révision.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d54985707d82df2b947a7cb615fc25f90aa31702
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026515"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a><span data-ttu-id="f0937-103">Les commandes confirmées directement dérivées sont traitées par un flux de travail en révision</span><span class="sxs-lookup"><span data-stu-id="f0937-103">Directly derived firmed orders are processed by an in-review workflow</span></span>

<span data-ttu-id="f0937-104">Numéro de la base de connaissances : 4612450</span><span class="sxs-lookup"><span data-stu-id="f0937-104">KB number: 4612450</span></span>

## <a name="symptoms"></a><span data-ttu-id="f0937-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="f0937-105">Symptoms</span></span>

<span data-ttu-id="f0937-106">Les commandes confirmées directement dérivées sont traitées par un flux de travail avec le statut *En révision*.</span><span class="sxs-lookup"><span data-stu-id="f0937-106">Directly derived firmed orders are processed by a workflow that has a status of *In-review*.</span></span>

## <a name="resolution"></a><span data-ttu-id="f0937-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="f0937-107">Resolution</span></span>

<span data-ttu-id="f0937-108">Lorsque le suivi des modifications est activé, le statut *En révision* est attribué aux commandes dérivées confirmées (commandes d'achat de sous-traitance).</span><span class="sxs-lookup"><span data-stu-id="f0937-108">When change tracking is enabled, a status of *In-review* is assigned to firmed derived orders (subcontract purchase orders).</span></span> <span data-ttu-id="f0937-109">Par conséquent, si une commande fournisseur est dérivée (une commande fournisseur de sous-traitance), elle est uniquement soumise à un workflow.</span><span class="sxs-lookup"><span data-stu-id="f0937-109">Therefore, if a purchase order is derived (a subcontract purchase order), it's only submitted to a workflow.</span></span> <span data-ttu-id="f0937-110">Si une commande d'achat est une commande d'achat planifiée confirmée, elle est automatiquement approuvée pour garantir que le moteur de planification ne crée pas de nouvelles commandes planifiées tant que la commande d'achat est toujours en cours avec le statut *Brouillon*.</span><span class="sxs-lookup"><span data-stu-id="f0937-110">If a purchase order is a firmed planned purchase order, it's automatically approved to ensure that the planning engine doesn't create new planned orders while the purchase order is still in *Draft* status.</span></span>
