--- 
title: Traiter les remises pour le paiement
description: "Cette procédure illustre comment convertir des remises client approuvées et traitées en avoirs."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 791ec304b9ea7c49fbea506d73c4daffd4478739
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="process-rebates-for-payment"></a><span data-ttu-id="2319e-103">Traiter les remises pour le paiement</span><span class="sxs-lookup"><span data-stu-id="2319e-103">Process rebates for payment</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2319e-104">Cette procédure illustre comment convertir des remises client approuvées et traitées en avoirs.</span><span class="sxs-lookup"><span data-stu-id="2319e-104">This procedure demonstrates how to convert approved and processed customer rebates to credit notes.</span></span> <span data-ttu-id="2319e-105">Vous pouvez utiliser ce guide à l'aide de la société USMF fictive.</span><span class="sxs-lookup"><span data-stu-id="2319e-105">You can use this guide in the USMF demo company.</span></span> <span data-ttu-id="2319e-106">La condition préalable à ce guide est d'avoir une ou plusieurs réclamations de remise qui présentent le statut Marquer.</span><span class="sxs-lookup"><span data-stu-id="2319e-106">The precondition for this guide is to have one or more rebate claims which have a status of Mark.</span></span> <span data-ttu-id="2319e-107">Si vous utilisez USMF, vous devez exécuter le guide « Générer et traiter les remises client » avant de lancer ce guide.</span><span class="sxs-lookup"><span data-stu-id="2319e-107">If you’re using USMF you should run the "Generate and process customer rebates" guide before you start this guide.</span></span>


## <a name="convert-rebate-claims-to-credit-note"></a><span data-ttu-id="2319e-108">Convertir des réclamations de remise en avoir</span><span class="sxs-lookup"><span data-stu-id="2319e-108">Convert rebate claims to credit note</span></span>
1. <span data-ttu-id="2319e-109">Accédez à Tous les clients.</span><span class="sxs-lookup"><span data-stu-id="2319e-109">Go to All customers.</span></span>
2. <span data-ttu-id="2319e-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2319e-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="2319e-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2319e-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="2319e-112">Cliquez sur Collecter dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="2319e-112">On the Action Pane, click Collect.</span></span>
5. <span data-ttu-id="2319e-113">Cliquez sur Régler les transactions.</span><span class="sxs-lookup"><span data-stu-id="2319e-113">Click Settle transactions.</span></span>
6. <span data-ttu-id="2319e-114">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="2319e-114">Click Functions.</span></span>
7. <span data-ttu-id="2319e-115">Cliquez sur Programme de remises.</span><span class="sxs-lookup"><span data-stu-id="2319e-115">Click Rebate program.</span></span>
    * <span data-ttu-id="2319e-116">La page Remise répertorie la réclamation de remise que vous avez traitée dans la console des remises client et dont le statut est Marquer.</span><span class="sxs-lookup"><span data-stu-id="2319e-116">The Rebate page lists the rebate claims that you have processed in the customer rebate workbench and that are in status Mark.</span></span>    
8. <span data-ttu-id="2319e-117">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="2319e-117">Click Edit.</span></span>
    * <span data-ttu-id="2319e-118">Définissez les traits de repère dans le champ Marquer pour les réclamations à inclure dans l'avoir.</span><span class="sxs-lookup"><span data-stu-id="2319e-118">Set checkmarks in the Mark field for the claims that you want to include into credit note.</span></span>   
9. <span data-ttu-id="2319e-119">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="2319e-119">Click Functions.</span></span>
10. <span data-ttu-id="2319e-120">Cliquez sur Créer un avoir.</span><span class="sxs-lookup"><span data-stu-id="2319e-120">Click Create credit note.</span></span>
    * <span data-ttu-id="2319e-121">Un message vous informe qu'un journal a été validé (il s'agit du journal des consommations de comptabilité client, comme indiqué dans la page Paramètres comptabilité).</span><span class="sxs-lookup"><span data-stu-id="2319e-121">A message appears to inform you that a journal has been posted (This is the Accounts receivable consumption journal, as specified in the Accounts receivable parameters page).</span></span> <span data-ttu-id="2319e-122">Cela entraîne le déplacement du montant réel passif (crédit) vers le solde du client.</span><span class="sxs-lookup"><span data-stu-id="2319e-122">This causes the real liability (credit) amount to be moved to the customer balance.</span></span> <span data-ttu-id="2319e-123">Cela signifie que le compte du client est crédité et que le compte de régularisation des remises est débité.</span><span class="sxs-lookup"><span data-stu-id="2319e-123">This means that the customer’s account has been credited, and the Rebate accrual account has been debited.</span></span>  
11. <span data-ttu-id="2319e-124">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2319e-124">Close the page.</span></span>
12. <span data-ttu-id="2319e-125">Cliquez sur Annuler.</span><span class="sxs-lookup"><span data-stu-id="2319e-125">Click Cancel.</span></span>
    * <span data-ttu-id="2319e-126">Cela actualise la page afin de pouvoir afficher les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="2319e-126">This refreshes the page so that you can see the updates.</span></span>  
13. <span data-ttu-id="2319e-127">Cliquez sur Collecter dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="2319e-127">On the Action Pane, click Collect.</span></span>
14. <span data-ttu-id="2319e-128">Cliquez sur Régler les transactions.</span><span class="sxs-lookup"><span data-stu-id="2319e-128">Click Settle transactions.</span></span>
    * <span data-ttu-id="2319e-129">Notez qu'une transaction pour un montant négatif, représentant le montant total de remise, sans référence de facture a été ajoutée au solde client.</span><span class="sxs-lookup"><span data-stu-id="2319e-129">Note that a transaction for negative amount, representing the total rebate amount, without invoice reference has been added to the customer balance.</span></span>   
15. <span data-ttu-id="2319e-130">Cliquez sur Annuler.</span><span class="sxs-lookup"><span data-stu-id="2319e-130">Click Cancel.</span></span>


