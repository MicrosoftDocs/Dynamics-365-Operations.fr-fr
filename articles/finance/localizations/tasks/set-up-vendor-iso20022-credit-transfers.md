---
title: Paramétrer les fournisseurs et les comptes bancaires fournisseur pour les virements ISO20022
description: Cette procédure illustre comment paramétrer le fournisseur et les informations de compte bancaire spécifiques au fournisseur qui sont requises pour le virement ISO20022 ou toute autre génération du fichier de paiement fournisseur.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4809a352f87cc3d88429461a06dfe36189ed5f31
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4442998"
---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="1e12c-103">Paramétrer les fournisseurs et les comptes bancaires fournisseur pour les virements ISO20022</span><span class="sxs-lookup"><span data-stu-id="1e12c-103">Set up vendors and vendor bank accounts for ISO20022 credit transfers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1e12c-104">Cette procédure illustre comment paramétrer le fournisseur et les informations de compte bancaire spécifiques au fournisseur qui sont requises pour le virement ISO20022 ou toute autre génération du fichier de paiement fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1e12c-104">This procedure demonstrates how to set up the vendor and vendor specific bank account information required for ISO20022 Credit transfer or any other vendor payment file generation.</span></span> 

<span data-ttu-id="1e12c-105">La société fictive de démonstration utilisée pour créer cette procédure est DEMF.</span><span class="sxs-lookup"><span data-stu-id="1e12c-105">The demo data company used to create this procedure is DEMF.</span></span>
<span data-ttu-id="1e12c-106">Il s’agit de la quatrième des cinq procédures illustrant le processus de paiement fournisseur à l’aide des configurations de génération d’états électroniques.</span><span class="sxs-lookup"><span data-stu-id="1e12c-106">This is the fourth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="1e12c-107">Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="1e12c-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-bank-details"></a><span data-ttu-id="1e12c-108">Paramétrer les détails bancaires</span><span class="sxs-lookup"><span data-stu-id="1e12c-108">Set up bank details</span></span>
1. <span data-ttu-id="1e12c-109">Accédez à Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="1e12c-109">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="1e12c-110">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="1e12c-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="1e12c-111">Par exemple, appliquez un filtre au champ Compte fournisseur avec une valeur de « DE-001 ».</span><span class="sxs-lookup"><span data-stu-id="1e12c-111">For example, filter on the Vendor account field with a value of 'DE-001'.</span></span>
3. <span data-ttu-id="1e12c-112">Cliquez sur DE-001 pour ouvrir les détails sur le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1e12c-112">Click DE-001 to open vendor details.</span></span>
4. <span data-ttu-id="1e12c-113">Cliquez sur Fournisseur dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="1e12c-113">On the Action Pane, click Vendor.</span></span>
5. <span data-ttu-id="1e12c-114">Cliquez sur Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="1e12c-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="1e12c-115">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="1e12c-115">Click Edit.</span></span>
    * <span data-ttu-id="1e12c-116">Si aucun compte bancaire disponible, vous devez en créer un.</span><span class="sxs-lookup"><span data-stu-id="1e12c-116">If there is no bank account available, you need to create a new one.</span></span>  
7. <span data-ttu-id="1e12c-117">Tapez le code « COBADEFFXXX » dans le champ Code SWIFT.</span><span class="sxs-lookup"><span data-stu-id="1e12c-117">In the SWIFT code field, type 'COBADEFFXXX'.</span></span>
8. <span data-ttu-id="1e12c-118">Tapez DE36200400000628808808 dans le champ IBAN.</span><span class="sxs-lookup"><span data-stu-id="1e12c-118">In the IBAN field, type 'DE36200400000628808808'.</span></span>
9. <span data-ttu-id="1e12c-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e12c-119">Close the page.</span></span>

## <a name="set-up-a-method-of-payment-for-the-vendor"></a><span data-ttu-id="1e12c-120">Paramétrer un mode de paiement pour le fournisseur</span><span class="sxs-lookup"><span data-stu-id="1e12c-120">Set up a method of payment for the vendor</span></span>
1. <span data-ttu-id="1e12c-121">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="1e12c-121">Click Edit.</span></span>
2. <span data-ttu-id="1e12c-122">Développez ou réduisez la section Paiement.</span><span class="sxs-lookup"><span data-stu-id="1e12c-122">Expand or collapse the Payment section.</span></span>
3. <span data-ttu-id="1e12c-123">Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1e12c-123">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="1e12c-124">Dans la liste, cliquez sur le lien dans la ligne SEPA CT.</span><span class="sxs-lookup"><span data-stu-id="1e12c-124">In the list, click the link in the SEPA CT row.</span></span>
5. <span data-ttu-id="1e12c-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1e12c-125">Click Save.</span></span>

