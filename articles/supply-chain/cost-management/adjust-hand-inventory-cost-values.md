---
title: "Ajustement des valeurs de coût du stock disponible"
description: "Utilisez la page Ajustement du stock disponible pour ajuster le coût des quantités de stock disponible une fois qu'un processus de clôture de stock a été exécuté."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fb74ddfbc46047251a1f96512891bfbdca8e0389
ms.openlocfilehash: 2b4a27465908b5ffe19e91cb7ad0d29bce49505a
ms.contentlocale: fr-fr
ms.lasthandoff: 08/15/2017

---

# <a name="adjust-on-hand-inventory-cost-values"></a><span data-ttu-id="28e0a-103">Ajustement des valeurs de coût du stock disponible</span><span class="sxs-lookup"><span data-stu-id="28e0a-103">Adjust on-hand inventory cost values</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="28e0a-104">Utilisez la page Ajustement du stock disponible pour ajuster le coût des quantités de stock disponible une fois qu'un processus de clôture de stock a été exécuté.</span><span class="sxs-lookup"><span data-stu-id="28e0a-104">Use the Adjustment of on-hand inventory page to adjust the cost value of the on-hand inventory quantities after an inventory close process is run.</span></span>

<span data-ttu-id="28e0a-105">Vous pouvez utiliser la page **Ajustement du stock disponible** pour ajuster le coût des quantités de stock disponible une fois qu'un processus de clôture de stock a été exécuté.</span><span class="sxs-lookup"><span data-stu-id="28e0a-105">You can use the **Adjustment of on-hand inventory** page to adjust the cost value of on-hand inventory quantities after an inventory close process is run.</span></span> <span data-ttu-id="28e0a-106">**Remarque :** pour ouvrir la page **Ajustement du stock disponible**, dans la page **Clôture et ajustement**, sélectionnez l'enregistrement d'un processus de clôture de stock terminé, puis cliquez sur **Ajustement** &gt; **Disponible**.</span><span class="sxs-lookup"><span data-stu-id="28e0a-106">**Note:** To open the **Adjustment of on-hand inventory** page, on the **Closing and adjustment** page, select the record of a completed inventory close process, and then click **Adjustment** &gt; **On-hand**.</span></span> <span data-ttu-id="28e0a-107">**Exemple :** les transactions suivantes ont lieu en février :</span><span class="sxs-lookup"><span data-stu-id="28e0a-107">**Example:** You have the following transactions in February:</span></span>

-   <span data-ttu-id="28e0a-108">1er février : réception financière de stock d'une quantité de 2 au coût de 10,00 EUR ;</span><span class="sxs-lookup"><span data-stu-id="28e0a-108">February 1: An inventory financial receipt for a quantity of 2 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="28e0a-109">5 février : réception financière de stock d'une quantité de 1 au coût de 13,00 EUR ;</span><span class="sxs-lookup"><span data-stu-id="28e0a-109">February 5: An inventory financial receipt for a quantity of 1 at a cost of USD 13.00</span></span>
-   <span data-ttu-id="28e0a-110">19 février : sortie financière de stock d'une quantité de 1 au coût moyen en cours de 11,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="28e0a-110">February 19: An inventory financial issue for a quantity of 1 at a running average cost of USD 11.00</span></span>

<span data-ttu-id="28e0a-111">Cet article était paramétré avec le modèle de stock FIFO (premier entré, premier sorti) et la clôture de stock a commencé le 28 février.</span><span class="sxs-lookup"><span data-stu-id="28e0a-111">This item was set up with the first in, first out (FIFO) inventory model, and inventory close was performed as of February 28.</span></span> <span data-ttu-id="28e0a-112">La transaction de sortie financière de 11,00 EUR sera réglée avec la réception financière datée du 1er février et un ajustement de 1,00 EUR sera effectué.</span><span class="sxs-lookup"><span data-stu-id="28e0a-112">The financial issue transaction of USD 11.00 will be settled against the financial receipt that is dated February 1, and an adjustment of USD 1.00 will be made.</span></span> <span data-ttu-id="28e0a-113">Les réceptions en stock suivantes contiennent les quantités de stock en cours :</span><span class="sxs-lookup"><span data-stu-id="28e0a-113">The following inventory receipts will then contain open inventory quantities:</span></span>

-   <span data-ttu-id="28e0a-114">1 février : quantité de 1 à un coût de 10,00 EUR ;</span><span class="sxs-lookup"><span data-stu-id="28e0a-114">February 1: A quantity of 1 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="28e0a-115">5 février : quantité de 1 à un coût de 13,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="28e0a-115">February 5: A quantity of 1 at a cost of USD 13.00</span></span>

<span data-ttu-id="28e0a-116">Pour définir le coût de ces deux articles sur 15,00 EUR, utilisez l'option d'ajustement disponible et ajustez les quantités disponibles ouvertes à partir de la dernière période de clôture de stock.</span><span class="sxs-lookup"><span data-stu-id="28e0a-116">To set the cost of these two items to USD 15.00, use the on-hand adjustment option to adjust the open on-hand quantities as of the last inventory close period.</span></span> <span data-ttu-id="28e0a-117">**Remarque :** la date de validation de la transaction d'ajustement disponible sera la date de la dernière clôture de stock.</span><span class="sxs-lookup"><span data-stu-id="28e0a-117">**Note:** The posting date of the on-hand adjustment transaction will be the date of the last inventory close.</span></span> <span data-ttu-id="28e0a-118">Cette date ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="28e0a-118">This date can't be modified.</span></span>

