--- 
title: "Paramétrer un mode de paiement (France)"
description: "La procédure vous guide dans la configuration des modes de paiement d'établissement afin de vous aider à créer et valider la lettre de change après l'avoir approuvée dans le journal de création de lettres de change."
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7ea1354c51e5bc5ee9c4a9a44afe67d48faec162
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-method-of-payment-france"></a><span data-ttu-id="1c818-103">Paramétrer un mode de paiement (France)</span><span class="sxs-lookup"><span data-stu-id="1c818-103">Set up method of payment (France)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1c818-104">La procédure vous guide dans la configuration des modes de paiement d'établissement afin de vous aider à créer et valider la lettre de change après l'avoir approuvée dans le journal de création de lettres de change.</span><span class="sxs-lookup"><span data-stu-id="1c818-104">The procedure walks you through setting up methods of payment so that you can create and post the bill of exchange after approving it from the draw bill of exchange journal.</span></span>

<span data-ttu-id="1c818-105">Cette procédure a été créée à l'aide des données fictives de la société FRSI.</span><span class="sxs-lookup"><span data-stu-id="1c818-105">This procedure was created using the demo data company FRSI.</span></span> 

<span data-ttu-id="1c818-106">Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est en France.</span><span class="sxs-lookup"><span data-stu-id="1c818-106">This functionality is available for legal entities whose primary address is in France.</span></span>

<span data-ttu-id="1c818-107">Pour effectuer cette procédure, vous devez avoir le rôle de responsable de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="1c818-107">You should have a role of Accounts receivables manager to perform this procedure.</span></span>





1. <span data-ttu-id="1c818-108">Accédez à Comptabilité client > Paramétrage des paiements > Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="1c818-108">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="1c818-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1c818-109">Click New.</span></span>
3. <span data-ttu-id="1c818-110">Tapez une valeur dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="1c818-110">In the Method of payment field, type a value.</span></span>
4. <span data-ttu-id="1c818-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1c818-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1c818-112">Dans le champ Statut de paiement, sélectionnez « Approuvé ».</span><span class="sxs-lookup"><span data-stu-id="1c818-112">In the Payment status field, select 'Approved'.</span></span>
6. <span data-ttu-id="1c818-113">Dans le champ Type de paiement, sélectionnez « Lettre de change ».</span><span class="sxs-lookup"><span data-stu-id="1c818-113">In the Payment type field, select 'Bill of exchange'.</span></span>
7. <span data-ttu-id="1c818-114">Développez ou réduisez la section Général.</span><span class="sxs-lookup"><span data-stu-id="1c818-114">Expand or collapse the General section.</span></span>
8. <span data-ttu-id="1c818-115">Sélectionnez Banque dans le champ Type de compte.</span><span class="sxs-lookup"><span data-stu-id="1c818-115">In the Account type field, select 'Bank'.</span></span>
9. <span data-ttu-id="1c818-116">Dans le champ Compte de paiement, indiquez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="1c818-116">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="1c818-117">Par exemple : « FRSI OPER »</span><span class="sxs-lookup"><span data-stu-id="1c818-117">For example: 'FRSI OPER'</span></span>  
10. <span data-ttu-id="1c818-118">Développez ou réduisez la section Formats de fichier.</span><span class="sxs-lookup"><span data-stu-id="1c818-118">Expand or collapse the File formats section.</span></span>
11. <span data-ttu-id="1c818-119">Cliquez sur Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="1c818-119">Click Setup.</span></span>
12. <span data-ttu-id="1c818-120">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1c818-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1c818-121">Recherchez et sélectionnez « Lettre de change française » et utilisez la flèche pour la déplacer vers la liste sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c818-121">Find and select "French bill of exchange" and use the arrow to move it to the Selected list.</span></span>  
13. <span data-ttu-id="1c818-122">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1c818-122">Click Save.</span></span>
14. <span data-ttu-id="1c818-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1c818-123">Close the page.</span></span>
15. <span data-ttu-id="1c818-124">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1c818-124">In the Name field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="1c818-125">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c818-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1c818-126">Sélectionnez « EnmmEAR »</span><span class="sxs-lookup"><span data-stu-id="1c818-126">Select "EnmmEAR"</span></span>  
17. <span data-ttu-id="1c818-127">Dans le champ Format d'exportation, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1c818-127">In the Export format field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="1c818-128">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c818-128">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1c818-129">Par exemple : Sélectionnez « Lettre de change française »</span><span class="sxs-lookup"><span data-stu-id="1c818-129">For example: Select "French bill of exchange"</span></span>  
19. <span data-ttu-id="1c818-130">Cochez ou décochez la case Créer et valider automatiquement le journal de création lors de la validation des factures.</span><span class="sxs-lookup"><span data-stu-id="1c818-130">Select or clear the Create and post draw journal automatically when posting invoices check box.</span></span>
20. <span data-ttu-id="1c818-131">Cochez ou décochez la case à cocher Exécuter le script d'exportation.</span><span class="sxs-lookup"><span data-stu-id="1c818-131">Select or clear the Run export script check box.</span></span>
21. <span data-ttu-id="1c818-132">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1c818-132">Click Save.</span></span>


