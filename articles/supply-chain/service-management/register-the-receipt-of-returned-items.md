---
title: Enregistrement de la réception d'articles retournés
description: Vous pouvez enregistrer la réception des articles retournés à l'aide de l'écran Vue d'ensemble des arrivées ou de l'écran Enregistrement.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2be628d312e623e8ea6d92eb5edce12334190d9e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571073"
---
# <a name="register-the-receipt-of-returned-items"></a><span data-ttu-id="158d0-103">Enregistrement de la réception d'articles retournés</span><span class="sxs-lookup"><span data-stu-id="158d0-103">Register the receipt of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="158d0-104">Il existe deux méthodes d'enregistrement de la réception des articles retournés.</span><span class="sxs-lookup"><span data-stu-id="158d0-104">There are two methods for registering the receipt of returned items.</span></span> <span data-ttu-id="158d0-105">La première méthode est un processus de réception dans l'entrepôt qui utilise l'écran **Vue d'ensemble des arrivées**.</span><span class="sxs-lookup"><span data-stu-id="158d0-105">The first method is a warehouse receiving process that uses the **Arrival overview** form.</span></span> <span data-ttu-id="158d0-106">La deuxième méthode utilise l'écran **Enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="158d0-106">The second uses the **Registration** form.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a><span data-ttu-id="158d0-107">Enregistrement de la réception des articles retournés à l'aide de l'écran Vue d'ensemble des arrivées</span><span class="sxs-lookup"><span data-stu-id="158d0-107">Register the receipt of returned items in the Arrival overview form</span></span>

<span data-ttu-id="158d0-108">L'écran **Vue d'ensemble des arrivées** permet d'identifier une expédition de retour par son numéro de retour marchandises.</span><span class="sxs-lookup"><span data-stu-id="158d0-108">You can use the **Arrival overview** form to identify a return shipment by its Return Material Authorization (RMA) number.</span></span> <span data-ttu-id="158d0-109">Si un nom de journal est défini sous l'onglet **Paramétrage** et que les lignes de journal correspondant aux lignes sélectionnées dans l'écran **Vue d'ensemble des arrivées** existent, un en-tête de journal est créé lorsque vous cliquez sur **Commencer une arrivée**.</span><span class="sxs-lookup"><span data-stu-id="158d0-109">If a journal name is defined on the **Setup** tab, and journal lines that correspond to the lines selected on the **Arrival overview** form exist, a new journal header is created when you click **Start arrival**.</span></span>

1.  <span data-ttu-id="158d0-110">Cliquez sur **Gestion des stocks** \> **Périodique** \> **Vue d'ensemble des arrivées**.</span><span class="sxs-lookup"><span data-stu-id="158d0-110">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="158d0-111">Dans le champ **Nom du paramétrage**, sélectionnez **Ordre de retour**, puis cliquez sur **Mettre à jour**.</span><span class="sxs-lookup"><span data-stu-id="158d0-111">In the **Setup name** field, select **Return order**, and then click **Update**.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="158d0-112">Les champs <STRONG>Plage</STRONG> permettent d'affiner les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="158d0-112">You can use the <STRONG>Range</STRONG> fields to narrow the search results.</span></span> <span data-ttu-id="158d0-113">Vous pouvez taper ou sélectionner le numéro de retour marchandises dans le champ <STRONG>Numéro de retour marchandises</STRONG> pour obtenir un résultat exact.</span><span class="sxs-lookup"><span data-stu-id="158d0-113">You can type or select the RMA number in the <STRONG>RMA number</STRONG> field for an exact result.</span></span> <span data-ttu-id="158d0-114">Pour définir et enregistrer un ensemble de filtres qui limiteront les arrivées entrantes affichées, cliquez sur l'onglet <STRONG>Paramétrage</STRONG>. Les filtres disponibles sont des types, des entrepôts et des quais.</span><span class="sxs-lookup"><span data-stu-id="158d0-114">To define and save a set of filters that will restrict which incoming arrivals are displayed, click the <STRONG>Setup</STRONG> tab. The available filters include types, warehouses, and docks.</span></span></P>

    

    > [!WARNING]
    > <P><span data-ttu-id="158d0-115">Les ordres de retour ne peuvent pas être mélangés à d'autres types d'arrivées dans l'écran <STRONG>Vue d'ensemble des arrivées</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="158d0-115">Return orders cannot be mixed with other arrival types in the <STRONG>Arrival overview</STRONG> form.</span></span> <span data-ttu-id="158d0-116">Par conséquent, la référence est toujours la commande client, mais aucun ID de commande client n'est spécifié dans l'en-tête de journal.</span><span class="sxs-lookup"><span data-stu-id="158d0-116">Therefore, the reference will always be sales order, but no sales order ID will be specified on the journal header.</span></span></P>



