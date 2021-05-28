---
title: Vous ne pouvez pas importer un article à l'aide de l'entité Produits lancés V2
description: Vous ne pouvez pas importer un article à l'aide de l'entité Produits lancés V2.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended, DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8182f2f83f6a3e4cf54fe6fa64b25a2f461ff541
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026499"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a><span data-ttu-id="2237e-103">Vous ne pouvez pas importer un article à l'aide de l'entité Produits lancés V2</span><span class="sxs-lookup"><span data-stu-id="2237e-103">You can't import an item by using the Released products V2 entity</span></span>

<span data-ttu-id="2237e-104">Numéro de la base de connaissances : 4611825</span><span class="sxs-lookup"><span data-stu-id="2237e-104">KB number: 4611825</span></span>

## <a name="symptoms"></a><span data-ttu-id="2237e-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="2237e-105">Symptoms</span></span>

<span data-ttu-id="2237e-106">Lorsque vous essayez d'importer un élément à l'aide de l'entité *Produits lancés V2*, vous recevez un message d'erreur semblable à l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="2237e-106">When you try to import an item by using the *Released products V2* entity, you receive an error message that resembles the following example:</span></span>

> <span data-ttu-id="2237e-107">Impossible de créer un enregistrement dans les éléments - groupes de dimensions de suivi (EcoResTrackingDimensionGroupItem).</span><span class="sxs-lookup"><span data-stu-id="2237e-107">Cannot create a record in Items - tracking dimension groups (EcoResTrackingDimensionGroupItem).</span></span> <span data-ttu-id="2237e-108">Numéro de l'article : 2040663, Lot.</span><span class="sxs-lookup"><span data-stu-id="2237e-108">Item number: 2040663, Batch.</span></span> <span data-ttu-id="2237e-109">L'enregistrement existe déjà.</span><span class="sxs-lookup"><span data-stu-id="2237e-109">The record already exists.</span></span>

## <a name="resolution"></a><span data-ttu-id="2237e-110">Résolution</span><span class="sxs-lookup"><span data-stu-id="2237e-110">Resolution</span></span>

<span data-ttu-id="2237e-111">Pour importer de nouveaux produits lancés, vous devez utiliser l'entité *Sortie de la création de produit V2* au lieu de l'entité *Produits lancés V2*.</span><span class="sxs-lookup"><span data-stu-id="2237e-111">To import new released products, you must use the *Released product creation V2* entity instead of the *Released products V2* entity.</span></span>
