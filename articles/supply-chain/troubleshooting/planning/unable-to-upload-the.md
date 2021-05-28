---
title: Vous ne pouvez pas mettre à jour le coût unitaire prévu lorsque vous importez des enregistrements de prévision de la demande
description: Lorsque vous utilisez des entités de données pour importer des enregistrements de prévision de la demande, le prix de revient des enregistrements existants n'est pas mis à jour afin qu'il corresponde aux données importées.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c8ea8322a6c7bafe2dfcaaee3e9989f753c85e2a
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026511"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a><span data-ttu-id="fade4-103">Vous ne pouvez pas mettre à jour le coût unitaire prévu lorsque vous importez des enregistrements de prévision de la demande</span><span class="sxs-lookup"><span data-stu-id="fade4-103">You can't update the forecasted unit cost when you import demand forecast records</span></span>

<span data-ttu-id="fade4-104">Numéro de la base de connaissances : 4614109</span><span class="sxs-lookup"><span data-stu-id="fade4-104">KB number: 4614109</span></span>

## <a name="symptoms"></a><span data-ttu-id="fade4-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="fade4-105">Symptoms</span></span>

<span data-ttu-id="fade4-106">Lorsque vous utilisez des entités de données pour importer des enregistrements de prévision de la demande, la valeur **Coût unitaire prévu** des enregistrements existants n'est pas mis à jour afin qu'il corresponde aux données importées.</span><span class="sxs-lookup"><span data-stu-id="fade4-106">When you use data entities to import demand forecast records, the **Forecasted unit cost** value for existing records isn't updated so that it matches the imported data.</span></span>

## <a name="cause"></a><span data-ttu-id="fade4-107">Cause</span><span class="sxs-lookup"><span data-stu-id="fade4-107">Cause</span></span>

<span data-ttu-id="fade4-108">**Coût unitaire prévu** est un champ en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="fade4-108">**Forecasted unit cost** is a read-only field.</span></span> <span data-ttu-id="fade4-109">La valeur est basée sur le coût unitaire du produit et ne peut pas être définie directement via l'importation.</span><span class="sxs-lookup"><span data-stu-id="fade4-109">The value is based on the product unit cost and can't be set directly through import.</span></span>

## <a name="resolution"></a><span data-ttu-id="fade4-110">Résolution</span><span class="sxs-lookup"><span data-stu-id="fade4-110">Resolution</span></span>

<span data-ttu-id="fade4-111">Étant donné que le champ est en lecture seule, vous ne pouvez pas en importer les valeurs.</span><span class="sxs-lookup"><span data-stu-id="fade4-111">Because the field is read only, you can't import values for it.</span></span> <span data-ttu-id="fade4-112">La valeur sera calculée selon la logique métier existante.</span><span class="sxs-lookup"><span data-stu-id="fade4-112">The value will be calculated according to the existing business logic.</span></span>
