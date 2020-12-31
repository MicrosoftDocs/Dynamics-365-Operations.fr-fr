---
title: Fractionner une immobilisation
description: Cette rubrique explique comment fractionner un pourcentage d’un registre d’immobilisations en un nouveau registre d’immobilisations.
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
ms.openlocfilehash: da2dd4889a5f4722ff60a76a4a023c63fb59ad55
ms.sourcegitcommit: 9f32389715b226c11e74c53547527e0a8b51e300
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/12/2020
ms.locfileid: "4514324"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="81584-103">Fractionner une immobilisation</span><span class="sxs-lookup"><span data-stu-id="81584-103">Split a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="81584-104">Cette rubrique explique comment fractionner un pourcentage d’un registre d’immobilisations en un nouveau registre d’immobilisations.</span><span class="sxs-lookup"><span data-stu-id="81584-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="81584-105">Il utilise le rôle de comptable et les données de démonstration de la société USMF fictive.</span><span class="sxs-lookup"><span data-stu-id="81584-105">It uses the Accountant role and USMF demo data.</span></span>

## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="81584-106">Créer une nouvelle immobilisation</span><span class="sxs-lookup"><span data-stu-id="81584-106">Create a new fixed asset</span></span>

1. <span data-ttu-id="81584-107">Dans le volet de navigation, accédez à **Modules \> Immobilisations \> Immobilisations \> Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="81584-107">In the navigation pane, go to **Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="81584-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="81584-108">Select **New**.</span></span>
3. <span data-ttu-id="81584-109">Entrez ou sélectionnez une valeur dans le champ **Groupe d’immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="81584-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="81584-110">Notez le numéro d’immobilisation à utiliser dans le processus de fractionnement ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="81584-110">Note the fixed asset number to use in the split process later.</span></span>
4. <span data-ttu-id="81584-111">Dans le champ **Nom**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="81584-111">In the **Name** field, enter a value.</span></span>
5. <span data-ttu-id="81584-112">Permet de fermer l’écran.</span><span class="sxs-lookup"><span data-stu-id="81584-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="81584-113">Fractionner une immobilisation</span><span class="sxs-lookup"><span data-stu-id="81584-113">Split a fixed asset</span></span>

<span data-ttu-id="81584-114">Avant qu’un actif entièrement amorti ne soit fractionné, le statut du registre des immobilisations doit être modifié manuellement de **Clôturé** à **En cours**.</span><span class="sxs-lookup"><span data-stu-id="81584-114">Before a fully depreciated asset is split, the asset book status should be manually changed from **Closed** to **Open**.</span></span> <span data-ttu-id="81584-115">Cette étape est obligatoire car le statut du registre doit être **En cours** si vous devez valider des transactions pour l’immobilisation (par exemple, pour une vente de cession).</span><span class="sxs-lookup"><span data-stu-id="81584-115">This step is required because the book status has to be **Open** if you must post transactions for the asset (for example, for a disposal sale).</span></span> <span data-ttu-id="81584-116">Vous devez également activer le paramètre **Autoriser plusieurs transactions dans un seul N° document** sur l’onglet **Général** de la page **Paramètres comptables**.</span><span class="sxs-lookup"><span data-stu-id="81584-116">You must also turn on the **Allow multiple transactions within one voucher** parameter on the **General** tab of the **General ledger parameters** page.</span></span> <span data-ttu-id="81584-117">Une fois que le statut du registre d’actifs a été modifié et que plusieurs transactions au sein d’un même N° document ont été autorisées, procédez comme suit pour fractionner l’actif.</span><span class="sxs-lookup"><span data-stu-id="81584-117">After the asset book status is changed and multiple transactions within one voucher have been allowed, complete the following steps to split the asset.</span></span>

1. <span data-ttu-id="81584-118">Dans la liste, recherchez et sélectionnez le lien de l’immobilisation à fractionner.</span><span class="sxs-lookup"><span data-stu-id="81584-118">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="81584-119">Sélectionnez **Registres**.</span><span class="sxs-lookup"><span data-stu-id="81584-119">Select **Books**.</span></span> <span data-ttu-id="81584-120">Sélectionnez le registre pour fractionner la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="81584-120">Select the book to split to the new asset.</span></span>
3. <span data-ttu-id="81584-121">Sélectionnez **Fonctions**.</span><span class="sxs-lookup"><span data-stu-id="81584-121">Select **Functions**.</span></span>
4. <span data-ttu-id="81584-122">Sélectionnez **Fractionner une immobilisation**.</span><span class="sxs-lookup"><span data-stu-id="81584-122">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="81584-123">Dans le champ **À l’immobilisation**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="81584-123">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="81584-124">Dans le champ **Vers le registre**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="81584-124">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="81584-125">Entrez une date dans le champ **Date de transaction**.</span><span class="sxs-lookup"><span data-stu-id="81584-125">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="81584-126">Entrez un numéro dans le champ **Pourcentage**.</span><span class="sxs-lookup"><span data-stu-id="81584-126">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="81584-127">Dans le champ **Nom de journal**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="81584-127">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="81584-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81584-128">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="81584-129">Valider la transaction de journal</span><span class="sxs-lookup"><span data-stu-id="81584-129">Post the journal transaction</span></span>

1. <span data-ttu-id="81584-130">Dans le volet de navigation, accédez à **Modules \> Immobilisations \> Entrées de journal \> Journal des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="81584-130">In the navigation pane, go to **Modules \> Fixed assets \> Journal entries \> Fixed assets journal**.</span></span>
2. <span data-ttu-id="81584-131">Dans la liste, sélectionnez le journal créé avec le processus de fractionnement.</span><span class="sxs-lookup"><span data-stu-id="81584-131">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="81584-132">Sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="81584-132">Select **Lines**.</span></span>

    - <span data-ttu-id="81584-133">Vérifiez les lignes de journal créées.</span><span class="sxs-lookup"><span data-stu-id="81584-133">Verify the journal lines created.</span></span>
    - <span data-ttu-id="81584-134">Une transaction d’ajustement d’acquisition est créée pour l’actif original pour diminuer la valeur par le pourcentage spécifié lors du processus de fractionnement.</span><span class="sxs-lookup"><span data-stu-id="81584-134">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>
    - <span data-ttu-id="81584-135">Une transaction d’acquisition est créée pour le nouvel actif pour le même montant.</span><span class="sxs-lookup"><span data-stu-id="81584-135">An Acquisition transaction is created for the new asset for the same amount.</span></span>

4. <span data-ttu-id="81584-136">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="81584-136">Select **Post**.</span></span>
