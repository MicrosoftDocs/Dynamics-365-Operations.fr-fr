---
title: Les bons de commande reçus physiquement n'apparaissent pas dans le rapport de clôture des stocks
description: Les bons de commande reçus physiquement n'apparaissent pas dans le rapport de clôture des stocks Vérifier les quantités en cours.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventOpenQtyCritical
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 9508d6d75d8ebee7ca10140ed4c4215d7ad1dda7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026507"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a><span data-ttu-id="c309d-103">Les bons de commande reçus physiquement n'apparaissent pas dans le rapport de clôture des stocks</span><span class="sxs-lookup"><span data-stu-id="c309d-103">Physically received purchase orders don't appear on the inventory closing report</span></span>

<span data-ttu-id="c309d-104">Numéro de la base de connaissances : 4612595</span><span class="sxs-lookup"><span data-stu-id="c309d-104">KB number: 4612595</span></span>

## <a name="symptoms"></a><span data-ttu-id="c309d-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="c309d-105">Symptoms</span></span>

<span data-ttu-id="c309d-106">Les bons de commande reçus physiquement n'apparaissent pas dans le rapport de clôture des stocks **Vérifier les quantités en cours**.</span><span class="sxs-lookup"><span data-stu-id="c309d-106">Physically received purchase orders don't appear on the **Check open quantities** inventory closing report.</span></span>

## <a name="resolution"></a><span data-ttu-id="c309d-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="c309d-107">Resolution</span></span>

<span data-ttu-id="c309d-108">Le rapport **Vérifier les quantités en cours** affiche les mouvements de sortie qui ne peuvent pas être réglés par rapport aux réceptions de stock mises à jour financièrement à la date de clôture sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c309d-108">The **Check open quantities** report shows issue transactions that can't be settled against financially updated inventory receipts as of the selected closing date.</span></span> <span data-ttu-id="c309d-109">Vous pouvez choisir d'inclure les reçus physiques dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="c309d-109">You can choose to include physical receipts on the report.</span></span> <span data-ttu-id="c309d-110">Dans ce cas, les reçus physiques seront affichés s'ils peuvent couvrir les transactions d'émission qui ne peuvent pas être réglées.</span><span class="sxs-lookup"><span data-stu-id="c309d-110">In that case, physical receipts will be shown if they can cover the issue transactions that can't be settled.</span></span> <span data-ttu-id="c309d-111">=Pour plus d’informations, voir [Préparation de l'exécution de la clôture de stock](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).</span><span class="sxs-lookup"><span data-stu-id="c309d-111">For more information, see [Preparing to run inventory close](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).</span></span>
