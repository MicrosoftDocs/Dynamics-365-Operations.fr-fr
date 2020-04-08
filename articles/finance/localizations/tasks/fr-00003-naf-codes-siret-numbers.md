---
title: FR-00003 Codes NAF et numéros Siret
description: Cette procédure indique comment créer des codes NAF et comment les entrer pour les entités juridiques, les clients, les fournisseurs, et les prospects.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CompanyNAFCode, CustTable, VendTable, smmBusRelTable, OMLegalEntity
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bbe68cece66e661c9114331d43ac9abc03cd4b8d
ms.sourcegitcommit: b92c3e1b3403d0455fc4e0bf9132d6bc0d7aba5e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139013"
---
# <a name="fr-00003-naf-codes-and-siret-numbers"></a><span data-ttu-id="e2107-103">FR-00003 Codes NAF et numéros Siret</span><span class="sxs-lookup"><span data-stu-id="e2107-103">FR-00003 NAF codes and Siret numbers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e2107-104">Cette procédure indique comment créer des codes NAF et comment les entrer pour les entités juridiques, les clients, les fournisseurs, et les prospects.</span><span class="sxs-lookup"><span data-stu-id="e2107-104">This procedure shows how to create NAF codes and then enter the codes for legal entities, customers, vendors, and prospects.</span></span> <span data-ttu-id="e2107-105">Vous pouvez utiliser les codes NAF pour identifier le secteur d'activité d'une entreprise.</span><span class="sxs-lookup"><span data-stu-id="e2107-105">NAF codes are used to identify the business of an enterprise.</span></span> <span data-ttu-id="e2107-106">Par exemple, si votre entité juridique fabrique des ordinateurs, son code NAF pourrait être 300C, à savoir le code NAF de fabrication d'ordinateurs et de matériel informatique.</span><span class="sxs-lookup"><span data-stu-id="e2107-106">For instance, if your legal entity manufactures computers, the NAF code for your legal entity may be 300C, which is the NAF code for manufacturing computers and other computer hardware.</span></span> <span data-ttu-id="e2107-107">Si votre entité juridique est active dans le secteur de la construction, votre code NAF pourra être 452A.</span><span class="sxs-lookup"><span data-stu-id="e2107-107">If your legal entity is involved in building houses, your NAF code may be 452A.</span></span>



<span data-ttu-id="e2107-108">Cette procédure décrit également comment entrer des numéros de siret pour les clients, les fournisseurs, et les prospects.</span><span class="sxs-lookup"><span data-stu-id="e2107-108">This procedure also shows how to enter siret numbers for customers, vendors, and prospects.</span></span> <span data-ttu-id="e2107-109">Le Siret est un nombre à 14 chiffres qui identifie une entreprise, une branche de cette entreprise et une personne associée aux activités de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="e2107-109">The siret is a 14-digit number that identifies a business, a branch of the business, and a person who is associated with the business activity.</span></span> <span data-ttu-id="e2107-110">Ce numéro permet de vérifier qu'une entreprise est correctement enregistrée et autorisée à exercer ce type d'activité.</span><span class="sxs-lookup"><span data-stu-id="e2107-110">You can use the siret number to verify that an enterprise is correctly registered and authorized to do business with you.</span></span>



<span data-ttu-id="e2107-111">Cette procédure a été créée à l'aide des données fictives de la société FRSI.</span><span class="sxs-lookup"><span data-stu-id="e2107-111">This procedure was created using the demo data company FRSI.</span></span> <span data-ttu-id="e2107-112">Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est en France.</span><span class="sxs-lookup"><span data-stu-id="e2107-112">This functionality is available for legal entities whose primary address is in France.</span></span> <span data-ttu-id="e2107-113">Vous devez être dans l'un ou l'autre</span><span class="sxs-lookup"><span data-stu-id="e2107-113">You should be in either</span></span>


## <a name="set-up-a-naf-code"></a><span data-ttu-id="e2107-114">Paramétrage d'un code NAF</span><span class="sxs-lookup"><span data-stu-id="e2107-114">Set up a NAF code</span></span>
1. <span data-ttu-id="e2107-115">Accédez à Administration d'organisation > Carnet d'adresses global > Adresses > Codes NAF.</span><span class="sxs-lookup"><span data-stu-id="e2107-115">Go to Organization administration > Global address book > Addresses > NAF codes.</span></span>
2. <span data-ttu-id="e2107-116">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e2107-116">Click New.</span></span>
3. <span data-ttu-id="e2107-117">Tapez une valeur dans le champ Code NAF.</span><span class="sxs-lookup"><span data-stu-id="e2107-117">In the NAF code field, type a value.</span></span>
4. <span data-ttu-id="e2107-118">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e2107-118">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e2107-119">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e2107-119">Click Save.</span></span>

## <a name="enter-a-naf-code-and-a-siret-number-for-a-customer"></a><span data-ttu-id="e2107-120">Entrer un code NAF et un numéro SIRET pour un client</span><span class="sxs-lookup"><span data-stu-id="e2107-120">Enter a NAF code and a siret number for a customer</span></span>
1. <span data-ttu-id="e2107-121">Accédez à Comptabilité client > Clients > Tous les clients.</span><span class="sxs-lookup"><span data-stu-id="e2107-121">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="e2107-122">Cliquez sur l'enregistrement client à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="e2107-122">Click the customer record that you want to update.</span></span>
3. <span data-ttu-id="e2107-123">Développez la section Démographie de vente.</span><span class="sxs-lookup"><span data-stu-id="e2107-123">Expand the Sales demographics section.</span></span>
4. <span data-ttu-id="e2107-124">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="e2107-124">Click Edit.</span></span>
5. <span data-ttu-id="e2107-125">Tapez une valeur dans le champ N° de Siret.</span><span class="sxs-lookup"><span data-stu-id="e2107-125">In the French Siret field, type a value.</span></span>
6. <span data-ttu-id="e2107-126">Saisissez ou sélectionnez une valeur dans le champ Code NAF.</span><span class="sxs-lookup"><span data-stu-id="e2107-126">In the NAF code field, enter or select a value.</span></span>
7. <span data-ttu-id="e2107-127">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e2107-127">Click Save.</span></span>

