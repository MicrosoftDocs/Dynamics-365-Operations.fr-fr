---
title: Créer des plans de régularisation
description: Cette rubrique explique comment créer un plan de régularisation.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e8f8cf8546187ae1c65d4966887e1c5842dff431
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867557"
---
# <a name="create-accrual-schemes"></a><span data-ttu-id="f142b-103">Créer des plans de régularisation</span><span class="sxs-lookup"><span data-stu-id="f142b-103">Create accrual schemes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f142b-104">Cette rubrique explique comment créer un plan de régularisation.</span><span class="sxs-lookup"><span data-stu-id="f142b-104">This topic explains how to create an accrual scheme.</span></span> <span data-ttu-id="f142b-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="f142b-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="f142b-106">Allez dans **Volet de navigation > Modules > Comptabilité > Paramétrage du journal > Plans de régularisation**.</span><span class="sxs-lookup"><span data-stu-id="f142b-106">Go to **Navigation pane > Modules > General ledger > Journal setup > Accrual schemes**.</span></span>
2. <span data-ttu-id="f142b-107">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f142b-107">Select **New**.</span></span>
3. <span data-ttu-id="f142b-108">Entrez une valeur dans le champ **Identification de la régularisation**.</span><span class="sxs-lookup"><span data-stu-id="f142b-108">In the **Accrual identification** field, type a value.</span></span>
4. <span data-ttu-id="f142b-109">Entrez une valeur dans le champ **Description du plan de régularisation**.</span><span class="sxs-lookup"><span data-stu-id="f142b-109">In the **Description of accrual scheme** field, type a value.</span></span>
5. <span data-ttu-id="f142b-110">Dans le champ **Débit**, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="f142b-110">In the **Debit** field, specify the desired values.</span></span> <span data-ttu-id="f142b-111">Le compte principal défini remplacera le compte principal de débit dans la ligne de N° document de journal et il sera également utilisé pour la contrepassation des différés en fonction des transactions de régularisation des comptes.</span><span class="sxs-lookup"><span data-stu-id="f142b-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="f142b-112">Dans le champ **Crédit**, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="f142b-112">In the **Credit** field, specify the desired values.</span></span> <span data-ttu-id="f142b-113">Le compte principal défini remplacera le compte principal de crédit dans la ligne de N° document de journal et il sera également utilisé pour la contrepassation des différés en fonction des transactions de régularisation des comptes.</span><span class="sxs-lookup"><span data-stu-id="f142b-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="f142b-114">Dans le champ **N° document**, sélectionnez la manière dont vous souhaitez que le N° document soit déterminé lorsque les transactions sont validées.</span><span class="sxs-lookup"><span data-stu-id="f142b-114">In the **Voucher** field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="f142b-115">Dans le champ **Description**, entrez une valeur pour décrire les transactions qui seront validées.</span><span class="sxs-lookup"><span data-stu-id="f142b-115">In the **Description** field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="f142b-116">Dans le champ **Fréquence**, sélectionnez la fréquence à laquelle les transactions doivent se produire.</span><span class="sxs-lookup"><span data-stu-id="f142b-116">In the **Period frequency** field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="f142b-117">Entrez un nombre dans le champ **Occurrences par période**.</span><span class="sxs-lookup"><span data-stu-id="f142b-117">In the **Number of occurrences by period** field, enter a number.</span></span>
11. <span data-ttu-id="f142b-118">Dans le champ **Valider les transactions**, sélectionnez à quel moment les transactions doivent être validées, comme **Mensuel**.</span><span class="sxs-lookup"><span data-stu-id="f142b-118">In the **Post transactions** field, select when the transactions should be posted, such as **Monthly**.</span></span>

