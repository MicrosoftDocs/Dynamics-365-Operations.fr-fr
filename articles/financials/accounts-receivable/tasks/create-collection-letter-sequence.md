--- 
title: "Créer une série de lettres de relance"
description: "Utilisez ce guide de tâche pour créer une série de lettres de relance."
author: mikefalkner
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
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6331c3680169b305c4bfbfada4ba106b619be092
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-collection-letter-sequence"></a><span data-ttu-id="208bf-103">Créer une série de lettres de relance</span><span class="sxs-lookup"><span data-stu-id="208bf-103">Create a collection letter sequence</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="208bf-104">Utilisez ce guide de tâche pour créer une série de lettres de relance.</span><span class="sxs-lookup"><span data-stu-id="208bf-104">Use this task guide to create a collection letter sequence.</span></span> <span data-ttu-id="208bf-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="208bf-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="208bf-106">Accédez à Crédit et relances > Paramétrage > Paramétrer la série de lettres de relance.</span><span class="sxs-lookup"><span data-stu-id="208bf-106">Go to Credit and collections > Setup > Set up collection letter sequence.</span></span>
2. <span data-ttu-id="208bf-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="208bf-107">Click New.</span></span>
3. <span data-ttu-id="208bf-108">Dans le champ Série de lettres de relance, entrez un ID souche qui représentera la séquence.</span><span class="sxs-lookup"><span data-stu-id="208bf-108">In the Collection letter sequence field, enter a sequence ID that will represent the sequence.</span></span> <span data-ttu-id="208bf-109">Il sera utilisé pour paramétrer un profil de validation.</span><span class="sxs-lookup"><span data-stu-id="208bf-109">It will be used when you set up a posting profile.</span></span>
4. <span data-ttu-id="208bf-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="208bf-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="208bf-111">Les conditions de paiement sont facultatives.</span><span class="sxs-lookup"><span data-stu-id="208bf-111">The terms of payment is optional.</span></span> <span data-ttu-id="208bf-112">Si vous entrez une valeur ici, la facture de frais de relance utilise ces conditions de paiement à la place de ceux enregistrés avec le client.</span><span class="sxs-lookup"><span data-stu-id="208bf-112">If you enter a value here, the collection letter fee invoice will use these terms of payment instead of the terms of payment stored with the customer.</span></span>  
5. <span data-ttu-id="208bf-113">Dans le champ de code lettre de relance, sélectionnez le code pour la première lettre de relance à envoyer.</span><span class="sxs-lookup"><span data-stu-id="208bf-113">In the collection letter code field, select the code for the first collection letter that you want to send.</span></span>
    * <span data-ttu-id="208bf-114">La première lettre de relance est créée en fonction de la date d'échéance figurant sur la facture, de la valeur que vous entrez pour la période de grâce dans le champ Jours de cette ligne, et des autres informations que vous entrez dans cette ligne.</span><span class="sxs-lookup"><span data-stu-id="208bf-114">The first collection letter is created according to the due date on the invoice, the value that you enter for the grace period in the Days field on this line, and other information that you enter on this line.</span></span>  
6. <span data-ttu-id="208bf-115">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="208bf-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="208bf-116">La devise des frais est définie par défaut sur la devise du client.</span><span class="sxs-lookup"><span data-stu-id="208bf-116">The currency for the fee defaults to the customer currency.</span></span> <span data-ttu-id="208bf-117">Ce code devise peut être différent de la devise de facturation.</span><span class="sxs-lookup"><span data-stu-id="208bf-117">This currency code can be different than the invoice currency.</span></span>  
7. <span data-ttu-id="208bf-118">Cliquez sur Ajouter pour ajouter la lettre de relance suivante qui sera envoyée dans la séquence</span><span class="sxs-lookup"><span data-stu-id="208bf-118">Click Add to add the next collection letter that will be sent in the sequence</span></span>
    * <span data-ttu-id="208bf-119">Dans de nombreux cas, la première lettre de relance est simplement un avertissement.</span><span class="sxs-lookup"><span data-stu-id="208bf-119">In many cases, the first collection letter is just a warning.</span></span> <span data-ttu-id="208bf-120">Vous pouvez ajouter des frais si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="208bf-120">You can add fees if needed.</span></span>  
