---
title: Reclasser la partie à court terme d’un passif locatif
description: Cette rubrique explique comment créer une entrée de journal mensuelle pour reclasser une partie du passif locatif comme à court terme.
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
ms.openlocfilehash: ae5aebab507479775626579e8b08d68001326a06
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881564"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a><span data-ttu-id="f002a-103">Reclasser la partie à court terme du passif locatif</span><span class="sxs-lookup"><span data-stu-id="f002a-103">Reclassify the short-term portion of lease liability</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f002a-104">Cette rubrique explique comment créer une entrée de journal mensuelle pour reclasser une partie du passif locatif comme à court terme.</span><span class="sxs-lookup"><span data-stu-id="f002a-104">This topic explains how to create a monthly journal entry to reclassify a portion of the lease liability as short-term.</span></span> <span data-ttu-id="f002a-105">Lorsque la planification sélectionnée dans le traitement par lots est **Reclassement du passif locatif à court terme**, une entrée de journal est créée.</span><span class="sxs-lookup"><span data-stu-id="f002a-105">When the schedule that is selected in the batch process is **Short-term lease liability reclass**, a journal entry is created.</span></span> <span data-ttu-id="f002a-106">Cette entrée est utilisée pour enregistrer la partie courante du passif locatif le dernier jour du mois.</span><span class="sxs-lookup"><span data-stu-id="f002a-106">This entry is used to post the current portion of the lease liability on the last day of the month.</span></span> <span data-ttu-id="f002a-107">Dans le même temps, une écriture de contrepassation est validée à partir du premier jour du mois suivant.</span><span class="sxs-lookup"><span data-stu-id="f002a-107">At the same time, a reversal entry is posted as of the first day of the next month.</span></span>

<span data-ttu-id="f002a-108">La partie à court terme du passif locatif est présentée dans le tableau d’amortissement du passif.</span><span class="sxs-lookup"><span data-stu-id="f002a-108">The short-term portion of the lease liability is shown on the liability amortization schedule.</span></span> <span data-ttu-id="f002a-109">Lorsque l’entrée de journal est validée, la colonne **Journal de reclassement du passif créé** devient disponible et l’ID du journal est également renseignée dans le programme.</span><span class="sxs-lookup"><span data-stu-id="f002a-109">When the journal entry is posted, the **Liability reclass journal created** column becomes available, and the journal ID is also filled in on the schedule.</span></span>

<span data-ttu-id="f002a-110">Pour créer et valider l’entrée de journal de reclassement de passif à court terme, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f002a-110">To create and post the short-term liability reclassification journal entry, follow these steps.</span></span>

1. <span data-ttu-id="f002a-111">Aller à **Location d’actifs \> Périodique \> Création de journal par lot**.</span><span class="sxs-lookup"><span data-stu-id="f002a-111">Go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span>
2. <span data-ttu-id="f002a-112">Dans la boîte de dialogue **Création de journaux par lots**, dans le champ **Sélectionner un échéancier**, sélectionnez **Reclassement du passif locatif à court terme**.</span><span class="sxs-lookup"><span data-stu-id="f002a-112">In the **Batch journal creation** dialog box, in the **Select schedule** field, select **Short-term lease liability reclass**.</span></span>
3. <span data-ttu-id="f002a-113">Dans le champ **Groupe de location**, sélectionnez un groupe de locations.</span><span class="sxs-lookup"><span data-stu-id="f002a-113">In the **Lease group** field, select a lease group.</span></span> <span data-ttu-id="f002a-114">Alternativement, dans le champ **ID du registre**, sélectionnez l’ID du registre.</span><span class="sxs-lookup"><span data-stu-id="f002a-114">Alternatively, in the **Book ID** field, select the book ID.</span></span>
4. <span data-ttu-id="f002a-115">Activez le paramètre **valider**.</span><span class="sxs-lookup"><span data-stu-id="f002a-115">Turn on the **Post** parameter.</span></span> <span data-ttu-id="f002a-116">Sinon, si l’écriture doit être créée mais pas publiée, laissez ce paramètre désactivé.</span><span class="sxs-lookup"><span data-stu-id="f002a-116">Alternatively, if the entry should be created but not posted, leave this parameter turned off.</span></span>
5. <span data-ttu-id="f002a-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f002a-117">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
