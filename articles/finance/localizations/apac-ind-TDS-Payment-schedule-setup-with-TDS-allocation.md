---
title: Définir des échéanciers de paiement avec une répartition TDS
description: Cette rubrique explique comment configurer des échéanciers de paiement avec allocation de la Taxe déduite à la source (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 47551f52f35fec5ae49d696e3f4027b7d2eb2e19
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023246"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a><span data-ttu-id="b64d6-103">Définir des échéanciers de paiement avec une répartition TDS</span><span class="sxs-lookup"><span data-stu-id="b64d6-103">Set up payment schedules with TDS allocation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b64d6-104">Cette rubrique explique comment configurer des échéanciers de paiement avec allocation de la Taxe déduite à la source (TDS).</span><span class="sxs-lookup"><span data-stu-id="b64d6-104">This topic explains how to set up payment schedules with Tax Deducted at Source (TDS) allocation.</span></span>

1. <span data-ttu-id="b64d6-105">Accédez à **Comptabilité fournisseur \> Paramétrage des paiements \> Échéanciers de paiement**.</span><span class="sxs-lookup"><span data-stu-id="b64d6-105">Go to **Accounts payable \> Payment setup \> Payment schedules**.</span></span>

    <span data-ttu-id="b64d6-106">[![Page Échéanciers de paiement](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span><span class="sxs-lookup"><span data-stu-id="b64d6-106">[![Payment schedules page](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span></span>

2. <span data-ttu-id="b64d6-107">Dans le volet Actions, sélectionnez **Nouveau** pour créer un échéancier de paiement, puis entrez les détails requis.</span><span class="sxs-lookup"><span data-stu-id="b64d6-107">On the Action Pane, select **New** to create a payment schedule, and enter the required details.</span></span>
3. <span data-ttu-id="b64d6-108">Dans le champ **Allocation**, sélectionnez la méthode à utiliser pour allouer le paiement pour l'échéancier de paiement :</span><span class="sxs-lookup"><span data-stu-id="b64d6-108">In the **Allocation** field, select the method to use to allocate the payment for the payment schedule:</span></span>

    - <span data-ttu-id="b64d6-109">Total</span><span class="sxs-lookup"><span data-stu-id="b64d6-109">Total</span></span>
    - <span data-ttu-id="b64d6-110">Montant fixe</span><span class="sxs-lookup"><span data-stu-id="b64d6-110">Fixed amount</span></span>
    - <span data-ttu-id="b64d6-111">Nombre fixe</span><span class="sxs-lookup"><span data-stu-id="b64d6-111">Fixed quantity</span></span>
    - <span data-ttu-id="b64d6-112">Spécifié</span><span class="sxs-lookup"><span data-stu-id="b64d6-112">Specified</span></span>

    <span data-ttu-id="b64d6-113">Le champ **Attribution de la retenue à la source** indique la méthode d'allocation TDS pour l'échéancier de paiement.</span><span class="sxs-lookup"><span data-stu-id="b64d6-113">The **Withholding tax allocation** field shows the TDS allocation method for the payment schedule.</span></span> <span data-ttu-id="b64d6-114">Si vous sélectionnez **Total** dans le champ **Attribution**, le champ **Attribution de la retenue à la source** est automatiquement défini sur **Total**.</span><span class="sxs-lookup"><span data-stu-id="b64d6-114">If you select **Total** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Total**.</span></span> <span data-ttu-id="b64d6-115">Si vous sélectionnez **Montant fixe**, **Quantité fixe** ou **Spécifié** dans le champ **Attribution**, le champ **Attribution de la retenue à la source** est automatiquement défini sur **Proportionnellement**.</span><span class="sxs-lookup"><span data-stu-id="b64d6-115">If you select **Fixed amount**, **Fixed quantity**, or **Specified** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Proportionally**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b64d6-116">Si le champ **Attribution de la retenue à la source** est défini sur **Total**, les acomptes sont calculés sur la base du montant brut, qui comprend le montant TDS.</span><span class="sxs-lookup"><span data-stu-id="b64d6-116">If the **Withholding tax allocation** field is set to **Total**, the payment installments are calculated based on the gross amount, which includes the TDS amount.</span></span> <span data-ttu-id="b64d6-117">Si le champ **Attribution de la retenue à la source** est défini sur **Proportionnellement**, les acomptes sont calculés sur la base du montant net de la facture après déduction du montant TDS.</span><span class="sxs-lookup"><span data-stu-id="b64d6-117">If the **Withholding tax allocation** field is set to **Proportionally**, the payment installments are calculated based on the net invoice amount after the TDS amount is deducted.</span></span>

4. <span data-ttu-id="b64d6-118">Entrez les autres informations demandées, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b64d6-118">Enter the other required details, and then close the page.</span></span>
