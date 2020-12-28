---
title: Recevoir des livraisons partielles d'articles retournés
description: Des livraisons partielles sont définies en termes de lignes d'ordre de retour, pas d'expéditions de retour.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf35169d8afd6e88b8ebe921514ed6d55607a4dd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427635"
---
# <a name="receive-partial-deliveries-of-returned-items"></a><span data-ttu-id="dd500-103">Recevoir des livraisons partielles d'articles retournés</span><span class="sxs-lookup"><span data-stu-id="dd500-103">Receive partial deliveries of returned items</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="dd500-104">Des livraisons partielles sont définies en termes de lignes d'ordre de retour, pas d'expéditions de retour.</span><span class="sxs-lookup"><span data-stu-id="dd500-104">Partial deliveries are defined in terms of return order lines, not return order shipments.</span></span>

<span data-ttu-id="dd500-105">Cela signifie que, si vous recevez la quantité complète indiquée sur une ligne d'ordre de retour, mais rien en rapport avec les autres lignes, la livraison n'est pas partielle.</span><span class="sxs-lookup"><span data-stu-id="dd500-105">This means that if you receive the full quantity that is indicated on one return order line, but you receive nothing from the other lines in the return order, the delivery is not a partial delivery.</span></span> <span data-ttu-id="dd500-106">En revanche, si une ligne d'ordre de retour indique que dix unités d'un article doivent être retournées et que vous n'en recevez que quatre, la livraison est partielle.</span><span class="sxs-lookup"><span data-stu-id="dd500-106">However, if a return order line requires 10 units of a particular item to be returned, but you receive only four, it is a partial delivery.</span></span>

<span data-ttu-id="dd500-107">Si une expédition de retour contient une quantité inférieure à celle indiquée sur une ligne d'ordre de retour, vous pouvez soit mettre l'expédition de côté en attendant de recevoir le reste de la quantité retournée, soit enregistrer et valider la quantité partielle.</span><span class="sxs-lookup"><span data-stu-id="dd500-107">If a return shipment contains less than the full quantity of a return order line, you can set the shipment aside and wait for the rest of the returned quantity to arrive, or you can register and post the partial quantity.</span></span>

## <a name="register-and-post-a-partial-quantity"></a><span data-ttu-id="dd500-108">Enregistrement et validation d'une quantité partielle</span><span class="sxs-lookup"><span data-stu-id="dd500-108">Register and post a partial quantity</span></span>

1.  <span data-ttu-id="dd500-109">Après avoir sélectionné un ordre de retour pour arrivée dans l'écran **Vue d'ensemble des arrivées - Entrepôt : %1, Quai : %2, Nom du journal : %3**, cliquez sur **Commencer une arrivée** pour créer le journal des arrivées, puis sur **Journaux** \> **Afficher les arrivées à partir des réceptions** pour ouvrir l'écran **Journaux des emplacements**.</span><span class="sxs-lookup"><span data-stu-id="dd500-109">After you select a return order for arrival on the **Arrival overview - Warehouse: %1, Dock: %2, Journal name: %3** form, click **Start arrival** to create the arrival journal, and then click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>

2.  <span data-ttu-id="dd500-110">Sélectionnez la ligne du journal sur laquelle vous voulez travailler, puis cliquez sur **Lignes** pour ouvrir l'écran **Lignes de journal, emplacements**.</span><span class="sxs-lookup"><span data-stu-id="dd500-110">Select the line of the journal that you want to work with, and then click **Lines** to open the **Journal lines, locations** form.</span></span>

3.  <span data-ttu-id="dd500-111">Sélectionnez la ligne du numéro d'article pour laquelle seule une quantité partielle est arrivée, puis cliquez sur **Fonctions** \> **Fractionner** pour ouvrir l'écran **Fractionner**.</span><span class="sxs-lookup"><span data-stu-id="dd500-111">Select the line of the item number for which only a partial quantity has arrived, and then click **Functions** \> **Split** to open the **Split** form.</span></span>

4.  <span data-ttu-id="dd500-112">Dans le champ **Quantité fractionnée**, entrez la quantité correspondant au nombre total d'articles reçus, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd500-112">In the **Split quantity** field, enter the quantity for the total number of items that have been received, and then click **OK**.</span></span>

5.  <span data-ttu-id="dd500-113">Dans l'écran **Lignes de journal, emplacements**, sélectionnez la ligne indiquant la quantité d'articles arrivés, puis cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="dd500-113">On the **Journal lines, locations** form, select the line for the quantity of items that has arrived, and then click **Post**.</span></span> <span data-ttu-id="dd500-114">Vous pouvez valider la ligne pour la quantité supplémentaire une fois les articles arrivés.</span><span class="sxs-lookup"><span data-stu-id="dd500-114">You can post the line for the additional quantity after the items have arrived.</span></span>




