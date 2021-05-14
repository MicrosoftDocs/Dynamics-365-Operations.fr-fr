---
title: Le travail ne peut pas être annulé en raison de son statut
description: Le travail ne peut pas être annulé en raison de son statut
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
ms.openlocfilehash: 60b4da44ca5e6790302e0797640317cef8493db7
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924253"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a><span data-ttu-id="d147c-103">Le travail ne peut pas être annulé en raison de son statut</span><span class="sxs-lookup"><span data-stu-id="d147c-103">Work can't be canceled because of its status</span></span>

<span data-ttu-id="d147c-104">Code d’erreur : WAX2190</span><span class="sxs-lookup"><span data-stu-id="d147c-104">Error code: WAX2190</span></span>

## <a name="symptoms"></a><span data-ttu-id="d147c-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="d147c-105">Symptoms</span></span>

<span data-ttu-id="d147c-106">Le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="d147c-106">The system shows the following error message:</span></span>

> <span data-ttu-id="d147c-107">Vous ne pouvez pas annuler le travail %1 en raison de son statut %2.</span><span class="sxs-lookup"><span data-stu-id="d147c-107">You cannot cancel work %1 because it has a status of %2.</span></span>

## <a name="cause"></a><span data-ttu-id="d147c-108">Cause</span><span class="sxs-lookup"><span data-stu-id="d147c-108">Cause</span></span>

<span data-ttu-id="d147c-109">Le travail ne peut pas être annulé dans son état actuel.</span><span class="sxs-lookup"><span data-stu-id="d147c-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="d147c-110">L'en-tête de travail ou les lignes de travail n'ont pas la valeur **Statut du travail** attendue.</span><span class="sxs-lookup"><span data-stu-id="d147c-110">The work header or work lines don't have the expected **Work status** value.</span></span> <span data-ttu-id="d147c-111">Le champ **Statut du travail** de l'en-tête de travail n'est pas défini sur *Ouvert* ou *En cours*.</span><span class="sxs-lookup"><span data-stu-id="d147c-111">The **Work status** field on the work header isn't set to *Open* or *In progress*.</span></span>

## <a name="resolution"></a><span data-ttu-id="d147c-112">Résolution</span><span class="sxs-lookup"><span data-stu-id="d147c-112">Resolution</span></span>

<span data-ttu-id="d147c-113">Pour annuler le travail, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d147c-113">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="d147c-114">Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.</span><span class="sxs-lookup"><span data-stu-id="d147c-114">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="d147c-115">Dans le champ **ID de travail**, spécifiez l'ID du travail que vous souhaitez annuler.</span><span class="sxs-lookup"><span data-stu-id="d147c-115">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="d147c-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d147c-116">Select **OK**.</span></span>
1. <span data-ttu-id="d147c-117">Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.</span><span class="sxs-lookup"><span data-stu-id="d147c-117">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="d147c-118">Pour en savoir plus, voir [Annuler le travail en entrepôt pour la gestion des exceptions](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="d147c-118">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
