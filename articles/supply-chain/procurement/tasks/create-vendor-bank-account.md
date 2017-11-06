--- 
title: "Créer un compte bancaire fournisseur"
description: "Cette procédure décrit comment créer un compte bancaire pour un fournisseur."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: adb759c59d7275e7323dbb760de56acdef2e3cff
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-vendor-bank-account"></a><span data-ttu-id="b94ac-103">Créer un compte bancaire fournisseur</span><span class="sxs-lookup"><span data-stu-id="b94ac-103">Create a vendor bank account</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b94ac-104">Cette procédure décrit comment créer un compte bancaire pour un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b94ac-104">This procedure shows you how to create a bank account for a vendor.</span></span> <span data-ttu-id="b94ac-105">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="b94ac-105">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="b94ac-106">Accédez à Approvisionnements > Fournisseurs > Tous les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="b94ac-106">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="b94ac-107">Choisissez le fournisseur pour lequel vous voulez créer un compte bancaire, puis cliquez sur le lien sur l'ID compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b94ac-107">Select the vendor that you want to create a bank account for, and then click the link on the Vendor account ID.</span></span>
3. <span data-ttu-id="b94ac-108">Cliquez sur Fournisseur dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="b94ac-108">On the Action Pane, click Vendor.</span></span>
4. <span data-ttu-id="b94ac-109">Cliquez sur Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="b94ac-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="b94ac-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="b94ac-110">Click New.</span></span>
6. <span data-ttu-id="b94ac-111">Tapez une valeur dans le champ Compte en banque.</span><span class="sxs-lookup"><span data-stu-id="b94ac-111">In the Bank account field, type a value.</span></span>
    * <span data-ttu-id="b94ac-112">Cette identification sera employée pour identifier le compte bancaire sur l'enregistrement fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b94ac-112">This ID will be used to identify the bank account on the vendor record.</span></span>  
7. <span data-ttu-id="b94ac-113">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="b94ac-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="b94ac-114">Dans le champ Groupes de banques, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b94ac-114">In the Bank groups field, enter or select a value.</span></span>
9. <span data-ttu-id="b94ac-115">Sélectionnez une option dans le champ Type de numéro d'acheminement.</span><span class="sxs-lookup"><span data-stu-id="b94ac-115">In the Routing number type field, select an option.</span></span>
    * <span data-ttu-id="b94ac-116">Il s'agit du type de numéro d'acheminement utilisé pour les paiements internationaux.</span><span class="sxs-lookup"><span data-stu-id="b94ac-116">This is the type of routing number that’s used for international payments.</span></span>  
10. <span data-ttu-id="b94ac-117">Tapez une valeur dans le champ Numéro de compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="b94ac-117">In the Bank account number field, type a value.</span></span>
11. <span data-ttu-id="b94ac-118">Tapez une valeur dans le champ Code SWIFT.</span><span class="sxs-lookup"><span data-stu-id="b94ac-118">In the SWIFT code field, type a value.</span></span>
12. <span data-ttu-id="b94ac-119">Tapez une valeur dans le champ IBAN.</span><span class="sxs-lookup"><span data-stu-id="b94ac-119">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="b94ac-120">Le numéro IBAN doit être dans un format correct.</span><span class="sxs-lookup"><span data-stu-id="b94ac-120">The IBAN number must be in the correct format.</span></span> <span data-ttu-id="b94ac-121">Par exemple, vous pouvez utiliser DE89370400440532013000.</span><span class="sxs-lookup"><span data-stu-id="b94ac-121">For example, you could use DE89370400440532013000.</span></span>  
    * <span data-ttu-id="b94ac-122">Le statut du compte bancaire est Actif si la date active a été atteinte, et si la date d'échéance n'a pas été dépassée.</span><span class="sxs-lookup"><span data-stu-id="b94ac-122">The status of the bank account is Active if the Active date has been reached, and the Expiration date has not been exceeded.</span></span> <span data-ttu-id="b94ac-123">Elle est également active si les champs Date active et Date d'expiration sont vides.</span><span class="sxs-lookup"><span data-stu-id="b94ac-123">It’s also active if both the Active date and Expiration date fields are blank.</span></span> <span data-ttu-id="b94ac-124">Si les dates des champs Date active et Date d'expiration se situent dans le futur, les paiements électroniques ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="b94ac-124">If the dates in both the Active date and Expiration date fields are in the future electronic payments are not available.</span></span> <span data-ttu-id="b94ac-125">Les autres types de paiements sont disponibles et le compte bancaire est actif.</span><span class="sxs-lookup"><span data-stu-id="b94ac-125">Other payment types are available and the bank account is active.</span></span>  
