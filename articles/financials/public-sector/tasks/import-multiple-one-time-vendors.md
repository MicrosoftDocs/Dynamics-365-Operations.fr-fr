---
title: Importer et créer plusieurs fournisseurs et factures occasionnels dans le secteur public
description: Lorsqu'une approbation ou un contrat sous forme d'une commande fournisseur n'est pas nécessaire, vous pouvez créer une facture pour un nouveau fournisseur avec vous n'entretenez pas de relation régulière, tout en créant un enregistrement pour le fournisseur.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendImportOneTimeVendFileUpload_PSN
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 650215df59018d6a930e432483f5bc3d73fef692
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557175"
---
# <a name="import-and-create-multiple-one-time-vendors-and-invoices-in-the-public-sector"></a><span data-ttu-id="31372-103">Importer et créer plusieurs fournisseurs et factures occasionnels dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="31372-103">Import and create multiple one-time vendors and invoices in the public sector</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="31372-104">Lorsqu'une approbation ou un contrat sous forme d'une commande fournisseur n'est pas nécessaire, vous pouvez créer une facture pour un nouveau fournisseur avec vous n'entretenez pas de relation régulière, tout en créant un enregistrement pour le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="31372-104">When approval or a contract in the form of a purchase order is not required, you can create an invoice for a new vendor with whom you have no regular relationship, at the same time as creating a record for the vendor.</span></span> <span data-ttu-id="31372-105">Cette procédure a été créée à l'aide des données de la société fictive PSUS dans la partition du secteur public.</span><span class="sxs-lookup"><span data-stu-id="31372-105">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="31372-106">Accédez à Comptabilité fournisseur > Tâches périodiques > Importer des fournisseurs occasionnels et des factures.</span><span class="sxs-lookup"><span data-stu-id="31372-106">Go to Accounts payable > Periodic tasks > Import one-time vendors and invoices.</span></span>
2. <span data-ttu-id="31372-107">Recherchez et sélectionnez le fichier CSV contenant les informations fournisseur.</span><span class="sxs-lookup"><span data-stu-id="31372-107">Browse for and select the CSV file that contains vendor information.</span></span>
3. <span data-ttu-id="31372-108">Dans le champ Structure de compte, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="31372-108">In the Account structure field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="31372-109">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="31372-109">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="31372-110">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="31372-110">Click OK.</span></span>
    * <span data-ttu-id="31372-111">Les informations du fournisseur et de facturation sont importées.</span><span class="sxs-lookup"><span data-stu-id="31372-111">The vendor and invoice information is imported.</span></span> <span data-ttu-id="31372-112">S'il existe des erreurs, un état est imprimé, et vous devez corriger les entrées répertoriées dans le fichier d'importation puis réimporter le fichier.</span><span class="sxs-lookup"><span data-stu-id="31372-112">If there are errors, a report will be printed, and you should correct any listed entries in the import file and then reimport the file.</span></span>  
6. <span data-ttu-id="31372-113">Accédez à Comptabilité fournisseur > Tâches périodiques > Traiter les fournisseurs occasionnels et les factures.</span><span class="sxs-lookup"><span data-stu-id="31372-113">Go to Accounts payable > Periodic tasks > Process one-time vendors and invoices.</span></span>
    * <span data-ttu-id="31372-114">Les noms de fournisseur ou les ID de taxe fédérale en double feront l'objet d'une recherche.</span><span class="sxs-lookup"><span data-stu-id="31372-114">Duplicate vendor names or Federal tax IDs will be looked for.</span></span>  <span data-ttu-id="31372-115">Important :si vous choisissez de ne pas traiter les fournisseurs en double, les factures associées ne seront pas traitées non plus.</span><span class="sxs-lookup"><span data-stu-id="31372-115">Important: If you choose not to process duplicate vendors, the related invoices won’t be processed either.</span></span> <span data-ttu-id="31372-116">Vous pouvez créer manuellement une facture à l'aide des informations du fichier csv.</span><span class="sxs-lookup"><span data-stu-id="31372-116">You can manually create an invoice by using the information in the CSV file.</span></span>    
7. <span data-ttu-id="31372-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="31372-117">Click OK.</span></span>

