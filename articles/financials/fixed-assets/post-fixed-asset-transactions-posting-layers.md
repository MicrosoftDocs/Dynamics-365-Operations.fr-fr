---
title: Valider des transactions d'immobilisation dans des couches de validation
description: Cet article donne une vue d'ensemble de la fonctionnalité de couche de validation pour les transactions d'immobilisation.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22feb15a1891c57576a5809f4ff3f4d089c6dfa4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556340"
---
# <a name="post-fixed-asset-transactions-to-posting-layers"></a><span data-ttu-id="a3aec-103">Valider des transactions d'immobilisation dans des couches de validation</span><span class="sxs-lookup"><span data-stu-id="a3aec-103">Post fixed asset transactions to posting layers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a3aec-104">Cet article donne une vue d'ensemble de la fonctionnalité de couche de validation pour les transactions d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="a3aec-104">This article gives an overview of posting layer functionality for fixed asset transactions.</span></span>

<span data-ttu-id="a3aec-105">Une immobilisation est souvent amortie de différentes manières, en fonction des différents objectifs.</span><span class="sxs-lookup"><span data-stu-id="a3aec-105">A fixed asset is often depreciated in different ways for different purposes.</span></span> <span data-ttu-id="a3aec-106">L'amortissement à des fins fiscales est calculé conformément aux règles de taxe actuelles afin d'atteindre l'amortissement le plus élevé possible avant impôts, tandis que l'amortissement à des fins de génération d'états est calculé conformément à la législation et aux normes comptables.</span><span class="sxs-lookup"><span data-stu-id="a3aec-106">Depreciation for tax purposes is calculated by using current tax rules to achieve the highest possible depreciation before taxes, but depreciation for reporting purposes is calculated according to accounting laws and standards.</span></span> <span data-ttu-id="a3aec-107">Les différents types d'amortissements sont calculés et enregistrés de manière distincte dans les couches de validation.</span><span class="sxs-lookup"><span data-stu-id="a3aec-107">The various kinds of depreciation are calculated and recorded separately in the posting layers.</span></span>

<span data-ttu-id="a3aec-108">Chaque registre associé à une immobilisation est paramétré pour une couche de validation particulière qui a un objectif d'amortissement global.</span><span class="sxs-lookup"><span data-stu-id="a3aec-108">Each book that is attached to a fixed asset is set up for a particular posting layer that has an overall depreciation objective.</span></span> <span data-ttu-id="a3aec-109">Il existe dix couches de validation : Actuel, Opérations, Taxes, puis sept couches personnalisées.</span><span class="sxs-lookup"><span data-stu-id="a3aec-109">There are ten posting layers: Current, Operations, Tax, and seven Custom layers.</span></span> <span data-ttu-id="a3aec-110">Vous pouvez aussi désactiver la validation dans la comptabilité pour le registre en définissant le champ Valider dans la comptabilité sur Non.</span><span class="sxs-lookup"><span data-stu-id="a3aec-110">You can also disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="a3aec-111">Le champ Couche de validation est alors automatiquement défini sur Aucune.</span><span class="sxs-lookup"><span data-stu-id="a3aec-111">The Posting layer field is then automatically set to None.</span></span> <span data-ttu-id="a3aec-112">En général, les registres qui ne sont pas validés dans la comptabilité sont utilisés à des fins de déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="a3aec-112">Typically, books that don’t post to the general ledger are used for tax reporting purposes.</span></span> <span data-ttu-id="a3aec-113">Cette approche vous donne une flexibilité supplémentaire pour supprimer les transactions historiques du registre des actifs, car elles n'ont pas été validées dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="a3aec-113">This approach gives you the additional flexibility to delete historical transactions for the asset book, because they haven’t been committed to the general ledger.</span></span>

<span data-ttu-id="a3aec-114">Les journaux des immobilisations sont définis à l'aide de la page  Noms des journaux sous Comptabilité > Paramétrage du journal > Noms des journaux.</span><span class="sxs-lookup"><span data-stu-id="a3aec-114">Fixed asset journals are defined by using the Journal names page at General ledger > Journal setup > Journal names.</span></span> <span data-ttu-id="a3aec-115">Chaque journal dans lequel vous pouvez valider des amortissements est défini par son nom pour une seule et unique couche de validation.</span><span class="sxs-lookup"><span data-stu-id="a3aec-115">Each journal that you can post depreciations in is defined by its journal name for only one posting layer.</span></span> <span data-ttu-id="a3aec-116">La couche de validation du journal ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="a3aec-116">The posting layer in the journal can’t be changed.</span></span> <span data-ttu-id="a3aec-117">Cette restriction permet de garantir que les transactions de chaque couche de validation sont distinctes.</span><span class="sxs-lookup"><span data-stu-id="a3aec-117">This restriction helps guarantee that transactions for each posting layer are kept separate.</span></span> <span data-ttu-id="a3aec-118">Au moins un nom de journal doit être créé pour chaque couche de validation.</span><span class="sxs-lookup"><span data-stu-id="a3aec-118">At least one journal name must be created for each posting layer.</span></span> <span data-ttu-id="a3aec-119">Si vous utilisez des registres qui ne sont pas validés dans la comptabilité, vous devez également créer un journal dans lequel la couche de validation est définie sur Aucune.</span><span class="sxs-lookup"><span data-stu-id="a3aec-119">If you’re using books that don’t post to the general ledger, you must also create a journal where the posting layer is set to None.</span></span>

<span data-ttu-id="a3aec-120">Vous pouvez désigner les comptes généraux pour les transactions d'immobilisation dans la page Profils de validation d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="a3aec-120">You can designate ledger accounts for fixed asset transactions on the Fixed asset posting profiles page.</span></span> <span data-ttu-id="a3aec-121">Pour chaque profil de validation, vous devez sélectionner le type de transaction et le registre appropriés, puis désigner les comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="a3aec-121">For each posting profile, you must select the relevant transaction type and book, and then designate the ledger accounts.</span></span> <span data-ttu-id="a3aec-122">Paramétrez un enregistrement de profil de validation pour chaque registre qui sera validé dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="a3aec-122">Set up a posting profile record for each book that will post to the general ledger.</span></span>

> [!NOTE] 
> <span data-ttu-id="a3aec-123">En utilisant les registres déduits, vous pouvez valider des transactions dans les différentes couches de validation simultanément.</span><span class="sxs-lookup"><span data-stu-id="a3aec-123">By using derived books, you can post transactions to different posting layers at the same time.</span></span> <span data-ttu-id="a3aec-124">Vous créez les transactions du registre principal dans un journal dans lequel la couche de validation qui correspond à la couche de validation du registre.</span><span class="sxs-lookup"><span data-stu-id="a3aec-124">You create the transactions of the primary book in a journal where the posting layer corresponds to the book posting layer.</span></span> <span data-ttu-id="a3aec-125">Lors de la validation, les transactions du registre déduit sont validées dans leurs couches de validation appropriées.</span><span class="sxs-lookup"><span data-stu-id="a3aec-125">During posting, the derived book transactions are posted to the appropriate posting layers.</span></span>

<span data-ttu-id="a3aec-126">Pour plus d'informations, voir [Registres dérivés](derived-books.md) et [Validation avec des registres déduits](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="a3aec-126">For more information see, [Derived books](derived-books.md) and [Posting with derived books](post-derived-value-models.md).</span></span>



