---
title: Plusieurs transactions de stock pour les numéros de lot lorsque la mise à jour physique est désactivée
description: Plusieurs transactions de stock sont créées après avoir ajusté une ligne de commande d'achat pour les articles pour lesquels l'option Sur mise à jour physique du groupe de numéros de lot est définie sur Non.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventNumGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1fa54cdfdbc5608fb6c7114dced0f96bab47253e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026521"
---
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a><span data-ttu-id="27ce9-103">Plusieurs transactions de stock pour les numéros de lot lorsque la mise à jour physique est désactivée</span><span class="sxs-lookup"><span data-stu-id="27ce9-103">Multiple inventory transactions for batch numbers when On physical update is disabled</span></span>

<span data-ttu-id="27ce9-104">Numéro de la base de connaissances : 4613390</span><span class="sxs-lookup"><span data-stu-id="27ce9-104">KB number: 4613390</span></span>

## <a name="symptoms"></a><span data-ttu-id="27ce9-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="27ce9-105">Symptoms</span></span>

<span data-ttu-id="27ce9-106">Plusieurs transactions de stock sont créées après avoir ajusté une ligne de commande d'achat pour les articles pour lesquels l'option **Sur mise à jour physique** du groupe de numéros de lot est définie sur *Non*.</span><span class="sxs-lookup"><span data-stu-id="27ce9-106">Multiple inventory transactions are created after you adjust a purchase order line for items where the **On physical update** option of the batch number group is set to *No*.</span></span>

<span data-ttu-id="27ce9-107">Lorsque vous créez un élément où l'option **Sur mise à jour physique** du groupe de numéros de lot est définie sur *Non*, le système crée automatiquement un nouveau numéro de lot si vous modifiez une quantité de ligne d'achat et enregistrez la page de commande d'achat.</span><span class="sxs-lookup"><span data-stu-id="27ce9-107">When you create an item where the **On physical update** option of the batch number group is set to *No*, the system automatically creates a new batch number if you modify a purchase line quantity and save the purchase order page.</span></span>

## <a name="resolution"></a><span data-ttu-id="27ce9-108">Résolution</span><span class="sxs-lookup"><span data-stu-id="27ce9-108">Resolution</span></span>

<span data-ttu-id="27ce9-109">Le paramètre **Sur mise à jour physique** des groupes de numéros de lot fonctionne de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="27ce9-109">The **On physical update** setting for batch number groups works in the following way:</span></span>

- <span data-ttu-id="27ce9-110">Lorsque l'option est définie sur *Oui*, les nouveaux numéros de lot ne sont créés qu'après une mise à jour physique (par exemple, lorsque les articles sont expédiés ou reçus).</span><span class="sxs-lookup"><span data-stu-id="27ce9-110">When the option is set to *Yes*, new batch numbers are created only after a physical update (for example, when items are shipped or received).</span></span>
- <span data-ttu-id="27ce9-111">Lorsque l'option est définie sur *Non*, un nouveau numéro de lot est créé chaque fois qu'une mise à jour applicable se produit (par exemple, lorsqu'une nouvelle quantité est ajoutée à une commande fournisseur).</span><span class="sxs-lookup"><span data-stu-id="27ce9-111">When the option is set to *No*, a new batch number is created every time that an applicable update occurs (for example, when a new quantity is added to a purchase order).</span></span>
