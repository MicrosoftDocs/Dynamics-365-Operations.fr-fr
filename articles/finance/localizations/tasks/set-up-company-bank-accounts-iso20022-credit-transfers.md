---
title: Paramétrer les comptes bancaires de société pour les virements ISO20022
description: Cette procédure indique comment paramétrer les informations de compte bancaire spécifiques à une société qui sont requises pour la génération du fichier de paiement.
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
ms.openlocfilehash: 2bbbf55ed28ad2131d7e1253dd44842d85d39315
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174865"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="28fcc-103">Paramétrer les comptes bancaires de société pour les virements ISO20022</span><span class="sxs-lookup"><span data-stu-id="28fcc-103">Set up company bank accounts for ISO20022 credit transfers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="28fcc-104">Cette procédure indique comment paramétrer les informations de compte bancaire spécifiques à une société qui sont requises pour la génération du fichier de paiement.</span><span class="sxs-lookup"><span data-stu-id="28fcc-104">This procedure shows how to set up company-specific bank account information that is required for payment file generation.</span></span> <span data-ttu-id="28fcc-105">Vous paramétrez les informations requises pour générer le format du virement ISO 20022, mais selon le format, d'autres informations peuvent être requises, comme l'ID société ou la priorité.</span><span class="sxs-lookup"><span data-stu-id="28fcc-105">You set up information required to generate ISO 20022 credit transfer format but depending on the format there might be other information required, such as the Company ID or the Sort code.</span></span> 

<span data-ttu-id="28fcc-106">La société fictive de démonstration utilisée pour créer cette procédure est DEMF.</span><span class="sxs-lookup"><span data-stu-id="28fcc-106">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="28fcc-107">Il s'agit de la deuxième des cinq procédures illustrant le processus de paiement fournisseur à l'aide des configurations de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="28fcc-107">This is the second procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="28fcc-108">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="28fcc-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-iban-and-swift-code"></a><span data-ttu-id="28fcc-109">Paramétrer un code IBAN et SWIFT</span><span class="sxs-lookup"><span data-stu-id="28fcc-109">Set up IBAN and SWIFT code</span></span>
1. <span data-ttu-id="28fcc-110">Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="28fcc-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="28fcc-111">Utilisez le filtre rapide pour filtrer sur le champ Compte bancaire avec une valeur de « DEMF OPER ».</span><span class="sxs-lookup"><span data-stu-id="28fcc-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="28fcc-112">Cliquez sur DEMF OPER pour ouvrir les détails du compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="28fcc-112">Click DEMF OPER to open bank account details.</span></span>
4. <span data-ttu-id="28fcc-113">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="28fcc-113">Click Edit.</span></span>
5. <span data-ttu-id="28fcc-114">Développez la section Identification supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="28fcc-114">Expand the Additional identification section.</span></span>
6. <span data-ttu-id="28fcc-115">Tapez DE89370400440532013000 dans le champ IBAN.</span><span class="sxs-lookup"><span data-stu-id="28fcc-115">In the IBAN field, type 'DE89370400440532013000'.</span></span>
7. <span data-ttu-id="28fcc-116">Tapez « DEUTDEFF » dans le champ Code SWIFT.</span><span class="sxs-lookup"><span data-stu-id="28fcc-116">In the SWIFT code field, type 'DEUTDEFF'.</span></span>
    * <span data-ttu-id="28fcc-117">Notez que le code SWIFT\BIC n'est pas requis pour de nombreux formats de paiement, mais il est recommandé de le faire enregistrer pour un compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="28fcc-117">Note that SWIFT\BIC is not required for many payment formats, however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="28fcc-118">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="28fcc-118">Click Save.</span></span>

## <a name="set-up-bank-account-for-the-legal-entity"></a><span data-ttu-id="28fcc-119">Paramétrer le compte bancaire de l'entité juridique</span><span class="sxs-lookup"><span data-stu-id="28fcc-119">Set up bank account for the legal entity</span></span>
1. <span data-ttu-id="28fcc-120">Accédez à Administration d'organisation > Organisations > Entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="28fcc-120">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="28fcc-121">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="28fcc-121">Click Edit.</span></span>
3. <span data-ttu-id="28fcc-122">Développez la section Informations sur le compte en banque.</span><span class="sxs-lookup"><span data-stu-id="28fcc-122">Expand the Bank account information section.</span></span>
4. <span data-ttu-id="28fcc-123">Dans le champ Compte en banque, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="28fcc-123">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="28fcc-124">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="28fcc-124">Click Save.</span></span>

