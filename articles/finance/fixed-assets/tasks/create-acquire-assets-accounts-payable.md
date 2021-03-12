---
title: Créer et acquérir des actifs à partir de la comptabilité fournisseur
description: Ce guide de tâche décrit la création et l’acquisition d’une immobilisation avec le processus d’achat.
author: saraschi2
manager: AnnBe
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b27ccc3b4c4f5470d3a5b8ed7347e269c6793b87
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976039"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a><span data-ttu-id="07f65-103">Créer et acquérir des actifs à partir de la comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="07f65-103">Create and acquire assets from Accounts payable</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="07f65-104">Ce guide de tâche décrit la création et l’acquisition d’une immobilisation avec le processus d’achat.</span><span class="sxs-lookup"><span data-stu-id="07f65-104">This task guide will walk through creation and acquisition of a fixed asset with the purchasing process.</span></span>  <span data-ttu-id="07f65-105">Il utilise les données de démonstration de la société fictive USMF et les fonctions de comptable et de commis à la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="07f65-105">It uses the Accountant and Accounts payable clerks and the demo company USMF .</span></span>


## <a name="set-fixed-assets-parameters"></a><span data-ttu-id="07f65-106">Définir les paramètres des immobilisations</span><span class="sxs-lookup"><span data-stu-id="07f65-106">Set Fixed assets parameters</span></span>
1. <span data-ttu-id="07f65-107">Dans le **volet de navigation** accédez à **Modules > Immobilisations > Paramétrage > Paramètres des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="07f65-107">In the **Navigation pane**, go to **Modules > Fixed assets > Setup > Fixed assets parameters**.</span></span>
2. <span data-ttu-id="07f65-108">Développez l’organisateur **Commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="07f65-108">Expand the **Purchase orders** fastTab.</span></span>
3. <span data-ttu-id="07f65-109">Activez la case à cocher **Autoriser l’acquisition d’actifs à partir d’Achats**.</span><span class="sxs-lookup"><span data-stu-id="07f65-109">Check the **Allow asset acquisition from Purchasing** checkbox.</span></span>
4. <span data-ttu-id="07f65-110">Activez la case à cocher **Créer un actif lors de la validation de l’accusé de réception des marchandises ou de la facture**.</span><span class="sxs-lookup"><span data-stu-id="07f65-110">Check the **Create asset during product receipt or invoice posting** checkbox.</span></span>

## <a name="create-a-new-vendor-invoice"></a><span data-ttu-id="07f65-111">Créer une facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="07f65-111">Create a new vendor invoice</span></span>
1. <span data-ttu-id="07f65-112">Dans le **Volet de navigation**, allez dans **Modules > Comptabilité fournisseur > Espaces de travail > Saisie de facture fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="07f65-112">In the **Navigation pane**, go to **Modules > Accounts payable > Workspaces > Vendor invoice entry**.</span></span>
2. <span data-ttu-id="07f65-113">Cliquez sur **Nouvelle facture fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="07f65-113">Click **New vendor invoice**.</span></span>
3. <span data-ttu-id="07f65-114">Dans le champ **Compte de facturation**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="07f65-114">In the **Invoice account** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="07f65-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="07f65-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="07f65-116">Dans le champ **Nombre**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="07f65-116">In the **Number** field, type a value.</span></span>
6. <span data-ttu-id="07f65-117">Entrez une date dans le champ **Date de validation**.</span><span class="sxs-lookup"><span data-stu-id="07f65-117">In the **Posting date** field, enter a date.</span></span>
7. <span data-ttu-id="07f65-118">Cliquez sur **Ajouter une ligne**.</span><span class="sxs-lookup"><span data-stu-id="07f65-118">Click **Add line**.</span></span>
8. <span data-ttu-id="07f65-119">Dans le champ **Numéro d’article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="07f65-119">In the **Item number** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="07f65-120">Les articles non stockés ou les catégories d’approvisionnement peuvent être utilisés pour l’acquisition d’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="07f65-120">Either non-stocked items or procurement categories can be used for fixed asset acquisition.</span></span>  
9. <span data-ttu-id="07f65-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="07f65-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="07f65-122">Entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="07f65-122">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="07f65-123">Une ligne de facture crée une seule immobilisation, indépendamment de la quantité.</span><span class="sxs-lookup"><span data-stu-id="07f65-123">One invoice line will only create one fixed asset, regardless of quantity.</span></span> <span data-ttu-id="07f65-124">La valeur contenue dans le champ de quantité de la facture sera transférée vers la quantité d’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="07f65-124">The invoice quantity field value will be transferred to the fixed asset quantity.</span></span>  
11. <span data-ttu-id="07f65-125">Entrez un nombre dans le champ **Prix unitaire**.</span><span class="sxs-lookup"><span data-stu-id="07f65-125">In the **Unit price** field, enter a number.</span></span>
12. <span data-ttu-id="07f65-126">Développez le raccourci **Détails de ligne**.</span><span class="sxs-lookup"><span data-stu-id="07f65-126">Expand the **Line details** fastTab.</span></span>
13. <span data-ttu-id="07f65-127">Cliquez sur l’onglet **Immobilisation**.</span><span class="sxs-lookup"><span data-stu-id="07f65-127">Click the **Fixed assets** tab.</span></span>
14. <span data-ttu-id="07f65-128">Activez la case à cocher **Créer une nouvelle immobilisation**.</span><span class="sxs-lookup"><span data-stu-id="07f65-128">Check the **Create a new fixed asset** checkbox.</span></span>
15. <span data-ttu-id="07f65-129">Dans le champ **Groupe d’immobilisations**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="07f65-129">In the **Fixed asset group** field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="07f65-130">Dans la liste, sélectionnez le groupe d’immobilisations à utiliser lors de la création de la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="07f65-130">In the list, select the fixed asset group to be used when creating the new fixed asset.</span></span>
17. <span data-ttu-id="07f65-131">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="07f65-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="07f65-132">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="07f65-132">Click **Post**.</span></span> <span data-ttu-id="07f65-133">L’immobilisation est créée et acquise lors de la validation de la facture.</span><span class="sxs-lookup"><span data-stu-id="07f65-133">The fixed asset will be created and acquired when the invoice is posted.</span></span>  

