--- 
title: "Création d'un compte fournisseur"
description: "Cette procédure indique comment créer un compte fournisseur, puis ajouter une adresse et des informations de contact."
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 22c7a1a2b7468f00aa25a67a2c5f62b088e2fe7c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-vendor-account"></a><span data-ttu-id="085f9-103">Création d'un compte fournisseur</span><span class="sxs-lookup"><span data-stu-id="085f9-103">Create a vendor account</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="085f9-104">Cette procédure indique comment créer un compte fournisseur, puis ajouter une adresse et des informations de contact.</span><span class="sxs-lookup"><span data-stu-id="085f9-104">This procedure shows how to create a vendor account, and add an address and contact information.</span></span> <span data-ttu-id="085f9-105">La procédure ne montre pas comment renseigner tous les champs à des fins d'achat et de gestion financière.</span><span class="sxs-lookup"><span data-stu-id="085f9-105">The procedure does not show how to populate all fields for purchasing and financial purposes.</span></span> <span data-ttu-id="085f9-106">Pour plus d'informations sur ces champs, lisez les descriptions des champs.</span><span class="sxs-lookup"><span data-stu-id="085f9-106">To learn more about those fields, please read the field descriptions.</span></span> <span data-ttu-id="085f9-107">Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="085f9-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="085f9-108">Les comptes fournisseur sont généralement créés par un professionnel de l'approvisionnement ou de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="085f9-108">Vendor accounts are typically created by a procurement professional or accounts receivable personnel.</span></span>


## <a name="create-a-vendor-account"></a><span data-ttu-id="085f9-109">Création d'un compte fournisseur</span><span class="sxs-lookup"><span data-stu-id="085f9-109">Create a vendor account</span></span>
1. <span data-ttu-id="085f9-110">Accédez à Approvisionnements > Fournisseurs > Tous les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="085f9-110">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="085f9-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="085f9-111">Click New.</span></span>
3. <span data-ttu-id="085f9-112">Tapez une valeur dans le champ Compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="085f9-112">In the Vendor account field, type a value.</span></span>
    * <span data-ttu-id="085f9-113">La valeur peut être automatiquement renseignée.</span><span class="sxs-lookup"><span data-stu-id="085f9-113">The value may be populated automatically.</span></span> <span data-ttu-id="085f9-114">Dans ce cas, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="085f9-114">If so, you can skip this step.</span></span>  
    * <span data-ttu-id="085f9-115">Vous pouvez créer des comptes fournisseurs pour une personne ou une organisation.</span><span class="sxs-lookup"><span data-stu-id="085f9-115">You can create vendor accounts for a person or organization.</span></span> <span data-ttu-id="085f9-116">Cela affecte la disponibilité des champs.</span><span class="sxs-lookup"><span data-stu-id="085f9-116">This will affect which fields are available.</span></span> <span data-ttu-id="085f9-117">Dans cet exemple, nous créerons un compte fournisseur pour une organisation.</span><span class="sxs-lookup"><span data-stu-id="085f9-117">In this example, we’ll create a vendor account for an organization.</span></span>   
4. <span data-ttu-id="085f9-118">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="085f9-118">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="085f9-119">Si votre fournisseur est déjà enregistré dans votre système, vous pouvez utiliser la liste déroulante et le sélectionner dans ce champ. Le compte fournisseur héritera des informations d'adresse et de contact qui sont déjà enregistrées.</span><span class="sxs-lookup"><span data-stu-id="085f9-119">If your vendor is an already a registered party in your system you can use drop down and select them in this field and the new vendor account will inherit the address and contact information that’s already registered.</span></span>  
5. <span data-ttu-id="085f9-120">Saisissez ou sélectionnez une valeur dans le champ Groupe.</span><span class="sxs-lookup"><span data-stu-id="085f9-120">In the Group field, enter or select a value.</span></span>
    * <span data-ttu-id="085f9-121">Le groupe de fournisseurs permet de regrouper les fournisseurs qui ont l'un des paramètres suivants en commun : Conditions de paiement ; retards de règlement, y compris les groupes de taxes ; comptes généraux par défaut ; codes de filtres produits ou configuration des prévisions d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="085f9-121">The vendor group is used to group vendors that have any of the following parameters in common: Terms of payment , settle period,  inventory posting ledger accounts – including the sales tax group, default ledger accounts, product filter codes, or supply forecast configuration.</span></span>  
