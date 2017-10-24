--- 
title: "Enregistrer et valider un chèque postdaté pour un client"
description: "Vous pouvez enregistrer les informations relatives à un chèque postdaté reçu d'un client."
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1610036815349f625a67d5dd67260114d42fff97
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="register-and-post-a-postdated-check-for-a-customer"></a><span data-ttu-id="6332e-103">Enregistrer et valider un chèque postdaté pour un client</span><span class="sxs-lookup"><span data-stu-id="6332e-103">Register and post a postdated check for a customer</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6332e-104">Vous pouvez enregistrer les informations relatives à un chèque postdaté reçu d'un client.</span><span class="sxs-lookup"><span data-stu-id="6332e-104">You can register details of a postdated cheque received from a customer.</span></span> <span data-ttu-id="6332e-105">Vous pouvez également valider le chèque postdaté et générer des transactions financières.</span><span class="sxs-lookup"><span data-stu-id="6332e-105">You can also post the postdated cheque and generate financial transactions.</span></span>   <span data-ttu-id="6332e-106">Effectuez les tâches suivantes avant d'enregistrer et de valider un chèque postdaté reçu d'un client :   • Paramétrez les chèques postdatés dans la page Gestion de la trésorerie et de la banque • Paramétrez un mode de paiement pour les chèques postdatés. Le rôle pour cette procédure est Trésorier.</span><span class="sxs-lookup"><span data-stu-id="6332e-106">Complete the following tasks before you register and post a postdated cheque received from a customer:   • Set up postdated Cheques in the Cash and bank management page • Set up a method of payment for postdated Cheques   The role for this procedure is Treasurer.</span></span> <span data-ttu-id="6332e-107">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="6332e-107">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="6332e-108">Accédez à Comptabilité client > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="6332e-108">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="6332e-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6332e-109">Click New.</span></span>
3. <span data-ttu-id="6332e-110">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="6332e-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="6332e-111">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="6332e-111">Click Lines.</span></span>
5. <span data-ttu-id="6332e-112">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6332e-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="6332e-113">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="6332e-113">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="6332e-114">Entrez un numéro dans le champ Crédit.</span><span class="sxs-lookup"><span data-stu-id="6332e-114">In the Credit field, enter a number.</span></span>
    * <span data-ttu-id="6332e-115">Entrez le montant spécifié dans le chèque postdaté.</span><span class="sxs-lookup"><span data-stu-id="6332e-115">Enter the amount specified in the postdated cheque.</span></span>  
8. <span data-ttu-id="6332e-116">Cliquez sur l'onglet Paiement.</span><span class="sxs-lookup"><span data-stu-id="6332e-116">Click the Payment tab.</span></span>
9. <span data-ttu-id="6332e-117">Tapez une valeur dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="6332e-117">In the Method of payment field, type a value.</span></span>
    * <span data-ttu-id="6332e-118">Sélectionner le mode de paiement du chèque postdaté</span><span class="sxs-lookup"><span data-stu-id="6332e-118">Select the method of payment for the postdated cheque</span></span>  
10. <span data-ttu-id="6332e-119">Cliquez sur l'onglet Chèques postdatés.</span><span class="sxs-lookup"><span data-stu-id="6332e-119">Click the Postdated checks tab.</span></span>
11. <span data-ttu-id="6332e-120">Dans le champ Date d'échéance, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="6332e-120">In the Maturity date field, enter a date.</span></span>
    * <span data-ttu-id="6332e-121">Entrez la date de paiement du chèque postdaté.</span><span class="sxs-lookup"><span data-stu-id="6332e-121">Enter the date when the postdated cheque is due for payment.</span></span>  
12. <span data-ttu-id="6332e-122">Dans le champ Filiale de la banque émettrice, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6332e-122">In the Issuing bank branch field, type a value.</span></span>
    * <span data-ttu-id="6332e-123">Entrez les détails sur la banque du chèque postdaté.</span><span class="sxs-lookup"><span data-stu-id="6332e-123">Enter the bank details of the postdated cheque.</span></span>  
13. <span data-ttu-id="6332e-124">Dans le champ Numéro du chèque, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6332e-124">In the cheque number field, type a value.</span></span>
14. <span data-ttu-id="6332e-125">Dans le champ Nom de la banque émettrice, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6332e-125">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="6332e-126">Entrez les détails sur la banque du chèque postdaté.</span><span class="sxs-lookup"><span data-stu-id="6332e-126">Enter the bank details of the postdated check.</span></span>  
15. <span data-ttu-id="6332e-127">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="6332e-127">Click Post.</span></span>
16. <span data-ttu-id="6332e-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6332e-128">Close the page.</span></span>


