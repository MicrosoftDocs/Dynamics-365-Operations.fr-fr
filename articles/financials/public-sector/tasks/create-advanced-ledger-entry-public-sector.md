---
title: Créer une écriture comptable avancée dans le secteur public
description: Les organisations du secteur public peuvent utiliser les écritures comptables avancées pour créer, ajuster et contrepasser des écritures comptables.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AdvancedLedgerEntry, AdvancedLedgerEntryCreate, ProjTableLookup, ProjCategoryLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: efb0fa85c5c34cf058bf9c48a6d6928c9b2d7acd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557241"
---
# <a name="create-an-advanced-ledger-entry-in-the-public-sector"></a><span data-ttu-id="9ae31-103">Créer une écriture comptable avancée dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="9ae31-103">Create an advanced ledger entry in the public sector</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9ae31-104">Les organisations du secteur public peuvent utiliser les écritures comptables avancées pour créer, ajuster et contrepasser des écritures comptables.</span><span class="sxs-lookup"><span data-stu-id="9ae31-104">Public-sector organizations can use advanced ledger entries to create, adjust, and reverse ledger entries.</span></span> <span data-ttu-id="9ae31-105">Par exemple, vous pouvez utiliser des écritures comptables avancées pour reclassifier des dépenses si des factures sont validées par erreur dans un compte ou projet inapproprié.</span><span class="sxs-lookup"><span data-stu-id="9ae31-105">For example, advanced ledger entries can be used to reclassify expenditures if invoices are mistakenly posted to the wrong account or project.</span></span> <span data-ttu-id="9ae31-106">Cette procédure a été créée à l'aide des données de la société fictive PSUS dans la partition du secteur public.</span><span class="sxs-lookup"><span data-stu-id="9ae31-106">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="9ae31-107">Accédez à Comptabilité > Entrées de journal > Écritures comptables avancées.</span><span class="sxs-lookup"><span data-stu-id="9ae31-107">Go to General ledger > Journal entries > Advanced ledger entries.</span></span>
2. <span data-ttu-id="9ae31-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9ae31-108">Click New.</span></span>
3. <span data-ttu-id="9ae31-109">Dans le champ Comptabilité, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="9ae31-109">In the Accounting date field, enter a date.</span></span>
4. <span data-ttu-id="9ae31-110">Dans le champ Libellé de transaction, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9ae31-110">In the Transaction text field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="9ae31-111">Dans la liste, cliquez sur le libellé de transaction pour cette écriture comptable avancée.</span><span class="sxs-lookup"><span data-stu-id="9ae31-111">In the list, click the transaction text for this advanced ledger entry.</span></span>
6. <span data-ttu-id="9ae31-112">Dans le champ Définition de validation, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9ae31-112">In the Posting definition field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="9ae31-113">Dans la liste, cliquez sur Définition de validation pour cette écriture comptable avancée.</span><span class="sxs-lookup"><span data-stu-id="9ae31-113">In the list, click the Posting definition for this advanced ledger entry.</span></span>
8. <span data-ttu-id="9ae31-114">Dans le champ Code motif, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9ae31-114">In the Reason code field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="9ae31-115">Dans la liste, cliquez sur le code motif pour cette écriture comptable avancée.</span><span class="sxs-lookup"><span data-stu-id="9ae31-115">In the list, click the Reason code for this advanced ledger entry.</span></span>
10. <span data-ttu-id="9ae31-116">Dans le champ Commentaire du motif, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9ae31-116">In the Reason comment field, type a value.</span></span>
11. <span data-ttu-id="9ae31-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9ae31-117">Click OK.</span></span>
12. <span data-ttu-id="9ae31-118">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="9ae31-118">Click Add line.</span></span>
13. <span data-ttu-id="9ae31-119">Dans le champ ID projet, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9ae31-119">In the Project ID field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="9ae31-120">Dans la liste, cliquez sur un ID projet.</span><span class="sxs-lookup"><span data-stu-id="9ae31-120">In the list, click a project ID.</span></span>
15. <span data-ttu-id="9ae31-121">Dans le champ Catégorie de projets, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9ae31-121">In the Project category field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="9ae31-122">Dans la liste, cliquez sur une catégorie de projet.</span><span class="sxs-lookup"><span data-stu-id="9ae31-122">In the list, click a project category.</span></span>
    * <span data-ttu-id="9ae31-123">Si vous sélectionnez la catégorie de projet, le compte général est automatiquement spécifié.</span><span class="sxs-lookup"><span data-stu-id="9ae31-123">If you select the project category, the ledger account is entered automatically.</span></span>  
    * <span data-ttu-id="9ae31-124">Ajoutez un montant de débit ou de crédit à cette ligne.</span><span class="sxs-lookup"><span data-stu-id="9ae31-124">Add a debit or a credit amount to this line.</span></span> <span data-ttu-id="9ae31-125">Si nécessaire, cliquez sur Ajouter une ligne pour ajouter des lignes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="9ae31-125">If needed, click Add line to add more lines.</span></span>  
17. <span data-ttu-id="9ae31-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9ae31-126">Click Save.</span></span>