3.  <span data-ttu-id="158d0-117">Dans la grille **Réceptions**, localisez la ligne correspondant à l'article retourné, puis activez la case à cocher dans la colonne **Sélectionner pour l'arrivée**.</span><span class="sxs-lookup"><span data-stu-id="158d0-117">In the **Receipts** grid, locate the line that matches the item being returned, and then select the check box in the **Select for arrival** column.</span></span>

4.  <span data-ttu-id="158d0-118">Pour exclure certaines lignes de la réception de retour, telles que les articles de la commande d'origine non inclus dans l'expédition de retour, désactivez les cases à cocher **Sélectionner pour l'arrivée** associées dans le tableau **Lignes** dans la partie inférieure de l'écran.</span><span class="sxs-lookup"><span data-stu-id="158d0-118">To exclude certain lines from the return receipt, such as items from the original order that were not included in the return shipment, clear the associated **Select for arrival** check boxes in the **Lines** table in the lower part of the form.</span></span>

5.  <span data-ttu-id="158d0-119">Cliquez sur le bouton **Commencer une arrivée** pour créer un journal des arrivées.</span><span class="sxs-lookup"><span data-stu-id="158d0-119">Click the **Start arrival** button to create an arrival journal.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="158d0-120">Vous pouvez sélectionner plusieurs ordres de retour et les inclure dans un processus d'arrivée unique.</span><span class="sxs-lookup"><span data-stu-id="158d0-120">You can select multiple return orders and include them all in a single arrival process.</span></span> <span data-ttu-id="158d0-121">Chaque ligne d'ordre de retour est copiée dans une ligne correspondante du journal des arrivées d'articles.</span><span class="sxs-lookup"><span data-stu-id="158d0-121">Each return order line will be copied into a corresponding item arrival journal line.</span></span></P>

    

    > [!NOTE]
    > <P><span data-ttu-id="158d0-122">Vous pouvez également créer manuellement un journal des arrivées à l'aide de l'écran <STRONG>Arrivée d'articles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="158d0-122">You can also manually create an arrival journal by using the <STRONG>Item arrival</STRONG> form.</span></span> 



6.  <span data-ttu-id="158d0-123">Cliquez sur **Gestion des stocks** \> **Journaux** \> **Arrivée d'articles** \> **Arrivée d'articles**.</span><span class="sxs-lookup"><span data-stu-id="158d0-123">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>

7.  <span data-ttu-id="158d0-124">Sélectionnez le journal des arrivées que vous venez de créer, puis cliquez sur **Lignes** pour ouvrir l'écran **Lignes de journal, emplacements**.</span><span class="sxs-lookup"><span data-stu-id="158d0-124">Select the arrival journal that you just created and then click **Lines** to open the **Journal lines, locations** form.</span></span>

8.  <span data-ttu-id="158d0-125">Sous l'onglet **Général**, ajustez le numéro dans le champ **Quantité**, si nécessaire, puis affectez un code disposition dans le champ **Code disposition**.</span><span class="sxs-lookup"><span data-stu-id="158d0-125">On the **General** tab, adjust the number in the **Quantity** field, if it is required, and then assign a disposition code in the **Disposition code** field.</span></span>
    
    <span data-ttu-id="158d0-126">Sinon, vous pouvez activer la case à cocher **Gestion des contrôles** pour que les articles retournés soient envoyés via un processus d'inspection dans le contexte d'un ordre de contrôle.</span><span class="sxs-lookup"><span data-stu-id="158d0-126">Alternatively, you can select the **Quarantine management** check box to have the returned items sent through an inspection process in the context of a quarantine order.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="158d0-127">Si vous envoyez les articles retournés via contrôle, vous ne pouvez pas spécifier de code disposition.</span><span class="sxs-lookup"><span data-stu-id="158d0-127">If you send the returned items through quarantine, you cannot specify a disposition code.</span></span></P>



