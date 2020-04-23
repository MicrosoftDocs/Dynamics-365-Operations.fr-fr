---
title: Statut de maintenance
description: Cette rubrique explique comment calculer le statut de maintenance dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
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
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fbe2b3fd9ce63c34aedb790583dea572d3d9b079
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205466"
---
# <a name="maintenance-status"></a><span data-ttu-id="414e9-103">Statut de maintenance</span><span class="sxs-lookup"><span data-stu-id="414e9-103">Maintenance status</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="414e9-104">Dans le module Gestion des actifs, vous pouvez effectuer un calcul de vue d'ensemble pendant une période spécifique des demandes de maintenance et des ordres de travail inédits, actifs et terminés, et des activités des temps d'arrêt pour maintenance.</span><span class="sxs-lookup"><span data-stu-id="414e9-104">In Asset Management, you can make an overview calculation for a specific period for new, active, and completed maintenance requests, work orders, and maintenance downtime activities.</span></span> <span data-ttu-id="414e9-105">Vous pouvez également voir le nombre des évaluations des conditions terminées pour la même période.</span><span class="sxs-lookup"><span data-stu-id="414e9-105">You can also see the number of completed condition assessments for the same period.</span></span> <span data-ttu-id="414e9-106">Utilisez ce calcul pour obtenir une vue d'ensemble de la charge de travail pour les demandes de maintenance et les ordres de travail entrants et terminés.</span><span class="sxs-lookup"><span data-stu-id="414e9-106">Use this calculation to get an overview of workload for incoming and completed maintenance requests and work orders.</span></span>

## <a name="make-a-maintenance-status-calculation"></a><span data-ttu-id="414e9-107">Effectuer un calcul du statut de maintenance</span><span class="sxs-lookup"><span data-stu-id="414e9-107">Make a maintenance status calculation</span></span>

1. <span data-ttu-id="414e9-108">Cliquez sur **Gestion des actifs** > **Recherches** > **Statut de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="414e9-108">Click **Asset management** > **Inquiries** > **Maintenance status**.</span></span>

2. <span data-ttu-id="414e9-109">Dans la boîte de dialogue **Calculer le statut**, sélectionnez la plage horaire pendant laquelle vous souhaitez faire le calcul dans les champs **Du** et **Au**.</span><span class="sxs-lookup"><span data-stu-id="414e9-109">In the **Calculate status** dialog, select the time range that you want to make the calculation in the **From date** and **To date** fields.</span></span>

3. <span data-ttu-id="414e9-110">Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de maintenance en fonction des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="414e9-110">You can use the **Level** field to indicate how detailed you want the maintenance lines to be regarding functional locations.</span></span> 

  <span data-ttu-id="414e9-111">Par exemple, si vous insérez le chiffre « 1 » dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes de maintenance pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter le statut sur une ligne à partir des postes techniques situés à un niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="414e9-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance lines for a functional location will be shown on the top level, and therefore the status on a line may be added up from functional locations located at a lower level.</span></span> 
  
  <span data-ttu-id="414e9-112">Par exemple, si vous insérez le chiffre « 0 » dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes de maintenance sur tous les niveaux du poste technique auxquels elles sont liées.</span><span class="sxs-lookup"><span data-stu-id="414e9-112">If you insert the number "0" in the **Level** field, you see a detailed result showing all maintenance lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="414e9-113">Cliquez sur **OK** pour démarrer le calcul.</span><span class="sxs-lookup"><span data-stu-id="414e9-113">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="414e9-114">Cliquez sur les boutons **Grouper par** pour afficher le niveau requis de détail du calcul.</span><span class="sxs-lookup"><span data-stu-id="414e9-114">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="414e9-115">Les boutons **Grouper par** sélectionnés sont mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="414e9-115">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="414e9-116">Cliquez sur un bouton pour l'activer ou le désactiver.</span><span class="sxs-lookup"><span data-stu-id="414e9-116">Click on a button to activate or deactivate it.</span></span>

6. <span data-ttu-id="414e9-117">N'oubliez pas de cliquer sur le bouton **Mettre à jour** pour mettre le calcul à jour chaque fois que vous apportez des modifications en activant ou en désactivant les boutons **Grouper par**, ou en choisissant un calcul pour une nouvelle période.</span><span class="sxs-lookup"><span data-stu-id="414e9-117">Remember to click the **Update** button to update the calculation each time you make changes by activating or deactivating **Group by** buttons, or by making a calculation for a new period.</span></span>

7. <span data-ttu-id="414e9-118">Cliquez sur **Statut** si vous souhaitez créer un nouveau calcul de statut de maintenance.</span><span class="sxs-lookup"><span data-stu-id="414e9-118">Click **Status** if you want to create a new maintenance status calculation.</span></span>

>[!NOTE]
><span data-ttu-id="414e9-119">Les résultats affichés dans **Statut de maintenance** incluent uniquement les demandes de maintenance et les ordres de travail ayant une date et une heure de début réelles.</span><span class="sxs-lookup"><span data-stu-id="414e9-119">The results shown in **Maintenance status** only include maintenance requests and work orders that have an actual start date and time.</span></span> <span data-ttu-id="414e9-120">La date de fin peut être vide.</span><span class="sxs-lookup"><span data-stu-id="414e9-120">End date and time may be blank.</span></span>

## <a name="example-1"></a><span data-ttu-id="414e9-121">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="414e9-121">Example 1</span></span>

<span data-ttu-id="414e9-122">Dans la capture d'écran ci-dessous, les boutons **Année** et **Mois** ont été actionnés.</span><span class="sxs-lookup"><span data-stu-id="414e9-122">In the screenshot below, the **Year** and **Month** buttons have been activated.</span></span> <span data-ttu-id="414e9-123">Avec ces options **Grouper par** sélectionnées, vous obtenez une vue d'ensemble générale sur une base mensuelle de charge de travail et le débit associé aux demandes de maintenance et aux ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="414e9-123">With these **Group by** options selected, you get a general overview on a monthly basis of workload and throughput related to maintenance requests and work orders.</span></span> 

![Exemple de charge de travail mensuelle](media/13-controlling-and-reporting.png)

## <a name="example-2"></a><span data-ttu-id="414e9-125">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="414e9-125">Example 2</span></span>

<span data-ttu-id="414e9-126">Dans la capture d'écran ci-dessous, les informations concernant les postes techniques ont été ajoutées.</span><span class="sxs-lookup"><span data-stu-id="414e9-126">In the screenshot below, information about functional locations has been added.</span></span> <span data-ttu-id="414e9-127">À présent il est possible de comparer la charge de travail et le débit entre les postes techniques, qui peuvent représenter les emplacements géographiques, les usines ou les espaces de travail.</span><span class="sxs-lookup"><span data-stu-id="414e9-127">Now it is possible to compare workload and throughput across functional locations, which may represent geographical locations, factories, or work areas.</span></span> 

![Exemple de charge de travail mensuelle avec des postes techniques](media/14-controlling-and-reporting.png)

