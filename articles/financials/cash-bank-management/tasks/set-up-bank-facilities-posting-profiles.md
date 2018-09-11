--- 
title: "Paramétrer les établissements bancaires et les profils de validation pour les lettres de garantie"
description: "Cette tâche crée un établissement bancaire et un profil de validation qui est nécessaire pour traiter une lettre de garantie."
author: kweekley
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: b78f82b60ee72bb91a4dd4aa13776eb8b74d7367
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a><span data-ttu-id="e75fb-103">Paramétrer les établissements bancaires et les profils de validation pour les lettres de garantie</span><span class="sxs-lookup"><span data-stu-id="e75fb-103">Set up bank facilities and posting profiles for letters of guarantee</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e75fb-104">Cette tâche crée un établissement bancaire et un profil de validation qui est nécessaire pour traiter une lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="e75fb-104">This task creates a Bank facility and posting profile that is needed to process a letter of guarantee.</span></span>



<span data-ttu-id="e75fb-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="e75fb-105">This task uses the USMF demo company.</span></span> 




## <a name="general-ledger-parameter"></a><span data-ttu-id="e75fb-106">Paramètre de comptabilité</span><span class="sxs-lookup"><span data-stu-id="e75fb-106">General ledger parameter</span></span>
1. <span data-ttu-id="e75fb-107">Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque.</span><span class="sxs-lookup"><span data-stu-id="e75fb-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="e75fb-108">Développez la section Document bancaire.</span><span class="sxs-lookup"><span data-stu-id="e75fb-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="e75fb-109">Sélectionnez l'option Activer la lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="e75fb-109">Select the Enable letter of guarantee option.</span></span>
4. <span data-ttu-id="e75fb-110">Dans le champ Journal des transactions, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e75fb-110">In the Transaction journal field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="e75fb-111">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e75fb-111">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="e75fb-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e75fb-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="e75fb-113">Cliquez sur l'onglet Souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="e75fb-113">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="e75fb-114">Définir le code souche de numéros du numéro de lettre de garantie et les références de transaction de lettre de garantie</span><span class="sxs-lookup"><span data-stu-id="e75fb-114">Define number sequence code for Letter of guarantee number and Letter of guarantee transaction references</span></span>  
8. <span data-ttu-id="e75fb-115">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e75fb-115">Click Save.</span></span>
9. <span data-ttu-id="e75fb-116">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e75fb-116">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="e75fb-117">Créer un établissement bancaire</span><span class="sxs-lookup"><span data-stu-id="e75fb-117">Create Bank facility</span></span>
1. <span data-ttu-id="e75fb-118">Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Établissements bancaires.</span><span class="sxs-lookup"><span data-stu-id="e75fb-118">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="e75fb-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e75fb-119">Click New.</span></span>
3. <span data-ttu-id="e75fb-120">Dans le champ Groupe d'établissements, entrez le nom du groupe d'établissements bancaires pour la transaction de lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="e75fb-120">In the Facility group field, enter the bank facility group name for the letter of guarantee transaction.</span></span>
4. <span data-ttu-id="e75fb-121">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e75fb-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e75fb-122">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e75fb-122">Click Save.</span></span>
6. <span data-ttu-id="e75fb-123">Cliquez sur l'onglet Types d'installations.</span><span class="sxs-lookup"><span data-stu-id="e75fb-123">Click the Facility types tab.</span></span>
7. <span data-ttu-id="e75fb-124">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e75fb-124">Click New.</span></span>
8. <span data-ttu-id="e75fb-125">Dans le champ Type d'établissement, entrez le nom du type d'établissement bancaire lié à l'accord d'établissement bancaire.</span><span class="sxs-lookup"><span data-stu-id="e75fb-125">In the Facility type field, enter the name of the bank facility type that is related to the bank facility agreement.</span></span>
9. <span data-ttu-id="e75fb-126">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="e75fb-126">In the Description field, type a value.</span></span>
10. <span data-ttu-id="e75fb-127">Dans le champ Groupe d'installations, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e75fb-127">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="e75fb-128">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e75fb-128">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="e75fb-129">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e75fb-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="e75fb-130">Dans le champ Nature de l'établissement, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="e75fb-130">In the Facility nature field, select an option.</span></span>
14. <span data-ttu-id="e75fb-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e75fb-131">Click Save.</span></span>
15. <span data-ttu-id="e75fb-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e75fb-132">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="e75fb-133">Profil de validation bancaire</span><span class="sxs-lookup"><span data-stu-id="e75fb-133">Bank posting profile</span></span>
1. <span data-ttu-id="e75fb-134">Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Profil de validation des documents bancaires.</span><span class="sxs-lookup"><span data-stu-id="e75fb-134">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="e75fb-135">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e75fb-135">Click New.</span></span>
3. <span data-ttu-id="e75fb-136">Dans le champ Numéro de compte/groupe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e75fb-136">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e75fb-137">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e75fb-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="e75fb-138">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e75fb-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e75fb-139">Dans le champ Compte de règlement, sélectionnez le compte principal pour le règlement.</span><span class="sxs-lookup"><span data-stu-id="e75fb-139">In the Settle account field, select the main account for settlement.</span></span>
7. <span data-ttu-id="e75fb-140">Dans le champ Frais, sélectionnez le compte pour les transactions de dépense.</span><span class="sxs-lookup"><span data-stu-id="e75fb-140">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="e75fb-141">Dans le champ Marge, sélectionnez le compte pour la transaction de marge.</span><span class="sxs-lookup"><span data-stu-id="e75fb-141">In the Margin account field, select the account for the margin transaction.</span></span>
9. <span data-ttu-id="e75fb-142">Dans le champ Compte de liquidation, sélectionnez le compte de liquidation pour la transaction de lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="e75fb-142">In the Liquidation account field, select the liquidation account for the letter of guarantee transaction.</span></span> 
10. <span data-ttu-id="e75fb-143">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e75fb-143">Click Save.</span></span>
11. <span data-ttu-id="e75fb-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e75fb-144">Close the page.</span></span>


