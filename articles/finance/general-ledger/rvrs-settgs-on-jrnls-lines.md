---
title: Paramètres de contrepassation sur les journaux et les lignes
description: Cette rubrique explique pourquoi une écriture de contrepassation qui a été saisie dans un journal des opérations diverses peut ne pas être incluse dans la transaction validée.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 74020f6fc9b0fa8e05a1e2a09fd13dcd60490dc0
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028562"
---
# <a name="reverse-settings-on-journals-and-lines"></a><span data-ttu-id="e2b91-103">Paramètres de contrepassation sur les journaux et les lignes</span><span class="sxs-lookup"><span data-stu-id="e2b91-103">Reverse settings on journals and lines</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e2b91-104">Cette rubrique explique pourquoi une écriture de contrepassation qui a été saisie dans un journal des opérations diverses peut ne pas être incluse dans la transaction validée.</span><span class="sxs-lookup"><span data-stu-id="e2b91-104">This topic addresses why a reversing entry that was entered on a general journal might not be included on the posted transaction.</span></span>  

## <a name="symptom"></a><span data-ttu-id="e2b91-105">Problème</span><span class="sxs-lookup"><span data-stu-id="e2b91-105">Symptom</span></span>

<span data-ttu-id="e2b91-106">Un journal des opérations diverses comprend une écriture de contrepassation et une date de contrepassation.</span><span class="sxs-lookup"><span data-stu-id="e2b91-106">A general journal includes a reversing entry and reversing date on the journal.</span></span> <span data-ttu-id="e2b91-107">Lorsque vous validez le journal, aucun des justificatifs n’est contrepassé.</span><span class="sxs-lookup"><span data-stu-id="e2b91-107">When you post the journal, none of the vouchers are reversed.</span></span> <span data-ttu-id="e2b91-108">Pourquoi ?</span><span class="sxs-lookup"><span data-stu-id="e2b91-108">Why does this happen?</span></span>

## <a name="resolution"></a><span data-ttu-id="e2b91-109">Résolution</span><span class="sxs-lookup"><span data-stu-id="e2b91-109">Resolution</span></span>

<span data-ttu-id="e2b91-110">Lorsque le journal est validé, le processus de contrepassation examine uniquement les paramètres des champs **Écriture de contrepassation** et **Date de contrepassation** sur la section **Lignes** du justificatif.</span><span class="sxs-lookup"><span data-stu-id="e2b91-110">When the journal is posted, the reversing process looks only at the **Revering entry** and **Reversing date** settings on the **Lines** section of the voucher.</span></span> <span data-ttu-id="e2b91-111">Cette approche permet à un journal d’inclure certains justificatifs qui sont marqués pour contrepassation et d’autres qui ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="e2b91-111">This approach allows a journal to include some vouchers that are marked for reversing, and others that are not.</span></span>

<span data-ttu-id="e2b91-112">Les valeurs du journal sont utilisées par défaut uniquement lors de l’ajout de *nouvelles* lignes.</span><span class="sxs-lookup"><span data-stu-id="e2b91-112">The values from the journal are only used as defaults when adding *new* lines.</span></span> <span data-ttu-id="e2b91-113">La modification des valeurs dans le journal n’affecte pas les lignes existantes.</span><span class="sxs-lookup"><span data-stu-id="e2b91-113">Changing the values on the journal doesn’t affect existing lines.</span></span> <span data-ttu-id="e2b91-114">Dans cet exemple, les lignes du justificatif ont été saisies en premier.</span><span class="sxs-lookup"><span data-stu-id="e2b91-114">In this example, the voucher lines were entered first.</span></span> <span data-ttu-id="e2b91-115">Lorsque vous saisissez le détail de la ligne avant de désigner le journal comme contrepassation, la désignation comme écriture et date de contrepassation n’est appliquée à aucune ligne existante.</span><span class="sxs-lookup"><span data-stu-id="e2b91-115">When you enter the line detail before designating the journal as reversing, the designation as a reversing entry and date won't be applied to any existing lines.</span></span>

<span data-ttu-id="e2b91-116">La modification de l’écriture ou de la date de contrepassation sur une ligne existante propage cette modification sur d’autres lignes du même document.</span><span class="sxs-lookup"><span data-stu-id="e2b91-116">Changing the reversing entry or reversing date on an existing line propagates that change to other lines in the same voucher.</span></span> <span data-ttu-id="e2b91-117">Pour optimiser les performances, la grille n’est pas actualisée après la propagation des modifications vers d’autres lignes.</span><span class="sxs-lookup"><span data-stu-id="e2b91-117">To optimize performance, the grid is not refreshed after propagating changes to other Lines.</span></span> <span data-ttu-id="e2b91-118">Vous pouvez afficher les valeurs mises à jour en actualisant la grille.</span><span class="sxs-lookup"><span data-stu-id="e2b91-118">You can display the updated values by refreshing the grid.</span></span>


