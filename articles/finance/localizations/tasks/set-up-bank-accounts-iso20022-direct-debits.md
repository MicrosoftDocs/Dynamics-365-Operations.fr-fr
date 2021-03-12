---
title: Paramétrer les clients et les comptes bancaires du client pour les débits directs ISO20022
description: Cette tâche vous guide dans le paramétrage d’un compte bancaire client et d’un mandat de débit direct client qui sont requis pour générer le fichier de paiement client, par exemple le débit direct ISO20022.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, CustDirectDebitMandate, BankAccountTableLookUp,  LogisticsAddressCityLookup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 85c1faebe9a61ad2e708ba26c7a5f0cad15f5f8b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988199"
---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a><span data-ttu-id="fa238-103">Paramétrer les clients et les comptes bancaires du client pour les débits directs ISO20022</span><span class="sxs-lookup"><span data-stu-id="fa238-103">Set up customers and customer bank accounts for ISO20022 direct debits</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fa238-104">Cette tâche vous guide dans le paramétrage d’un compte bancaire client et d’un mandat de débit direct client qui sont requis pour générer le fichier de paiement client, par exemple le débit direct ISO20022.</span><span class="sxs-lookup"><span data-stu-id="fa238-104">This task walks you through setting up a customer bank account and a customer direct debit mandate which are required to generate the customer payment file like ISO20022 direct debit.</span></span> <span data-ttu-id="fa238-105">Selon les formats de paiement client paramétrés, des informations supplémentaires non décrites dans cette procédure peuvent être requises pour un client ou un compte bancaire client.</span><span class="sxs-lookup"><span data-stu-id="fa238-105">Depending on the customer payment formats tha are set up, additional information, not covered in this procedure, might be required for a customer or a customer bank account.</span></span> 

<span data-ttu-id="fa238-106">Cette tâche a été créée avec les données de démonstration de la société fictive DEMF, avec l’adresse principale de l’entité juridique en Allemagne.</span><span class="sxs-lookup"><span data-stu-id="fa238-106">This task was created using the demo data company DEMF with a legal entity primary address in Germany.</span></span>



<span data-ttu-id="fa238-107">Il s’agit de la quatrième des cinq procédures illustrant le processus de paiement client à l’aide des configurations de génération d’états électroniques.</span><span class="sxs-lookup"><span data-stu-id="fa238-107">This is the fourth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>


## <a name="set-up-a-customer-bank-account"></a><span data-ttu-id="fa238-108">Paramétrer un compte bancaire client</span><span class="sxs-lookup"><span data-stu-id="fa238-108">Set up a customer bank account</span></span>
1. <span data-ttu-id="fa238-109">Accédez à Comptabilité client > Clients > Tous les clients.</span><span class="sxs-lookup"><span data-stu-id="fa238-109">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="fa238-110">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="fa238-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="fa238-111">Par exemple, appliquez un filtre au champ Compte avec une valeur de « DE-010 ».</span><span class="sxs-lookup"><span data-stu-id="fa238-111">For example, filter on the Account field with a value of 'DE-010 '.</span></span>
3. <span data-ttu-id="fa238-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fa238-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="fa238-113">Cliquez sur Client dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="fa238-113">On the Action Pane, click Customer.</span></span>
5. <span data-ttu-id="fa238-114">Cliquez sur Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="fa238-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="fa238-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fa238-115">Click New.</span></span>
7. <span data-ttu-id="fa238-116">Tapez une valeur dans le champ Compte en banque.</span><span class="sxs-lookup"><span data-stu-id="fa238-116">In the Bank account field, type a value.</span></span>
8. <span data-ttu-id="fa238-117">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="fa238-117">In the Name field, type a value.</span></span>
    * <span data-ttu-id="fa238-118">Par exemple, entrez « Compte bancaire EUR ».</span><span class="sxs-lookup"><span data-stu-id="fa238-118">For example, enter 'EUR bank'.</span></span>  
