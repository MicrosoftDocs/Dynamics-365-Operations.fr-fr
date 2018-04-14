--- 
title: "Enregistrement et validation d'un chèque postdaté pour un fournisseur"
description: "Vous pouvez enregistrer les détails d'un chèque postdaté avant sa remise à un fournisseur, par l'intermédiaire du n° document de journal."
author: kweekley
manager: AnnBe
ms.date: 10/31/2017
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: cd00227ed6d288a4b2041630bc7a604ac94d3c70
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a><span data-ttu-id="08acc-103">Enregistrement et validation d'un chèque postdaté pour un fournisseur</span><span class="sxs-lookup"><span data-stu-id="08acc-103">Register and post a postdated check for a vendor</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="08acc-104">Vous pouvez enregistrer les détails d'un chèque postdaté avant sa remise à un fournisseur, par l'intermédiaire du n° document de journal.</span><span class="sxs-lookup"><span data-stu-id="08acc-104">You can register the details of a postdated check before you issue the check to a vendor by using the journal voucher.</span></span> <span data-ttu-id="08acc-105">Vous pouvez également valider le chèque postdaté et générer des transactions financières.</span><span class="sxs-lookup"><span data-stu-id="08acc-105">You can also post the postdated check and generate financial transactions.</span></span> <span data-ttu-id="08acc-106">Avant d'enregistrer et de valider un chèque postdaté reçu d'un client, effectuez la tâche suivante :</span><span class="sxs-lookup"><span data-stu-id="08acc-106">Before you register and post a postdated check from a vendor, complete the following task:</span></span> 

<span data-ttu-id="08acc-107">Paramétrer des chèques postdatés dans la page Gestion de la trésorerie et de la banque.</span><span class="sxs-lookup"><span data-stu-id="08acc-107">Set up postdated checks in the Cash and bank management page.</span></span> 



<span data-ttu-id="08acc-108">Le rôle de ces guides de tâches est Trésorier.</span><span class="sxs-lookup"><span data-stu-id="08acc-108">The role of this task guides is Treasurer.</span></span> <span data-ttu-id="08acc-109">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="08acc-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="08acc-110">Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="08acc-110">Go to Accounts payable > Payments > Payment journal</span></span>
2. <span data-ttu-id="08acc-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="08acc-111">Click New.</span></span>
3. <span data-ttu-id="08acc-112">Dans le champ Nom, tapez « VendPay ».</span><span class="sxs-lookup"><span data-stu-id="08acc-112">In the Name field, type 'VendPay'.</span></span>
4. <span data-ttu-id="08acc-113">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="08acc-113">Click Lines.</span></span>
5. <span data-ttu-id="08acc-114">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="08acc-114">In the Account field, specify the desired values.</span></span>
6. <span data-ttu-id="08acc-115">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="08acc-115">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="08acc-116">Entrez un nombre dans le champ Débit.</span><span class="sxs-lookup"><span data-stu-id="08acc-116">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="08acc-117">Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="08acc-117">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="08acc-118">Sélectionner le mode de paiement du chèque postdaté</span><span class="sxs-lookup"><span data-stu-id="08acc-118">Select the method of payment for the postdated check</span></span>  
9. <span data-ttu-id="08acc-119">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="08acc-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="08acc-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="08acc-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="08acc-121">Cliquez sur l'onglet Chèques postdatés.</span><span class="sxs-lookup"><span data-stu-id="08acc-121">Click the Postdated checks tab.</span></span>
12. <span data-ttu-id="08acc-122">Dans le champ Numéro du chèque, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="08acc-122">In the Check number field, type a value.</span></span>
    * <span data-ttu-id="08acc-123">Spécifiez ou modifiez le numéro du chèque postdaté.</span><span class="sxs-lookup"><span data-stu-id="08acc-123">Enter or modify the number of the postdated check.</span></span>  
13. <span data-ttu-id="08acc-124">Dans le champ Nom de la banque émettrice, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="08acc-124">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="08acc-125">Entrez les détails bancaires pour la banque émettrice.</span><span class="sxs-lookup"><span data-stu-id="08acc-125">enter the bank details for the issuing bank.</span></span>  
14. <span data-ttu-id="08acc-126">Cliquez sur l'onglet Liste.</span><span class="sxs-lookup"><span data-stu-id="08acc-126">Click the List tab.</span></span>
15. <span data-ttu-id="08acc-127">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="08acc-127">Click Post.</span></span>
16. <span data-ttu-id="08acc-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="08acc-128">Close the page.</span></span>
17. <span data-ttu-id="08acc-129">Cliquez sur l'onglet Chèques postdatés.</span><span class="sxs-lookup"><span data-stu-id="08acc-129">Click the Postdated checks tab.</span></span>


