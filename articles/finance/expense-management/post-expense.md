---
title: Valider un état de dépenses
description: Cette rubrique explique comment valider un état de dépenses dans la comptabilité.
author: saraschi2
manager: AnnBe
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPerDiems
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d008ef8dd55550431fbb9e329cd7d9428a08831
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177715"
---
# <a name="post-an-expense-report"></a><span data-ttu-id="65250-103">Valider un état de dépenses</span><span class="sxs-lookup"><span data-stu-id="65250-103">Post an expense report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="65250-104">Après son approbation et son transfert dans le journal des opérations diverses, un état de dépenses peut être validé dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="65250-104">After an expense report has been approved and transferred to the general journal, it can be posted to the general ledger.</span></span> <span data-ttu-id="65250-105">Lorsque vous validez un état des dépenses, les dépenses admissibles pour la récupération de la taxe sur la valeur ajoutée (TVA) sont identifiées.</span><span class="sxs-lookup"><span data-stu-id="65250-105">When you post an expense report, expenses that are eligible for recovery of value-added tax (VAT) are identified.</span></span> <span data-ttu-id="65250-106">La tâche de vérification et de récupération des paiements de TVA est affectée à l'employé responsable de la vérification de l'état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="65250-106">The task of verifying and recovering VAT payments is assigned to the employee who is responsible for verifying the expense report.</span></span>

<span data-ttu-id="65250-107">Si les dépenses figurant sur un état de dépenses sont facturées à une société autre que celle qui emploie le collaborateur, vous devez vérifier la société pour laquelle les dépenses sont dues et la société qui les doit.</span><span class="sxs-lookup"><span data-stu-id="65250-107">If expenses on an expense report are charged to a company other than the company that employs the employee, you must verify the company that those expenses are owed to and the company that the expenses are owed from.</span></span> <span data-ttu-id="65250-108">Par exemple, l'employé qui a envoyé un état de dépenses travaille pour la société DAT mais a facturé une dépense à la société DIR.</span><span class="sxs-lookup"><span data-stu-id="65250-108">For example, the employee who submitted an expense report works for the DAT company but charged an expense to the DIR company.</span></span> <span data-ttu-id="65250-109">Dans ce cas, DAT est la société à laquelle la dépense est due, et DIR est la société qui doit la dépense.</span><span class="sxs-lookup"><span data-stu-id="65250-109">In this case, DAT is the company that the expense is owed to, and DIR is the company that the expense is owed from.</span></span> <span data-ttu-id="65250-110">Une fois ces lignes de journal vérifiées, vous pouvez valider les lignes de dépense dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="65250-110">After you verify these journal lines, you can post the expense lines to the general ledger.</span></span>

<span data-ttu-id="65250-111">Pour valider un état de dépenses, sur la page **États de dépenses approuvés**, sélectionnez l'état de dépenses, puis, dans le volet Actions, sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="65250-111">To post an expense report, on the **Approved expense reports** page, select the expense report, and then, on the Action Pane, select **Post**.</span></span>

<span data-ttu-id="65250-112">Vous pouvez également valider tous les états de dépenses dans la liste simultanément.</span><span class="sxs-lookup"><span data-stu-id="65250-112">You can also post all the expense reports in the list at the same time.</span></span> <span data-ttu-id="65250-113">Sélectionnez tous les états de dépenses, puis **Valider**.</span><span class="sxs-lookup"><span data-stu-id="65250-113">Select all the expense reports, and then select **Post**.</span></span>
