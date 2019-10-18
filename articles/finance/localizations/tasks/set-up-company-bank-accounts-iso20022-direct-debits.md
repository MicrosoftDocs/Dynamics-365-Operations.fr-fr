---
title: Paramétrer les comptes bancaires de société pour les débits directs ISO20022
description: Cette tâche vous guide dans le paramétrage des informations de compte bancaire spécifiques à une société qui sont requises pour la génération des fichiers de paiement client.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 89c4a8d3cb504df97bad5679bf12b3cdb5931d95
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185702"
---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a><span data-ttu-id="bec15-103">Paramétrer les comptes bancaires de société pour les débits directs ISO20022</span><span class="sxs-lookup"><span data-stu-id="bec15-103">Set up company bank accounts for ISO20022 direct debits</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bec15-104">Cette tâche vous guide dans le paramétrage des informations de compte bancaire spécifiques à une société qui sont requises pour la génération des fichiers de paiement client.</span><span class="sxs-lookup"><span data-stu-id="bec15-104">This task walks you through setting up the company specific bank account information that is required for generating customer payment files.</span></span> <span data-ttu-id="bec15-105">Cette procédure utilise le format de débit direct ISO 20022 comme exemple.</span><span class="sxs-lookup"><span data-stu-id="bec15-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> <span data-ttu-id="bec15-106">D'autres formats peuvent nécessiter des informations de paramétrage supplémentaires, par exemple l'ID société ou la priorité.</span><span class="sxs-lookup"><span data-stu-id="bec15-106">Other formats might require additional setup information like the Company ID or the Sort code.</span></span>



<span data-ttu-id="bec15-107">Cette tâche a été créé à l'aide de la société DEMF fictive.</span><span class="sxs-lookup"><span data-stu-id="bec15-107">This task was created using the demo data company DEMF.</span></span>



<span data-ttu-id="bec15-108">Il s'agit de la deuxième des cinq procédures illustrant le processus de paiement client à l'aide des configurations de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="bec15-108">This is the second of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>


## <a name="set-up-the-iban-and-swift-codes"></a><span data-ttu-id="bec15-109">Paramétrer des codes IBAN et SWIFT</span><span class="sxs-lookup"><span data-stu-id="bec15-109">Set up the IBAN and SWIFT codes</span></span>
1. <span data-ttu-id="bec15-110">Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="bec15-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="bec15-111">Utilisez le filtre rapide pour filtrer sur le champ Compte bancaire avec une valeur de « DEMF OPER ».</span><span class="sxs-lookup"><span data-stu-id="bec15-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="bec15-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bec15-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="bec15-113">Par exemple, cliquez sur « DEMF OPER » pour ouvrir les détails du compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="bec15-113">For example, click 'DEMF OPER' to open the bank account details.</span></span>  
4. <span data-ttu-id="bec15-114">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="bec15-114">Click Edit.</span></span>
5. <span data-ttu-id="bec15-115">Développez ou réduisez la section Identification supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="bec15-115">Expand or collapse the Additional identification section.</span></span>
6. <span data-ttu-id="bec15-116">Tapez une valeur dans le champ IBAN.</span><span class="sxs-lookup"><span data-stu-id="bec15-116">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="bec15-117">Par exemple, entrez « DE89370400440532013000 ».</span><span class="sxs-lookup"><span data-stu-id="bec15-117">For example, enter 'DE89370400440532013000'.</span></span>  
7. <span data-ttu-id="bec15-118">Tapez une valeur dans le champ Code SWIFT.</span><span class="sxs-lookup"><span data-stu-id="bec15-118">In the SWIFT code field, type a value.</span></span>
    * <span data-ttu-id="bec15-119">Par exemple, entrez « DEUTDEFF ».</span><span class="sxs-lookup"><span data-stu-id="bec15-119">For example, enter 'DEUTDEFF'.</span></span>    <span data-ttu-id="bec15-120">Notez que le code SWIFT\BIC n'est pas obligatoire pour de nombreux formats de paiement, mais il est recommandé de le faire enregistrer pour un compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="bec15-120">Please note that SWIFT \ BIC is not mandatory for many payment formats however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="bec15-121">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bec15-121">Click Save.</span></span>

## <a name="set-up-a-bank-account-for-the-legal-entity"></a><span data-ttu-id="bec15-122">Paramétrer un compte bancaire pour l'entité juridique</span><span class="sxs-lookup"><span data-stu-id="bec15-122">Set up a bank account for the legal entity</span></span>
1. <span data-ttu-id="bec15-123">Accédez à Administration d'organisation > Organisations > Entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="bec15-123">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="bec15-124">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="bec15-124">Click Edit.</span></span>
3. <span data-ttu-id="bec15-125">Développez ou réduisez la section la section Informations sur le compte en banque.</span><span class="sxs-lookup"><span data-stu-id="bec15-125">Expand or collapse the Bank account information section.</span></span>
4. <span data-ttu-id="bec15-126">Dans le champ Compte bancaire, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="bec15-126">In the Bank account field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="bec15-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bec15-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="bec15-128">Par exemple, sélectionnez le compte bancaire « DEMF OPER ».</span><span class="sxs-lookup"><span data-stu-id="bec15-128">For example, select the "DEMF OPER" bank account.</span></span>  
6. <span data-ttu-id="bec15-129">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bec15-129">Click Save.</span></span>

