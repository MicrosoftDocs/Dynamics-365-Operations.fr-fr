---
title: Fournisseurs occasionnels dans le secteur public
description: "Cet article fournit des informations sur la création d'un fournisseur occasionnel et d'une facture, et sur l'importation et la création de plusieurs fournisseurs occasionnels et factures."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerTransVoucher, SysConfiguration, Tax1099Summary, VendTableListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 19801
ms.assetid: 403857a3-bebb-4ff7-b1b5-c88f41fc18ae
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8da7965c741cf1b8faf149d7c763753579ab9572
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="one-time-vendors-in-the-public-sector"></a><span data-ttu-id="15dc4-103">Fournisseurs occasionnels dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="15dc4-103">One-time vendors in the public sector</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="15dc4-104">Cet article fournit des informations sur la création d'un fournisseur occasionnel et d'une facture, et sur l'importation et la création de plusieurs fournisseurs occasionnels et factures.</span><span class="sxs-lookup"><span data-stu-id="15dc4-104">This article provides information about how to create a one-time vendor and invoice, and how to import and create multiple one-time vendors and invoices.</span></span> 

<span data-ttu-id="15dc4-105">Il peut arriver que vous deviez créer une facture pour un nouveau fournisseur avec qui vous n'avez pas de relation régulière.</span><span class="sxs-lookup"><span data-stu-id="15dc4-105">Occasionally, you might have to create an invoice for a new vendor that you have no regular relationship with.</span></span> <span data-ttu-id="15dc4-106">Dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, si une approbation ou un contrat sous la forme d'une commande fournisseur n'est pas nécessaire, vous pouvez rapidement créer une facture tout en créant un enregistrement pour le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="15dc4-106">In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, if approval or a contract in the form of a purchase order isn't required, you can quickly create an invoice at the same time that you create a record for the vendor.</span></span> <span data-ttu-id="15dc4-107">Par exemple, vous devez payer des référents ou effectuer des remboursements, mais il n'existe pas d'enregistrement pour le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="15dc4-107">For example, you have to pay referees or refunds, but a master vendor record doesn't exist.</span></span> <span data-ttu-id="15dc4-108">Vous pouvez toujours créer plusieurs factures pour de nouveaux fournisseurs avec qui vous n'avez pas de relation régulière.</span><span class="sxs-lookup"><span data-stu-id="15dc4-108">Alternatively, you might have to create multiple invoices for new vendors that you have no regular relationship with.</span></span> <span data-ttu-id="15dc4-109">Si ni une approbation ni une commande fournisseur ne sont nécessaires, vous pouvez rapidement créer des factures en même temps que vous créez des enregistrements pour les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="15dc4-109">If neither approval nor a purchase order is required, you can quickly create invoices at the same time that you create records for the vendors.</span></span> <span data-ttu-id="15dc4-110">Par exemple, vous souhaitez peut-être prendre en charge les paiements fournisseur à des fins juridiques, de paiement d'enregistrement et de remboursement de clients ou pour d'autres paiements pour lesquels il n'existe pas d'enregistrements fournisseur principaux.</span><span class="sxs-lookup"><span data-stu-id="15dc4-110">For example, you want to support vendor payments for jury duty, registration payments, and customer refunds or other payments, but master vendor records don't exist.</span></span> <span data-ttu-id="15dc4-111">Pour plus d'informations, voir [Planification pour les fournisseurs occasionnels dans le secteur public](plan-one-time-vendors-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="15dc4-111">For more information, see [Planning for one-time vendors in the public-sector](plan-one-time-vendors-public-sector.md).</span></span>

## <a name="how-do-i-create-a-onetime-vendor-and-invoice"></a><span data-ttu-id="15dc4-112">Comment créer un fournisseur occasionnel et une facture ?</span><span class="sxs-lookup"><span data-stu-id="15dc4-112">How do I create a onetime vendor and invoice?</span></span>
<span data-ttu-id="15dc4-113">L'enregistrement fournisseur utilise les valeurs du compte fournisseur occasionnel par défaut, sauf si de nouvelles valeurs sont spécifiées.</span><span class="sxs-lookup"><span data-stu-id="15dc4-113">The vendor record uses values from the default one-time vendor account, unless new values are entered.</span></span> <span data-ttu-id="15dc4-114">Ce compte est spécifié dans la section **Général** de la page **Paramètres de la comptabilité fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="15dc4-114">That account is specified in the **General** section of the **Accounts payable parameters** page.</span></span> <span data-ttu-id="15dc4-115">Pour afficher les détails du compte, accédez à la page **Tous les fournisseurs**, puis double-cliquez sur le numéro de compte du fournisseur occasionnel par défaut.</span><span class="sxs-lookup"><span data-stu-id="15dc4-115">To view the account details, on the **All vendors** page, click the vendor account number of the default one-time vendor.</span></span>

## <a name="how-do-i-import-and-create-multiple-onetime-vendors-and-invoices"></a><span data-ttu-id="15dc4-116">Comment importer et créer plusieurs fournisseurs occasionnels et factures ?</span><span class="sxs-lookup"><span data-stu-id="15dc4-116">How do I import and create multiple onetime vendors and invoices?</span></span>
<span data-ttu-id="15dc4-117">Pour créer plusieurs fournisseurs et factures occasionnels, commencez par créer un fichier contenant les informations du fournisseur et de la facturation, puis importez-le dans une table intermédiaire dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="15dc4-117">To create multiple one-time vendors and invoices, you first create a file that contains the vendor and invoice information, and then import the file into a staging table in Finance and Operations.</span></span> <span data-ttu-id="15dc4-118">Traitez ensuite le fichier importé et générez les factures.</span><span class="sxs-lookup"><span data-stu-id="15dc4-118">You then process the imported file and generate the invoices.</span></span> <span data-ttu-id="15dc4-119">Pour plus d'informations sur la manière de créer le fichier, voir [Planification pour les fournisseurs occasionnels dans le secteur public](plan-one-time-vendors-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="15dc4-119">For information about how to create the file, see [Planning for one-time vendors in the public sector](plan-one-time-vendors-public-sector.md).</span></span>  




