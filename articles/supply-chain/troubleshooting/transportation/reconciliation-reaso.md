---
title: Vous ne pouvez ajouter que le compte principal comme compte de crédit pour des raisons de rapprochement
description: Lorsque vous configurez un motif de rapprochement dans la gestion des transports, vous ne pouvez ajouter que le compte principal comme compte de crédit.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 708081370b27fd51ef9a2329d8392f4515353dcb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026493"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a><span data-ttu-id="f7e25-103">Vous ne pouvez ajouter que le compte principal comme compte de crédit pour des raisons de rapprochement</span><span class="sxs-lookup"><span data-stu-id="f7e25-103">You can add only the main account as the credit account for reconciliation reasons</span></span>

<span data-ttu-id="f7e25-104">Numéro de la base de connaissances : 4603538</span><span class="sxs-lookup"><span data-stu-id="f7e25-104">KB number: 4603538</span></span>

## <a name="symptoms"></a><span data-ttu-id="f7e25-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="f7e25-105">Symptoms</span></span>

<span data-ttu-id="f7e25-106">Lorsque vous configurez un motif de rapprochement dans la gestion des transports, vous ne pouvez ajouter que le compte principal comme compte de crédit.</span><span class="sxs-lookup"><span data-stu-id="f7e25-106">When you set up a reconciliation reason in Transportation management, you can add only the main account as the credit account.</span></span> <span data-ttu-id="f7e25-107">Vous ne pouvez pas ajouter de centre de coûts ou toute autre dimension comme compte de crédit.</span><span class="sxs-lookup"><span data-stu-id="f7e25-107">You can't add a cost center or any other dimension as the credit account.</span></span> <span data-ttu-id="f7e25-108">Cependant, le compte de débit vous permet de sélectionner d'autres dimensions.</span><span class="sxs-lookup"><span data-stu-id="f7e25-108">However, the debit account lets you select other dimensions.</span></span>

## <a name="resolution"></a><span data-ttu-id="f7e25-109">Résolution</span><span class="sxs-lookup"><span data-stu-id="f7e25-109">Resolution</span></span>

<span data-ttu-id="f7e25-110">Si le rapprochement n'est pas effectué pour payer le fournisseur mais pour créditer un compte principal spécifique, le système ne vous permet pas de sélectionner une dimension financière pour le compte de crédit lorsque vous configurez le motif de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="f7e25-110">If the reconciliation isn't done to pay the vendor but to credit a specific main account, the system doesn't allow you to select a financial dimension for the credit account when you set up the reconciliation reason.</span></span>

<span data-ttu-id="f7e25-111">Si la structure du compte nécessite une valeur de dimension financière spécifique pour le compte principal de crédit, le journal fournisseur résultant ne peut pas être validé automatiquement, car la valeur de dimension financière est manquante.</span><span class="sxs-lookup"><span data-stu-id="f7e25-111">If the account structure requires a specific financial dimension value for the credit main account, the resulting vendor journal can't be posted automatically, because the financial dimension value is missing.</span></span> <span data-ttu-id="f7e25-112">Par conséquent, vous devez d'abord spécifier manuellement le compte de crédit en utilisant la page **Journal des factures**.</span><span class="sxs-lookup"><span data-stu-id="f7e25-112">Therefore, you must first manually specify the credit account by using the **Invoice journal** page.</span></span>

<span data-ttu-id="f7e25-113">Étant donné qu'une valeur de dimension est requise pour le compte de crédit, le journal des factures fournisseur ne peut pas être automatiquement imputé.</span><span class="sxs-lookup"><span data-stu-id="f7e25-113">Because a dimension value is required for the credit account, the vendor invoice journal can't be automatically posted.</span></span> <span data-ttu-id="f7e25-114">Vous devez le valider manuellement après avoir ajouté manuellement la valeur de dimension au compte principal pour la limite de crédit.</span><span class="sxs-lookup"><span data-stu-id="f7e25-114">You must manually post it after you manually add the dimension value to the main account for the credit line.</span></span>
