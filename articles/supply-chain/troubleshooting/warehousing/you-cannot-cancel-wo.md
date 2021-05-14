---
title: Vous ne pouvez pas annuler un travail affecté à un utilisateur.
description: Vous ne pouvez pas annuler un travail affecté à un utilisateur.
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e5f6912cfb1d5be8e46b7989856af99f8a611c11
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924399"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a><span data-ttu-id="a2a79-103">Vous ne pouvez pas annuler un travail affecté à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a2a79-103">You can't cancel work that is on a user</span></span>

<span data-ttu-id="a2a79-104">Code d’erreur : WAX708</span><span class="sxs-lookup"><span data-stu-id="a2a79-104">Error code: WAX708</span></span>

## <a name="symptoms"></a><span data-ttu-id="a2a79-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="a2a79-105">Symptoms</span></span>

<span data-ttu-id="a2a79-106">Le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="a2a79-106">The system shows the following error message:</span></span>

> <span data-ttu-id="a2a79-107">Vous ne pouvez pas annuler un travail affecté à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a2a79-107">You cannot cancel work that is on a user.</span></span>

## <a name="cause"></a><span data-ttu-id="a2a79-108">Cause</span><span class="sxs-lookup"><span data-stu-id="a2a79-108">Cause</span></span>

<span data-ttu-id="a2a79-109">Le travail est verrouillé par un utilisateur et ne peut pas être annulé.</span><span class="sxs-lookup"><span data-stu-id="a2a79-109">The work is locked by a user and can't be canceled.</span></span> <span data-ttu-id="a2a79-110">Pour confirmer cela, ouvrez l'ID de travail, puis ouvrez l'onglet **Général**. Si le travail est verrouillé, le champ **Statut du travail** est défini sur *En cours*, et le champ **Verrouillé par** est défini sur un ID utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a2a79-110">To confirm this, open the work ID and then open the **General** tab. If the work is locked, the **Work status** field will be set to *In progress*, and the **Locked by** field will be set to a user ID.</span></span>

## <a name="resolution"></a><span data-ttu-id="a2a79-111">Résolution</span><span class="sxs-lookup"><span data-stu-id="a2a79-111">Resolution</span></span>

<span data-ttu-id="a2a79-112">Pour annuler le travail, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a2a79-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="a2a79-113">Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.</span><span class="sxs-lookup"><span data-stu-id="a2a79-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="a2a79-114">Dans le champ **ID de travail**, spécifiez l'ID du travail que vous souhaitez annuler.</span><span class="sxs-lookup"><span data-stu-id="a2a79-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="a2a79-115">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2a79-115">Select **OK**.</span></span>
1. <span data-ttu-id="a2a79-116">Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.</span><span class="sxs-lookup"><span data-stu-id="a2a79-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="a2a79-117">Pour en savoir plus, voir [Annuler le travail en entrepôt pour la gestion des exceptions](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="a2a79-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