9.  <span data-ttu-id="158d0-128">Cliquez sur le bouton **Contrôler**.</span><span class="sxs-lookup"><span data-stu-id="158d0-128">Click the **Validate** button.</span></span>

10. <span data-ttu-id="158d0-129">S'il n'y a aucune erreur dans le processus de contrôle, cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="158d0-129">If there are no errors in the validation process, click **Post**.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a><span data-ttu-id="158d0-130">Enregistrement de la réception des articles retournés à l'aide de l'écran Enregistrement</span><span class="sxs-lookup"><span data-stu-id="158d0-130">Register the receipt of returned items in the Registration form</span></span>

<span data-ttu-id="158d0-131">Au lieu d'utiliser l'écran **Vue d'ensemble des arrivées**, vous pouvez utiliser l'écran **Enregistrement** pour enregistrer l'arrivée des articles retournés.</span><span class="sxs-lookup"><span data-stu-id="158d0-131">As an alternative to using the **Arrival overview** form, you can use the **Registration** form to register the arrival of returned items.</span></span>

1.  <span data-ttu-id="158d0-132">Cliquez sur **Ventes et marketing** \> **Commun** \> **Ordres de retour** \> **Tous les ordres de retour**.</span><span class="sxs-lookup"><span data-stu-id="158d0-132">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span> <span data-ttu-id="158d0-133">Créez un ordre de retour ou ouvrez un ordre de retour dans la liste.</span><span class="sxs-lookup"><span data-stu-id="158d0-133">Create a new return order or open the return order from the list.</span></span> <span data-ttu-id="158d0-134">Dans l'organisateur **Lignes**, sélectionnez la ligne d'ordre de retour.</span><span class="sxs-lookup"><span data-stu-id="158d0-134">On the **Lines** FastTab, select the return order line.</span></span> <span data-ttu-id="158d0-135">Cliquez sur **Mettre à jour la ligne**, puis sur **Enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="158d0-135">Click **Update line**, and then click **Registration**.</span></span>

2.  <span data-ttu-id="158d0-136">Affectez un code disposition dans le champ **Code disposition**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="158d0-136">Assign a disposition code in the **Disposition code** field, and then click **OK**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="158d0-137">Il est impossible d'envoyer l'article pour inspection comme ordre de contrôle à l'aide de l'écran <STRONG>Enregistrement</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="158d0-137">It is not possible to send the item for inspection as a quarantine order using the <STRONG>Registration</STRONG> form.</span></span></P>



3.  <span data-ttu-id="158d0-138">Dans la grille **Transactions**, sélectionnez la transaction à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="158d0-138">In the **Transactions** grid, select the transaction to be registered.</span></span>

4.  <span data-ttu-id="158d0-139">Dans la grille **Enregistrer maintenant**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="158d0-139">In the **Register now** grid, click **Add**.</span></span> <span data-ttu-id="158d0-140">Répétez les deux étapes précédentes jusqu'à ce que tous les articles retournés soient affichés dans la grille **Enregistrer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="158d0-140">Repeat the previous two steps until all of the returned items appear in the **Register now** grid.</span></span>

5.  <span data-ttu-id="158d0-141">Cliquez sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="158d0-141">Click **Post all**.</span></span>

## <a name="see-also"></a><span data-ttu-id="158d0-142">Voir également :</span><span class="sxs-lookup"><span data-stu-id="158d0-142">See also</span></span>

<span data-ttu-id="158d0-143">[Vue d'ensemble des arrivées (écran)](https://technet.microsoft.com/en-us/library/hh227654\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="158d0-143">[Arrival overview (form)](https://technet.microsoft.com/en-us/library/hh227654\(v=ax.60\))</span></span>

  


