---
title: FR-00004 Paramétrer le mode de paiement
description: La procédure vous guide dans la configuration des modes de paiement d’établissement afin de vous aider à créer et valider la lettre de change après l’avoir approuvée dans le journal de création de lettres de change.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, CustVendPaymFormat
audience: Application User
ms.reviewer: kfend
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e584142e1a5031e465817923872a0f353dfdea9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962475"
---
# <a name="fr-00004-setup-method-of-payment"></a><span data-ttu-id="4d1a4-103">FR-00004 Paramétrer le mode de paiement</span><span class="sxs-lookup"><span data-stu-id="4d1a4-103">FR-00004 Setup method of payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4d1a4-104">La procédure vous guide dans la configuration des modes de paiement d’établissement afin de vous aider à créer et valider la lettre de change après l’avoir approuvée dans le journal de création de lettres de change.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-104">The procedure walks you through setting up methods of payment so that you can create and post the bill of exchange after approving it from the draw bill of exchange journal.</span></span>

<span data-ttu-id="4d1a4-105">Cette procédure a été créée à l’aide des données fictives de la société FRSI.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-105">This procedure was created using the demo data company FRSI.</span></span> 

<span data-ttu-id="4d1a4-106">Cette fonctionnalité est disponible pour les entités juridiques dont l’adresse principale est en France.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-106">This functionality is available for legal entities whose primary address is in France.</span></span>

<span data-ttu-id="4d1a4-107">Pour effectuer cette procédure, vous devez avoir le rôle de responsable de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-107">You should have a role of Accounts receivables manager to perform this procedure.</span></span>





1. <span data-ttu-id="4d1a4-108">Accédez à Comptabilité client > Paramétrage des paiements > Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-108">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="4d1a4-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-109">Click New.</span></span>
3. <span data-ttu-id="4d1a4-110">Tapez une valeur dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-110">In the Method of payment field, type a value.</span></span>
4. <span data-ttu-id="4d1a4-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="4d1a4-112">Dans le champ Statut de paiement, sélectionnez « Approuvé ».</span><span class="sxs-lookup"><span data-stu-id="4d1a4-112">In the Payment status field, select 'Approved'.</span></span>
6. <span data-ttu-id="4d1a4-113">Dans le champ Type de paiement, sélectionnez « Lettre de change ».</span><span class="sxs-lookup"><span data-stu-id="4d1a4-113">In the Payment type field, select 'Bill of exchange'.</span></span>
7. <span data-ttu-id="4d1a4-114">Développez ou réduisez la section Général.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-114">Expand or collapse the General section.</span></span>
8. <span data-ttu-id="4d1a4-115">Sélectionnez Banque dans le champ Type de compte.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-115">In the Account type field, select 'Bank'.</span></span>
9. <span data-ttu-id="4d1a4-116">Dans le champ Compte de paiement, indiquez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-116">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="4d1a4-117">Par exemple : « FRSI OPER »</span><span class="sxs-lookup"><span data-stu-id="4d1a4-117">For example: 'FRSI OPER'</span></span>  
10. <span data-ttu-id="4d1a4-118">Développez ou réduisez la section Formats de fichier.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-118">Expand or collapse the File formats section.</span></span>
11. <span data-ttu-id="4d1a4-119">Cliquez sur Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-119">Click Setup.</span></span>
12. <span data-ttu-id="4d1a4-120">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4d1a4-121">Recherchez et sélectionnez « Lettre de change française » et utilisez la flèche pour la déplacer vers la liste sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-121">Find and select "French bill of exchange" and use the arrow to move it to the Selected list.</span></span>  
13. <span data-ttu-id="4d1a4-122">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-122">Click Save.</span></span>
14. <span data-ttu-id="4d1a4-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-123">Close the page.</span></span>
15. <span data-ttu-id="4d1a4-124">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-124">In the Name field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="4d1a4-125">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4d1a4-126">Sélectionnez « EnmmEAR »</span><span class="sxs-lookup"><span data-stu-id="4d1a4-126">Select "EnmmEAR"</span></span>  
17. <span data-ttu-id="4d1a4-127">Dans le champ Format d’exportation, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-127">In the Export format field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="4d1a4-128">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-128">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4d1a4-129">Par exemple : Sélectionnez « Lettre de change française »</span><span class="sxs-lookup"><span data-stu-id="4d1a4-129">For example: Select "French bill of exchange"</span></span>  
19. <span data-ttu-id="4d1a4-130">Cochez ou décochez la case Créer et valider automatiquement le journal de création lors de la validation des factures.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-130">Select or clear the Create and post draw journal automatically when posting invoices check box.</span></span>
20. <span data-ttu-id="4d1a4-131">Cochez ou décochez la case à cocher Exécuter le script d’exportation.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-131">Select or clear the Run export script check box.</span></span>
21. <span data-ttu-id="4d1a4-132">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="4d1a4-132">Click Save.</span></span>