13. <span data-ttu-id="b94ac-126">Développez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="b94ac-126">Expand the Setup section.</span></span>
14. <span data-ttu-id="b94ac-127">Tapez une valeur dans le champ Code texte.</span><span class="sxs-lookup"><span data-stu-id="b94ac-127">In the Text code field, type a value.</span></span>
    * <span data-ttu-id="b94ac-128">Ce champ spécifie un code qui apparaîtra sur le relevé bancaire du destinataire.</span><span class="sxs-lookup"><span data-stu-id="b94ac-128">This field specifies a code that will appear on the bank statement of the recipient.</span></span>  
15. <span data-ttu-id="b94ac-129">Tapez une valeur dans le champ Message pour la banque.</span><span class="sxs-lookup"><span data-stu-id="b94ac-129">In the Message to bank field, type a value.</span></span>
16. <span data-ttu-id="b94ac-130">Tapez une valeur dans le champ Référence de change.</span><span class="sxs-lookup"><span data-stu-id="b94ac-130">In the Exchange reference field, type a value.</span></span>
    * <span data-ttu-id="b94ac-131">Il s'agit du numéro de référence d'un taux de change à terme ou fixe.</span><span class="sxs-lookup"><span data-stu-id="b94ac-131">This is the reference number for any forward-term or fixed-term rate of exchange.</span></span>  
17. <span data-ttu-id="b94ac-132">Dans le champ Devise, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b94ac-132">In the Currency field, enter or select a value.</span></span>
    * <span data-ttu-id="b94ac-133">Quand des notes préliminaires sont publiées, cette section fournit un aperçu de leur statut (en attente ou approuvé).</span><span class="sxs-lookup"><span data-stu-id="b94ac-133">When prenotes are issued, this section provides an overview of their status (pending or approved).</span></span>  
18. <span data-ttu-id="b94ac-134">Développez la section Adresse.</span><span class="sxs-lookup"><span data-stu-id="b94ac-134">Expand the Address section.</span></span>
19. <span data-ttu-id="b94ac-135">Développez la section Notes préliminaires.</span><span class="sxs-lookup"><span data-stu-id="b94ac-135">Expand the Prenotes section.</span></span>
20. <span data-ttu-id="b94ac-136">Développez la section Informations de contact.</span><span class="sxs-lookup"><span data-stu-id="b94ac-136">Expand the Contact information section.</span></span>
21. <span data-ttu-id="b94ac-137">Dans le champ Téléphone, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b94ac-137">In the Telephone field, type a value.</span></span>
22. <span data-ttu-id="b94ac-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b94ac-138">Close the page.</span></span>
23. <span data-ttu-id="b94ac-139">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="b94ac-139">Click Edit.</span></span>
24. <span data-ttu-id="b94ac-140">Développez la section Paiement.</span><span class="sxs-lookup"><span data-stu-id="b94ac-140">Expand the Payment section.</span></span>
25. <span data-ttu-id="b94ac-141">Dans le champ Compte bancaire, choisissez le compte que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="b94ac-141">In the Bank  account field, select the account that you’ve just created.</span></span>
26. <span data-ttu-id="b94ac-142">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="b94ac-142">Click Save.</span></span>
    * <span data-ttu-id="b94ac-143">L'adresse peut être héritée du groupe bancaire, s'il est spécifié, ou vous pouvez l'ajouter ici.</span><span class="sxs-lookup"><span data-stu-id="b94ac-143">The address may be inherited from the bank group, if one is specified, or you can add it here.</span></span>  


