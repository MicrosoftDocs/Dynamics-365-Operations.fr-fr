---
title: FR-00004 Valider le journal de renouvellement de lettres de change
description: Cette procédure vous guide dans l'approbation d'un journal de renouvellement de lettres de change.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustBillOfExchange, CustOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4c6bec2b9be3cf668a7f5915bfd7c9eabd67c7b8
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1537907"
---
# <a name="fr-00004-post-re-draw-bill-of-exchange-journal"></a><span data-ttu-id="58876-103">FR-00004 Valider le journal de renouvellement de lettres de change</span><span class="sxs-lookup"><span data-stu-id="58876-103">FR-00004 Post re-draw bill of exchange journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="58876-104">Cette procédure vous guide dans l'approbation d'un journal de renouvellement de lettres de change.</span><span class="sxs-lookup"><span data-stu-id="58876-104">This procedure walks you through posting a re-draw bill of exchange.</span></span>

<span data-ttu-id="58876-105">Cette procédure a été créée à l'aide des données fictives de la société FRSI.</span><span class="sxs-lookup"><span data-stu-id="58876-105">This procedure was created using the demo data company FRSI.</span></span> 

<span data-ttu-id="58876-106">Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est en France.</span><span class="sxs-lookup"><span data-stu-id="58876-106">This functionality is available for legal entities whose primary address is in France.</span></span>

<span data-ttu-id="58876-107">Pour effectuer cette procédure, vous devez avoir le rôle de commis à la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="58876-107">You should have a role of Accounts receivable clerk to complete this procedure.</span></span>

1. <span data-ttu-id="58876-108">Accédez à Comptabilité client > Paiements > Lettre de change > Journal de renouvellement des lettres de change.</span><span class="sxs-lookup"><span data-stu-id="58876-108">Go to Accounts receivable > Payments > Bill of exchange > Redraw bill of exchange journal.</span></span>
2. <span data-ttu-id="58876-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="58876-109">Click New.</span></span>
3. <span data-ttu-id="58876-110">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="58876-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="58876-111">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="58876-111">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="58876-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="58876-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="58876-113">Sélectionnez « ReemmEAR »</span><span class="sxs-lookup"><span data-stu-id="58876-113">Select "ReemmEAR"</span></span>  
6. <span data-ttu-id="58876-114">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="58876-114">Click Lines.</span></span>
7. <span data-ttu-id="58876-115">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="58876-115">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="58876-116">Dans le champ Compte, spécifiez les valeurs « FR_SI_0001 ».</span><span class="sxs-lookup"><span data-stu-id="58876-116">In the Account field, specify the values 'FR_SI_0001'.</span></span>
9. <span data-ttu-id="58876-117">Cliquez sur Régler les transactions.</span><span class="sxs-lookup"><span data-stu-id="58876-117">Click Settle transactions.</span></span>
10. <span data-ttu-id="58876-118">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="58876-118">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="58876-119">Marquer le journal de création de lettres de change le plus récemment contesté</span><span class="sxs-lookup"><span data-stu-id="58876-119">Mark the most recently protested draw bill of exchange journal</span></span>  
11. <span data-ttu-id="58876-120">Cochez la case Marquer.</span><span class="sxs-lookup"><span data-stu-id="58876-120">Select the Mark check box.</span></span>
12. <span data-ttu-id="58876-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="58876-121">Click OK.</span></span>
13. <span data-ttu-id="58876-122">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="58876-122">Click Post.</span></span>
14. <span data-ttu-id="58876-123">Accédez à Comptabilité client > Recherches et états > Paiements > Journal des lettres de change.</span><span class="sxs-lookup"><span data-stu-id="58876-123">Go to Accounts receivable > Inquiries and reports > Payments > Bill of exchange journal.</span></span>
    * <span data-ttu-id="58876-124">Vérifiez que le statut du journal récemment validé est Représenté.</span><span class="sxs-lookup"><span data-stu-id="58876-124">Verify that Status for the newly posted journal should be Redrawn.</span></span> <span data-ttu-id="58876-125">Si c'est le cas, le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="58876-125">If it is, then the process is complete.</span></span>  

