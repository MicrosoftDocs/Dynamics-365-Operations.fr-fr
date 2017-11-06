---
title: "Définir les stratégies de dépenses"
description: "Vous pouvez définir des stratégies de dépenses que vos employés doivent suivre lorsqu'ils saisissent et soumettent des états de dépenses et des demandes de voyage dans Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: saraschi2
manager: AnnBe
ms.date: 09/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 9a5ce1a3b6519b510c9f5aa5618ab91f77a2d91a
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="expense-policies"></a><span data-ttu-id="7f1ac-103">Stratégies des dépenses</span><span class="sxs-lookup"><span data-stu-id="7f1ac-103">Expense policies</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7f1ac-104">Vous pouvez définir des stratégies ou règles que vos collaborateurs sont tenus de suivre lorsqu'ils entrent et soumettent des états de dépenses et des demandes de voyage.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span> <span data-ttu-id="7f1ac-105">L'application de stratégies des dépenses permet une gestion efficace des dépenses.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-105">Implementing expense policies can help you manage expenses effectively.</span></span> 

<span data-ttu-id="7f1ac-106">Par exemple, vous pouvez définir une stratégie pour les frais d'hôtel à New York, qui stipule que la dépense par nuit ne peut pas dépasser 250 USD</span><span class="sxs-lookup"><span data-stu-id="7f1ac-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span> <span data-ttu-id="7f1ac-107">Si un collaborateur soumet un état de dépenses ou une demande de voyage dans lequel le prix de la chambre dépasse ce montant, le système notifie à l'utilisateur qu'il a dépassé le montant prévu par la stratégie pour ces frais.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="7f1ac-108">Vous pouvez configurer le message que le travailleur recevra lorsque vous définissez la stratégie.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-108">You can configure the message that the worker will receive when you define the policy.</span></span> 

<span data-ttu-id="7f1ac-109">Vous pouvez définir trois types de stratégies :</span><span class="sxs-lookup"><span data-stu-id="7f1ac-109">You can define three types of policies:</span></span> 

 - <span data-ttu-id="7f1ac-110">Avertissement – Permet au travailleur d'envoyer un état de dépenses ou une demande de voyage, mais la dépense sera marquée pour tous les approbateurs et</span><span class="sxs-lookup"><span data-stu-id="7f1ac-110">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>  
 <span data-ttu-id="7f1ac-111">pour un état ultérieur.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-111">for later reporting.</span></span> 
 - <span data-ttu-id="7f1ac-112">Erreur – Nécessite que le travailleur modifie la dépense pour respecter la stratégie avant d'envoyer l'état de dépenses ou la demande de voyage.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-112">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span> 
 - <span data-ttu-id="7f1ac-113">Justification – Nécessite que le travailleur ou un responsable entre une justification du dépassement du montant prévu par la stratégie avant d'envoyer l'état de dépenses ou la demande de voyage.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-113">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span> 

<span data-ttu-id="7f1ac-114">Vous pouvez également paramétrer une plage de dates pendant laquelle les stratégies des dépenses s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-114">You can also set up a date range for which expense policies are in effect.</span></span> <span data-ttu-id="7f1ac-115">Par exemple, il se peut que le prix des vols entre le Danemark et New York soient chers pendant la période de vacances.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-115">For example, airline fares for flights between Denmark and New York City can be expensive during the peak holiday travel season.</span></span> <span data-ttu-id="7f1ac-116">Vous pouvez définir une règle de frais de vol limitant les frais des vols vers New York à 5 000 DKK et spécifier que cette règle s'applique entre le 15 mars et le 15 septembre.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-116">You can define a flight expense rule that restricts the cost of flights to New York City to a limit of DKK 5000, and you can specify that this rule be in effect between March 15 and September 15.</span></span> 

