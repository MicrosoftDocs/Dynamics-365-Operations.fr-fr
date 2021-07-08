---
title: Le numéro de formule sélectionné n’est pas approuvé pour un lot de commandes
description: Lorsque vous essayez de confirmer une commande planifiée, vous recevez un message d’erreur indiquant que le numéro de formule sélectionné n’est pas approuvé pour un lot de commandes.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4f993c92ca0a2f8f79e4b0e0eda43904529163f8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294070"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a><span data-ttu-id="c4c80-103">Le numéro de formule sélectionné n’est pas approuvé pour un lot de commandes</span><span class="sxs-lookup"><span data-stu-id="c4c80-103">Selected formula number isn't approved for a batch order</span></span>

<span data-ttu-id="c4c80-104">Code d’erreur : PRO2614</span><span class="sxs-lookup"><span data-stu-id="c4c80-104">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="c4c80-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="c4c80-105">Symptoms</span></span>

<span data-ttu-id="c4c80-106">Lorsque vous essayez de confirmer une commande planifiée, vous recevez le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="c4c80-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="c4c80-107">Le numéro de formule sélectionné n’est pas approuvé pour un lot de production.</span><span class="sxs-lookup"><span data-stu-id="c4c80-107">The selected formula number is not approved for a batch order.</span></span>

## <a name="cause"></a><span data-ttu-id="c4c80-108">Cause</span><span class="sxs-lookup"><span data-stu-id="c4c80-108">Cause</span></span>

<span data-ttu-id="c4c80-109">Le système valide l’opération de confirmation pour s’assurer qu’une formule approuvée est disponible pour l’article actif.</span><span class="sxs-lookup"><span data-stu-id="c4c80-109">The system validates the firming operation to make sure that an approved formula is available for the active item.</span></span> <span data-ttu-id="c4c80-110">Vous devez probablement approuver la formule.</span><span class="sxs-lookup"><span data-stu-id="c4c80-110">You must probably approve the formula.</span></span>

## <a name="resolution"></a><span data-ttu-id="c4c80-111">Résolution</span><span class="sxs-lookup"><span data-stu-id="c4c80-111">Resolution</span></span>

<span data-ttu-id="c4c80-112">Pour approuver une formule, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c4c80-112">To approve a formula, follow these steps.</span></span>

1. <span data-ttu-id="c4c80-113">Accédez à **Gestion des informations sur les produits \> Nomenclatures et formules \> Formules**.</span><span class="sxs-lookup"><span data-stu-id="c4c80-113">Go to **Product information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="c4c80-114">Sélectionnez la formule appropriée.</span><span class="sxs-lookup"><span data-stu-id="c4c80-114">Select the relevant formula.</span></span>
1. <span data-ttu-id="c4c80-115">Dans le volet Actions, sous l’onglet **Formule**, dans le groupe **Tenir à jour**, sélectionnez **Approuver la formule**.</span><span class="sxs-lookup"><span data-stu-id="c4c80-115">On the Action Pane, on the **Formula** tab, in the **Maintain** group, select **Approve formula**.</span></span>
1. <span data-ttu-id="c4c80-116">Dans la boîte de dialogue **Approuver une nomenclature ou une formule**, sélectionnez un approbateur, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4c80-116">In the **Approve BOM or formula** dialog box, select an approver, and then select **OK**.</span></span>
