---
title: Paramétrer les registres d’amortissement
description: Cette procédure parcourt le processus de création d’un nouveau registre d’amortissement et l’associe à un groupe d’immobilisations.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0ab7f9332e3224c3dadd62aae532ccffb05c82a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815594"
---
# <a name="set-up-depreciation-books"></a><span data-ttu-id="b6293-103">Paramétrer les registres d’amortissement</span><span class="sxs-lookup"><span data-stu-id="b6293-103">Set up depreciation books</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b6293-104">Cette procédure parcourt le processus de création d’un nouveau registre d’amortissement et l’associe à un groupe d’immobilisations.</span><span class="sxs-lookup"><span data-stu-id="b6293-104">This procedure walks through the process of creating a new depreciation book and associate it with a fixed asset group.</span></span> 

## <a name="create-a-depreciation-book"></a><span data-ttu-id="b6293-105">Créer un registre des amortissements</span><span class="sxs-lookup"><span data-stu-id="b6293-105">Create a depreciation book</span></span>
1. <span data-ttu-id="b6293-106">Accédez à Immobilisations > Paramétrage > Registres des amortissements.</span><span class="sxs-lookup"><span data-stu-id="b6293-106">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="b6293-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="b6293-107">Click New.</span></span>
3. <span data-ttu-id="b6293-108">Tapez une valeur dans le champ Registre des amortissements.</span><span class="sxs-lookup"><span data-stu-id="b6293-108">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="b6293-109">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b6293-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b6293-110">Cochez ou décochez la case Calculer l’amortissement.</span><span class="sxs-lookup"><span data-stu-id="b6293-110">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="b6293-111">Dans le champ Profil d’amortissement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="b6293-111">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="b6293-112">Dans la liste, recherchez et sélectionnez le profil d’amortissement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b6293-112">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="b6293-113">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b6293-113">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="b6293-114">Dans le champ Autre profil d’amortissement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="b6293-114">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="b6293-115">Dans la liste, sélectionnez le profil d’amortissement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b6293-115">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="b6293-116">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b6293-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b6293-117">Le profil d’amortissement exceptionnel est utilisé pour l’amortissement supplémentaire d’un actif dans des circonstances peu courantes.</span><span class="sxs-lookup"><span data-stu-id="b6293-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="b6293-118">Par exemple, vous pouvez utiliser cette opération pour enregistrer l’amortissement résultant d’une catastrophe naturelle.</span><span class="sxs-lookup"><span data-stu-id="b6293-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="b6293-119">Cochez ou décochez la case Créer des ajustements d’amortissement avec des amortissements de base</span><span class="sxs-lookup"><span data-stu-id="b6293-119">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="b6293-120">Dans le champ Calendrier, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="b6293-120">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="b6293-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b6293-121">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="b6293-122">Associer le registre des amortissements à un groupe d’immobilisations</span><span class="sxs-lookup"><span data-stu-id="b6293-122">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="b6293-123">Cliquez sur Groupes d’immobilisations.</span><span class="sxs-lookup"><span data-stu-id="b6293-123">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="b6293-124">Dans le champ Groupe d’immobilisations, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="b6293-124">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b6293-125">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b6293-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="b6293-126">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b6293-126">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b6293-127">Sélectionnez une option dans le champ Convention d’amortissement.</span><span class="sxs-lookup"><span data-stu-id="b6293-127">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="b6293-128">Entrez un nombre dans le champ Durée de vie.</span><span class="sxs-lookup"><span data-stu-id="b6293-128">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="b6293-129">Notez que la valeur du champ Périodes d’amortissement est calculée après la définition de la durée de vie.</span><span class="sxs-lookup"><span data-stu-id="b6293-129">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]