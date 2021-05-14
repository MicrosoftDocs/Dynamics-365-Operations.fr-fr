---
title: Le justificatif n'est pas généré
description: Cette rubrique fournit des informations de dépannage qui peuvent vous aider lorsqu'un justificatif doit être généré mais ne l'est pas.
author: qire
manager: beya
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: eafc9110ec58be5083569188d59b67a62e86c85d
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947640"
---
# <a name="voucher-isnt-generated"></a><span data-ttu-id="50604-103">Le justificatif n'est pas généré</span><span class="sxs-lookup"><span data-stu-id="50604-103">Voucher isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="50604-104">Si un justificatif doit être généré, mais que la page **Justificatif de transaction** n'affiche rien, suivez les étapes des sections suivantes pour résoudre ce problème.</span><span class="sxs-lookup"><span data-stu-id="50604-104">If a voucher should be generated, but the **Voucher transactions** page doesn't show any vouchers, follow the steps in the following sections as required to troubleshoot this issue.</span></span>

<span data-ttu-id="50604-105">[![Page Justificatif de transaction sans justificatif](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="50604-105">[![Voucher transactions page that has no vouchers](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span></span>

## <a name="check-the-tax-applicability"></a><span data-ttu-id="50604-106">Vérifier l'applicabilité de la taxe</span><span class="sxs-lookup"><span data-stu-id="50604-106">Check the tax applicability</span></span>

1. <span data-ttu-id="50604-107">Accédez à **Taxe** \> **Tâches périodiques** \> **Écritures de journal de comptabilité auxiliaire non encore transférées**.</span><span class="sxs-lookup"><span data-stu-id="50604-107">Go to **Tax** \> **Periodic tasks** \> **Subledger journal entries not yet transferred**.</span></span>
2. <span data-ttu-id="50604-108">S'il existe un enregistrement de journal, sélectionnez-le, puis sélectionnez **Transférer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="50604-108">If there is a journal record, select it, and then select **Transfer now**.</span></span>

    <span data-ttu-id="50604-109">[![Bouton Transférer maintenant sur la page Écritures de journal de comptabilité auxiliaire non encore transférées](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="50604-109">[![Transfer now button on the Subledger journal entries not yet transferred page](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span></span>

3. <span data-ttu-id="50604-110">Ouvrez la page **Justificatif de transaction** à nouveau pour voir si le justificatif a été généré.</span><span class="sxs-lookup"><span data-stu-id="50604-110">Open the **Voucher transactions** page again to see whether the voucher was generated.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="50604-111">Déterminer si la personnalisation existe</span><span class="sxs-lookup"><span data-stu-id="50604-111">Determine whether customization exists</span></span>

<span data-ttu-id="50604-112">Si vous avez terminé les étapes de la section précédente mais que vous n'avez trouvé aucun problème, déterminez s'il existe une personnalisation.</span><span class="sxs-lookup"><span data-stu-id="50604-112">If you've completed the steps in the previous section but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="50604-113">Si aucune personnalisation n'existe, créez une demande de service Microsoft pour une assistance supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="50604-113">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
