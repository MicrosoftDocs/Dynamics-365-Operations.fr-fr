---
title: "Validation du journal des arrivées pour les produits retournés"
description: "Validation du journal des arrivées pour les produits retournés."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSArrivalOverview
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: cbe60846f0a16b5061349d9960c49bb5310bd6f9
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---


# <a name="post-arrival-journal-for-returned-products"></a><span data-ttu-id="856d6-103">Validation du journal des arrivées pour les produits retournés</span><span class="sxs-lookup"><span data-stu-id="856d6-103">Post arrival journal for returned products</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="856d6-104">Pour traiter un retour, commencez par valider la quantité retournée et mettre à jour le champ de quantité dans le journal des arrivées d'articles.</span><span class="sxs-lookup"><span data-stu-id="856d6-104">To process a return, first validate the return quantity, update the quantity field in the item arrival journal.</span></span> <span data-ttu-id="856d6-105">Puis sélectionnez un code disposition ou indiquez que les articles retournés doivent être inspectés.</span><span class="sxs-lookup"><span data-stu-id="856d6-105">Then select a disposition code or indicate that the returned items have to be inspected.</span></span> <span data-ttu-id="856d6-106">Une fois ces opérations accomplies, vous pouvez valider le journal des arrivées d'articles pour l'ordre de retour.</span><span class="sxs-lookup"><span data-stu-id="856d6-106">After completing these steps, you can post the item arrival journal for the return order.</span></span>

1.  <span data-ttu-id="856d6-107">Cliquez sur **Gestion des stocks** \> **Périodique** \> **Vue d'ensemble des arrivées**.</span><span class="sxs-lookup"><span data-stu-id="856d6-107">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="856d6-108">Dans le filtre **Nom du paramétrage**, sélectionnez **Ordre de retour**.</span><span class="sxs-lookup"><span data-stu-id="856d6-108">In the **Setup name** filter, select **Return order**.</span></span>

3.  <span data-ttu-id="856d6-109">Si la liste des réceptions est longue, utilisez les champs de la zone **Plage** pour la raccourcir.</span><span class="sxs-lookup"><span data-stu-id="856d6-109">If the list of receipts is long, use the fields in the **Range** area to narrow the list.</span></span>

4.  <span data-ttu-id="856d6-110">Repérez la ligne de l'ordre de retour à valider, activez la case **Sélectionner pour l'arrivée** associée, puis cliquez sur **Commencer une arrivée**.</span><span class="sxs-lookup"><span data-stu-id="856d6-110">Locate the line of the return order that you want to post, select its **Select for arrival** box, and then click **Start arrival**.</span></span>

5.  <span data-ttu-id="856d6-111">Cliquez sur **Journaux** \> **Afficher les arrivées à partir des réceptions** pour ouvrir l'écran **Journal des emplacements**.</span><span class="sxs-lookup"><span data-stu-id="856d6-111">Click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="856d6-112">Pour afficher des informations détaillées, sélectionnez un journal, puis cliquez sur <STRONG>Lignes</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="856d6-112">To view detailed information, select a journal, and then click <STRONG>Lines</STRONG>.</span></span></P>


6.  <span data-ttu-id="856d6-113">Apportez les mises à jour nécessaires, puis cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="856d6-113">Make any necessary updates, and then click **Post**.</span></span>

<span data-ttu-id="856d6-114">Une fois le journal validé, les articles retournés sont enregistrés en stock et l'écran **Ordres de retour** indique qu'ils sont arrivés à l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="856d6-114">After the journal is posted, the returned items are registered in inventory, and the **Return orders** form indicates that the items have arrived at the warehouse.</span></span>

## <a name="see-also"></a><span data-ttu-id="856d6-115">Voir également :</span><span class="sxs-lookup"><span data-stu-id="856d6-115">See also</span></span>

<span data-ttu-id="856d6-116">[Journal des emplacements (écran)](https://technet.microsoft.com/en-us/library/aa584822\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="856d6-116">[Location journal (form)](https://technet.microsoft.com/en-us/library/aa584822\(v=ax.60\))</span></span>

  



