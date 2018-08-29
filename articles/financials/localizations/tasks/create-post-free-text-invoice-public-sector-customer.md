--- 
title: "Créer et valider une facture financière pour un client du secteur public (Danemark)"
description: "Cette procédure vous guide dans la création et la validation d'une facture financière pour un client à l'aide de la facturation électronique OIOUBL."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Denmark
ms.search.industry: Public Sector
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c689087f499330c8d662aed2632fd2e079145fde
ms.openlocfilehash: 3b23be85ec0ec60f62a30348ea72c633e8d515c9
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="create-and-post-a-free-text-invoice-for-a-public-sector-customer-denmark"></a><span data-ttu-id="61193-103">Créer et valider une facture financière pour un client du secteur public (Danemark)</span><span class="sxs-lookup"><span data-stu-id="61193-103">Create and post a free text invoice for a public sector customer (Denmark)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="61193-104">Cette procédure vous guide dans la création et la validation d'une facture financière pour un client à l'aide de la facturation électronique OIOUBL.</span><span class="sxs-lookup"><span data-stu-id="61193-104">This procedure walks you through creating and posting a free text invoice for a customer using OIOUBL electronic invoicing.</span></span> 



<span data-ttu-id="61193-105">Elle a été créée avec les données de démonstration de la société fictive USMF, avec l'adresse principale de l'entité juridique au Danemark.</span><span class="sxs-lookup"><span data-stu-id="61193-105">It was created using the demo data company USMF with a legal entity primary address in Denmark.</span></span>



<span data-ttu-id="61193-106">Il s'agit de la quatrième des six procédures illustrant le processus de bout en bout de génération de factures électroniques à l'aide des configurations de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="61193-106">This is the fourth procedure out of six illustrating end to end process of generating e-invoices using electronic reporting configurations.</span></span> <span data-ttu-id="61193-107">Elle est basée sur l'exemple de facture électronique OIOUBL, qui est commun au Danemark, à l'Autriche et à la Norvège.</span><span class="sxs-lookup"><span data-stu-id="61193-107">It is based on OIOUBL e-invoice example which is common for Denmark, Austria and Norway.</span></span> <span data-ttu-id="61193-108">Afin d'identifier les différences mineures pour d'autres implémentations de facture électronique spécifiques au pays, comme l'espagnol ou l'italien, reportez-vous aux articles WIKI disponibles.</span><span class="sxs-lookup"><span data-stu-id="61193-108">In order to find minor differences for other country specific e-Invoice implementations, like Spanish or Italian, please refer to available WIKI articles.</span></span>



<span data-ttu-id="61193-109">Avant d'exécuter cette procédure, vous devez effectuer les procédures suivantes : « Importer les configurations de génération d'état électronique de facturation électronique OIOUBL », « Paramétrer la facturation électronique OIOUBL » et « Paramétrer un compte client pour la facturation électronique OIOUBL ».</span><span class="sxs-lookup"><span data-stu-id="61193-109">Before you can complete this procedure, you must complete the following procedures: ‘Import OIOUBL electronic invoicing electronic reporting configurations’, ‘Set up OIOUBL electronic invoicing’ and ‘Set up a customer account for OIOUBL electronic invoicing’.</span></span>

1. <span data-ttu-id="61193-110">Accédez à Comptabilité client > Factures > Toutes factures financières.</span><span class="sxs-lookup"><span data-stu-id="61193-110">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="61193-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="61193-111">Click New.</span></span>
3. <span data-ttu-id="61193-112">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="61193-112">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="61193-113">Un client sélectionné pour la facture financière doit être activé pour la facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="61193-113">A customer selected for the free text invoice must be enabled for electronic invoicing.</span></span>  
4. <span data-ttu-id="61193-114">Sélectionnez une vue d'en-tête de facture financière.</span><span class="sxs-lookup"><span data-stu-id="61193-114">Select a free text invoice header view.</span></span>
5. <span data-ttu-id="61193-115">Développez la section Client.</span><span class="sxs-lookup"><span data-stu-id="61193-115">Expand the Customer section.</span></span>
6. <span data-ttu-id="61193-116">Tapez une valeur dans le champ Demande d'achat client.</span><span class="sxs-lookup"><span data-stu-id="61193-116">In the Customer requisition field, type a value.</span></span>
7. <span data-ttu-id="61193-117">Tapez une valeur dans le champ Référence client.</span><span class="sxs-lookup"><span data-stu-id="61193-117">In the Customer reference field, type a value.</span></span>
8. <span data-ttu-id="61193-118">Dans le champ Contact, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="61193-118">In the Contact field, enter or select a value.</span></span>
9. <span data-ttu-id="61193-119">Sélectionnez une vue de lignes de facture financière.</span><span class="sxs-lookup"><span data-stu-id="61193-119">Select a free text invoice lines view.</span></span>
10. <span data-ttu-id="61193-120">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="61193-120">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="61193-121">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="61193-121">In the Description field, type a value.</span></span>
12. <span data-ttu-id="61193-122">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="61193-122">In the Main account field, specify the desired values.</span></span>
13. <span data-ttu-id="61193-123">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="61193-123">In the Unit price field, enter a number.</span></span>
14. <span data-ttu-id="61193-124">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="61193-124">Click Post.</span></span>
15. <span data-ttu-id="61193-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="61193-125">Click OK.</span></span>

## <a name="generate-an-oioubl-electronic-invoice"></a><span data-ttu-id="61193-126">Générer une facture électronique OIOUBL</span><span class="sxs-lookup"><span data-stu-id="61193-126">Generate an OIOUBL electronic invoice</span></span>
1. <span data-ttu-id="61193-127">Cliquez sur Envoyer.</span><span class="sxs-lookup"><span data-stu-id="61193-127">Click Send.</span></span>
2. <span data-ttu-id="61193-128">Cliquez sur Original.</span><span class="sxs-lookup"><span data-stu-id="61193-128">Click Original.</span></span>
    * <span data-ttu-id="61193-129">Vous pouvez vérifier le statut de la tâche et télécharger le fichier en cours dans la page des tâches de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="61193-129">You can verify the status of the job and download the actual file on the Electronic reporting jobs page.</span></span>  


