---
title: ER Générer les documents électroniques pour les paiements à l’aide d’une configuration de format
description: Cette rubrique décrit comment utiliser une nouvelle configuration de format de gestion des états électroniques pour générer les documents électroniques pour le traitement des paiements.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 816f98660a5508ada203f49a71e0785548fb9a31
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092198"
---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a><span data-ttu-id="13c94-103">ER Générer les documents électroniques pour les paiements à l’aide d’une configuration de format</span><span class="sxs-lookup"><span data-stu-id="13c94-103">ER Generate electronic documents for payments using a format configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="13c94-104">Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d’états électroniques peut utiliser une nouvelle configuration de format pour la génération d’états électronique (ER) pour générer des documents électroniques pour traiter les paiements.</span><span class="sxs-lookup"><span data-stu-id="13c94-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can use a new Electronic reporting (ER) format configuration to generate electronic documents for processing payments.</span></span> <span data-ttu-id="13c94-105">Ces étapes peuvent être effectuées dans la société fictive GBSI.</span><span class="sxs-lookup"><span data-stu-id="13c94-105">These steps can be performed in the GBSI sample company.</span></span>

<span data-ttu-id="13c94-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer une configuration avec le format du document de paiement ».</span><span class="sxs-lookup"><span data-stu-id="13c94-106">To complete these steps, you must first complete the steps in the "Create a configuration with format of payment document" procedure.</span></span>


## <a name="change-the-configuration-of-the-electronic-payment-method"></a><span data-ttu-id="13c94-107">Modifier la configuration de la méthode de paiement électronique</span><span class="sxs-lookup"><span data-stu-id="13c94-107">Change the configuration of the electronic payment method</span></span>
1. <span data-ttu-id="13c94-108">Accédez à Comptabilité fournisseur > Paramétrage des paiements > Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="13c94-108">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="13c94-109">Basculez la section de format de fichier pour la développer, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="13c94-109">Toggle the File format section to expand it, if needed.</span></span>
3. <span data-ttu-id="13c94-110">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="13c94-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="13c94-111">Par exemple, filtrez le champ Mode de paiement avec une valeur « Électronique ».</span><span class="sxs-lookup"><span data-stu-id="13c94-111">For example, filter on the Method of payment field with a value of 'Electronic'.</span></span>
4. <span data-ttu-id="13c94-112">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="13c94-112">Click Edit.</span></span>
5. <span data-ttu-id="13c94-113">Définissez le champ de génération d’états électroniques génériques sur Oui.</span><span class="sxs-lookup"><span data-stu-id="13c94-113">Set the General electronic reporting field to Yes.</span></span>
    * <span data-ttu-id="13c94-114">Sélectionnez Oui pour utiliser le modèle de génération d’états électroniques génériques pour la génération des fichiers de paiement.</span><span class="sxs-lookup"><span data-stu-id="13c94-114">Select Yes to use the General electronic reporting pattern for payment files generation.</span></span>  
6. <span data-ttu-id="13c94-115">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="13c94-115">In the Name field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="13c94-116">Sélectionnez la configuration de format BACS (nom fictif britannique).</span><span class="sxs-lookup"><span data-stu-id="13c94-116">Select BACS (UK fictitious) format configuration.</span></span>
8. <span data-ttu-id="13c94-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="13c94-117">Click Save.</span></span>
9. <span data-ttu-id="13c94-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="13c94-118">Close the page.</span></span>

## <a name="test-the-format-of-generated-payment-files"></a><span data-ttu-id="13c94-119">Tester le format des fichiers de paiement générés</span><span class="sxs-lookup"><span data-stu-id="13c94-119">Test the format of generated payment files</span></span>
1. <span data-ttu-id="13c94-120">Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="13c94-120">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="13c94-121">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="13c94-121">Click New.</span></span>
3. <span data-ttu-id="13c94-122">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13c94-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="13c94-123">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="13c94-123">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="13c94-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13c94-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="13c94-125">Sélectionnez VendPay.</span><span class="sxs-lookup"><span data-stu-id="13c94-125">Select VendPay.</span></span>  
6. <span data-ttu-id="13c94-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="13c94-126">Click Save.</span></span>
7. <span data-ttu-id="13c94-127">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="13c94-127">Click Lines.</span></span>
8. <span data-ttu-id="13c94-128">Tapez DEMF dans le champ Société.</span><span class="sxs-lookup"><span data-stu-id="13c94-128">In the Company field, type 'DEMF'.</span></span>
    * <span data-ttu-id="13c94-129">DEMF</span><span class="sxs-lookup"><span data-stu-id="13c94-129">DEMF</span></span>  
