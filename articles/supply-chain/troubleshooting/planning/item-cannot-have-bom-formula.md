---
title: L’article ne peut pas avoir de nomenclature ou de formule
description: Lorsque vous essayez de confirmer une commande, vous recevez un message d’erreur lors de la validation de l’article. Il indique que l’article ne peut pas avoir de nomenclature ou de formule.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6739b8b1e4d080055a2a0501427eac1c2e8a96c5
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294074"
---
# <a name="item-cant-have-a-bom-or-formula"></a><span data-ttu-id="32e7d-104">L’article ne peut pas avoir de nomenclature ou de formule</span><span class="sxs-lookup"><span data-stu-id="32e7d-104">Item can't have a BOM or formula</span></span>

<span data-ttu-id="32e7d-105">Code d’erreur : PRO2614</span><span class="sxs-lookup"><span data-stu-id="32e7d-105">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="32e7d-106">Symptômes</span><span class="sxs-lookup"><span data-stu-id="32e7d-106">Symptoms</span></span>

<span data-ttu-id="32e7d-107">Lorsque vous essayez de confirmer une commande, vous recevez le message d’erreur suivant lors de la validation de l’article :</span><span class="sxs-lookup"><span data-stu-id="32e7d-107">When you try to firm an order, you receive the following error message during item validation:</span></span>

> <span data-ttu-id="32e7d-108">L’article ne peut pas avoir de nomenclature ou de formule</span><span class="sxs-lookup"><span data-stu-id="32e7d-108">Item cannot have a BOM or formula</span></span>

## <a name="resolution"></a><span data-ttu-id="32e7d-109">Résolution</span><span class="sxs-lookup"><span data-stu-id="32e7d-109">Resolution</span></span>

<span data-ttu-id="32e7d-110">Les articles qui ont une nomenclature ou une formule doivent être du type *Élément de planification*, *Nomenclature* ou *Formule*.</span><span class="sxs-lookup"><span data-stu-id="32e7d-110">Items that have a bill of materials (BOM) or formula must be of the *Planning item*, *BOM*, or *formula* type.</span></span> <span data-ttu-id="32e7d-111">Pour modifier le type d’un article, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="32e7d-111">To change the type of an item, follow these steps.</span></span>

1. <span data-ttu-id="32e7d-112">Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="32e7d-112">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="32e7d-113">Ouvrez le produit concerné.</span><span class="sxs-lookup"><span data-stu-id="32e7d-113">Open the relevant product.</span></span>
1. <span data-ttu-id="32e7d-114">Dans le raccourci **Ingénieur**, définissez le champ **Type de production** sur *Élément de planification*, *Nomenclature* ou *Formule*.</span><span class="sxs-lookup"><span data-stu-id="32e7d-114">On the **Engineer** FastTab, set the **Production type** field to *Planning item*, *BOM*, or *formula*.</span></span>
