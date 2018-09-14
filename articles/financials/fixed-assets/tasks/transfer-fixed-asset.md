--- 
title: "Transférer une immobilisation"
description: "Ce Guide de tâche transfèrera les informations financières pour un registre d'immobilisation provenant d'un ensemble de dimensions financières vers le nouvel ensemble de dimensions financières."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: bb8a5b94d9a0bb510daa2a698524e0c380597991
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="transfer-a-fixed-asset"></a><span data-ttu-id="0a54b-103">Transférer une immobilisation</span><span class="sxs-lookup"><span data-stu-id="0a54b-103">Transfer a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0a54b-104">Ce Guide de tâche transfèrera les informations financières pour un registre d'immobilisation provenant d'un ensemble de dimensions financières vers le nouvel ensemble de dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="0a54b-104">This task guide will transfer the financial information for a fixed asset book from one financial dimension set to a new financial dimension set.</span></span>  <span data-ttu-id="0a54b-105">Il utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="0a54b-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="0a54b-106">Accédez à Immobilisations > Immobilisations > Immobilisations.</span><span class="sxs-lookup"><span data-stu-id="0a54b-106">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="0a54b-107">Dans la liste, recherchez et sélectionnez l'immobilisation à transférer.</span><span class="sxs-lookup"><span data-stu-id="0a54b-107">In the list, find and select the fixed asset to transfer.</span></span>
3. <span data-ttu-id="0a54b-108">Cliquez sur Immobilisation dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="0a54b-108">On the Action Pane, click Fixed asset.</span></span>
4. <span data-ttu-id="0a54b-109">Cliquez sur Transférer des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="0a54b-109">Click Transfer fixed assets.</span></span>
5. <span data-ttu-id="0a54b-110">Entrez une date dans le champ Date de transfert.</span><span class="sxs-lookup"><span data-stu-id="0a54b-110">In the Transfer date field, enter a date.</span></span>
6. <span data-ttu-id="0a54b-111">Entrez des commentaires pour décrire le transfert.</span><span class="sxs-lookup"><span data-stu-id="0a54b-111">Enter comments to describe the transfer.</span></span>
    * <span data-ttu-id="0a54b-112">Cette liste répertorie tous les registres pour l'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="0a54b-112">This list shows all books for the fixed asset.</span></span>  
7. <span data-ttu-id="0a54b-113">Marquez les registres à transférer vers le nouvel ensemble de dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="0a54b-113">Mark the books you want to transfer to a new financial dimension set.</span></span>
    * <span data-ttu-id="0a54b-114">Cette liste répertorie les valeurs de dimension financière existantes pour le registre sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0a54b-114">This list shows the existing financial dimension values for the selected book.</span></span>  
    * <span data-ttu-id="0a54b-115">Sélectionnez la dimension financière que vous souhaitez mettre à jour pour le registre d'immobilisation sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0a54b-115">Select the financial dimension you want to update for the selected fixed asset book.</span></span>  
8. <span data-ttu-id="0a54b-116">Dans le champ Dimension financière, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="0a54b-116">In the Financial dimension field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="0a54b-117">Définissez d'autres valeurs de dimension financière, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="0a54b-117">Set other financial dimension values as appropriate.</span></span>  
    * <span data-ttu-id="0a54b-118">Toutes les valeurs de dimension financière sont modifiées lorsqu'un transfert a lieu, même si une valeur a été entrée ou est laissée vide.</span><span class="sxs-lookup"><span data-stu-id="0a54b-118">All financial dimension values change when a transfer occurs, whether a value has been entered or left blank.</span></span> <span data-ttu-id="0a54b-119">Par exemple, si vous avez entré une valeur pour BusinessUnit et laissé les dimensions financières pour CostCenter et Département vides.</span><span class="sxs-lookup"><span data-stu-id="0a54b-119">For example, if you entered a value for the BusinessUnit and left the CostCenter and Department financial dimensions blank.</span></span> <span data-ttu-id="0a54b-120">Si votre structure de compte avait autorisé les valeurs vides pour CostCenter et Département, suite au transfert, chaque modèle de valeur aurait eu la nouvelle valeur pour BusinessUnit et une valeur vide pour CostCenter et Département.</span><span class="sxs-lookup"><span data-stu-id="0a54b-120">If your account structure allows blank values for CostCenter and Department, the transfer would result in each value model having the new value for BusinessUnit and a blank value for CostCenter and Department.</span></span>  
9. <span data-ttu-id="0a54b-121">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="0a54b-121">Click Update.</span></span>
    * <span data-ttu-id="0a54b-122">Vous pouvez prévisualiser les modifications avant de finaliser le transfert.</span><span class="sxs-lookup"><span data-stu-id="0a54b-122">You have the opportunity to preview the changes before finalizing the transfer.</span></span>  
    * <span data-ttu-id="0a54b-123">Réexaminez les résultats avant de transférer les registres d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="0a54b-123">Review results before transferring the fixed asset books.</span></span>  
10. <span data-ttu-id="0a54b-124">Cliquez sur Transférer.</span><span class="sxs-lookup"><span data-stu-id="0a54b-124">Click Transfer.</span></span>


