---
title: Fractionner une immobilisation
description: Ce guide de tâche fractionnera un pourcentage d'un registre d'immobilisations en un nouveau registre d'immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6be9de64265a4d7b5c91af3ee8acfce80c78e0f1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "333367"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="a44bc-103">Fractionner une immobilisation</span><span class="sxs-lookup"><span data-stu-id="a44bc-103">Split a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a44bc-104">Ce guide de tâche fractionnera un pourcentage d'un registre d'immobilisations en un nouveau registre d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="a44bc-104">This task guide will split a percentage of one asset book to a new asset book.</span></span>  <span data-ttu-id="a44bc-105">Il utilise le rôle de comptable et les données de démonstration de la société USMF fictive.</span><span class="sxs-lookup"><span data-stu-id="a44bc-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="a44bc-106">Créer une nouvelle immobilisation</span><span class="sxs-lookup"><span data-stu-id="a44bc-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="a44bc-107">Accédez à Immobilisations > Immobilisations > Immobilisations.</span><span class="sxs-lookup"><span data-stu-id="a44bc-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="a44bc-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a44bc-108">Click New.</span></span>
3. <span data-ttu-id="a44bc-109">Saisissez ou sélectionnez une valeur dans le champ Groupe d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="a44bc-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="a44bc-110">Notez le numéro d'immobilisation à utiliser dans le processus de fractionnement ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="a44bc-110">Note the fixed asset number to use in the split process later.</span></span>
5. <span data-ttu-id="a44bc-111">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="a44bc-111">In the Name field, type a value.</span></span>
6. <span data-ttu-id="a44bc-112">Permet de fermer l'écran.</span><span class="sxs-lookup"><span data-stu-id="a44bc-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="a44bc-113">Fractionner une immobilisation</span><span class="sxs-lookup"><span data-stu-id="a44bc-113">Split a fixed asset</span></span>
1. <span data-ttu-id="a44bc-114">Dans la liste, recherchez et sélectionnez l'immobilisation à fractionner.</span><span class="sxs-lookup"><span data-stu-id="a44bc-114">In the list, find and select the fixed asset to split.</span></span>
2. <span data-ttu-id="a44bc-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a44bc-115">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="a44bc-116">Cliquez sur Registres.</span><span class="sxs-lookup"><span data-stu-id="a44bc-116">Click Books.</span></span>
    * <span data-ttu-id="a44bc-117">Sélectionnez le registre pour fractionner la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="a44bc-117">Select the book to split to the new asset.</span></span>  
4. <span data-ttu-id="a44bc-118">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="a44bc-118">Click Functions.</span></span>
5. <span data-ttu-id="a44bc-119">Cliquez sur Fractionner une immobilisation.</span><span class="sxs-lookup"><span data-stu-id="a44bc-119">Click Split fixed asset.</span></span>
6. <span data-ttu-id="a44bc-120">Dans le champ À l'immobilisation, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a44bc-120">In the To fixed asset field, enter or select a value.</span></span>
7. <span data-ttu-id="a44bc-121">Dans le champ Vers le registre, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="a44bc-121">In the To book field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="a44bc-122">Entrez une date dans le champ Date de transaction.</span><span class="sxs-lookup"><span data-stu-id="a44bc-122">In the Transaction date field, enter a date.</span></span>
9. <span data-ttu-id="a44bc-123">Entrez un numéro dans le champ Pourcentage.</span><span class="sxs-lookup"><span data-stu-id="a44bc-123">In the Percent field, enter a number.</span></span>
10. <span data-ttu-id="a44bc-124">Dans le champ Nom de journal, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a44bc-124">In the Journal name field, enter or select a value.</span></span>
11. <span data-ttu-id="a44bc-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a44bc-125">Click OK.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="a44bc-126">Valider la transaction de journal</span><span class="sxs-lookup"><span data-stu-id="a44bc-126">Post the journal transaction</span></span>
1. <span data-ttu-id="a44bc-127">Accédez à Immobilisations > Entrées de journal > Journal des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="a44bc-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="a44bc-128">Dans la liste, sélectionnez le journal créé avec le processus de fractionnement.</span><span class="sxs-lookup"><span data-stu-id="a44bc-128">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="a44bc-129">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="a44bc-129">Click Lines.</span></span>
    * <span data-ttu-id="a44bc-130">Vérifiez les lignes de journal créées.</span><span class="sxs-lookup"><span data-stu-id="a44bc-130">Verify the journal lines created.</span></span>  <span data-ttu-id="a44bc-131">Une transaction d'ajustement d'acquisition est créée pour l'actif original pour diminuer la valeur par le pourcentage spécifié lors du processus de fractionnement.</span><span class="sxs-lookup"><span data-stu-id="a44bc-131">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  <span data-ttu-id="a44bc-132">Une transaction d'acquisition est créée pour le nouvel actif pour le même montant.</span><span class="sxs-lookup"><span data-stu-id="a44bc-132">An Acquisition transaction is created for the new asset for the same amount.</span></span>  
4. <span data-ttu-id="a44bc-133">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="a44bc-133">Click Post.</span></span>