## <a name="enter-a-naf-code-and-a-siret-number-for-a-vendor"></a><span data-ttu-id="e2107-128">Entrer un code NAF et un numéro SIRET pour un fournisseur</span><span class="sxs-lookup"><span data-stu-id="e2107-128">Enter a NAF code and a siret number for a vendor</span></span>
1. <span data-ttu-id="e2107-129">Accédez à Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="e2107-129">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="e2107-130">Cliquez sur l'enregistrement fournisseur à mettre à jour</span><span class="sxs-lookup"><span data-stu-id="e2107-130">Click the vendor record that you want to update.</span></span>
3. <span data-ttu-id="e2107-131">Développez la section Démographie des achats.</span><span class="sxs-lookup"><span data-stu-id="e2107-131">Expand the Purchasing demographics section.</span></span>
4. <span data-ttu-id="e2107-132">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="e2107-132">Click Edit.</span></span>
5. <span data-ttu-id="e2107-133">Tapez une valeur dans le champ N° de Siret.</span><span class="sxs-lookup"><span data-stu-id="e2107-133">In the French Siret field, type a value.</span></span>
6. <span data-ttu-id="e2107-134">Saisissez ou sélectionnez une valeur dans le champ Code NAF.</span><span class="sxs-lookup"><span data-stu-id="e2107-134">In the NAF code field, enter or select a value.</span></span>
7. <span data-ttu-id="e2107-135">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e2107-135">Click Save.</span></span>

## <a name="enter-a-naf-code-and-a-siret-number-for-a-prospect"></a><span data-ttu-id="e2107-136">Entrer un code NAF et un numéro SIRET pour un prospect</span><span class="sxs-lookup"><span data-stu-id="e2107-136">Enter a NAF code and a siret number for a prospect</span></span>
1. <span data-ttu-id="e2107-137">Accédez à Ventes et marketing > Relation > Prospects > Tous les prospects.</span><span class="sxs-lookup"><span data-stu-id="e2107-137">Go to Sales and marketing > Relationships > Prospects > All prospects.</span></span>
2. <span data-ttu-id="e2107-138">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e2107-138">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e2107-139">Cliquez sur l'enregistrement de prospect à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="e2107-139">Click the prospect record that you want to update.</span></span>
4. <span data-ttu-id="e2107-140">Développez la section Démographie de vente.</span><span class="sxs-lookup"><span data-stu-id="e2107-140">Expand the Sales demographics section.</span></span>
5. <span data-ttu-id="e2107-141">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="e2107-141">Click Edit.</span></span>
6. <span data-ttu-id="e2107-142">Tapez une valeur dans le champ N° de Siret.</span><span class="sxs-lookup"><span data-stu-id="e2107-142">In the French Siret field, type a value.</span></span>
7. <span data-ttu-id="e2107-143">Saisissez ou sélectionnez une valeur dans le champ Code NAF.</span><span class="sxs-lookup"><span data-stu-id="e2107-143">In the NAF code field, enter or select a value.</span></span>
8. <span data-ttu-id="e2107-144">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e2107-144">Click Save.</span></span>

## <a name="set-up-commerce-registration-a-legal-form-and-a-naf-code-for-a-legal-entity"></a><span data-ttu-id="e2107-145">Paramétrer un registre du commerce, une forme juridique, et un code NAF pour une entité juridique</span><span class="sxs-lookup"><span data-stu-id="e2107-145">Set up commerce registration, a legal form, and a NAF code for a legal entity</span></span>
1. <span data-ttu-id="e2107-146">Accédez à Administration d'organisation > Organisations > Entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="e2107-146">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="e2107-147">Développez la section Numéros d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e2107-147">Expand the Registration numbers section.</span></span>
3. <span data-ttu-id="e2107-148">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="e2107-148">Click Edit.</span></span>
4. <span data-ttu-id="e2107-149">Entrez une valeur dans le champ Registre du commerce.</span><span class="sxs-lookup"><span data-stu-id="e2107-149">In the Commerce registration field, type a value.</span></span>
    * <span data-ttu-id="e2107-150">Entrez le nom de l'agence française dans laquelle l'entité juridique a été enregistrée, par exemple le Registre du commerce et des sociétés.</span><span class="sxs-lookup"><span data-stu-id="e2107-150">Enter the name of the French agency where the legal entity is registered, such as the Registre du commerce et des sociétés.</span></span>  
5. <span data-ttu-id="e2107-151">Saisissez ou sélectionnez une valeur dans le champ Code NAF.</span><span class="sxs-lookup"><span data-stu-id="e2107-151">In the NAF code field, enter or select a value.</span></span>
6. <span data-ttu-id="e2107-152">Entrez une valeur dans le champ Forme juridique.</span><span class="sxs-lookup"><span data-stu-id="e2107-152">In the Legal form field, type a value.</span></span>
    * <span data-ttu-id="e2107-153">Entrez le type légal de l'entité juridique, tel que Organisation sans but lucratif, Entreprise industrielle ou Institution financière.</span><span class="sxs-lookup"><span data-stu-id="e2107-153">Enter the legal type of the legal entity, such as non-profit organization, manufacturing company, or financial institution.</span></span>  
7. <span data-ttu-id="e2107-154">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e2107-154">Click Save.</span></span>

