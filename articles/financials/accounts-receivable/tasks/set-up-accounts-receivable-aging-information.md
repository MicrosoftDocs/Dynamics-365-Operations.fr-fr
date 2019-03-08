---
title: Paramétrer et générer des informations sur la plage âgée de la comptabilité client
description: Ce guide vous aidera à paramétrer une définition de plage âgée, des soldes client échus et à afficher des soldes dans la liste Solde échu et sur la page Recouvrement.
author: mikefalkner
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9fd8738cfd3466464c9fec1760e9a369ff3a4a67
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "334632"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a><span data-ttu-id="341c9-103">Paramétrer et générer des informations sur la plage âgée de la comptabilité client</span><span class="sxs-lookup"><span data-stu-id="341c9-103">Set up and generate accounts receivable aging information</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="341c9-104">Ce guide vous aidera à paramétrer une définition de plage âgée, des soldes client échus et à afficher des soldes dans la liste Solde échu et sur la page Recouvrement.</span><span class="sxs-lookup"><span data-stu-id="341c9-104">This guide will help you set up an aging period definition, age customer balances, and view balances in the Aged balance list and the Collections page.</span></span> <span data-ttu-id="341c9-105">La société fictive USMF sert d'exemple dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="341c9-105">This recording uses the USMF demo company.</span></span>


## <a name="create-an-aging-period-definition"></a><span data-ttu-id="341c9-106">Créer une définition de plage âgée</span><span class="sxs-lookup"><span data-stu-id="341c9-106">Create an aging period definition</span></span>
1. <span data-ttu-id="341c9-107">Accédez à Crédit et relances > Paramétrage > Définitions de plage âgée.</span><span class="sxs-lookup"><span data-stu-id="341c9-107">Go to Credit and collections > Setup > Aging period definitions.</span></span>
2. <span data-ttu-id="341c9-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="341c9-108">Click New.</span></span>
3. <span data-ttu-id="341c9-109">Entrez une valeur dans le champ Définition de la plage âgée.</span><span class="sxs-lookup"><span data-stu-id="341c9-109">In the Aging period definition field, type a value.</span></span>
4. <span data-ttu-id="341c9-110">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="341c9-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="341c9-111">Cliquez sur Ajouter au-dessous pour insérer une nouvelle plage âgée.</span><span class="sxs-lookup"><span data-stu-id="341c9-111">Click Add below to insert a new aging period.</span></span>
6. <span data-ttu-id="341c9-112">Dans le champ Période, entrez la description à indiquer sur les balances âgées.</span><span class="sxs-lookup"><span data-stu-id="341c9-112">In the Period field, enter the description to show on aging reports.</span></span>
7. <span data-ttu-id="341c9-113">Entrez un numéro dans le champ Unité.</span><span class="sxs-lookup"><span data-stu-id="341c9-113">In the Unit field, enter a number.</span></span>
8. <span data-ttu-id="341c9-114">Sélectionnez une option dans le champ Intervalle.</span><span class="sxs-lookup"><span data-stu-id="341c9-114">In the Interval field, select an option.</span></span>
    * <span data-ttu-id="341c9-115">La période comptable correspond à la période de votre calendrier comptable.</span><span class="sxs-lookup"><span data-stu-id="341c9-115">Ledger period matches the period to your ledger calendar.</span></span> <span data-ttu-id="341c9-116">Le jour, la semaine, le mois, le trimestre et les années définissent l'étendue de l'intervalle par type de date.</span><span class="sxs-lookup"><span data-stu-id="341c9-116">Day, week, month, quarter and years define the size of the interval by date type.</span></span> <span data-ttu-id="341c9-117">L'option Illimité permet de sélectionner l'ensemble des transactions avant ou après la période précédente, selon qu'il s'agisse de la première ou la dernière période.</span><span class="sxs-lookup"><span data-stu-id="341c9-117">Unlimited selects all transactions before or after the previous period, depending on whether it is the first or last period.</span></span>  
9. <span data-ttu-id="341c9-118">Sélectionnez une option dans le champ Indicateur âgé.</span><span class="sxs-lookup"><span data-stu-id="341c9-118">In the Aging indicator field, select an option.</span></span>
10. <span data-ttu-id="341c9-119">Sélectionnez la période en haut de la grille.</span><span class="sxs-lookup"><span data-stu-id="341c9-119">Select the period at the top of the grid.</span></span> <span data-ttu-id="341c9-120">Mettez la description à jour pour décrire la période la plus ancienne dans la définition de plage âgée.</span><span class="sxs-lookup"><span data-stu-id="341c9-120">Update the description to describe the oldest period in the aging period definition</span></span>
11. <span data-ttu-id="341c9-121">Entrez la nouvelle description de la plage âgée dans le champ Période.</span><span class="sxs-lookup"><span data-stu-id="341c9-121">In the Period field, enter the new description of the aging period.</span></span>
12. <span data-ttu-id="341c9-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="341c9-122">Close the page.</span></span>