8. <span data-ttu-id="208bf-121">Dans le champ de code lettre de relance, sélectionnez la lettre de relance suivante qui sera envoyée dans la séquence.</span><span class="sxs-lookup"><span data-stu-id="208bf-121">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
9. <span data-ttu-id="208bf-122">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="208bf-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="208bf-123">Dans le champ de compte principal, sélectionnez le compte de produit à utiliser pour les frais.</span><span class="sxs-lookup"><span data-stu-id="208bf-123">In the main account field, select the revenue account that will be used for fees.</span></span>
11. <span data-ttu-id="208bf-124">Entrez les frais qui seront facturés lorsque cette lettre de relance sera validée.</span><span class="sxs-lookup"><span data-stu-id="208bf-124">Enter the fee that will be charged when this collection letter is posted.</span></span>
12. <span data-ttu-id="208bf-125">Dans le champ Groupes de taxe d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="208bf-125">In the Item sales tax group field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="208bf-126">Sélectionnez un groupe de taxe d'article si des taxes doivent être calculées sur les frais.</span><span class="sxs-lookup"><span data-stu-id="208bf-126">Select an item sales tax group if sales taxes must be calculated on the fee.</span></span>  
13. <span data-ttu-id="208bf-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="208bf-127">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="208bf-128">Entrez le solde minimal en retard nécessaire avant qu'une lettre de relance soit envoyée.</span><span class="sxs-lookup"><span data-stu-id="208bf-128">Enter the minimum overdue balance required before a collection letter is sent.</span></span>
15. <span data-ttu-id="208bf-129">Entrez le nombre de jours de grâce que vous allez autoriser.</span><span class="sxs-lookup"><span data-stu-id="208bf-129">Enter the number of grace days that you will allow.</span></span>
    * <span data-ttu-id="208bf-130">Il s'agit du nombre de jours après la date d'échéance qu'une lettre de relance peut être générée.</span><span class="sxs-lookup"><span data-stu-id="208bf-130">This is the number of days after the due date that a collection letter can be generated.</span></span> <span data-ttu-id="208bf-131">La date d'échéance utilisée pour le calcul dépend de la position de la lettre de relance dans la série :   ⦁    La période de grâce pour la lettre de relance 1 est relative à la date d'échéance de la facture.</span><span class="sxs-lookup"><span data-stu-id="208bf-131">The due date that is used for the calculation depends on the position of the collection letter in the collection letter sequence:   ⦁    The grace period for collection letter 1 is relative to the due date on the invoice.</span></span>  <span data-ttu-id="208bf-132">⦁ La période de grâce pour les lettres de relance 2 et ultérieures est relative à la date à laquelle la lettre de relance précédente est validée ou imprimée, selon la sélection du champ Mettre à jour un code lettre de relance dans la page Paramètres de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="208bf-132">⦁ The grace period for collection letters 2 and higher is relative to the date that the previous collection letter is posted or printed, depending on the selection in the Update collection letter code field in the Accounts receivable parameters page.</span></span>  
16. <span data-ttu-id="208bf-133">Cliquez sur Ajouter pour ajouter la dernière lettre de relance de la séquence.</span><span class="sxs-lookup"><span data-stu-id="208bf-133">Click Add to add the last collection letter in the sequence.</span></span>
    * <span data-ttu-id="208bf-134">Vous pouvez ajouter jusqu'à cinq codes lettre de relance pour une série de lettres de relance.</span><span class="sxs-lookup"><span data-stu-id="208bf-134">You can add up to five collection letter codes for a collection letter sequence.</span></span>  
17. <span data-ttu-id="208bf-135">Dans le champ de code lettre de relance, sélectionnez la lettre de relance suivante qui sera envoyée dans la séquence.</span><span class="sxs-lookup"><span data-stu-id="208bf-135">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
18. <span data-ttu-id="208bf-136">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="208bf-136">In the Description field, type a value.</span></span>
19. <span data-ttu-id="208bf-137">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="208bf-137">In the Main account field, specify the desired values.</span></span>
20. <span data-ttu-id="208bf-138">Entrez un nombre dans le champ Frais en devise.</span><span class="sxs-lookup"><span data-stu-id="208bf-138">In the Fee in currency field, enter a number.</span></span>
21. <span data-ttu-id="208bf-139">Dans le champ Groupes de taxe d'article : cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="208bf-139">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="208bf-140">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="208bf-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="208bf-141">Entrez un nombre dans le champ Solde minimal en retard.</span><span class="sxs-lookup"><span data-stu-id="208bf-141">In the Minimum overdue balance field, enter a number.</span></span>
24. <span data-ttu-id="208bf-142">Entrez un nombre dans le champ Jour.</span><span class="sxs-lookup"><span data-stu-id="208bf-142">In the Days field, enter a number.</span></span>
25. <span data-ttu-id="208bf-143">Activez cette case à cocher pour empêcher de nouvelles livraisons ou facturations avec le client.</span><span class="sxs-lookup"><span data-stu-id="208bf-143">Select this check box to stop the customer from additional deliveries and invoicing.</span></span>
    * <span data-ttu-id="208bf-144">Pour débloquer le compte, sélectionnez Non dans le champ Facturation et livraison en attente dans la page Clients.</span><span class="sxs-lookup"><span data-stu-id="208bf-144">To unblock the account, select No in the Invoicing and delivery on hold field in the Customers page.</span></span>  
26. <span data-ttu-id="208bf-145">Développer l'organisateur Note.</span><span class="sxs-lookup"><span data-stu-id="208bf-145">Expand the Note fasttab.</span></span>
27. <span data-ttu-id="208bf-146">Entrez le texte tel que vous souhaitez qu'il apparaisse dans la lettre de relance pour le code lettre de relance sélectionné.</span><span class="sxs-lookup"><span data-stu-id="208bf-146">Enter the text to appear on the collection letter for the selected collection letter code.</span></span>
    * <span data-ttu-id="208bf-147">Vous pouvez traduire ce texte dans plusieurs langues à l'aide du menu Traductions au-dessus de la zone de note.</span><span class="sxs-lookup"><span data-stu-id="208bf-147">You can translate this text in to multiple languages using the Translations menu above the note box.</span></span>  


