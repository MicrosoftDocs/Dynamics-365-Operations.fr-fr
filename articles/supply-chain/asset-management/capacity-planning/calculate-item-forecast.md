---
title: Calculer les prévisions en matière d'articles
description: Cette rubrique explique comment calculer la prévision d'article dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetItemForecast
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f8f38ac7bfb270f648cd561da50ee5477721ab47
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428005"
---
# <a name="calculate-item-forecast"></a><span data-ttu-id="168a8-103">Calculer les prévisions en matière d'articles</span><span class="sxs-lookup"><span data-stu-id="168a8-103">Calculate item forecast</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="168a8-104">Tout comme vous pouvez effectuer des calculs de charge, comme décrit dans la section précédente, vous pouvez également effectuer des calculs de prévision d'article sur :</span><span class="sxs-lookup"><span data-stu-id="168a8-104">Just as you can make capacity load calculations, which are described in the previous section, you can also make item forecast calculations on:</span></span>

- <span data-ttu-id="168a8-105">les lignes du programme de maintenance</span><span class="sxs-lookup"><span data-stu-id="168a8-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="168a8-106">les ordres de travail qui n'ont pas encore été planifiés</span><span class="sxs-lookup"><span data-stu-id="168a8-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="168a8-107">les ordres de travail planifiés</span><span class="sxs-lookup"><span data-stu-id="168a8-107">scheduled work orders</span></span>

<span data-ttu-id="168a8-108">Cela est utile si vous souhaitez obtenir une vue d'ensemble de la consommation d'article prévue (des pièces détachées ainsi que d'autres articles requis pour accomplir des ordres de travail) pour une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="168a8-108">This is useful if you want to get an overview of expected item consumption (spare parts as well as other items required for completing work orders) for a specific period.</span></span> <span data-ttu-id="168a8-109">Le calcul de la prévision d'article peut être effectué sur tous les actifs ou sur des actifs sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="168a8-109">Calculation of item forecast can be done on all assets or selected assets.</span></span> <span data-ttu-id="168a8-110">Vous pouvez également effectuer un calcul sur une activité de temps d'arrêt pour maintenance (**Toutes les activités de temps d'arrêt pour maintenance** ou **Activités de temps d'arrêt pour maintenance**) ou sur un regroupement d'ordres de travail (**Tous les regroupements d'ordres de travail** ou **Regroupements d'ordres de travail actifs**).</span><span class="sxs-lookup"><span data-stu-id="168a8-110">You can also make a calculation on a maintenance downtime activity (**All maintenance downtime activities** or **Active maintenance downtime activities**), or on a work order pool (**All work order pools** or **Active work order pools**).</span></span>

1. <span data-ttu-id="168a8-111">Cliquez sur **Gestion des actifs** > **Recherches** > **Prévision d'article** ou **Gestion des actifs** > **Commun** > **Regroupements d'ordres de travail** > **Tous les regroupements d'ordres de travail** / **Regroupements d'ordres de travail actifs** > sélectionnez le regroupement d'ordres de travail dans la liste > cliquez sur le bouton **Prévision d'article** ou **Gestion des actifs** > **Commun** > **Activités de temps d'arrêt pour maintenance** > **Toutes les activités de temps d'arrêt pour maintenance** / **Activités de temps d'arrêt pour maintenance actifs** > sélectionnez l'activité de temps d'arrêt pour maintenance dans la liste > cliquez sur le bouton **Prévision d'article**.</span><span class="sxs-lookup"><span data-stu-id="168a8-111">Click **Asset management** > **Inquiries** > **Item forecast**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Item forecast** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance downtime activity in the list > **Item forecast** button.</span></span>

2. <span data-ttu-id="168a8-112">Dans la boîte de dialogue **Calculer les prévisions en matière d'articles**, sélectionnez une période de calcul dans les champs **Date et heure de début** et **Date et heure de fin**.</span><span class="sxs-lookup"><span data-stu-id="168a8-112">In the **Calculate item forecast** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="168a8-113">Sélectionnez « Oui » sur le bouton bascule **Inclure le programme de maintenance** pour inclure les lignes du programme de maintenance dans le calcul des prévisions.</span><span class="sxs-lookup"><span data-stu-id="168a8-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the forecast calculation.</span></span>

4. <span data-ttu-id="168a8-114">Sélectionnez « Oui » sur le bouton bascule **Inclure l'ordre de travail** pour inclure les tâches d'ordre de travail dans le calcul des prévisions.</span><span class="sxs-lookup"><span data-stu-id="168a8-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the forecast calculation.</span></span>

5. <span data-ttu-id="168a8-115">Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de prévision d'article en fonction des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="168a8-115">You can use the **Level** field to indicate how detailed you want the item forecast lines to be regarding functional locations.</span></span> 

      <span data-ttu-id="168a8-116">Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes du programme de maintenance et les ordres de travail pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter des heures sur une ligne à partir des postes techniques situés à un niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="168a8-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
  
      <span data-ttu-id="168a8-117">Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes du programme de maintenance et tous les ordres de travail sur tous les niveaux du poste technique auquel elles sont liées.</span><span class="sxs-lookup"><span data-stu-id="168a8-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="168a8-118">Cliquez sur **OK** pour démarrer le calcul.</span><span class="sxs-lookup"><span data-stu-id="168a8-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="168a8-119">Dans les groupes **Grouper par…**, cliquez sur les boutons appropriés à afficher le niveau requis de détail du calcul.</span><span class="sxs-lookup"><span data-stu-id="168a8-119">In the **Group by...** groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="168a8-120">Dans le capture d'écran ci-dessous, les boutons **Grouper par** sélectionnés sont mis en surbrillance en bleu.</span><span class="sxs-lookup"><span data-stu-id="168a8-120">In the screenshot below, the selected **Group by** buttons are highlighted in blue color.</span></span> <span data-ttu-id="168a8-121">Cliquez sur un bouton pour l'activer ou le désactiver.</span><span class="sxs-lookup"><span data-stu-id="168a8-121">Click on a button to activate or deactivate it.</span></span>

8. <span data-ttu-id="168a8-122">Cliquez sur le bouton **Afficher les dimensions** si vous souhaitez afficher le produit, le stockage, ou les dimensions de suivi associées aux articles.</span><span class="sxs-lookup"><span data-stu-id="168a8-122">Click the **Display dimensions** button if you want to see the product, storage, or tracking dimensions related to the items.</span></span> <span data-ttu-id="168a8-123">Cliquez sur la case à cocher appropriée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="168a8-123">Select the relevant check boxes, and click **OK**.</span></span>

![Figure 1](media/02-capacity-planning.png)
