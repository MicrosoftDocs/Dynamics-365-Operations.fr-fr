---
title: Créer et acquérir des actifs à partir de la comptabilité fournisseur
description: Ce guide de tâche décrit la création et l'acquisition d'une immobilisation avec le processus d'achat.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e6c36338cc67855c79ec97d88bb8b633417b85c7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "316416"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a><span data-ttu-id="9b134-103">Créer et acquérir des actifs à partir de la comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="9b134-103">Create and acquire assets from Accounts payable</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9b134-104">Ce guide de tâche décrit la création et l'acquisition d'une immobilisation avec le processus d'achat.</span><span class="sxs-lookup"><span data-stu-id="9b134-104">This task guide will walk through creation and acquisition of a fixed asset with the purchasing process.</span></span>  <span data-ttu-id="9b134-105">Il utilise les données de démonstration de la société fictive USMF et les fonctions de comptable et de commis à la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9b134-105">It uses the Accountant and Accounts payable clerks and the demo company USMF .</span></span>


## <a name="set-fixed-assets-parameters"></a><span data-ttu-id="9b134-106">Définir les paramètres des immobilisations</span><span class="sxs-lookup"><span data-stu-id="9b134-106">Set Fixed assets parameters</span></span>
1. <span data-ttu-id="9b134-107">Accédez à Immobilisations > Paramétrage > Paramètres des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="9b134-107">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="9b134-108">Développez ou réduisez la section Commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9b134-108">Expand or collapse the Purchase orders section.</span></span>
3. <span data-ttu-id="9b134-109">Activez la case à cocher Autoriser l'acquisition d'actifs à partir d'Achats.</span><span class="sxs-lookup"><span data-stu-id="9b134-109">Check the Allow asset acquisition from Purchasing checkbox.</span></span>
4. <span data-ttu-id="9b134-110">Activez la case à cocher Créer un actif lors de la validation de l'accusé de réception des marchandises ou de la facture.</span><span class="sxs-lookup"><span data-stu-id="9b134-110">Check the Create asset during product receipt or invoice posting checkbox.</span></span>

## <a name="create-a-new-vendor-invoice"></a><span data-ttu-id="9b134-111">Créer une facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="9b134-111">Create a new vendor invoice</span></span>
1. <span data-ttu-id="9b134-112">Accédez à Comptabilité fournisseur > Espaces de travail > Saisie de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9b134-112">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="9b134-113">Cliquez sur Nouvelle facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9b134-113">Click New vendor invoice.</span></span>
3. <span data-ttu-id="9b134-114">Dans le champ Compte de facturation, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9b134-114">In the Invoice account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="9b134-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9b134-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="9b134-116">Tapez une valeur dans le champ Nombre.</span><span class="sxs-lookup"><span data-stu-id="9b134-116">In the Number field, type a value.</span></span>
6. <span data-ttu-id="9b134-117">Entrez une date dans le champ Date de validation.</span><span class="sxs-lookup"><span data-stu-id="9b134-117">In the Posting date field, enter a date.</span></span>
7. <span data-ttu-id="9b134-118">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="9b134-118">Click Add line.</span></span>
8. <span data-ttu-id="9b134-119">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9b134-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9b134-120">Les articles non stockés ou les catégories d'approvisionnement peuvent être utilisés pour l'acquisition d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="9b134-120">Either non-stocked items or procurement categories can be used for fixed asset acquisition.</span></span>  
9. <span data-ttu-id="9b134-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9b134-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="9b134-122">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="9b134-122">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="9b134-123">Une ligne de facture crée une seule immobilisation, indépendamment de la quantité.</span><span class="sxs-lookup"><span data-stu-id="9b134-123">One invoice line will only create one fixed asset, regardless of quantity.</span></span>  <span data-ttu-id="9b134-124">La valeur contenue dans le champ de quantité de la facture sera transférée vers la quantité d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="9b134-124">The invoice quantity field value will be transferred to the fixed asset quantity.</span></span>  
11. <span data-ttu-id="9b134-125">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="9b134-125">In the Unit price field, enter a number.</span></span>
12. <span data-ttu-id="9b134-126">Développez ou réduisez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="9b134-126">Expand or collapse the Line details section.</span></span>
13. <span data-ttu-id="9b134-127">Cliquez sur l'onglet Immobilisation.</span><span class="sxs-lookup"><span data-stu-id="9b134-127">Click the Fixed assets tab.</span></span>
14. <span data-ttu-id="9b134-128">Activez la case à cocher Créer une nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="9b134-128">Check the Create a new fixed asset checkbox.</span></span>
15. <span data-ttu-id="9b134-129">Dans le champ Groupe d'immobilisations, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9b134-129">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="9b134-130">Dans la liste, sélectionnez le groupe d'immobilisations à utiliser lors de la création de la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="9b134-130">In the list, select the fixed asset group to be used when creating the new fixed asset.</span></span>
17. <span data-ttu-id="9b134-131">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9b134-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="9b134-132">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="9b134-132">Click Post.</span></span>
    * <span data-ttu-id="9b134-133">L'immobilisation est créée et acquise lors de la validation de la facture.</span><span class="sxs-lookup"><span data-stu-id="9b134-133">The fixed asset will be created and acquired when the invoice is posted.</span></span>  

