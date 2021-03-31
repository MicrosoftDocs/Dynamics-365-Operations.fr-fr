---
title: Enregistrement et validation d’un chèque postdaté pour un fournisseur
description: Vous pouvez enregistrer les détails d’un chèque postdaté avant sa remise à un fournisseur, par l’intermédiaire du n° document de journal.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ffd482facc629e65a79f328cb237fd72f6f6b5c5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5225319"
---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a><span data-ttu-id="6bdaf-103">Enregistrement et validation d’un chèque postdaté pour un fournisseur</span><span class="sxs-lookup"><span data-stu-id="6bdaf-103">Register and post a postdated check for a vendor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6bdaf-104">Vous pouvez enregistrer les détails d’un chèque postdaté avant sa remise à un fournisseur, par l’intermédiaire du n° document de journal.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-104">You can register the details of a postdated check before you issue the check to a vendor by using the journal voucher.</span></span> <span data-ttu-id="6bdaf-105">Vous pouvez également valider le chèque postdaté et générer des transactions financières.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-105">You can also post the postdated check and generate financial transactions.</span></span> <span data-ttu-id="6bdaf-106">Avant d’enregistrer et de valider un chèque postdaté reçu d’un client, effectuez la tâche suivante :</span><span class="sxs-lookup"><span data-stu-id="6bdaf-106">Before you register and post a postdated check from a vendor, complete the following task:</span></span> 

<span data-ttu-id="6bdaf-107">Paramétrer des chèques postdatés dans la page Gestion de la trésorerie et de la banque.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-107">Set up postdated checks in the Cash and bank management page.</span></span> 



<span data-ttu-id="6bdaf-108">Le rôle de ces guides de tâches est Trésorier.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-108">The role of this task guides is Treasurer.</span></span> <span data-ttu-id="6bdaf-109">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="6bdaf-110">Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-110">Go to Acounts payable > Payments > Payment journal</span></span>
2. <span data-ttu-id="6bdaf-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-111">Click New.</span></span>
3. <span data-ttu-id="6bdaf-112">Dans le champ Nom, tapez « VendPay ».</span><span class="sxs-lookup"><span data-stu-id="6bdaf-112">In the Name field, type 'VendPay'.</span></span>
4. <span data-ttu-id="6bdaf-113">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-113">Click Lines.</span></span>
5. <span data-ttu-id="6bdaf-114">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-114">In the Account field, specify the desired values.</span></span>
6. <span data-ttu-id="6bdaf-115">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-115">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="6bdaf-116">Entrez un nombre dans le champ Débit.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-116">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="6bdaf-117">Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-117">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6bdaf-118">Sélectionner le mode de paiement du chèque postdaté</span><span class="sxs-lookup"><span data-stu-id="6bdaf-118">Select the method of payment for the postdated check</span></span>  
9. <span data-ttu-id="6bdaf-119">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="6bdaf-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="6bdaf-121">Cliquez sur l’onglet Chèques postdatés.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-121">Click the Postdated checks tab.</span></span>
12. <span data-ttu-id="6bdaf-122">Dans le champ Numéro du chèque, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-122">In the Check number field, type a value.</span></span>
    * <span data-ttu-id="6bdaf-123">Spécifiez ou modifiez le numéro du chèque postdaté.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-123">Enter or modify the number of the postdated check.</span></span>  
13. <span data-ttu-id="6bdaf-124">Dans le champ Nom de la banque émettrice, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-124">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="6bdaf-125">Entrez les détails bancaires pour la banque émettrice.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-125">enter the bank details for the issuing bank.</span></span>  
14. <span data-ttu-id="6bdaf-126">Cliquez sur l’onglet Liste.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-126">Click the List tab.</span></span>
15. <span data-ttu-id="6bdaf-127">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-127">Click Post.</span></span>
16. <span data-ttu-id="6bdaf-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-128">Close the page.</span></span>
17. <span data-ttu-id="6bdaf-129">Cliquez sur l’onglet Chèques postdatés.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-129">Click the Postdated checks tab.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]