9. <span data-ttu-id="13c94-130">Dans le champ Compte, spécifiez les valeurs « DE-01001 ».</span><span class="sxs-lookup"><span data-stu-id="13c94-130">In the Account field, specify the values 'DE-01001'.</span></span>
    * <span data-ttu-id="13c94-131">DE - 01001</span><span class="sxs-lookup"><span data-stu-id="13c94-131">DE-01001</span></span>  
10. <span data-ttu-id="13c94-132">Tapez Paiement dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="13c94-132">In the Description field, type 'Payment'.</span></span>
    * <span data-ttu-id="13c94-133">Paiement</span><span class="sxs-lookup"><span data-stu-id="13c94-133">Payment</span></span>  
11. <span data-ttu-id="13c94-134">Entrez un nombre dans le champ Débit.</span><span class="sxs-lookup"><span data-stu-id="13c94-134">In the Debit field, enter a number.</span></span>
    * <span data-ttu-id="13c94-135">1 000</span><span class="sxs-lookup"><span data-stu-id="13c94-135">1000</span></span>  
12. <span data-ttu-id="13c94-136">Cliquez sur l’onglet Paiement.</span><span class="sxs-lookup"><span data-stu-id="13c94-136">Click the Payment tab.</span></span>
13. <span data-ttu-id="13c94-137">Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="13c94-137">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="13c94-138">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="13c94-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="13c94-139">Sélectionnez la valeur électronique.</span><span class="sxs-lookup"><span data-stu-id="13c94-139">Select the Electronic value.</span></span>  
15. <span data-ttu-id="13c94-140">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13c94-140">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="13c94-141">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="13c94-141">Click Save.</span></span>
17. <span data-ttu-id="13c94-142">Cliquez sur Générer les paiements.</span><span class="sxs-lookup"><span data-stu-id="13c94-142">Click Generate payments.</span></span>
18. <span data-ttu-id="13c94-143">Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="13c94-143">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="13c94-144">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="13c94-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="13c94-145">Sélectionnez la valeur électronique.</span><span class="sxs-lookup"><span data-stu-id="13c94-145">Select the Electronic value.</span></span>  
20. <span data-ttu-id="13c94-146">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13c94-146">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="13c94-147">Sélectionnez la valeur électronique.</span><span class="sxs-lookup"><span data-stu-id="13c94-147">Select the Electronic value.</span></span>  
21. <span data-ttu-id="13c94-148">Tapez une valeur dans le champ Nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="13c94-148">In the File name field, type a value.</span></span>
    * <span data-ttu-id="13c94-149">Tapez Paiements, par exemple.</span><span class="sxs-lookup"><span data-stu-id="13c94-149">For example, type 'payments'.</span></span>  
22. <span data-ttu-id="13c94-150">Dans le champ Compte bancaire, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="13c94-150">In the Bank account field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="13c94-151">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13c94-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="13c94-152">Sélectionnez la valeur GBSI OPER.</span><span class="sxs-lookup"><span data-stu-id="13c94-152">Select the value GBSI OPER.</span></span>  
24. <span data-ttu-id="13c94-153">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="13c94-153">Click OK.</span></span>
25. <span data-ttu-id="13c94-154">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="13c94-154">Click OK.</span></span>
    * <span data-ttu-id="13c94-155">Analysez le fichier de paiement créé au format XML.</span><span class="sxs-lookup"><span data-stu-id="13c94-155">Analyze the created payment file in XML format.</span></span> <span data-ttu-id="13c94-156">Comparez-le à la structure de document conçue et aux attributs de transaction de paiement définis.</span><span class="sxs-lookup"><span data-stu-id="13c94-156">Compare it with the designed document layout and defined payment transaction attributes.</span></span>  

