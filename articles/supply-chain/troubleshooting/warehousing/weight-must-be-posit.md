---
title: Le poids doit être positif
description: Le poids doit être positif
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dcbcde3143cb509b68b277cb7c709263e2659b5b
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924301"
---
# <a name="weight-must-be-positive"></a><span data-ttu-id="7fb50-103">Le poids doit être positif</span><span class="sxs-lookup"><span data-stu-id="7fb50-103">Weight must be positive</span></span>

<span data-ttu-id="7fb50-104">Code d'erreur : WeightMustBePositive</span><span class="sxs-lookup"><span data-stu-id="7fb50-104">Error code: WeightMustBePositive</span></span>

## <a name="symptoms"></a><span data-ttu-id="7fb50-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="7fb50-105">Symptoms</span></span>

<span data-ttu-id="7fb50-106">Le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="7fb50-106">The system shows the following error message:</span></span>

> <span data-ttu-id="7fb50-107">Le poids doit être positif.</span><span class="sxs-lookup"><span data-stu-id="7fb50-107">Weight must be positive.</span></span>

## <a name="cause"></a><span data-ttu-id="7fb50-108">Cause</span><span class="sxs-lookup"><span data-stu-id="7fb50-108">Cause</span></span>

<span data-ttu-id="7fb50-109">Le champ **Poids brut** est défini sur *0* (zéro) ou une valeur négative.</span><span class="sxs-lookup"><span data-stu-id="7fb50-109">The **Gross Weight** field is set to *0* (zero) or a negative value.</span></span>

## <a name="resolution"></a><span data-ttu-id="7fb50-110">Résolution</span><span class="sxs-lookup"><span data-stu-id="7fb50-110">Resolution</span></span>

<span data-ttu-id="7fb50-111">Pour spécifier un poids, suivez l’une des étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7fb50-111">To specify a weight, follow one of these steps.</span></span>

- <span data-ttu-id="7fb50-112">Définissez une valeur dans le champ **Poids brut**.</span><span class="sxs-lookup"><span data-stu-id="7fb50-112">In the **Gross weight** field, set a value.</span></span> <span data-ttu-id="7fb50-113">Sélectionnez ensuite une unité dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="7fb50-113">Then select a unit in the drop-down list.</span></span>
- <span data-ttu-id="7fb50-114">Sélectionnez **Obtenir le poids système** pour calculer la valeur **Poids brut**.</span><span class="sxs-lookup"><span data-stu-id="7fb50-114">Select **Get system weight** to calculate the **Gross weight** value.</span></span>
