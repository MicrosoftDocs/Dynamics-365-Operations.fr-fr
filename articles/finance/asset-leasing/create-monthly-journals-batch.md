---
title: Créer les entrées de journal mensuelles dans un lot
description: Cette rubrique explique comment créer des écritures de journal dans un lot pour améliorer l’efficacité lors de l’enregistrement des frais de location mensuels.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ca84e56569ea5ddbb4d5335d0944a6bd8a50a1b1
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881202"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a><span data-ttu-id="86e2d-103">Créer les entrées de journal mensuelles dans un lot</span><span class="sxs-lookup"><span data-stu-id="86e2d-103">Create monthly journal entries in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="86e2d-104">Cette rubrique explique comment créer des écritures de journal dans un lot pour améliorer l’efficacité lors de l’enregistrement des frais de location mensuels.</span><span class="sxs-lookup"><span data-stu-id="86e2d-104">This topic explains how to create journal entries in a batch to help increase efficiency when monthly lease expenses are recorded.</span></span> <span data-ttu-id="86e2d-105">Le traitement par lots peut être utilisé pour créer des écritures de journal à partir de plusieurs programmes.</span><span class="sxs-lookup"><span data-stu-id="86e2d-105">Batch processing can be used to create journal entries from multiple schedules.</span></span> <span data-ttu-id="86e2d-106">Ces écritures de journal peuvent inclure les paiements de location, l’amortissement du passif, l’amortissement des actifs au titre du droit d’utilisation de l’actif et les dépenses en frais accessoires.</span><span class="sxs-lookup"><span data-stu-id="86e2d-106">These journal entries can include lease payments, liability amortization, right-of-use (ROU) asset amortization, and executory cost expenses.</span></span> <span data-ttu-id="86e2d-107">Vous pouvez également utiliser le traitement par lots pour effectuer la comptabilisation initiale de plusieurs baux en même temps ou pour créer des ajustements de transition pour plusieurs baux en même temps.</span><span class="sxs-lookup"><span data-stu-id="86e2d-107">You can also use batch processing to do the initial recognition of multiple leases at the same time, or to create transition adjustments for multiple leases at the same time.</span></span>

<span data-ttu-id="86e2d-108">Pour configurer un traitement par lots ou pour traiter les factures de paiement, l’amortissement ou les intérêts pour plusieurs baux, accédez à **Location d’actifs \> Périodique \> Création de journaux par lots**.</span><span class="sxs-lookup"><span data-stu-id="86e2d-108">To set up a batch job, or to process payment invoices, depreciation, or interest for multiple leases, go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span> <span data-ttu-id="86e2d-109">Dans la boîte de dialogue qui apparaît, vous pouvez sélectionner le calendrier à partir duquel les écritures de journal doivent être créées.</span><span class="sxs-lookup"><span data-stu-id="86e2d-109">In the dialog box that appears, you can select the schedule that the journal entries should be created from.</span></span> <span data-ttu-id="86e2d-110">Vous pouvez également spécifier si le traitement par lots doit être exécuté pour des entités, des groupes de baux ou des registres de baux spécifiques.</span><span class="sxs-lookup"><span data-stu-id="86e2d-110">You can also specify whether the batch process should be run for specific entities, lease groups, or lease books.</span></span>

> [!NOTE]
> <span data-ttu-id="86e2d-111">Les transactions ultérieures, telles que les calendriers d’amortissement du passif, les paiements, l’amortissement et les dépenses, ne seront comptabilisées qu’après la comptabilisation initiale des baux correspondants.</span><span class="sxs-lookup"><span data-stu-id="86e2d-111">Subsequent transactions, such as liability amortization schedules, payments, depreciation, and expenses, will be posted only after the initial recognition for corresponding leases is posted.</span></span>
>
> <span data-ttu-id="86e2d-112">Les écritures de journal sont créées, mais elles ne sont validées que lorsque vous sélectionnez la commande **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="86e2d-112">The journal entries are created, but they won't be posted until you select the **Run** command.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