## <a name="age-the-balances"></a><span data-ttu-id="341c9-123">Définir l'âge des soldes</span><span class="sxs-lookup"><span data-stu-id="341c9-123">Age the balances</span></span>
1. <span data-ttu-id="341c9-124">Accédez à Crédit et relances > Tâches périodiques > Soldes client échus.</span><span class="sxs-lookup"><span data-stu-id="341c9-124">Go to Credit and collections > Periodic tasks > Age customer balances.</span></span>
2. <span data-ttu-id="341c9-125">Dans le champ Définition de la plage âgée, sélectionnez la définition de plage âgée que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="341c9-125">In the Aging period definition field, select the aging period definition that you created.</span></span>
    * <span data-ttu-id="341c9-126">Vous pouvez avoir un instantané actif pour chaque définition de plage âgée.</span><span class="sxs-lookup"><span data-stu-id="341c9-126">You can have one active snapshot for each aging period definition.</span></span>  
    * <span data-ttu-id="341c9-127">Tous les clients sont traités par défaut.</span><span class="sxs-lookup"><span data-stu-id="341c9-127">All customers are processed by default.</span></span> <span data-ttu-id="341c9-128">Vous pouvez utiliser cette sélection pour calculer un seul regroupement de recouvrements de clients.</span><span class="sxs-lookup"><span data-stu-id="341c9-128">You can use this selection to calculate a single collections pool of customers.</span></span>  
    * <span data-ttu-id="341c9-129">Sélectionnez la date de la transaction que vous utiliserez pour la balance âgée.</span><span class="sxs-lookup"><span data-stu-id="341c9-129">Select the date from the transaction that you will use for the aging.</span></span>  
    * <span data-ttu-id="341c9-130">Sélectionnez une date « en date du » pour la balance âgée.</span><span class="sxs-lookup"><span data-stu-id="341c9-130">Select an "as of" date for aging.</span></span> <span data-ttu-id="341c9-131">La valeur par défaut est la date du jour, mais si vous remplacez ce champ par Date sélectionnée, vous pourrez choisir la date que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="341c9-131">The default is today but, if you change this field to Selected date, you will be able to pick the date that you want.</span></span> <span data-ttu-id="341c9-132">Utilisez la date du jour pour le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="341c9-132">For batch processing, use Today's date.</span></span>  
3. <span data-ttu-id="341c9-133">Développez la plage de la société.</span><span class="sxs-lookup"><span data-stu-id="341c9-133">Expand the Company range.</span></span> <span data-ttu-id="341c9-134">Vous pouvez sélectionner les sociétés qui seront incluses dans l'instantané.</span><span class="sxs-lookup"><span data-stu-id="341c9-134">You can select the companies that will be included in the snapshot.</span></span> <span data-ttu-id="341c9-135">La société actuelle est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="341c9-135">The current company is selected by default.</span></span>
4. <span data-ttu-id="341c9-136">Cliquez sur OK pour traiter l'instantané.</span><span class="sxs-lookup"><span data-stu-id="341c9-136">Click Ok to process the snapshot.</span></span> <span data-ttu-id="341c9-137">Cela prendra un certain du temps, vous devez donc attendre que le curseur disparaisse et consulter les messages du centre de message.</span><span class="sxs-lookup"><span data-stu-id="341c9-137">It will take some time so wait for the slider to disappear and check the message center for a message.</span></span>

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a><span data-ttu-id="341c9-138">Afficher les soldes dans la liste Soldes chronologiques et dans la page Collection</span><span class="sxs-lookup"><span data-stu-id="341c9-138">View the balances on the Aged balances list and on the Collection page</span></span>
1. <span data-ttu-id="341c9-139">Accédez à Crédit et relances > Collections > Soldes chronologiques.</span><span class="sxs-lookup"><span data-stu-id="341c9-139">Go to Credit and collections > Collections > Aged balances.</span></span>
    * <span data-ttu-id="341c9-140">La page de liste affiche les soldes du client.</span><span class="sxs-lookup"><span data-stu-id="341c9-140">The list page shows the balances for the customer.</span></span> <span data-ttu-id="341c9-141">L'icône de balance âgée indique la plage âgée de la transaction la plus ancienne.</span><span class="sxs-lookup"><span data-stu-id="341c9-141">The aging icon shows the aging period for the oldest transaction.</span></span>  
2. <span data-ttu-id="341c9-142">Sélectionnez un client avec un solde.</span><span class="sxs-lookup"><span data-stu-id="341c9-142">Select a customer with a balance.</span></span>
3. <span data-ttu-id="341c9-143">Développez la zone de récapitulatif Âgé pour afficher les balances âgées.</span><span class="sxs-lookup"><span data-stu-id="341c9-143">Expand the Aging fact box area to view the aged balances.</span></span>
    * <span data-ttu-id="341c9-144">La définition de plage âgée pour le récapitulatif provient de celle par défaut spécifiée dans les paramètres.</span><span class="sxs-lookup"><span data-stu-id="341c9-144">The aging period definition for the fact box is taken from the default aging period definition specified in the parameters.</span></span> <span data-ttu-id="341c9-145">Vous pouvez la modifier à l'aide du menu Collecter.</span><span class="sxs-lookup"><span data-stu-id="341c9-145">You can change it using the Collect menu.</span></span>  

