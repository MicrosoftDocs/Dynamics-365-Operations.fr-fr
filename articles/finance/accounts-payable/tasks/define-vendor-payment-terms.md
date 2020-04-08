---
title: Définir les conditions de paiement fournisseur
description: Cette rubrique explique comment paramétrer des conditions de paiement pour les factures fournisseur.
author: abruer
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7e6778f61a9367399e4b71d5b2bb2459c09ba508
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143894"
---
# <a name="define-vendor-payment-terms"></a><span data-ttu-id="939c1-103">Définir les conditions de paiement fournisseur</span><span class="sxs-lookup"><span data-stu-id="939c1-103">Define vendor payment terms</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="939c1-104">Cette rubrique explique comment paramétrer des conditions de paiement pour les factures fournisseur.</span><span class="sxs-lookup"><span data-stu-id="939c1-104">This topic explains how to set up payment terms for vendor invoices.</span></span> <span data-ttu-id="939c1-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="939c1-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="939c1-106">Accédez à **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage des paiements > Conditions de paiement**.</span><span class="sxs-lookup"><span data-stu-id="939c1-106">Go to **Navigation pane > Modules > Accounts payable > Payment setup > Terms of payment**.</span></span>
2. <span data-ttu-id="939c1-107">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="939c1-107">Select **New**.</span></span> <span data-ttu-id="939c1-108">La page Conditions de paiement est utilisée pour définir la manière dont la date d'échéance est calculée.</span><span class="sxs-lookup"><span data-stu-id="939c1-108">The Terms of payment page is used to define how the due date will be calculated.</span></span> <span data-ttu-id="939c1-109">Elle ne permet pas de définir la manière dont la date d'escompte de règlement est calculée.</span><span class="sxs-lookup"><span data-stu-id="939c1-109">It is not used to define how the cash discount date will be calculated.</span></span>  
3. <span data-ttu-id="939c1-110">Tapez une valeur dans le champ **Conditions de paiement**.</span><span class="sxs-lookup"><span data-stu-id="939c1-110">In the **Terms of payment** field, type a value.</span></span>
4. <span data-ttu-id="939c1-111">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="939c1-111">In the **Description field**, type a value.</span></span>
5. <span data-ttu-id="939c1-112">Entrez un nombre dans le champ **Jours**.</span><span class="sxs-lookup"><span data-stu-id="939c1-112">In the **Days** field, enter a number.</span></span> <span data-ttu-id="939c1-113">Le nombre entré ici sera ajouté à la date d'échéance ou à la fin de la période identifiée dans le mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="939c1-113">The number entered here will be used to add to the due date, or to the end of the period identified in the Payment method.</span></span> <span data-ttu-id="939c1-114">Par exemple, si vous sélectionnez **Net**, le nombre sera ajouté à la date d'échéance.</span><span class="sxs-lookup"><span data-stu-id="939c1-114">For example, if you select **Net**, the number will be added to the due date.</span></span> <span data-ttu-id="939c1-115">Si vous sélectionnez **Mois en cours**, le nombre sera ajouté au dernier jour du mois actuel pour calculer la date d'échéance.</span><span class="sxs-lookup"><span data-stu-id="939c1-115">If you select **Current month**, it will add the number to the last day of the current month to calculate the due date.</span></span>  
6. <span data-ttu-id="939c1-116">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="939c1-116">Select **Save**.</span></span>
7. <span data-ttu-id="939c1-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="939c1-117">Close the page.</span></span>
8. <span data-ttu-id="939c1-118">Accédez à **Comptabilité fournisseur > Paramétrage des paiements > Escomptes de règlement**.</span><span class="sxs-lookup"><span data-stu-id="939c1-118">Go to **Accounts payable > Payment setup > Cash discounts**.</span></span>
9. <span data-ttu-id="939c1-119">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="939c1-119">Select **New**.</span></span>
10. <span data-ttu-id="939c1-120">Entrez un ID dans le champ **Escompte de règlement**.</span><span class="sxs-lookup"><span data-stu-id="939c1-120">In the **Cash discount** field, enter an ID.</span></span>
11. <span data-ttu-id="939c1-121">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="939c1-121">In the **Description** field, type a value.</span></span>
12. <span data-ttu-id="939c1-122">Si le fournisseur offre une remise progressive, sélectionnez l'escompte de règlement suivant une fois que l'escompte actuel a expiré.</span><span class="sxs-lookup"><span data-stu-id="939c1-122">If the vendor offers a tiered discount, select the next cash discount after the current one is expired.</span></span>
13. <span data-ttu-id="939c1-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="939c1-123">Close the page.</span></span>
14. <span data-ttu-id="939c1-124">Entrez un nombre dans le champ **Jours**.</span><span class="sxs-lookup"><span data-stu-id="939c1-124">In the **Days** field, enter a number.</span></span> <span data-ttu-id="939c1-125">La quantité entrée dans le champ **Jours** sera utilisée pour calculer la date d'escompte de règlement, selon l'option sélectionnée dans champ **Net/actuel**.</span><span class="sxs-lookup"><span data-stu-id="939c1-125">The quantity entered in the **Days** field will be used to calculate the Cash discount date, based on what option was selected in the **Net/Current** field.</span></span> <span data-ttu-id="939c1-126">Si **Net** est sélectionné, la quantité est ajoutée à la date de facturation pour déterminer la date d'escompte de règlement.</span><span class="sxs-lookup"><span data-stu-id="939c1-126">If **Net** was selected, the quantity will be added to the invoice date to determine the cash discount date.</span></span> <span data-ttu-id="939c1-127">Si **Mois en cours** est sélectionné, la quantité est ajoutée à la fin du mois en cours pour déterminer la date d'escompte de règlement.</span><span class="sxs-lookup"><span data-stu-id="939c1-127">If **Current month** was selected, the quantity will be added to the end of the currency month to determine the cash discount date.</span></span>  
15. <span data-ttu-id="939c1-128">Entrez le pourcentage de l'escompte de règlement dans le champ **Remise**.</span><span class="sxs-lookup"><span data-stu-id="939c1-128">Enter the percentage of the cash discount in the **Discount** field.</span></span> 
16. <span data-ttu-id="939c1-129">Saisissez le compte principal sur lequel l’escompte de règlement sera imputé pour les factures clients, puis le compte principal sur lequel l’escompte de règlement sera imputé pour les factures fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="939c1-129">Enter the main account to which the cash discount will be posted for customer invoices, then enter the main account to which the cash discount will be posted for vendor invoices.</span></span> <span data-ttu-id="939c1-130">Si **Comptes de contrepartie pour les remises** est défini pour **utiliser le compte principal pour la remise fournisseur**, le compte principal est utilisé.</span><span class="sxs-lookup"><span data-stu-id="939c1-130">If **Discount offset accounts** is set to **Use main account for vendor discount**, then the Main account will be used.</span></span> <span data-ttu-id="939c1-131">Si l'option est définie sur **Comptes sur les lignes de facture**, l'escompte de règlement sera validé sur les comptes de dépense/d'actif sur les lignes de la facture.</span><span class="sxs-lookup"><span data-stu-id="939c1-131">If the option is set to **Accounts on the invoice lines**, the cash discount will be posted to the asset/expense accounts on the invoice's lines.</span></span>  
17. <span data-ttu-id="939c1-132">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="939c1-132">Select **Save**.</span></span>

