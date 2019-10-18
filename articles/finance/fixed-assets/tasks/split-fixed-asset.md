---
title: Fractionner une immobilisation
description: Cette rubrique explique comment fractionner un pourcentage d'un registre d'immobilisations en un nouveau registre d'immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4e001a6fdf390c6211ba85aa327b60dcdf16d9e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177692"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="bcd39-103">Fractionner une immobilisation</span><span class="sxs-lookup"><span data-stu-id="bcd39-103">Split a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bcd39-104">Cette rubrique explique comment fractionner un pourcentage d'un registre d'immobilisations en un nouveau registre d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="bcd39-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="bcd39-105">Il utilise le rôle de comptable et les données de démonstration de la société USMF fictive.</span><span class="sxs-lookup"><span data-stu-id="bcd39-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="bcd39-106">Créer une nouvelle immobilisation</span><span class="sxs-lookup"><span data-stu-id="bcd39-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="bcd39-107">Dans le volet de navigation, accédez à **Modules > Immobilisations > Immobilisations > Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="bcd39-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="bcd39-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="bcd39-108">Select **New**.</span></span>
3. <span data-ttu-id="bcd39-109">Entrez ou sélectionnez une valeur dans le champ **Groupe d'immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="bcd39-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="bcd39-110">Notez le numéro d'immobilisation à utiliser dans le processus de fractionnement ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="bcd39-110">Note the fixed asset number to use in the split process later.</span></span>  
4. <span data-ttu-id="bcd39-111">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="bcd39-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="bcd39-112">Permet de fermer l'écran.</span><span class="sxs-lookup"><span data-stu-id="bcd39-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="bcd39-113">Fractionner une immobilisation</span><span class="sxs-lookup"><span data-stu-id="bcd39-113">Split a fixed asset</span></span>
1. <span data-ttu-id="bcd39-114">Dans la liste, recherchez et sélectionnez le lien de l'immobilisation à fractionner.</span><span class="sxs-lookup"><span data-stu-id="bcd39-114">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="bcd39-115">Sélectionnez **Registres**.</span><span class="sxs-lookup"><span data-stu-id="bcd39-115">Select **Books**.</span></span> <span data-ttu-id="bcd39-116">Sélectionnez le registre pour fractionner la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="bcd39-116">Select the book to split to the new asset.</span></span>  
3. <span data-ttu-id="bcd39-117">Sélectionnez **Fonctions**.</span><span class="sxs-lookup"><span data-stu-id="bcd39-117">Select **Functions**.</span></span>
4. <span data-ttu-id="bcd39-118">Sélectionnez **Fractionner une immobilisation**.</span><span class="sxs-lookup"><span data-stu-id="bcd39-118">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="bcd39-119">Dans le champ **À l'immobilisation**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bcd39-119">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="bcd39-120">Dans le champ **Vers le registre**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="bcd39-120">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="bcd39-121">Entrez une date dans le champ **Date de transaction**.</span><span class="sxs-lookup"><span data-stu-id="bcd39-121">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="bcd39-122">Entrez un numéro dans le champ **Pourcentage**.</span><span class="sxs-lookup"><span data-stu-id="bcd39-122">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="bcd39-123">Dans le champ **Nom de journal**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bcd39-123">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="bcd39-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcd39-124">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="bcd39-125">Valider la transaction de journal</span><span class="sxs-lookup"><span data-stu-id="bcd39-125">Post the journal transaction</span></span>
1. <span data-ttu-id="bcd39-126">Dans le volet de navigation, accédez à **Modules > Immobilisations > Entrées de journal > Journal des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="bcd39-126">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="bcd39-127">Dans la liste, sélectionnez le journal créé avec le processus de fractionnement.</span><span class="sxs-lookup"><span data-stu-id="bcd39-127">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="bcd39-128">Sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="bcd39-128">Select **Lines**.</span></span>

    - <span data-ttu-id="bcd39-129">Vérifiez les lignes de journal créées.</span><span class="sxs-lookup"><span data-stu-id="bcd39-129">Verify the journal lines created.</span></span>  
    - <span data-ttu-id="bcd39-130">Une transaction d'ajustement d'acquisition est créée pour l'actif original pour diminuer la valeur par le pourcentage spécifié lors du processus de fractionnement.</span><span class="sxs-lookup"><span data-stu-id="bcd39-130">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  
    - <span data-ttu-id="bcd39-131">Une transaction d'acquisition est créée pour le nouvel actif pour le même montant.</span><span class="sxs-lookup"><span data-stu-id="bcd39-131">An Acquisition transaction is created for the new asset for the same amount.</span></span>  

4. <span data-ttu-id="bcd39-132">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="bcd39-132">Select **Post**.</span></span>

