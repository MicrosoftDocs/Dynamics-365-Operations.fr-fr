--- 
title: "Paramétrer les établissements bancaires et les profils de validation pour les lettres de crédit"
description: "Cette procédure décrit la création d'un établissement bancaire et un profil de validation requis pour traiter les lettres de crédit."
author: kweekley
manager: AnnBe
ms.date: 10/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 18ad27eb673745d09569f6a49c8bc66132550f35
ms.openlocfilehash: 9ad19534091bdbd8924f90174b720d818b9ed778
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a><span data-ttu-id="8f32e-103">Paramétrer les établissements bancaires et les profils de validation pour les lettres de crédit</span><span class="sxs-lookup"><span data-stu-id="8f32e-103">Set up bank facilities and posting profiles for letter of credit</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8f32e-104">Cette procédure décrit la création d'un établissement bancaire et un profil de validation requis pour traiter les lettres de crédit.</span><span class="sxs-lookup"><span data-stu-id="8f32e-104">This procedure walks through creating a Bank facility and posting profile required to process Letters of credit.</span></span> 

<span data-ttu-id="8f32e-105">Cette tâche utilise la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="8f32e-105">This task uses the demo company 'USMF'.</span></span>






## <a name="general-ledger-parameter"></a><span data-ttu-id="8f32e-106">Paramètre de comptabilité</span><span class="sxs-lookup"><span data-stu-id="8f32e-106">General ledger parameter</span></span>
1. <span data-ttu-id="8f32e-107">Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque.</span><span class="sxs-lookup"><span data-stu-id="8f32e-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="8f32e-108">Développez la section Document bancaire.</span><span class="sxs-lookup"><span data-stu-id="8f32e-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="8f32e-109">Sélectionnez l'option Activer la lettre de crédit d'importation.</span><span class="sxs-lookup"><span data-stu-id="8f32e-109">Select the Enable import letter of credit option.</span></span>
4. <span data-ttu-id="8f32e-110">Sélectionnez l'option Activer la lettre de crédit d'exportation.</span><span class="sxs-lookup"><span data-stu-id="8f32e-110">Select the Enable export letter of credit option.</span></span>
5. <span data-ttu-id="8f32e-111">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8f32e-111">Click Save.</span></span>
6. <span data-ttu-id="8f32e-112">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8f32e-112">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="8f32e-113">Créer un établissement bancaire</span><span class="sxs-lookup"><span data-stu-id="8f32e-113">Create Bank facility</span></span>
1. <span data-ttu-id="8f32e-114">Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Établissements bancaires.</span><span class="sxs-lookup"><span data-stu-id="8f32e-114">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="8f32e-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8f32e-115">Click New.</span></span>
3. <span data-ttu-id="8f32e-116">Dans le champ Installations, entrez le nom du groupe d'établissements bancaires.</span><span class="sxs-lookup"><span data-stu-id="8f32e-116">In the Facility group field, enter the bank facility group name.</span></span>
4. <span data-ttu-id="8f32e-117">Dans le champ Description, entrez la description du groupe d'établissements bancaires.</span><span class="sxs-lookup"><span data-stu-id="8f32e-117">In the Description field, enter the bank facility group description.</span></span>
5. <span data-ttu-id="8f32e-118">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8f32e-118">Click Save.</span></span>
6. <span data-ttu-id="8f32e-119">Cliquez sur l'onglet Types d'installations.</span><span class="sxs-lookup"><span data-stu-id="8f32e-119">Click the Facility types tab.</span></span>
7. <span data-ttu-id="8f32e-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8f32e-120">Click New.</span></span>
8. <span data-ttu-id="8f32e-121">Dans le champ Installations, entrez un code unique.</span><span class="sxs-lookup"><span data-stu-id="8f32e-121">In the Facility type field, enter a unique code.</span></span>
9. <span data-ttu-id="8f32e-122">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8f32e-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="8f32e-123">Dans le champ Groupe d'installations, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="8f32e-123">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="8f32e-124">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="8f32e-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="8f32e-125">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8f32e-125">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="8f32e-126">Dans le champ Nature de l'installation, sélectionnez la nature de l'installation bancaire.</span><span class="sxs-lookup"><span data-stu-id="8f32e-126">In the Facility nature field, select the nature of the bank facility.</span></span>
14. <span data-ttu-id="8f32e-127">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8f32e-127">Click Save.</span></span>
15. <span data-ttu-id="8f32e-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8f32e-128">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="8f32e-129">Profil de validation bancaire</span><span class="sxs-lookup"><span data-stu-id="8f32e-129">Bank posting profile</span></span>
1. <span data-ttu-id="8f32e-130">Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Profil de validation des documents bancaires.</span><span class="sxs-lookup"><span data-stu-id="8f32e-130">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="8f32e-131">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8f32e-131">Click New.</span></span>
3. <span data-ttu-id="8f32e-132">Dans le champ Numéro de compte/groupe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="8f32e-132">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="8f32e-133">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="8f32e-133">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="8f32e-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8f32e-134">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="8f32e-135">Sélectionnez la catégorie principale de l'accord.</span><span class="sxs-lookup"><span data-stu-id="8f32e-135">Select the main account for settlement.</span></span>
    * <span data-ttu-id="8f32e-136">Ce compte est utilisé lors du calcul de la prévision de flux de trésorerie.</span><span class="sxs-lookup"><span data-stu-id="8f32e-136">This account is used when calculating cash flow forecast.</span></span>  
7. <span data-ttu-id="8f32e-137">Dans le champ Frais, sélectionnez le compte pour les transactions de dépense.</span><span class="sxs-lookup"><span data-stu-id="8f32e-137">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="8f32e-138">Dans le champ Marge, sélectionnez le compte pour les transactions de marge.</span><span class="sxs-lookup"><span data-stu-id="8f32e-138">In the Margin account field, select the account for margin transactions.</span></span>
    * <span data-ttu-id="8f32e-139">Ce compte est débité lorsque la marge d'ouverture est validée et crédité lorsque le paiement est validé.</span><span class="sxs-lookup"><span data-stu-id="8f32e-139">This account is debited when the opening margin is posted and credited when the payment is posted.</span></span>  
9. <span data-ttu-id="8f32e-140">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8f32e-140">Click Save.</span></span>

