---
title: Créer et exporter des paiements fournisseur à l'aide du format de paiement ISO20022
description: Cette procédure montre comment créer des lignes de paiement dans le journal des paiements fournisseur et générer un fichier de paiement fournisseur à l'aide de l'exemple de virement ISO2022.
author: mrolecki
manager: AnnBe
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b589d64a4446420164175b41f435cf48daac01a9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "340543"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="5d7c9-103">Créer et exporter des paiements fournisseur à l'aide du format de paiement ISO20022</span><span class="sxs-lookup"><span data-stu-id="5d7c9-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5d7c9-104">Cette rubrique explique comment créer des lignes de paiement dans le journal des paiements fournisseur et générer un fichier de paiement fournisseur à l'aide de l'exemple de virement ISO2022.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-104">This topic explains how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span>

<span data-ttu-id="5d7c9-105">Il s'agit de la cinquième des cinq procédures illustrant le processus de paiement fournisseur à l'aide des configurations de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-105">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="5d7c9-106">Utilisez les données fictives de DEMF pour réaliser cet exemple.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-106">Use the DEMF demo data to complete this example.</span></span>

## <a name="example"></a><span data-ttu-id="5d7c9-107">Exemple</span><span class="sxs-lookup"><span data-stu-id="5d7c9-107">Example</span></span>

1.  <span data-ttu-id="5d7c9-108">Accédez à **Comptabilité fournisseur > Paiements > Journal des paiements**.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-108">Go to **Accounts payable > Payments > Payment journal**.</span></span>
2.  <span data-ttu-id="5d7c9-109">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-109">Click **New**.</span></span>
3.  <span data-ttu-id="5d7c9-110">Dans le champ **Nom**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-110">In the **Name** field, enter or select a value.</span></span>
4.  <span data-ttu-id="5d7c9-111">Cliquez sur **Lignes > Proposition de paiement > Créer une proposition de paiement**.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-111">Click **Lines > Payment proposal > Create payment proposal**.</span></span>
5.  <span data-ttu-id="5d7c9-112">Développez la section **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-112">Expand the **Records to include** section.</span></span>
6.  <span data-ttu-id="5d7c9-113">Cliquez sur **Filtre**.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-113">Click **Filter**.</span></span>
7.  <span data-ttu-id="5d7c9-114">Dans la liste, sélectionnez la ligne de la **table Fournisseurs** et du **champ Compte fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-114">In the list, select the row for **Vendors table** and **Vendor account field**.</span></span>
8.  <span data-ttu-id="5d7c9-115">Dans le champ **Critères**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="5d7c9-116">Vous pouvez appliquer les critères de sélection des transactions fournisseur à payer. Pour cet exemple, utilisez DE-001 comme compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-116">You can apply any criteria for selecting vendor transactions to pay, for this example, use DE-001 as a vendor account.</span></span>
12. <span data-ttu-id="5d7c9-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-117">Click **OK**.</span></span>
13. <span data-ttu-id="5d7c9-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-118">Click **OK**.</span></span>
14. <span data-ttu-id="5d7c9-119">Cliquez sur **Créer des paiements.**</span><span class="sxs-lookup"><span data-stu-id="5d7c9-119">Click **Create payments**.</span></span>
15. <span data-ttu-id="5d7c9-120">Générez un fichier de paiement ISO20022.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-120">Generate an ISO20022 payment file.</span></span>
    1.  <span data-ttu-id="5d7c9-121">Cliquez sur **Générer les paiements**.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-121">Click **Generate payments**.</span></span>
    2.  <span data-ttu-id="5d7c9-122">Dans le champ **Mode de paiement**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-122">In the **Method of payment** field, enter or select a value.</span></span>
    3.  <span data-ttu-id="5d7c9-123">Dans le champ **Nom du fichier**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-123">In the **File name** field, type a value.</span></span> <span data-ttu-id="5d7c9-124">Pour cet exemple, en raison du paiement en EUR, le fichier généré sera conforme à la norme SEPA.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-124">For this example, because of the EUR payment, the generated file will be SEPA compliant.</span></span> <span data-ttu-id="5d7c9-125">Le transfert de crédit ISO20022 ainsi que tout autre format de paiement fournisseurs peut être également utilisé pour générer les paiements dans d'autres devises.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-125">ISO20022 credit transfer as well as other vendor payment formats can also be used for generating payments in other currencies.</span></span>
    4.  <span data-ttu-id="5d7c9-126">Dans le champ **Compte en banque**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5d7c9-126">In the **Bank account** field, enter or select a value.</span></span>

