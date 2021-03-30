---
title: Transférer une immobilisation
description: Ce Guide de tâche transfèrera les informations financières pour un registre d’immobilisation provenant d’un ensemble de dimensions financières vers le nouvel ensemble de dimensions financières.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 365fa7a54dcf6817f933c0d305561c5fd0f8ba27
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213482"
---
# <a name="transfer-a-fixed-asset"></a><span data-ttu-id="d1913-103">Transférer une immobilisation</span><span class="sxs-lookup"><span data-stu-id="d1913-103">Transfer a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d1913-104">Ce Guide de tâche transfèrera les informations financières pour un registre d’immobilisation provenant d’un ensemble de dimensions financières vers le nouvel ensemble de dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="d1913-104">This task guide will transfer the financial information for a fixed asset book from one financial dimension set to a new financial dimension set.</span></span>  <span data-ttu-id="d1913-105">Il utilise le rôle de comptable et les données de démonstration de l’entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="d1913-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="d1913-106">Dans le volet de navigation, accédez à **Modules > Immobilisations > Immobilisations > Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="d1913-106">In the Navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="d1913-107">Dans la liste, recherchez et sélectionnez l’immobilisation à transférer.</span><span class="sxs-lookup"><span data-stu-id="d1913-107">In the list, find and select the fixed asset to transfer.</span></span>
3. <span data-ttu-id="d1913-108">Dans le volet Actions, cliquez sur **Immobilisation**.</span><span class="sxs-lookup"><span data-stu-id="d1913-108">On the Action Pane, click **Fixed asset**.</span></span>
4. <span data-ttu-id="d1913-109">Cliquez sur **Transférer des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="d1913-109">Click **Transfer fixed assets**.</span></span>
5. <span data-ttu-id="d1913-110">Entrez une date dans le champ **Date de transfert**.</span><span class="sxs-lookup"><span data-stu-id="d1913-110">In the **Transfer date** field, enter a date.</span></span>
6. <span data-ttu-id="d1913-111">Entrez des commentaires pour décrire le transfert.</span><span class="sxs-lookup"><span data-stu-id="d1913-111">Enter comments to describe the transfer.</span></span>
    
    <span data-ttu-id="d1913-112">Cette liste répertorie tous les registres pour l’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="d1913-112">This list shows all books for the fixed asset.</span></span>  
7. <span data-ttu-id="d1913-113">Marquez les registres à transférer vers le nouvel ensemble de dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="d1913-113">Mark the books you want to transfer to a new financial dimension set.</span></span>
    * <span data-ttu-id="d1913-114">Cette liste répertorie les valeurs de dimension financière existantes pour le registre sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d1913-114">This list shows the existing financial dimension values for the selected book.</span></span>  
    * <span data-ttu-id="d1913-115">Sélectionnez la dimension financière que vous souhaitez mettre à jour pour le registre d’immobilisation sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d1913-115">Select the financial dimension you want to update for the selected fixed asset book.</span></span>  
8. <span data-ttu-id="d1913-116">Dans le champ **Dimension financière**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="d1913-116">In the **Financial dimension** field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="d1913-117">Définissez d’autres valeurs de dimension financière, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="d1913-117">Set other financial dimension values as appropriate.</span></span>  
    * <span data-ttu-id="d1913-118">Toutes les valeurs de dimension financière sont modifiées lorsqu’un transfert a lieu, même si une valeur a été entrée ou est laissée vide.</span><span class="sxs-lookup"><span data-stu-id="d1913-118">All financial dimension values change when a transfer occurs, whether a value has been entered or left blank.</span></span> <span data-ttu-id="d1913-119">Par exemple, si vous avez entré une valeur pour BusinessUnit et laissé les dimensions financières pour CostCenter et Département vides.</span><span class="sxs-lookup"><span data-stu-id="d1913-119">For example, if you entered a value for the BusinessUnit and left the CostCenter and Department financial dimensions blank.</span></span> <span data-ttu-id="d1913-120">Si votre structure de compte avait autorisé les valeurs vides pour CostCenter et Département, suite au transfert, chaque modèle de valeur aurait eu la nouvelle valeur pour BusinessUnit et une valeur vide pour CostCenter et Département.</span><span class="sxs-lookup"><span data-stu-id="d1913-120">If your account structure allows blank values for CostCenter and Department, the transfer would result in each value model having the new value for BusinessUnit and a blank value for CostCenter and Department.</span></span>  
9. <span data-ttu-id="d1913-121">Cliquez sur **Mettre à jour**.</span><span class="sxs-lookup"><span data-stu-id="d1913-121">Click **Update**.</span></span>
    * <span data-ttu-id="d1913-122">Vous pouvez prévisualiser les modifications avant de finaliser le transfert.</span><span class="sxs-lookup"><span data-stu-id="d1913-122">You have the opportunity to preview the changes before finalizing the transfer.</span></span>  
    * <span data-ttu-id="d1913-123">Réexaminez les résultats avant de transférer les registres d’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="d1913-123">Review results before transferring the fixed asset books.</span></span>  
10. <span data-ttu-id="d1913-124">Cliquez sur **Transférer**.</span><span class="sxs-lookup"><span data-stu-id="d1913-124">Click **Transfer**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]