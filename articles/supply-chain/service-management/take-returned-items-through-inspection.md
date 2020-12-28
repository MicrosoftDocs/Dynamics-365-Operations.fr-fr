---
title: Inspection des articles retournés
description: Inspection des articles retournés.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bdc42f9c5ece8e2c2570cadf623f52648b7b174e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428049"
---
# <a name="take-returned-items-through-inspection"></a><span data-ttu-id="17b73-103">Inspection des articles retournés</span><span class="sxs-lookup"><span data-stu-id="17b73-103">Take returned items through inspection</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="17b73-104">Cliquez sur **Gestion des stocks** \> **Périodique** \> **Gestion de la qualité** \> **Ordres de contrôle**.</span><span class="sxs-lookup"><span data-stu-id="17b73-104">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="17b73-105">Accédez à la ligne de commande qui correspond à l'article retourné que vous inspectez.</span><span class="sxs-lookup"><span data-stu-id="17b73-105">Locate the order line that corresponds to the returned item that you are inspecting.</span></span>

    > [!NOTE]
    > <P><span data-ttu-id="17b73-106">Un ordre de contrôle ne peut être associé qu'à un seul numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="17b73-106">A quarantine order can be associated with just a single item number.</span></span> <span data-ttu-id="17b73-107">Si 10 articles avec différents numéros d'article sont retournés en une seule fois et envoyés en contrôle, 10 ordres de contrôle individuels sont créés.</span><span class="sxs-lookup"><span data-stu-id="17b73-107">If 10 items that have different item numbers are returned in a single shipment and sent to quarantine, 10 individual quarantine orders are created.</span></span></P>

3.  <span data-ttu-id="17b73-108">Après inspection de l'article, effectuez une sélection dans le champ **Code disposition** pour indiquer les actions à réaliser et le mode de traitement des transactions financières associées.</span><span class="sxs-lookup"><span data-stu-id="17b73-108">After examining the item, make a selection in the **Disposition code** field to indicate what should be done with the item and how to handle the related financial transaction.</span></span> <span data-ttu-id="17b73-109">Voici quelques exemples d'actions : renvoi de l'article en stock et remboursement du client, mise au rebut de l'article et envoi d'un article de remplacement au client ou renvoi de l'article au client sans crédit.</span><span class="sxs-lookup"><span data-stu-id="17b73-109">Examples include returning the item to stock and refunding the customer, scrapping the item and sending a replacement to the customer, or returning the item to the customer without credit.</span></span>
    
    > [!NOTE]
    > <P><span data-ttu-id="17b73-110">S'il est impossible d'affecter le même code disposition à plusieurs articles retournés faisant partie d'un lot de numéros d'article, vous devez fractionner l'ordre de contrôle (<STRONG>Fonctions</STRONG> &gt; <STRONG>Fractionner</STRONG>) de manière à affecter un code disposition différent à chaque sous-lot.</span><span class="sxs-lookup"><span data-stu-id="17b73-110">If multiple returned items in a single item number batch cannot be assigned the same disposition code, you must split the quarantine order (<STRONG>Functions</STRONG> &gt; <STRONG>Split</STRONG>) to assign a different disposition code to each sub-batch.</span></span></P>


4.  <span data-ttu-id="17b73-111">Lorsque l'inspection est terminée, cliquez sur **Déclaration de fin** pour libérer les articles retournés, puis créez une entrée de journal des arrivées d'articles.</span><span class="sxs-lookup"><span data-stu-id="17b73-111">When you are finished with the inspection, click **Report as finished** to release the returned items and create an item arrival journal entry.</span></span> <span data-ttu-id="17b73-112">La personne ou le service qui reçoit les articles traite ensuite le journal pour que les articles soient renvoyés en stock.</span><span class="sxs-lookup"><span data-stu-id="17b73-112">The person or department that receives the items then processes the journal for the items to be returned to inventory.</span></span>
    
    <span data-ttu-id="17b73-113">- ou -</span><span class="sxs-lookup"><span data-stu-id="17b73-113">–or–</span></span>
    
    <span data-ttu-id="17b73-114">Terminez l'ordre de contrôle, puis retournez les articles en stock à l'aide de l'une des fonctions **Stock**.</span><span class="sxs-lookup"><span data-stu-id="17b73-114">End the quarantine order, and move the items back into inventory directly by using one of the **Inventory** functions.</span></span>

5.  <span data-ttu-id="17b73-115">Fermez l'écran pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="17b73-115">Close the form to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="17b73-116">Voir également :</span><span class="sxs-lookup"><span data-stu-id="17b73-116">See also</span></span>

[<span data-ttu-id="17b73-117">Spécification de la procédure de cession des articles retournés</span><span class="sxs-lookup"><span data-stu-id="17b73-117">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)

  