9. <span data-ttu-id="fa238-119">Dans le champ Groupes de banques, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fa238-119">In the Bank groups field, enter or select a value.</span></span>
10. <span data-ttu-id="fa238-120">Tapez une valeur dans le champ IBAN.</span><span class="sxs-lookup"><span data-stu-id="fa238-120">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="fa238-121">Par exemple, entrez « DE36200400000628808808 ».</span><span class="sxs-lookup"><span data-stu-id="fa238-121">For example, enter 'DE36200400000628808808'.</span></span>  
11. <span data-ttu-id="fa238-122">Tapez une valeur dans le champ Code SWIFT.</span><span class="sxs-lookup"><span data-stu-id="fa238-122">In the SWIFT code field, type a value.</span></span>
    * <span data-ttu-id="fa238-123">Par exemple, entrez COBADEFFXXX.</span><span class="sxs-lookup"><span data-stu-id="fa238-123">For example: Enter 'COBADEFFXXX'.</span></span>  <span data-ttu-id="fa238-124">Notez que le code SWIFT\BIC n’est pas obligatoire pour de nombreux formats de paiement, mais il est recommandé de le faire enregistrer pour un compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="fa238-124">Please note that SWIFT \ BIC is not mandatory for many payment formats however it is recommended to have it registered for a bank account.</span></span>  
12. <span data-ttu-id="fa238-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fa238-125">Click Save.</span></span>
13. <span data-ttu-id="fa238-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fa238-126">Close the page.</span></span>
14. <span data-ttu-id="fa238-127">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="fa238-127">Click Edit.</span></span>
15. <span data-ttu-id="fa238-128">Développez la section Valeurs par défaut du paiement.</span><span class="sxs-lookup"><span data-stu-id="fa238-128">Expand the Payment defaults section.</span></span>
16. <span data-ttu-id="fa238-129">Dans le champ Compte en banque, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fa238-129">In the Bank account field, enter or select a value.</span></span>

## <a name="add-a-direct-debit-mandate"></a><span data-ttu-id="fa238-130">Ajouter un mandat de débit direct</span><span class="sxs-lookup"><span data-stu-id="fa238-130">Add a direct debit mandate</span></span>
1. <span data-ttu-id="fa238-131">Développez la section Mandats de débit direct.</span><span class="sxs-lookup"><span data-stu-id="fa238-131">Expand the Direct debit mandates section.</span></span>
2. <span data-ttu-id="fa238-132">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="fa238-132">Click Add.</span></span>
3. <span data-ttu-id="fa238-133">Dans le champ Compte bancaire du créditeur, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fa238-133">In the Creditor bank account field, enter or select a value.</span></span>
    * <span data-ttu-id="fa238-134">Par exemple, sélectionnez DEMF OPER.</span><span class="sxs-lookup"><span data-stu-id="fa238-134">For example, select DEMF OPER.</span></span>  
4. <span data-ttu-id="fa238-135">Entrez une date dans le champ Date de signature.</span><span class="sxs-lookup"><span data-stu-id="fa238-135">In the Signature date field, enter a date.</span></span>
5. <span data-ttu-id="fa238-136">Cliquez sur Oui pour confirmer la mise à jour de la date.</span><span class="sxs-lookup"><span data-stu-id="fa238-136">Click Yes to confirm the date update.</span></span>
6. <span data-ttu-id="fa238-137">Saisissez ou sélectionnez une valeur dans le champ Emplacement de la signature.</span><span class="sxs-lookup"><span data-stu-id="fa238-137">In the Signature location field, enter or select a value.</span></span>
7. <span data-ttu-id="fa238-138">Entrez un nombre dans le champ Nombre de paiements prévus.</span><span class="sxs-lookup"><span data-stu-id="fa238-138">In the Expected number of payments field, enter a number.</span></span>
8. <span data-ttu-id="fa238-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fa238-139">Click OK.</span></span>
9. <span data-ttu-id="fa238-140">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fa238-140">Click Save.</span></span>

