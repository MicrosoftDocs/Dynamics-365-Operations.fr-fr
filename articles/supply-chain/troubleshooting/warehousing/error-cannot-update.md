---
title: Une erreur se produit lorsque l'emplacement est sélectionné lors de l'enregistrement de la liste de prélèvement
description: Une erreur se produit lorsque l'emplacement est sélectionné lors de l'enregistrement de la liste de prélèvement.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b7fc579821f9a80d94aea949fcc0301b9d8f6935
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026491"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a><span data-ttu-id="04337-103">Une erreur se produit lorsque l'emplacement est sélectionné lors de l'enregistrement de la liste de prélèvement</span><span class="sxs-lookup"><span data-stu-id="04337-103">An error occurs when the location is selected during picking list registration</span></span>

<span data-ttu-id="04337-104">Numéro de la base de connaissances : 4613106</span><span class="sxs-lookup"><span data-stu-id="04337-104">KB number: 4613106</span></span>

## <a name="symptoms"></a><span data-ttu-id="04337-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="04337-105">Symptoms</span></span>

<span data-ttu-id="04337-106">Ce problème se produit lorsque votre système est configuré pour réserver automatiquement les commandes client.</span><span class="sxs-lookup"><span data-stu-id="04337-106">This issue occurs when your system is configured to automatically reserve sales orders.</span></span> <span data-ttu-id="04337-107">Si vous essayez de sélectionner l'emplacement d'une ligne d'enregistrement de liste de prélèvement, vous recevez le message d'erreur suivant lorsque vous utilisez les processus de réservation de gestion d'entrepôt (WMS) :</span><span class="sxs-lookup"><span data-stu-id="04337-107">If you try to select the location for a picking list registration line, you receive the following error message when you use warehouse management (WMS) reservation processes:</span></span>

> <span data-ttu-id="04337-108">Impossible de mettre à jour la quantité avec de nouvelles dimensions</span><span class="sxs-lookup"><span data-stu-id="04337-108">Can't update quantity with new dimensions</span></span>

<span data-ttu-id="04337-109">Ce problème peut se produire car vous ne disposez pas de suffisamment de stock disponible à un emplacement spécifié.</span><span class="sxs-lookup"><span data-stu-id="04337-109">This issue can occur because you don't have enough on-hand inventory at a specified location.</span></span>

## <a name="resolution"></a><span data-ttu-id="04337-110">Résolution</span><span class="sxs-lookup"><span data-stu-id="04337-110">Resolution</span></span>

<span data-ttu-id="04337-111">Le système se comporte comme prévu.</span><span class="sxs-lookup"><span data-stu-id="04337-111">The system is behaving as designed.</span></span>

<span data-ttu-id="04337-112">Dans les scénarios où vous utilisez le processus de réservation au niveau de l'entrepôt, si le stock disponible ne sera pas réservé à tous les niveaux de dimension de stock et que vous ne disposez pas d'un stock disponible suffisant à un emplacement spécifié, nous vous recommandons d'utiliser le processus de réservation manuelle à partir de la ligne de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="04337-112">In scenarios where you use the warehouse-level reservation process, if the on-hand inventory won't be reserved on all inventory dimension levels, and you don't have enough on-hand inventory at a specified location, we recommend that you use the manual reservation process from the picking line.</span></span> <span data-ttu-id="04337-113">Vous pouvez ensuite utiliser la fonction *Lot de réserve* pour distribuer les réservations inférieures, telles que l'emplacement, pour toutes les quantités disponibles en stock.</span><span class="sxs-lookup"><span data-stu-id="04337-113">You can then use the *Reserve lot* function to distribute the lower reservations, such as location, for all the available on-hand quantities.</span></span>
