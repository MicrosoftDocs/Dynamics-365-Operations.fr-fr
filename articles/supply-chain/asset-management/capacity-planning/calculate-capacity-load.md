---
title: Calculer la charge de la capacité
description: Cette rubrique explique comment calculer la charge de la capacité dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCapacityLoad, EntAssetWorkOrderCapacityLoadCalculate, EntAssetWorkOrderCapacityLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7a9b235ecedf3399c79ee081a9fe7e2423045fa5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260056"
---
# <a name="calculate-capacity-load"></a><span data-ttu-id="bbf27-103">Calculer la charge de la capacité</span><span class="sxs-lookup"><span data-stu-id="bbf27-103">Calculate capacity load</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="bbf27-104">Dans le module Gestion des actifs, vous pouvez calculer la charge de la capacité sur :</span><span class="sxs-lookup"><span data-stu-id="bbf27-104">In Asset Management, you can calculate capacity load on:</span></span>

- <span data-ttu-id="bbf27-105">les lignes du programme de maintenance</span><span class="sxs-lookup"><span data-stu-id="bbf27-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="bbf27-106">les ordres de travail qui n’ont pas encore été planifiés</span><span class="sxs-lookup"><span data-stu-id="bbf27-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="bbf27-107">les ordres de travail planifiés</span><span class="sxs-lookup"><span data-stu-id="bbf27-107">scheduled work orders</span></span>

<span data-ttu-id="bbf27-108">Cela est utile si vous souhaitez obtenir une vue d’ensemble de la charge de la capacité prévue pour une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="bbf27-108">This is useful if you want to get an overview of expected capacity load for a specific period.</span></span> <span data-ttu-id="bbf27-109">Le calcul de la charge maximale peut être effectué sur tous les actifs ou sur des actifs sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="bbf27-109">Calculation of capacity load can be done on all assets or selected assets.</span></span> <span data-ttu-id="bbf27-110">Vous pouvez également effectuer un calcul sur les activités de temps d’arrêt pour maintenance ou les regroupements d’ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="bbf27-110">You can also make a calculation on maintenance downtime activities or work order pools.</span></span>

1. <span data-ttu-id="bbf27-111">Cliquez sur **Gestion des actifs** > **Recherches** > **Charge maximale** ou **Gestion des actifs** > **Commun** > **Regroupements d’ordres de travail** > **Tous les regroupements d’ordres de travail** / **Regroupements d’ordres de travail actifs** > sélectionnez le regroupement d’ordres de travail dans la liste > cliquez sur le bouton **Charge de la capacité** ou **Gestion des actifs** > **Commun** > **Activités de temps d’arrêt pour maintenance** > **Toutes les activités de temps d’arrêt pour maintenance** / **Activités de temps d’arrêt pour maintenance actifs** > sélectionnez l’activité de maintenance dans la liste > cliquez sur le bouton **Charge de la capacité**.</span><span class="sxs-lookup"><span data-stu-id="bbf27-111">Click **Asset management** > **Inquiries** > **Capacity load**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Capacity load** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance activity in the list > **Capacity load** button.</span></span>

2. <span data-ttu-id="bbf27-112">Dans la boîte de dialogue **Calculer la charge de la capacité**, sélectionnez une période de calcul dans les champs **Date et heure de début** et **Date et heure de fin**.</span><span class="sxs-lookup"><span data-stu-id="bbf27-112">In the **Calculate capacity load** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="bbf27-113">Sélectionnez « Oui » sur le bouton bascule **Inclure le programme de maintenance** pour inclure les lignes du programme de maintenance dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="bbf27-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the calculation.</span></span>

4. <span data-ttu-id="bbf27-114">Sélectionnez « Oui » sur le bouton bascule **Inclure l’ordre de travail** pour inclure les tâches d’ordre de travail dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="bbf27-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the calculation.</span></span>

5. <span data-ttu-id="bbf27-115">Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de charge maximale en fonction des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="bbf27-115">You can use the **Level** field to indicate how detailed you want the capacity load lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="bbf27-116">Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes du programme de maintenance et les ordres de travail pour un poste technique s’affichent dans le niveau supérieur et il est donc possible d’ajouter des heures sur une ligne à partir des postes techniques situés à un niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="bbf27-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="bbf27-117">Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s’affiche et indique toutes les lignes du programme de maintenance et tous les ordres de travail sur tous les niveaux du poste technique auquel elles sont liées.</span><span class="sxs-lookup"><span data-stu-id="bbf27-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="bbf27-118">Cliquez sur **OK** pour démarrer le calcul.</span><span class="sxs-lookup"><span data-stu-id="bbf27-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="bbf27-119">Dans les groupes **Grouper par…**, cliquez sur les boutons appropriés à afficher le niveau requis de détail du calcul.</span><span class="sxs-lookup"><span data-stu-id="bbf27-119">In the **Group by...** groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="bbf27-120">Dans le capture d’écran ci-dessous, les boutons **Grouper par** sélectionnés sont mis en surbrillance en bleu.</span><span class="sxs-lookup"><span data-stu-id="bbf27-120">In the screenshot below, the selected **Group by** buttons are highlighted in blue color.</span></span> <span data-ttu-id="bbf27-121">Cliquez sur un bouton pour l’activer ou le désactiver.</span><span class="sxs-lookup"><span data-stu-id="bbf27-121">Click on a button to activate or deactivate it.</span></span>

    ![Figure 1](media/01-capacity-planning.png)

>[!NOTE]
><span data-ttu-id="bbf27-123">Si vous voulez vous concentrer uniquement sur la planification de la capacité associée aux ordres de travail planifiés,voir [Calculer la charge de la capacité sur les ordres de travail planifiés](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span><span class="sxs-lookup"><span data-stu-id="bbf27-123">If you want to focus only on capacity planning regarding scheduled work orders, see [Calculate capacity load on scheduled work orders](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]