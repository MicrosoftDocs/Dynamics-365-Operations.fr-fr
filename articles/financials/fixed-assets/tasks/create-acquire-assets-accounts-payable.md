--- 
title: "Créer et acquérir des actifs à partir de la comptabilité fournisseur"
description: "Ce guide de tâche décrit la création et l'acquisition d'une immobilisation avec le processus d'achat."
author: saraschi2
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9149378047fc22efbd401b7af86df07c1403e4f5
ms.openlocfilehash: cfe920b2ef493ab3ae36a9557001086ed99c3e4e
ms.contentlocale: fr-fr
ms.lasthandoff: 10/05/2017

---
# <a name="create-and-acquire-assets-from-accounts-payable"></a><span data-ttu-id="e6f1a-103">Créer et acquérir des actifs à partir de la comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="e6f1a-103">Create and acquire assets from accounts payable</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e6f1a-104">Ce guide de tâche décrit la création et l'acquisition d'une immobilisation avec le processus d'achat.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-104">This task guide will walk through creation and acquisition of a fixed asset with the purchasing process.</span></span> <span data-ttu-id="e6f1a-105">Il utilise les données de démonstration de la société fictive USMF et les fonctions de comptable et de commis à la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-105">It uses the Accountant and Accounts payable clerks and the demo company USMF.</span></span>


## <a name="set-fixed-assets-parameters"></a><span data-ttu-id="e6f1a-106">Définir les paramètres des immobilisations</span><span class="sxs-lookup"><span data-stu-id="e6f1a-106">Set Fixed assets parameters</span></span>
1. <span data-ttu-id="e6f1a-107">Accédez à Immobilisations > Paramétrage > Paramètres des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-107">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="e6f1a-108">Développez ou réduisez la section Commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-108">Expand or collapse the Purchase orders section.</span></span>
3. <span data-ttu-id="e6f1a-109">Activez la case à cocher Autoriser l'acquisition d'actifs à partir d'Achats.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-109">Check the Allow asset acquisition from Purchasing checkbox.</span></span>
4. <span data-ttu-id="e6f1a-110">Activez la case à cocher Créer un actif lors de la validation de l'accusé de réception des marchandises ou de la facture.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-110">Check the Create asset during product receipt or invoice posting checkbox.</span></span>

## <a name="create-a-new-vendor-invoice"></a><span data-ttu-id="e6f1a-111">Créer une facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="e6f1a-111">Create a new vendor invoice</span></span>
1. <span data-ttu-id="e6f1a-112">Accédez à Comptabilité fournisseur > Espaces de travail > Saisie de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-112">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="e6f1a-113">Cliquez sur Nouvelle facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-113">Click New vendor invoice.</span></span>
3. <span data-ttu-id="e6f1a-114">Dans le champ Compte de facturation, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-114">In the Invoice account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e6f1a-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="e6f1a-116">Tapez une valeur dans le champ Nombre.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-116">In the Number field, type a value.</span></span>
6. <span data-ttu-id="e6f1a-117">Entrez une date dans le champ Date de validation.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-117">In the Posting date field, enter a date.</span></span>
7. <span data-ttu-id="e6f1a-118">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-118">Click Add line.</span></span>
8. <span data-ttu-id="e6f1a-119">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e6f1a-120">Les articles non stockés ou les catégories d'approvisionnement peuvent être utilisés pour l'acquisition d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-120">Either non-stocked items or procurement categories can be used for fixed asset acquisition.</span></span>  
9. <span data-ttu-id="e6f1a-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="e6f1a-122">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-122">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="e6f1a-123">Une ligne de facture crée une seule immobilisation, indépendamment de la quantité.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-123">One invoice line will only create one fixed asset, regardless of quantity.</span></span>  <span data-ttu-id="e6f1a-124">La valeur contenue dans le champ de quantité de la facture sera transférée vers la quantité d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-124">The invoice quantity field value will be transferred to the fixed asset quantity.</span></span>  
11. <span data-ttu-id="e6f1a-125">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-125">In the Unit price field, enter a number.</span></span>
12. <span data-ttu-id="e6f1a-126">Développez ou réduisez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-126">Expand or collapse the Line details section.</span></span>
13. <span data-ttu-id="e6f1a-127">Cliquez sur l'onglet Immobilisation.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-127">Click the Fixed assets tab.</span></span>
14. <span data-ttu-id="e6f1a-128">Activez la case à cocher Créer une nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-128">Check the Create a new fixed asset checkbox.</span></span>
15. <span data-ttu-id="e6f1a-129">Dans le champ Groupe d'immobilisations, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-129">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="e6f1a-130">Dans la liste, sélectionnez le groupe d'immobilisations à utiliser lors de la création de la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-130">In the list, select the fixed asset group to be used when creating the new fixed asset.</span></span>
17. <span data-ttu-id="e6f1a-131">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="e6f1a-132">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-132">Click Post.</span></span>
    * <span data-ttu-id="e6f1a-133">L'immobilisation est créée et acquise lors de la validation de la facture.</span><span class="sxs-lookup"><span data-stu-id="e6f1a-133">The fixed asset will be created and acquired when the invoice is posted.</span></span>  


