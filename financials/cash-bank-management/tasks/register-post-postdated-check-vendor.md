--- 
title: "Enregistrement et validation d'un chèque postdaté pour un fournisseur"
description: "Vous pouvez enregistrer les détails d'un chèque postdaté avant sa remise à un fournisseur, par l'intermédiaire du n° document de journal."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8689421d3281f93af9298f777f92c5c3b2c1c86c
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a><span data-ttu-id="0d002-103">Enregistrement et validation d'un chèque postdaté pour un fournisseur</span><span class="sxs-lookup"><span data-stu-id="0d002-103">Register and post a postdated check for a vendor</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0d002-104">Vous pouvez enregistrer les détails d'un chèque postdaté avant sa remise à un fournisseur, par l'intermédiaire du n° document de journal.</span><span class="sxs-lookup"><span data-stu-id="0d002-104">You can register the details of a postdated check before you issue the check to a vendor by using the journal voucher.</span></span> <span data-ttu-id="0d002-105">Vous pouvez également valider le chèque postdaté et générer des transactions financières.</span><span class="sxs-lookup"><span data-stu-id="0d002-105">You can also post the postdated check and generate financial transactions.</span></span> <span data-ttu-id="0d002-106">Avant d'enregistrer et de valider un chèque postdaté reçu d'un client, effectuez la tâche suivante :</span><span class="sxs-lookup"><span data-stu-id="0d002-106">Before you register and post a postdated check from a vendor, complete the following task:</span></span> 

<span data-ttu-id="0d002-107">Paramétrer des chèques postdatés dans la page Gestion de la trésorerie et de la banque.</span><span class="sxs-lookup"><span data-stu-id="0d002-107">Set up postdated checks in the Cash and bank management page.</span></span> 



<span data-ttu-id="0d002-108">Le rôle de ces guides de tâches est Trésorier.</span><span class="sxs-lookup"><span data-stu-id="0d002-108">The role of this task guides is Treasurer.</span></span> <span data-ttu-id="0d002-109">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="0d002-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="0d002-110">Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="0d002-110">Go to Acounts payable > Payments > Payment journal</span></span>
2. <span data-ttu-id="0d002-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="0d002-111">Click New.</span></span>
3. <span data-ttu-id="0d002-112">Dans le champ Nom, tapez « VendPay ».</span><span class="sxs-lookup"><span data-stu-id="0d002-112">In the Name field, type 'VendPay'.</span></span>
4. <span data-ttu-id="0d002-113">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="0d002-113">Click Lines.</span></span>
5. <span data-ttu-id="0d002-114">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="0d002-114">In the Account field, specify the desired values.</span></span>
6. <span data-ttu-id="0d002-115">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0d002-115">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="0d002-116">Entrez un nombre dans le champ Débit.</span><span class="sxs-lookup"><span data-stu-id="0d002-116">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="0d002-117">Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="0d002-117">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="0d002-118">Sélectionner le mode de paiement du chèque postdaté</span><span class="sxs-lookup"><span data-stu-id="0d002-118">Select the method of payment for the postdated check</span></span>  
9. <span data-ttu-id="0d002-119">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0d002-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="0d002-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0d002-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="0d002-121">Cliquez sur l'onglet Chèques postdatés.</span><span class="sxs-lookup"><span data-stu-id="0d002-121">Click the Postdated checks tab.</span></span>
12. <span data-ttu-id="0d002-122">Dans le champ Numéro du chèque, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0d002-122">In the Check number field, type a value.</span></span>
    * <span data-ttu-id="0d002-123">Spécifiez ou modifiez le numéro du chèque postdaté.</span><span class="sxs-lookup"><span data-stu-id="0d002-123">Enter or modify the number of the postdated check.</span></span>  
13. <span data-ttu-id="0d002-124">Dans le champ Nom de la banque émettrice, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0d002-124">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="0d002-125">Entrez les détails bancaires pour la banque émettrice.</span><span class="sxs-lookup"><span data-stu-id="0d002-125">enter the bank details for the issuing bank.</span></span>  
14. <span data-ttu-id="0d002-126">Cliquez sur l'onglet Liste.</span><span class="sxs-lookup"><span data-stu-id="0d002-126">Click the List tab.</span></span>
15. <span data-ttu-id="0d002-127">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="0d002-127">Click Post.</span></span>
16. <span data-ttu-id="0d002-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0d002-128">Close the page.</span></span>
17. <span data-ttu-id="0d002-129">Cliquez sur l'onglet Chèques postdatés.</span><span class="sxs-lookup"><span data-stu-id="0d002-129">Click the Postdated checks tab.</span></span>


