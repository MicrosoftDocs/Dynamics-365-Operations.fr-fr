---
title: La planification génère des commandes planifiées pour les produits fantômes
description: Les commandes planifiées sont générées pour les produits fantômes après l'exécution de la planification principale.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026514"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a><span data-ttu-id="5cbca-103">La planification génère des commandes planifiées pour les produits fantômes</span><span class="sxs-lookup"><span data-stu-id="5cbca-103">Master planning generates planned orders for phantom products</span></span>

<span data-ttu-id="5cbca-104">Numéro de la base de connaissances : 4614729</span><span class="sxs-lookup"><span data-stu-id="5cbca-104">KB number: 4614729</span></span>

## <a name="symptoms"></a><span data-ttu-id="5cbca-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="5cbca-105">Symptoms</span></span>

<span data-ttu-id="5cbca-106">Les commandes planifiées sont générées pour les produits fantômes après l'exécution de la planification principale.</span><span class="sxs-lookup"><span data-stu-id="5cbca-106">Planned orders are generated for phantom products after master planning is run.</span></span>

## <a name="resolution"></a><span data-ttu-id="5cbca-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="5cbca-107">Resolution</span></span>

<span data-ttu-id="5cbca-108">Le cadre de l'option **Fantôme** pour les produits lancés détermine le type de ligne par défaut sur la nomenclature (BOM).</span><span class="sxs-lookup"><span data-stu-id="5cbca-108">The setting of the **Phantom** option for released products determines the default line type on the bill of material (BOM).</span></span> <span data-ttu-id="5cbca-109">Quand l'option **Fantôme** est définie sur *Oui*, le système créera toujours des ordres planifiés pour l'article, mais l'option **Exigence dérivée directement** pour chaque ordre planifié sera définie sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="5cbca-109">When the **Phantom** option is set to *Yes*, the system will still create planned orders for the item, but the **Directly derived requirement** option for each planned order will be set to *Yes*.</span></span> <span data-ttu-id="5cbca-110">Par conséquent, l'ordre de fabrication planifié ne peut pas être confirmé seul.</span><span class="sxs-lookup"><span data-stu-id="5cbca-110">Therefore, the planned production order can't be firmed on its own.</span></span> <span data-ttu-id="5cbca-111">Au lieu de cela, il sera toujours automatiquement inclus lorsque l'ordre de fabrication parent est confirmé.</span><span class="sxs-lookup"><span data-stu-id="5cbca-111">Instead, it will always be automatically included when the parent production order is firmed.</span></span> <span data-ttu-id="5cbca-112">En outre, les lignes de nomenclature de l'ordre fantôme planifié seront incluses dans la nomenclature de l'ordre de fabrication parent.</span><span class="sxs-lookup"><span data-stu-id="5cbca-112">Additionally, the BOM lines of the planned phantom order will be included in the BOM of the parent production order.</span></span>
