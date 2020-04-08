---
title: EUR-00015 Enregistrement de l'ID de TVA du fournisseur
description: Cette procédure indique comment ajouter des ID d'enregistrement de TVA et un numéro sans TVA à un compte fournisseur.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddress, RegNumTaxIdLookup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5126868038801091c7a9c17eee78e31db322cbb7
ms.sourcegitcommit: b92c3e1b3403d0455fc4e0bf9132d6bc0d7aba5e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138878"
---
# <a name="eur-00015-registration-of-vendor-vat-id"></a><span data-ttu-id="9c149-103">EUR-00015 Enregistrement de l'ID de TVA du fournisseur</span><span class="sxs-lookup"><span data-stu-id="9c149-103">EUR-00015 Registration of vendor VAT ID</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9c149-104">Cette procédure indique comment ajouter des ID d'enregistrement de TVA et un numéro sans TVA à un compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9c149-104">This procedure shows how to add VAT registration IDs and a tax except number to a vendor account.</span></span> <span data-ttu-id="9c149-105">Ce processus est similaire pour les entités juridiques et les clients.</span><span class="sxs-lookup"><span data-stu-id="9c149-105">This process is similar for legal entities and customers.</span></span> 

<span data-ttu-id="9c149-106">Pour pouvoir effectuer cette procédure, vous devez paramétrer des ID de TVA.</span><span class="sxs-lookup"><span data-stu-id="9c149-106">Before you can complete this procedure you must set up VAT IDs.</span></span> <span data-ttu-id="9c149-107">Cette procédure s'applique à tous les pays/régions européens.</span><span class="sxs-lookup"><span data-stu-id="9c149-107">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="9c149-108">La procédure a été créée avec les données de démonstration de la société fictive DEMF, avec une adresse principale en Allemagne.</span><span class="sxs-lookup"><span data-stu-id="9c149-108">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="9c149-109">Cette procédure s'adresse à un administrateur de la gestion des données, à un responsable de la comptabilité fournisseur ou à un responsable de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="9c149-109">This procedure is intended for a data management administrator, accounts payable manager, or accounts receivable manager.</span></span> <span data-ttu-id="9c149-110">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="9c149-110">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="9c149-111">Accédez à Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="9c149-111">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="9c149-112">Dans la liste, recherchez et sélectionnez le fournisseur DE-01001</span><span class="sxs-lookup"><span data-stu-id="9c149-112">In the list find and select vendor DE-01001</span></span>
3. <span data-ttu-id="9c149-113">Cliquez sur ID enregistrement.</span><span class="sxs-lookup"><span data-stu-id="9c149-113">Click Registration IDs.</span></span>
4. <span data-ttu-id="9c149-114">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="9c149-114">Click Add.</span></span>
5. <span data-ttu-id="9c149-115">Sélectionnez l'ID de TVA.</span><span class="sxs-lookup"><span data-stu-id="9c149-115">Select VAT ID.</span></span>
6. <span data-ttu-id="9c149-116">Dans le champ Numéro d'enregistrement, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9c149-116">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="9c149-117">Spécifiez un ID de TVA en Allemagne pour le fournisseur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9c149-117">Specify a VAT ID in Germany for the selected vendor.</span></span> <span data-ttu-id="9c149-118">L'ID doit correspondre au format spécifié du type d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="9c149-118">The ID must match the specified format of the registration type.</span></span>  
7. <span data-ttu-id="9c149-119">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="9c149-119">Click the General tab.</span></span>
8. <span data-ttu-id="9c149-120">Dans le champ Effet, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="9c149-120">In the Effective field, enter a date.</span></span>
9. <span data-ttu-id="9c149-121">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9c149-121">Click Save.</span></span>
10. <span data-ttu-id="9c149-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9c149-122">Click New.</span></span>
11. <span data-ttu-id="9c149-123">Tapez une valeur dans le champ Nom ou description.</span><span class="sxs-lookup"><span data-stu-id="9c149-123">In the Name or description field, type a value.</span></span>
    * <span data-ttu-id="9c149-124">Par exemple, entrez ITA.</span><span class="sxs-lookup"><span data-stu-id="9c149-124">For example, enter ITA.</span></span>  
12. <span data-ttu-id="9c149-125">Dans le champ Pays/Région, sélectionnez ou entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9c149-125">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="9c149-126">Par exemple, sélectionnez ITA.</span><span class="sxs-lookup"><span data-stu-id="9c149-126">For example, select ITA.</span></span>  
13. <span data-ttu-id="9c149-127">Sélectionnez Oui dans le champ Principal pour le pays.</span><span class="sxs-lookup"><span data-stu-id="9c149-127">Select Yes in the Primary for country field.</span></span>
14. <span data-ttu-id="9c149-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9c149-128">Click Save.</span></span>
15. <span data-ttu-id="9c149-129">Cliquez sur l'onglet Vue d'ensemble.</span><span class="sxs-lookup"><span data-stu-id="9c149-129">Click the Overview tab.</span></span>
16. <span data-ttu-id="9c149-130">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="9c149-130">Click Add.</span></span>
17. <span data-ttu-id="9c149-131">Dans le champ Type d'enregistrement, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9c149-131">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="9c149-132">Par exemple, sélectionnez ID TVA.</span><span class="sxs-lookup"><span data-stu-id="9c149-132">For example, select VAT ID.</span></span>  
18. <span data-ttu-id="9c149-133">Dans le champ Numéro d'enregistrement, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9c149-133">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="9c149-134">Par exemple, spécifiez un ID de TVA en Italie.</span><span class="sxs-lookup"><span data-stu-id="9c149-134">For example, specify a VAT ID in Italy.</span></span>  <span data-ttu-id="9c149-135">L'ID doit avoir le même format que le type d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="9c149-135">The ID must have the same format as the registration type.</span></span>  
19. <span data-ttu-id="9c149-136">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9c149-136">Click Save.</span></span>
20. <span data-ttu-id="9c149-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9c149-137">Close the page.</span></span>
21. <span data-ttu-id="9c149-138">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9c149-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9c149-139">Par exemple, sélectionnez DE-01001.</span><span class="sxs-lookup"><span data-stu-id="9c149-139">For example, select DE-01001.</span></span>  
22. <span data-ttu-id="9c149-140">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9c149-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="9c149-141">Développez la section Facturation et livraison.</span><span class="sxs-lookup"><span data-stu-id="9c149-141">Expand the Invoice and delivery section.</span></span>
24. <span data-ttu-id="9c149-142">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="9c149-142">Click Edit.</span></span>
25. <span data-ttu-id="9c149-143">Dans le champ Numéro identifiant TVA, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9c149-143">In the Tax exempt number field, enter or select a value.</span></span>
26. <span data-ttu-id="9c149-144">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9c149-144">Click Save.</span></span>

