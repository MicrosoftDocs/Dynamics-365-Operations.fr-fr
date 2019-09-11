---
title: Statut de maintenance
description: Cette rubrique explique comment calculer le statut de maintenance dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 516607c056125a16e075c33f3c2ad069efb396d9
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918347"
---
# <a name="maintenance-status"></a><span data-ttu-id="3681e-103">Statut de maintenance</span><span class="sxs-lookup"><span data-stu-id="3681e-103">Maintenance status</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="3681e-104">Dans le module Gestion des actifs, vous pouvez effectuer un calcul pour obtenir une vue d'ensemble des demandes de maintenance et des ordres de travail inédits, actifs et terminés et des activités des temps d'arrêt pour maintenance pour une période donnée.</span><span class="sxs-lookup"><span data-stu-id="3681e-104">In Asset Management, you can make a calculation to see an overview of new, active, and completed maintenance requests, work orders, and maintenance downtime activities for a specific period.</span></span> <span data-ttu-id="3681e-105">Vous pouvez également voir le nombre des évaluations des conditions terminées pour la même période.</span><span class="sxs-lookup"><span data-stu-id="3681e-105">You can also see the number of completed condition assessments for the same period.</span></span> <span data-ttu-id="3681e-106">Utilisez ce calcul pour obtenir une vue d'ensemble de la charge de travail concernant les demandes de maintenance et les ordres de travail entrants et terminés.</span><span class="sxs-lookup"><span data-stu-id="3681e-106">Use this calculation to get an overview of workload regarding incoming and completed maintenance requests and work orders.</span></span>

## <a name="make-a-maintenance-status-calculation"></a><span data-ttu-id="3681e-107">Effectuer un calcul du statut de maintenance</span><span class="sxs-lookup"><span data-stu-id="3681e-107">Make a maintenance status calculation</span></span>

1. <span data-ttu-id="3681e-108">Cliquez sur **Gestion des actifs** > **Recherches** > **Statut de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="3681e-108">Click **Asset management** > **Inquiries** > **Maintenance status**.</span></span>

2. <span data-ttu-id="3681e-109">Dans la boîte de dialogue **Calculer le statut**, sélectionnez la période pendant laquelle vous souhaitez faire le calcul dans les champs **Du** et **Au**.</span><span class="sxs-lookup"><span data-stu-id="3681e-109">In the **Calculate status** dialog, select the period for which you want to make the calculation in the **From date** and **To date** fields.</span></span>

3. <span data-ttu-id="3681e-110">Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de maintenance en fonction des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="3681e-110">You can use the **Level** field to indicate how detailed you want the maintenance lines to be regarding functional locations.</span></span> <span data-ttu-id="3681e-111">Par exemple, si vous insérez le chiffre « 1 » dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes de maintenance pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter le statut sur une ligne à partir des postes techniques situés à un niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="3681e-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance lines for a functional location will be shown on the top level, and therefore the status on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="3681e-112">Par exemple, si vous insérez le chiffre « 0 » dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes de maintenance sur tous les niveaux du poste technique auxquels elles sont liées.</span><span class="sxs-lookup"><span data-stu-id="3681e-112">If you insert the number "0" in the **Level** field, you see a detailed result showing all maintenance lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="3681e-113">Cliquez sur **OK** pour démarrer le calcul.</span><span class="sxs-lookup"><span data-stu-id="3681e-113">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="3681e-114">Dans les groupes de volet Actions **Grouper par…**, cliquez sur les boutons appropriés à afficher le niveau requis de détail du calcul.</span><span class="sxs-lookup"><span data-stu-id="3681e-114">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="3681e-115">Les boutons sélectionnés du volet Actions sont mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="3681e-115">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="3681e-116">Cliquez sur un bouton pour l'activer ou le désactiver.</span><span class="sxs-lookup"><span data-stu-id="3681e-116">Click on a button to activate or deactivate it.</span></span>

6. <span data-ttu-id="3681e-117">N'oubliez pas de cliquer sur le bouton **Mettre à jour** pour mettre le calcul à jour chaque fois que vous apportez des modifications en activant ou en désactivant les boutons **Regrouper par…**, ou en choisissant un calcul pour une nouvelle période.</span><span class="sxs-lookup"><span data-stu-id="3681e-117">Remember to click the **Update** button to update the calculation each time you make changes by activating or deactivating **Group by...** buttons, or by making a calculation for a new period.</span></span>

7. <span data-ttu-id="3681e-118">Cliquez sur **Statut** si vous souhaitez créer un nouveau calcul de statut de maintenance.</span><span class="sxs-lookup"><span data-stu-id="3681e-118">Click **Status** if you want to create a new maintenance status calculation.</span></span>

>[!NOTE]
><span data-ttu-id="3681e-119">Les résultats affichés dans **Statut de maintenance** incluent uniquement les demandes de maintenance et les ordres de travail ayant une date et une heure de début réelles.</span><span class="sxs-lookup"><span data-stu-id="3681e-119">The results shown in **Maintenance status** only include maintenance requests and work orders that have an actual start date and time.</span></span> <span data-ttu-id="3681e-120">La date de fin peut être vide.</span><span class="sxs-lookup"><span data-stu-id="3681e-120">End date and time may be blank.</span></span>

<span data-ttu-id="3681e-121">*Exemple 1 :*</span><span class="sxs-lookup"><span data-stu-id="3681e-121">*Example 1:*</span></span>

<span data-ttu-id="3681e-122">Dans le graphique ci-dessous, les boutons **Année** et **Mois** ont été actionnés.</span><span class="sxs-lookup"><span data-stu-id="3681e-122">In the figure below, the **Year** and **Month** buttons have been activated.</span></span> <span data-ttu-id="3681e-123">Ici, vous obtenez une vue d'ensemble générale sur une base mensuelle de charge de travail et le débit associé aux demandes de maintenance et aux ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="3681e-123">Here, you get a general overview on a monthly basis of workload and throughput related to maintenance requests and work orders.</span></span> 

![Figure 1](media/13-controlling-and-reporting.png)

<span data-ttu-id="3681e-125">*Exemple 2 :*</span><span class="sxs-lookup"><span data-stu-id="3681e-125">*Example 2:*</span></span>

<span data-ttu-id="3681e-126">Dans la figure ci-dessous, les informations concernant les postes techniques ont été ajoutées.</span><span class="sxs-lookup"><span data-stu-id="3681e-126">In the figure below, information about functional locations has been added.</span></span> <span data-ttu-id="3681e-127">À présent, il est possible de comparer la charge de travail et le débit entre les postes techniques, qui peuvent représenter les emplacements géographiques, les usines ou les espaces de travail.</span><span class="sxs-lookup"><span data-stu-id="3681e-127">Now, it is possible to compare workload and throughput across functional locations, which may represent geographical locations, factories, or work areas.</span></span> 

![Figure 2](media/14-controlling-and-reporting.png)

