---
title: Paramétrer les documents de transfert pour le mouvement de marchandises dans une société
description: Cette procédure indique comment créer des documents de transfert pour le mouvement de marchandises dans une société.
author: v-oloski
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventTransferOrders, InventLocationIdLookup, TransportationDocument, HcmWorkerLookUp, SrsReportViewerForm, InventTransferParmShip
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2228f7354a91eda7e03ba4d3001265bfcbc20e90
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816848"
---
# <a name="set-up-the-transfer-documents-for-goods-movement-inside-a-company"></a><span data-ttu-id="003bf-103">Paramétrer les documents de transfert pour le mouvement de marchandises dans une société</span><span class="sxs-lookup"><span data-stu-id="003bf-103">Set up the transfer documents for goods movement inside a company</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="003bf-104">Cette procédure indique comment créer des documents de transfert pour le mouvement de marchandises dans une société.</span><span class="sxs-lookup"><span data-stu-id="003bf-104">This procedure shows how to create transfer documents for goods movement inside a company.</span></span> <span data-ttu-id="003bf-105">Cette procédure est uniquement disponible pour les entités juridiques dont l’adresse principale se situe en Lituanie.</span><span class="sxs-lookup"><span data-stu-id="003bf-105">This procedure is only available for legal entities with a primary address in Lithuania.</span></span> <span data-ttu-id="003bf-106">La procédure a été créée avec les données de démonstration de la société fictive DEMF, avec une adresse principale en Lituanie.</span><span class="sxs-lookup"><span data-stu-id="003bf-106">The procedure was created using the demo data company DEMF with a primary address in Lithuania.</span></span> <span data-ttu-id="003bf-107">Avant d’exécuter cette procédure, vous devez exécuter la procédure « Paramétrer les documents de transfert pour le mouvement de marchandises dans une société ».</span><span class="sxs-lookup"><span data-stu-id="003bf-107">Before you can complete this procedure, you must complete the "Set up transfer documents for goods movement inside a company" procedure.</span></span> <span data-ttu-id="003bf-108">Cette procédure est destinée aux comptables de stock.</span><span class="sxs-lookup"><span data-stu-id="003bf-108">This procedure is intended for inventory accountants.</span></span> <span data-ttu-id="003bf-109">Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="003bf-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-transfer-order"></a><span data-ttu-id="003bf-110">Création d’un ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="003bf-110">Create a transfer order</span></span>
1. <span data-ttu-id="003bf-111">Accédez à Gestion des stocks > Commandes entrantes > Ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="003bf-111">Go to Inventory management > Inbound orders > Transfer order.</span></span>
2. <span data-ttu-id="003bf-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="003bf-112">Click New.</span></span>
3. <span data-ttu-id="003bf-113">Dans le champ Entrepôt d’origine, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="003bf-113">In the From warehouse field, enter or select a value.</span></span>
4. <span data-ttu-id="003bf-114">Dans le champ Entrepôt de destination, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="003bf-114">In the To warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="003bf-115">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="003bf-115">Click Add.</span></span>
6. <span data-ttu-id="003bf-116">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="003bf-116">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="003bf-117">Entrez ou sélectionnez une valeur dans le champ Numéro d’article.</span><span class="sxs-lookup"><span data-stu-id="003bf-117">In the Item number field, enter or select a value.</span></span>

