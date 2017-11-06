--- 
title: "Création de plans de régularisation"
description: "Ce guide accompagne l'utilisateur le long de la création d'un plan de régularisation."
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 324be23a1e26de0d05c7cf6a61567f7260d0c390
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-accrual-schemes"></a><span data-ttu-id="c2f3d-103">Création de plans de régularisation</span><span class="sxs-lookup"><span data-stu-id="c2f3d-103">Create accrual schemes</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c2f3d-104">Ce guide accompagne l'utilisateur le long de la création d'un plan de régularisation.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-104">This task guide steps through creating an accrual scheme.</span></span> <span data-ttu-id="c2f3d-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="c2f3d-106">Accédez à Comptabilité > Paramétrage du journal > Plans de régularisation.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-106">Go to General ledger > Journal setup > Accrual schemes.</span></span>
2. <span data-ttu-id="c2f3d-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-107">Click New.</span></span>
3. <span data-ttu-id="c2f3d-108">Dans le champ Identification de la régularisation, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-108">In the Accrual identification field, type a value.</span></span>
4. <span data-ttu-id="c2f3d-109">Dans le champ Description du plan de régularisation, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-109">In the Description of accrual scheme field, type a value.</span></span>
5. <span data-ttu-id="c2f3d-110">Dans le champ Débit, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-110">In the Debit field, specify the desired values.</span></span>
    * <span data-ttu-id="c2f3d-111">Le compte principal défini remplacera le compte principal de débit dans la ligne de N° document de journal et il sera également utilisé pour la contrepassation des différés en fonction des transactions de régularisation des comptes.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="c2f3d-112">Dans le champ Crédit, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-112">In the Credit field, specify the desired values.</span></span>
    * <span data-ttu-id="c2f3d-113">Le compte principal défini remplacera le compte principal de crédit dans la ligne de N° document de journal et il sera également utilisé pour la contrepassation des différés en fonction des transactions de régularisation des comptes.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="c2f3d-114">Dans le champ N° document, sélectionnez la manière dont vous souhaitez que le N° document soit déterminé lorsque les transactions sont validées.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-114">In the Voucher field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="c2f3d-115">Dans le champ Description, entrez une valeur pour décrire les transactions qui seront validées.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-115">In the Description field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="c2f3d-116">Dans le champ Fréquence, sélectionnez la fréquence à laquelle les transactions doivent se produire.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-116">In the Period frequency field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="c2f3d-117">Entrez un nombre dans le champ Occurrences par période.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-117">In the Number of occurrences by period field, enter a number.</span></span>
11. <span data-ttu-id="c2f3d-118">Dans le champ Valider les transactions, sélectionnez à quel moment transactions doivent être validées, comme Mensuel.</span><span class="sxs-lookup"><span data-stu-id="c2f3d-118">In the Post transactions field, select when the transactions should be posted, such as Monthly.</span></span>


