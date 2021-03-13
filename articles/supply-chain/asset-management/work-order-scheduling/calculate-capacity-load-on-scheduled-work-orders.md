---
title: Calculer la charge maximale sur les ordres de travail planifiés
description: Cette rubrique explique comment calculer la charge maximale sur les ordres de travail planifiés dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7b7e4a20ed56b1eac29d16d527693d6e455cdc37
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021652"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a><span data-ttu-id="81963-103">Calculer la charge maximale sur les ordres de travail planifiés</span><span class="sxs-lookup"><span data-stu-id="81963-103">Calculate capacity load on scheduled work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="81963-104">Vous pouvez calculer la charge maximale sur les ordres de travail planifiés pour obtenir une vue d'ensemble de la charge de travail sur les ressources pour une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="81963-104">You can calculate capacity load on scheduled work orders to get an overview of the work load on resources for a specific period.</span></span> <span data-ttu-id="81963-105">Les calculs peuvent être effectués pour les ressources suivantes : agents de maintenance, groupes de collaborateurs, outils et actifs.</span><span class="sxs-lookup"><span data-stu-id="81963-105">Calculations can be made for the following resources: Maintenance workers, worker groups, tools, and assets.</span></span>

1. <span data-ttu-id="81963-106">Cliquez sur **Gestion des actifs** > **Recherches** > **Planification** > **Charge maximale**.</span><span class="sxs-lookup"><span data-stu-id="81963-106">Click **Asset management** > **Inquiries** > **Schedule** > **Capacity load**.</span></span>

2. <span data-ttu-id="81963-107">Dans la boîte de dialogue **Calculer la charge maximale** > champ **Afficher**, sélectionnez le type de charge à calculer : **Capacité**, **Réservé** ou **Solde**.</span><span class="sxs-lookup"><span data-stu-id="81963-107">In the **Calculate capacity load** dialog > **Show** field, select which load type you want to calculate: **Capacity**, **Reserved**, or **Remainder**.</span></span>

3. <span data-ttu-id="81963-108">Sélectionnez **Oui** sur le bouton bascule **Ignorer lignes nulles** si vous ne souhaitez pas afficher les résultats à zéro.</span><span class="sxs-lookup"><span data-stu-id="81963-108">Select **Yes** on the **Skip zero** toggle button if you do not want to show results containing zero.</span></span>

4. <span data-ttu-id="81963-109">Sélectionnez les types de ressources pour lesquels vous souhaitez calculer la charge maximale en sélectionnant **Oui** sur les boutons bascule appropriés : **Collaborateur**, **Groupe d'agents de maintenance**, **Outil** et **Actif**.</span><span class="sxs-lookup"><span data-stu-id="81963-109">Select the resource types for which you want to calculate capacity load by selecting **Yes** on the relevant toggle buttons: **Worker**, **Maintenance worker group**, **Tool**, and **Asset**.</span></span>

5. <span data-ttu-id="81963-110">Sélectionnez la date de début pour le calcul dans le champ **Date de début**.</span><span class="sxs-lookup"><span data-stu-id="81963-110">Select the start date for the calculation in the **From date** field.</span></span>

6. <span data-ttu-id="81963-111">Dans le champ **Type d'intervalle**, sélectionnez l'intervalle pour le calcul : **Jour**, **Semaine**, **Mois** ou **Trimestre**.</span><span class="sxs-lookup"><span data-stu-id="81963-111">In the **Interval type** field, select the interval for the calculation: **Day**, **Week**, **Month**, or **Quarter**.</span></span>

7. <span data-ttu-id="81963-112">Dans le champ **Fréquence**, insérez le nombre d'intervalles que vous souhaitez calculer.</span><span class="sxs-lookup"><span data-stu-id="81963-112">In the **Period frequency** field, insert the number of intervals you want to calculate.</span></span> <span data-ttu-id="81963-113">Par exemple, si vous avez sélectionné **Jour** comme type d'intervalle, et que vous entrez le chiffre « 5 » dans ce champ, un calcul sur cinq jours à compter de la date de début est effectué.</span><span class="sxs-lookup"><span data-stu-id="81963-113">For example, if you have selected **Day** as the interval type, and you enter the number "5" in this field, a calculation of five days from the start date will be made.</span></span>

8. <span data-ttu-id="81963-114">Cliquez sur **OK** pour démarrer le calcul.</span><span class="sxs-lookup"><span data-stu-id="81963-114">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="81963-115">L'illustration ci-dessous indique le résultat d'un calcul sur trois semaines pour le type de charge **Réservé**.</span><span class="sxs-lookup"><span data-stu-id="81963-115">The figure below shows the result of a calculation covering three weeks for the load type **Reserved**.</span></span>

![Figure 1](media/08-work-order-scheduling.png)

[!NOTE]
<span data-ttu-id="81963-117">Si vous sélectionnez les types de charge **Capacité** ou **Solde** pour votre calcul, le même résultat sera affiché si aucune réservation n'est effectuée pour les ressources dans la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81963-117">If you select the load types **Capacity** or **Remainder** for your calculation, the same result will be displayed if no reservations have been made for the resources in the selected period.</span></span>

<span data-ttu-id="81963-118">Pour plus d'informations sur le calcul de la charge maximale sur les lignes du programme de maintenance et non sur les ordres de travail planifiés, reportez-vous à [Calculer la charge maximale](../capacity-planning/calculate-capacity-load.md).</span><span class="sxs-lookup"><span data-stu-id="81963-118">For information about how to calculate capacity load on maintenance schedule lines and not scheduled work orders, refer to [Calculate capacity load](../capacity-planning/calculate-capacity-load.md).</span></span>