6. <span data-ttu-id="085f9-122">Dans le champ Nombre d'employés, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="085f9-122">In the Number of employees field, enter a number.</span></span>
7. <span data-ttu-id="085f9-123">Dans le champ Numéro de l'organisation, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="085f9-123">In the Organization number field, type a value.</span></span>

## <a name="add-an-address"></a><span data-ttu-id="085f9-124">Ajouter une adresse</span><span class="sxs-lookup"><span data-stu-id="085f9-124">Add an address</span></span>
1. <span data-ttu-id="085f9-125">Développez la section Adresses.</span><span class="sxs-lookup"><span data-stu-id="085f9-125">Expand the Addresses section.</span></span>
2. <span data-ttu-id="085f9-126">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="085f9-126">Click Add.</span></span>
3. <span data-ttu-id="085f9-127">Saisissez ou sélectionnez une valeur dans le champ Objectif.</span><span class="sxs-lookup"><span data-stu-id="085f9-127">In the Purpose field, enter or select a value.</span></span>
    * <span data-ttu-id="085f9-128">Vous pouvez sélectionner un ou plusieurs objets.</span><span class="sxs-lookup"><span data-stu-id="085f9-128">You can select one or more purposes.</span></span> <span data-ttu-id="085f9-129">Ils sont utilisés pour sélectionner l'adresse correcte pour un objet donné.</span><span class="sxs-lookup"><span data-stu-id="085f9-129">These are used to select the correct address for a given purpose.</span></span> <span data-ttu-id="085f9-130">Par exemple, si l'objet est « Facture » cette adresse est utilisée pour l'envoi des factures.</span><span class="sxs-lookup"><span data-stu-id="085f9-130">For example, if the purpose is “Invoice” that address will be used when you send invoices.</span></span>  
4. <span data-ttu-id="085f9-131">Tapez une valeur dans le champ Nom ou description.</span><span class="sxs-lookup"><span data-stu-id="085f9-131">In the Name or description field, type a value.</span></span>
5. <span data-ttu-id="085f9-132">Dans le champ Pays/Région, sélectionnez ou entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="085f9-132">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="085f9-133">Entrez les détails d'adresse.</span><span class="sxs-lookup"><span data-stu-id="085f9-133">Enter the address details.</span></span> <span data-ttu-id="085f9-134">Le pays/la région que vous avez sélectionné déterminera les champs qui apparaîtront, en fonction du format d'adresse pour le pays/la région.</span><span class="sxs-lookup"><span data-stu-id="085f9-134">The country/region that you selected will determine the fields you are presented with, corresponding to the address format for the country/region.</span></span>   
6. <span data-ttu-id="085f9-135">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="085f9-135">Click OK.</span></span>

## <a name="add-contact-information"></a><span data-ttu-id="085f9-136">Ajouter des informations de contact</span><span class="sxs-lookup"><span data-stu-id="085f9-136">Add contact information</span></span>
1. <span data-ttu-id="085f9-137">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="085f9-137">Click Add.</span></span>
2. <span data-ttu-id="085f9-138">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="085f9-138">In the Description field, type a value.</span></span>
3. <span data-ttu-id="085f9-139">Sélectionnez une option dans le champ Type.</span><span class="sxs-lookup"><span data-stu-id="085f9-139">In the Type field, select an option.</span></span>
4. <span data-ttu-id="085f9-140">Saisissez une valeur dans le champ Numéro/adresse du contact.</span><span class="sxs-lookup"><span data-stu-id="085f9-140">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="085f9-141">Vous pouvez activer la case à cocher Principal s'il s'agit de l'adresse principale du contact.</span><span class="sxs-lookup"><span data-stu-id="085f9-141">You can select the Primary check box if this is the primary contact.</span></span>  
5. <span data-ttu-id="085f9-142">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="085f9-142">Click Save.</span></span>
6. <span data-ttu-id="085f9-143">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="085f9-143">Close the page.</span></span>
7. <span data-ttu-id="085f9-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="085f9-144">Close the page.</span></span>


