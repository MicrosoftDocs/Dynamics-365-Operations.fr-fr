---
title: Paramétrer les registres des amortissements (mai 2016)
description: Ce guide de tâche va créer un registre des amortissements et l'associera à un groupe d'immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6840e211847494598a81cd3228dbd3796447e18c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186898"
---
# <a name="set-up-depreciation-books-may-2016"></a><span data-ttu-id="86567-103">Paramétrer les registres des amortissements (mai 2016)</span><span class="sxs-lookup"><span data-stu-id="86567-103">Set up depreciation books (May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="86567-104">Ce guide de tâche va créer un registre des amortissements et l'associera à un groupe d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="86567-104">This task guide will create a new depreciation book and associate it with a fixed asset group.</span></span>  <span data-ttu-id="86567-105">Il utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="86567-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-depreciation-book"></a><span data-ttu-id="86567-106">Créer un registre des amortissements</span><span class="sxs-lookup"><span data-stu-id="86567-106">Create a depreciation book</span></span>
1. <span data-ttu-id="86567-107">Accédez à Immobilisations > Paramétrage > Registres des amortissements.</span><span class="sxs-lookup"><span data-stu-id="86567-107">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="86567-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="86567-108">Click New.</span></span>
3. <span data-ttu-id="86567-109">Tapez une valeur dans le champ Registre des amortissements.</span><span class="sxs-lookup"><span data-stu-id="86567-109">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="86567-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="86567-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="86567-111">Cochez ou décochez la case Calculer l'amortissement.</span><span class="sxs-lookup"><span data-stu-id="86567-111">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="86567-112">Dans le champ Profil d'amortissement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="86567-112">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="86567-113">Dans la liste, recherchez et sélectionnez le profil d'amortissement souhaité.</span><span class="sxs-lookup"><span data-stu-id="86567-113">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="86567-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="86567-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="86567-115">Dans le champ Autre profil d'amortissement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="86567-115">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="86567-116">Dans la liste, sélectionnez le profil d'amortissement souhaité.</span><span class="sxs-lookup"><span data-stu-id="86567-116">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="86567-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="86567-117">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="86567-118">Le profil d'amortissement exceptionnel est utilisé pour l'amortissement supplémentaire d'un actif dans des circonstances peu courantes.</span><span class="sxs-lookup"><span data-stu-id="86567-118">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="86567-119">Par exemple, vous pouvez utiliser cette opération pour enregistrer l'amortissement résultant d'une catastrophe naturelle.</span><span class="sxs-lookup"><span data-stu-id="86567-119">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="86567-120">Cochez ou décochez la case Créer des ajustements d'amortissement avec des amortissements de base</span><span class="sxs-lookup"><span data-stu-id="86567-120">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="86567-121">Dans le champ Calendrier, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="86567-121">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="86567-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="86567-122">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="86567-123">Associer le registre des amortissements à un groupe d'immobilisations</span><span class="sxs-lookup"><span data-stu-id="86567-123">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="86567-124">Cliquez sur Groupes d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="86567-124">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="86567-125">Dans le champ Groupe d'immobilisations, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="86567-125">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="86567-126">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="86567-126">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="86567-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="86567-127">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="86567-128">Sélectionnez une option dans le champ Convention d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="86567-128">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="86567-129">Entrez un nombre dans le champ Durée de vie.</span><span class="sxs-lookup"><span data-stu-id="86567-129">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="86567-130">Notez que la valeur du champ Périodes d'amortissement est calculée après la définition de la durée de vie.</span><span class="sxs-lookup"><span data-stu-id="86567-130">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  

