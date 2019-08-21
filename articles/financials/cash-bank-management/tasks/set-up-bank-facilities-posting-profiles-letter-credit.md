---
title: Paramétrer les établissements bancaires et les profils de validation pour les lettres de crédit
description: Cette procédure décrit la création d'un établissement bancaire et un profil de validation requis pour traiter les lettres de crédit.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d3d35bd265ad31da083d2437fae886569766085
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841895"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a><span data-ttu-id="1acab-103">Paramétrer les établissements bancaires et les profils de validation pour les lettres de crédit</span><span class="sxs-lookup"><span data-stu-id="1acab-103">Set up bank facilities and posting profiles for letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1acab-104">Cette procédure décrit la création d'un établissement bancaire et un profil de validation requis pour traiter les lettres de crédit.</span><span class="sxs-lookup"><span data-stu-id="1acab-104">This procedure walks through creating a Bank facility and posting profile required to process Letters of credit.</span></span> 

<span data-ttu-id="1acab-105">La société fictive « USMF » est utilisée dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="1acab-105">This tasks uses the demo company 'USMF'.</span></span>






## <a name="general-ledger-parameter"></a><span data-ttu-id="1acab-106">Paramètre de comptabilité</span><span class="sxs-lookup"><span data-stu-id="1acab-106">General ledger parameter</span></span>
1. <span data-ttu-id="1acab-107">Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque.</span><span class="sxs-lookup"><span data-stu-id="1acab-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="1acab-108">Développez la section Document bancaire.</span><span class="sxs-lookup"><span data-stu-id="1acab-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="1acab-109">Sélectionnez l'option Activer la lettre de crédit d'importation.</span><span class="sxs-lookup"><span data-stu-id="1acab-109">Select the Enable import letter of credit option.</span></span>
4. <span data-ttu-id="1acab-110">Sélectionnez l'option Activer la lettre de crédit d'exportation.</span><span class="sxs-lookup"><span data-stu-id="1acab-110">Select the Enable export letter of credit option.</span></span>
5. <span data-ttu-id="1acab-111">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1acab-111">Click Save.</span></span>
6. <span data-ttu-id="1acab-112">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1acab-112">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="1acab-113">Créer un établissement bancaire</span><span class="sxs-lookup"><span data-stu-id="1acab-113">Create Bank facility</span></span>
1. <span data-ttu-id="1acab-114">Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Établissements bancaires.</span><span class="sxs-lookup"><span data-stu-id="1acab-114">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="1acab-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1acab-115">Click New.</span></span>
3. <span data-ttu-id="1acab-116">Dans le champ Installations, entrez le nom du groupe d'établissements bancaires.</span><span class="sxs-lookup"><span data-stu-id="1acab-116">In the Facility group field, enter the bank facility group name.</span></span>
4. <span data-ttu-id="1acab-117">Dans le champ Description, entrez la description du groupe d'établissements bancaires.</span><span class="sxs-lookup"><span data-stu-id="1acab-117">In the Description field, enter the bank facility group description.</span></span>
5. <span data-ttu-id="1acab-118">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1acab-118">Click Save.</span></span>
6. <span data-ttu-id="1acab-119">Cliquez sur l'onglet Types d'installations.</span><span class="sxs-lookup"><span data-stu-id="1acab-119">Click the Facility types tab.</span></span>
7. <span data-ttu-id="1acab-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1acab-120">Click New.</span></span>
8. <span data-ttu-id="1acab-121">Dans le champ Installations, entrez un code unique.</span><span class="sxs-lookup"><span data-stu-id="1acab-121">In the Facility type field, enter a unique code.</span></span>
9. <span data-ttu-id="1acab-122">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1acab-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="1acab-123">Dans le champ Groupe d'installations, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1acab-123">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="1acab-124">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1acab-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="1acab-125">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1acab-125">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="1acab-126">Dans le champ Nature de l'installation, sélectionnez la nature de l'installation bancaire.</span><span class="sxs-lookup"><span data-stu-id="1acab-126">In the Facility nature field, select the nature of the bank facility.</span></span>
14. <span data-ttu-id="1acab-127">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1acab-127">Click Save.</span></span>
15. <span data-ttu-id="1acab-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1acab-128">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="1acab-129">Profil de validation bancaire</span><span class="sxs-lookup"><span data-stu-id="1acab-129">Bank posting profile</span></span>
1. <span data-ttu-id="1acab-130">Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Profil de validation des documents bancaires.</span><span class="sxs-lookup"><span data-stu-id="1acab-130">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="1acab-131">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1acab-131">Click New.</span></span>
3. <span data-ttu-id="1acab-132">Dans le champ Numéro de compte/groupe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1acab-132">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="1acab-133">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1acab-133">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="1acab-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1acab-134">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="1acab-135">Sélectionnez la catégorie principale de l'accord.</span><span class="sxs-lookup"><span data-stu-id="1acab-135">Select the main account for settlement.</span></span>
    * <span data-ttu-id="1acab-136">Ce compte est utilisé lors du calcul de la prévision de flux de trésorerie.</span><span class="sxs-lookup"><span data-stu-id="1acab-136">This account is used when calculating cash flow forecast.</span></span>  
7. <span data-ttu-id="1acab-137">Dans le champ Frais, sélectionnez le compte pour les transactions de dépense.</span><span class="sxs-lookup"><span data-stu-id="1acab-137">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="1acab-138">Dans le champ Marge, sélectionnez le compte pour les transactions de marge.</span><span class="sxs-lookup"><span data-stu-id="1acab-138">In the Margin account field, select the account for margin transactions.</span></span>
    * <span data-ttu-id="1acab-139">Ce compte est débité lorsque la marge d'ouverture est validée et crédité lorsque le paiement est validé.</span><span class="sxs-lookup"><span data-stu-id="1acab-139">This account is debited when the opening margin is posted and credited when the payment is posted.</span></span>  
9. <span data-ttu-id="1acab-140">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1acab-140">Click Save.</span></span>