## <a name="enter-transportation-details-for-the-transfer-order"></a><span data-ttu-id="003bf-118">Entrer les détails du transport pour l’ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="003bf-118">Enter transportation details for the transfer order</span></span>
1. <span data-ttu-id="003bf-119">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="003bf-119">Click Save.</span></span>
2. <span data-ttu-id="003bf-120">Dans le volet Actions, cliquez sur Expédier.</span><span class="sxs-lookup"><span data-stu-id="003bf-120">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="003bf-121">Cliquez sur Détails du transport.</span><span class="sxs-lookup"><span data-stu-id="003bf-121">Click Transportation details.</span></span>
4. <span data-ttu-id="003bf-122">Sélectionnez Oui dans le champ Imprimer les détails du transport.</span><span class="sxs-lookup"><span data-stu-id="003bf-122">Select Yes in the Print transportation details field.</span></span>
5. <span data-ttu-id="003bf-123">Dans le champ Marchandises émises par, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="003bf-123">In the Goods issued by field, enter or select a value.</span></span>
6. <span data-ttu-id="003bf-124">Dans le champ Colis, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="003bf-124">In the Package field, type a value.</span></span>
7. <span data-ttu-id="003bf-125">Dans le champ Niveau de risque de la charge, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="003bf-125">In the Risk level of the load field, type a value.</span></span>
8. <span data-ttu-id="003bf-126">Dans le champ Transporteur, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="003bf-126">In the Carrier field, enter or select a value.</span></span>
9. <span data-ttu-id="003bf-127">Dans le champ Modèle, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="003bf-127">In the Model field, enter or select a value.</span></span>
10. <span data-ttu-id="003bf-128">Dans le champ Numéro d’enregistrement, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="003bf-128">In the Registration number field, type a value.</span></span>
11. <span data-ttu-id="003bf-129">Dans le champ Numéro d’enregistrement de la remorque, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="003bf-129">In the Trailer registration number field, type a value.</span></span>
12. <span data-ttu-id="003bf-130">Dans le champ Chauffeur, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="003bf-130">In the Driver field, enter or select a value.</span></span>
13. <span data-ttu-id="003bf-131">Dans le champ Nom du chauffeur, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="003bf-131">In the Driver name field, type a value.</span></span>
14. <span data-ttu-id="003bf-132">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="003bf-132">Click Save.</span></span>
15. <span data-ttu-id="003bf-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="003bf-133">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a><span data-ttu-id="003bf-134">Afficher le bon de livraison pour l’ordre de transfert non validé</span><span class="sxs-lookup"><span data-stu-id="003bf-134">View the packing slip for the unposted transfer order</span></span>
1. <span data-ttu-id="003bf-135">Cliquez sur Bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="003bf-135">Click Packing slip.</span></span>
2. <span data-ttu-id="003bf-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="003bf-136">Click OK.</span></span>
3. <span data-ttu-id="003bf-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="003bf-137">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a><span data-ttu-id="003bf-138">Afficher le bon de livraison pour l’ordre de transfert validé</span><span class="sxs-lookup"><span data-stu-id="003bf-138">View the packing slip for the posted transfer order</span></span>
1. <span data-ttu-id="003bf-139">Dans le volet Actions, cliquez sur Ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="003bf-139">On the Action Pane, click Transfer order.</span></span>
2. <span data-ttu-id="003bf-140">Dans le volet Actions, cliquez sur Expédier.</span><span class="sxs-lookup"><span data-stu-id="003bf-140">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="003bf-141">Cliquez sur Expédier l’ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="003bf-141">Click Ship transfer order.</span></span>
4. <span data-ttu-id="003bf-142">Cliquez sur l’onglet Général.</span><span class="sxs-lookup"><span data-stu-id="003bf-142">Click the General tab.</span></span>
5. <span data-ttu-id="003bf-143">Dans le champ Mettre à jour, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="003bf-143">In the Update field, select an option.</span></span>
6. <span data-ttu-id="003bf-144">Cliquez sur l’onglet Vue d’ensemble.</span><span class="sxs-lookup"><span data-stu-id="003bf-144">Click the Overview tab.</span></span>
7. <span data-ttu-id="003bf-145">Tapez une valeur dans le champ Bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="003bf-145">In the Packing slip field, type a value.</span></span>
8. <span data-ttu-id="003bf-146">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="003bf-146">Click OK.</span></span>
9. <span data-ttu-id="003bf-147">Dans le volet Actions, cliquez sur Expédier.</span><span class="sxs-lookup"><span data-stu-id="003bf-147">On the Action Pane, click Ship.</span></span>
10. <span data-ttu-id="003bf-148">Cliquez sur Bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="003bf-148">Click Packing slip.</span></span>
11. <span data-ttu-id="003bf-149">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="003bf-149">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]