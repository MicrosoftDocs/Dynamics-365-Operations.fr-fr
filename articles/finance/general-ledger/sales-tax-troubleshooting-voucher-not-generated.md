---
title: Le justificatif n'est pas généré
description: Cette rubrique fournit des informations de dépannage qui peuvent vous aider lorsqu'un justificatif doit être généré mais ne l'est pas.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: ba23b597b1d7d283b99638fb7d5d91da00afb09c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018755"
---
# <a name="voucher-isnt-generated"></a><span data-ttu-id="402d8-103">Le justificatif n'est pas généré</span><span class="sxs-lookup"><span data-stu-id="402d8-103">Voucher isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="402d8-104">Si un justificatif doit être généré, mais que la page **Justificatif de transaction** n'affiche rien, suivez les étapes des sections suivantes pour résoudre ce problème.</span><span class="sxs-lookup"><span data-stu-id="402d8-104">If a voucher should be generated, but the **Voucher transactions** page doesn't show any vouchers, follow the steps in the following sections as required to troubleshoot this issue.</span></span>

<span data-ttu-id="402d8-105">[![Page Justificatif de transaction sans justificatif](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="402d8-105">[![Voucher transactions page that has no vouchers](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span></span>

## <a name="check-the-tax-applicability"></a><span data-ttu-id="402d8-106">Vérifier l'applicabilité de la taxe</span><span class="sxs-lookup"><span data-stu-id="402d8-106">Check the tax applicability</span></span>

1. <span data-ttu-id="402d8-107">Accédez à **Taxe** \> **Tâches périodiques** \> **Écritures de journal de comptabilité auxiliaire non encore transférées**.</span><span class="sxs-lookup"><span data-stu-id="402d8-107">Go to **Tax** \> **Periodic tasks** \> **Subledger journal entries not yet transferred**.</span></span>
2. <span data-ttu-id="402d8-108">S'il existe un enregistrement de journal, sélectionnez-le, puis sélectionnez **Transférer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="402d8-108">If there is a journal record, select it, and then select **Transfer now**.</span></span>

    <span data-ttu-id="402d8-109">[![Bouton Transférer maintenant sur la page Écritures de journal de comptabilité auxiliaire non encore transférées](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="402d8-109">[![Transfer now button on the Subledger journal entries not yet transferred page](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span></span>

3. <span data-ttu-id="402d8-110">Ouvrez la page **Justificatif de transaction** à nouveau pour voir si le justificatif a été généré.</span><span class="sxs-lookup"><span data-stu-id="402d8-110">Open the **Voucher transactions** page again to see whether the voucher was generated.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="402d8-111">Déterminer si la personnalisation existe</span><span class="sxs-lookup"><span data-stu-id="402d8-111">Determine whether customization exists</span></span>

<span data-ttu-id="402d8-112">Si vous avez terminé les étapes de la section précédente mais que vous n'avez trouvé aucun problème, déterminez s'il existe une personnalisation.</span><span class="sxs-lookup"><span data-stu-id="402d8-112">If you've completed the steps in the previous section but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="402d8-113">Si aucune personnalisation n'existe, créez une demande de service Microsoft pour une assistance supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="402d8-113">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
