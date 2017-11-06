--- 
title: Valider le journal de renouvellement des lettres de change (France)
description: "Cette procédure vous guide dans l'approbation d'un journal de renouvellement de lettres de change."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 9e05054e0a6f5f9a56f9e32cda24c761d8920f65
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="post-re-draw-bill-of-exchange-journal-france"></a><span data-ttu-id="4d786-103">Valider le journal de renouvellement des lettres de change (France)</span><span class="sxs-lookup"><span data-stu-id="4d786-103">Post re-draw bill of exchange journal (France)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4d786-104">Cette procédure vous guide dans l'approbation d'un journal de renouvellement de lettres de change.</span><span class="sxs-lookup"><span data-stu-id="4d786-104">This procedure walks you through posting a re-draw bill of exchange.</span></span>

<span data-ttu-id="4d786-105">Cette procédure a été créée à l'aide des données fictives de la société FRSI.</span><span class="sxs-lookup"><span data-stu-id="4d786-105">This procedure was created using the demo data company FRSI.</span></span> 

<span data-ttu-id="4d786-106">Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est en France.</span><span class="sxs-lookup"><span data-stu-id="4d786-106">This functionality is available for legal entities whose primary address is in France.</span></span>

<span data-ttu-id="4d786-107">Pour effectuer cette procédure, vous devez avoir le rôle de commis à la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="4d786-107">You should have a role of Accounts receivable clerk to complete this procedure.</span></span>

1. <span data-ttu-id="4d786-108">Accédez à Comptabilité client > Paiements > Lettre de change > Journal de renouvellement des lettres de change.</span><span class="sxs-lookup"><span data-stu-id="4d786-108">Go to Accounts receivable > Payments > Bill of exchange > Redraw bill of exchange journal.</span></span>
2. <span data-ttu-id="4d786-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4d786-109">Click New.</span></span>
3. <span data-ttu-id="4d786-110">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4d786-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="4d786-111">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="4d786-111">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="4d786-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4d786-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4d786-113">Sélectionnez « ReemmEAR »</span><span class="sxs-lookup"><span data-stu-id="4d786-113">Select "ReemmEAR"</span></span>  
6. <span data-ttu-id="4d786-114">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="4d786-114">Click Lines.</span></span>
7. <span data-ttu-id="4d786-115">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4d786-115">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="4d786-116">Dans le champ Compte, spécifiez les valeurs « FR_SI_0001 ».</span><span class="sxs-lookup"><span data-stu-id="4d786-116">In the Account field, specify the values 'FR_SI_0001'.</span></span>
9. <span data-ttu-id="4d786-117">Cliquez sur Régler les transactions.</span><span class="sxs-lookup"><span data-stu-id="4d786-117">Click Settle transactions.</span></span>
10. <span data-ttu-id="4d786-118">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4d786-118">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="4d786-119">Marquer le journal de création de lettres de change le plus récemment contesté</span><span class="sxs-lookup"><span data-stu-id="4d786-119">Mark the most recently protested draw bill of exchange journal</span></span>  
11. <span data-ttu-id="4d786-120">Cochez la case Marquer.</span><span class="sxs-lookup"><span data-stu-id="4d786-120">Select the Mark check box.</span></span>
12. <span data-ttu-id="4d786-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4d786-121">Click OK.</span></span>
13. <span data-ttu-id="4d786-122">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="4d786-122">Click Post.</span></span>
14. <span data-ttu-id="4d786-123">Accédez à Comptabilité client > Recherches et états > Paiements > Journal des lettres de change.</span><span class="sxs-lookup"><span data-stu-id="4d786-123">Go to Accounts receivable > Inquiries and reports > Payments > Bill of exchange journal.</span></span>
    * <span data-ttu-id="4d786-124">Vérifiez que le statut du journal récemment validé est Représenté.</span><span class="sxs-lookup"><span data-stu-id="4d786-124">Verify that Status for the newly posted journal should be Redrawn.</span></span> <span data-ttu-id="4d786-125">Si c'est le cas, le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="4d786-125">If it is, then the process is complete.</span></span>  


