--- 
title: "Créer et exporter des paiements fournisseur à l'aide du format de paiement ISO20022"
description: "Cette procédure montre comment créer des lignes de paiement dans le journal des paiements fournisseur et générer un fichier de paiement fournisseur à l'aide de l'exemple de virement ISO2022."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7cc90bc86cd489b124a806c480632dd53ba47f3f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="0bf50-103">Créer et exporter des paiements fournisseur à l'aide du format de paiement ISO20022</span><span class="sxs-lookup"><span data-stu-id="0bf50-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0bf50-104">Cette procédure montre comment créer des lignes de paiement dans le journal des paiements fournisseur et générer un fichier de paiement fournisseur à l'aide de l'exemple de virement ISO2022.</span><span class="sxs-lookup"><span data-stu-id="0bf50-104">This procedure shows how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span> 

<span data-ttu-id="0bf50-105">La société fictive de démonstration utilisée pour créer cette procédure est DEMF.</span><span class="sxs-lookup"><span data-stu-id="0bf50-105">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="0bf50-106">Il s'agit de la cinquième des cinq procédures illustrant le processus de paiement fournisseur à l'aide des configurations de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="0bf50-106">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="0bf50-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="0bf50-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-payment-lines"></a><span data-ttu-id="0bf50-108">Créer des lignes de paiement</span><span class="sxs-lookup"><span data-stu-id="0bf50-108">Create payment lines</span></span>
1. <span data-ttu-id="0bf50-109">Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="0bf50-109">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="0bf50-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="0bf50-110">Click New.</span></span>
3. <span data-ttu-id="0bf50-111">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0bf50-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="0bf50-112">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="0bf50-112">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="0bf50-113">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="0bf50-113">Click Lines.</span></span>
6. <span data-ttu-id="0bf50-114">Cliquez sur Proposition de paiement.</span><span class="sxs-lookup"><span data-stu-id="0bf50-114">Click Payment proposal.</span></span>
7. <span data-ttu-id="0bf50-115">Cliquez sur Créer une proposition de paiement.</span><span class="sxs-lookup"><span data-stu-id="0bf50-115">Click Create payment proposal.</span></span>
8. <span data-ttu-id="0bf50-116">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="0bf50-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="0bf50-117">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="0bf50-117">Click Filter.</span></span>
10. <span data-ttu-id="0bf50-118">Dans la liste, sélectionnez la ligne de la table Fournisseurs et du champ Compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0bf50-118">In the list, select the row for Vendors table and Vendor account field.</span></span>
11. <span data-ttu-id="0bf50-119">Dans le champ Critères, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0bf50-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="0bf50-120">Vous pouvez appliquer les critères de sélection des transactions fournisseur à payer. Pour cet exemple, utilisez DE-001 comme compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0bf50-120">You can apply any criteria for selecting vendor transactions to pay, for this example use DE-001 as a vendor account.</span></span>  
12. <span data-ttu-id="0bf50-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0bf50-121">Click OK.</span></span>
13. <span data-ttu-id="0bf50-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0bf50-122">Click OK.</span></span>
14. <span data-ttu-id="0bf50-123">Cliquez sur Créer des paiements.</span><span class="sxs-lookup"><span data-stu-id="0bf50-123">Click Create payments.</span></span>

## <a name="generate-an-iso20022-payment-file"></a><span data-ttu-id="0bf50-124">Générer un fichier de paiement ISO20022</span><span class="sxs-lookup"><span data-stu-id="0bf50-124">Generate an ISO20022 payment file</span></span>


