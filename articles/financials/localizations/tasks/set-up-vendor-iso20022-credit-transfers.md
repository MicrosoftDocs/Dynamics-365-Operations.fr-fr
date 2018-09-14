--- 
title: "Paramétrer les fournisseurs et les comptes bancaires fournisseur pour les virements ISO20022"
description: "Cette procédure illustre comment paramétrer le fournisseur et les informations de compte bancaire spécifiques au fournisseur qui sont requises pour le virement ISO20022 ou toute autre génération du fichier de paiement fournisseur."
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 13b3c37f5d013dd896a456018813f20e5e70350b
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="3b548-103">Paramétrer les fournisseurs et les comptes bancaires fournisseur pour les virements ISO20022</span><span class="sxs-lookup"><span data-stu-id="3b548-103">Set up vendors and vendor bank accounts for ISO20022 credit transfers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3b548-104">Cette procédure illustre comment paramétrer le fournisseur et les informations de compte bancaire spécifiques au fournisseur qui sont requises pour le virement ISO20022 ou toute autre génération du fichier de paiement fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3b548-104">This procedure demonstrates how to set up the vendor and vendor specific bank account information required for ISO20022 Credit transfer or any other vendor payment file generation.</span></span> 

<span data-ttu-id="3b548-105">La société fictive de démonstration utilisée pour créer cette procédure est DEMF.</span><span class="sxs-lookup"><span data-stu-id="3b548-105">The demo data company used to create this procedure is DEMF.</span></span>
<span data-ttu-id="3b548-106">Il s'agit de la quatrième des cinq procédures illustrant le processus de paiement fournisseur à l'aide des configurations de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="3b548-106">This is the fourth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="3b548-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="3b548-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-bank-details"></a><span data-ttu-id="3b548-108">Paramétrer les détails bancaires</span><span class="sxs-lookup"><span data-stu-id="3b548-108">Set up bank details</span></span>
1. <span data-ttu-id="3b548-109">Accédez à Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="3b548-109">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="3b548-110">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="3b548-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="3b548-111">Par exemple, appliquez un filtre au champ Compte fournisseur avec une valeur de « DE-001 ».</span><span class="sxs-lookup"><span data-stu-id="3b548-111">For example, filter on the Vendor account field with a value of 'DE-001'.</span></span>
3. <span data-ttu-id="3b548-112">Cliquez sur DE-001 pour ouvrir les détails sur le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3b548-112">Click DE-001 to open vendor details.</span></span>
4. <span data-ttu-id="3b548-113">Cliquez sur Fournisseur dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="3b548-113">On the Action Pane, click Vendor.</span></span>
5. <span data-ttu-id="3b548-114">Cliquez sur Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="3b548-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="3b548-115">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="3b548-115">Click Edit.</span></span>
    * <span data-ttu-id="3b548-116">Si aucun compte bancaire disponible, vous devez en créer un.</span><span class="sxs-lookup"><span data-stu-id="3b548-116">If there is no bank account available, you need to create a new one.</span></span>  
7. <span data-ttu-id="3b548-117">Tapez le code « COBADEFFXXX » dans le champ Code SWIFT.</span><span class="sxs-lookup"><span data-stu-id="3b548-117">In the SWIFT code field, type 'COBADEFFXXX'.</span></span>
8. <span data-ttu-id="3b548-118">Tapez DE36200400000628808808 dans le champ IBAN.</span><span class="sxs-lookup"><span data-stu-id="3b548-118">In the IBAN field, type 'DE36200400000628808808'.</span></span>
9. <span data-ttu-id="3b548-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3b548-119">Close the page.</span></span>

## <a name="set-up-a-method-of-payment-for-the-vendor"></a><span data-ttu-id="3b548-120">Paramétrer un mode de paiement pour le fournisseur</span><span class="sxs-lookup"><span data-stu-id="3b548-120">Set up a method of payment for the vendor</span></span>
1. <span data-ttu-id="3b548-121">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="3b548-121">Click Edit.</span></span>
2. <span data-ttu-id="3b548-122">Développez ou réduisez la section Paiement.</span><span class="sxs-lookup"><span data-stu-id="3b548-122">Expand or collapse the Payment section.</span></span>
3. <span data-ttu-id="3b548-123">Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="3b548-123">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="3b548-124">Dans la liste, cliquez sur le lien dans la ligne SEPA CT.</span><span class="sxs-lookup"><span data-stu-id="3b548-124">In the list, click the link in the SEPA CT row.</span></span>
5. <span data-ttu-id="3b548-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3b548-125">Click Save.</span></span>


