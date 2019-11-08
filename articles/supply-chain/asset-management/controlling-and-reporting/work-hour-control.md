---
title: Contrôle de temps de travail
description: Cette rubrique explique le contrôle de temps de travail dans le module Gestion des actifs.
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
ms.openlocfilehash: 1a59b4bbf1a4612cea1ba3bd536ba4b018fc621f
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652331"
---
# <a name="work-hour-control"></a><span data-ttu-id="6f96c-103">Contrôle de temps de travail</span><span class="sxs-lookup"><span data-stu-id="6f96c-103">Work hour control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="6f96c-104">Dans le module Gestion des actifs, vous pouvez calculer des heures pour obtenir une vue d'ensemble des heures réelles comparées aux heures budgétaires des actifs, des postes techniques ou des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="6f96c-104">In Asset Management, you can calculate hours to get an overview of actual hours compared to budget hours on assets, functional locations, or work orders.</span></span> <span data-ttu-id="6f96c-105">Les heures réelles sont basées sur des transactions validées.</span><span class="sxs-lookup"><span data-stu-id="6f96c-105">Actual hours are based on posted transactions.</span></span>

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="6f96c-106">Contrôle des heures de travail pour des actifs, des postes techniques et des ordres de travail</span><span class="sxs-lookup"><span data-stu-id="6f96c-106">Work hour control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="6f96c-107">Les calculs effectués pour les actifs, les postes techniques et les ordres de travail sont quasiment identiques.</span><span class="sxs-lookup"><span data-stu-id="6f96c-107">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="6f96c-108">L'unique différence réside dans le fait que pour les actifs et les postes techniques, vous pouvez également inclure les sous-actifs et les sous-postes dans votre calcul.</span><span class="sxs-lookup"><span data-stu-id="6f96c-108">Only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="6f96c-109">La date est la date de transaction à laquelle l'enregistrement a été enregistré.</span><span class="sxs-lookup"><span data-stu-id="6f96c-109">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="6f96c-110">Cliquez sur **Gestion des actifs** > **Recherches** > **Actifs** > **Contrôle des heures d'actif** ou **Contrôle des heures du poste technique** ou **Gestion des actifs** > **Recherches** > **Ordres de travail** > **Contrôle des heures des ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="6f96c-110">Click **Asset management** > **Inquiries** > **Assets** > **Asset hour control** or **Functional location hour control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order hour control**.</span></span>

2. <span data-ttu-id="6f96c-111">Dans la boîte de dialogue **Contrôle des heures de l'actif**.</span><span class="sxs-lookup"><span data-stu-id="6f96c-111">In the **Asset hour control** dialog, .</span></span>

3. <span data-ttu-id="6f96c-112">Dans la boîte de dialogue **Contrôle des heures d'actif** / **Contrôle des heures de poste technique** / **Contrôle des heures de l'ordre de travail**, sélectionnez une période à calculer dans les champs **Date de début** et **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="6f96c-112">In the **Asset hour control** / **Functional location hour control** / **Work order hour control** dialog, select a period to be calculated in the **From date** and **To date** fields.</span></span>

4. <span data-ttu-id="6f96c-113">Si nécessaire, sélectionnez un **ensemble de dimensions financières** à inclure dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="6f96c-113">If required, select a **Financial dimension set** to be included in the calculation.</span></span>

5. <span data-ttu-id="6f96c-114">Sélectionnez « Oui » sur le bouton bascule **Ignorer lignes nulles** si vous ne souhaitez pas afficher les résultats ne contenant pas d'heure.</span><span class="sxs-lookup"><span data-stu-id="6f96c-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results containing zero hours.</span></span>

6. <span data-ttu-id="6f96c-115">Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de contrôle des heures en fonction des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="6f96c-115">You can use the **Level** field to indicate how detailed you want the hour control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="6f96c-116">Par exemple, si vous insérez le chiffre « 1 » dans le champ, et que vous avez une hiérarchie de postes techniques à plusieurs niveaux, toutes les lignes de contrôle des heures pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter les heures sur une ligne à partir des postes techniques situés à un niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="6f96c-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all hour control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="6f96c-117">Par exemple, si vous insérez le chiffre « 0 » dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes de contrôle des heures sur tous les niveaux du poste technique auxquels elles sont liées.</span><span class="sxs-lookup"><span data-stu-id="6f96c-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all hour control lines on all the functional location levels to which they are related.</span></span>

7. <span data-ttu-id="6f96c-118">Sélectionnez « Oui » sur le bouton à bascule **Inclure les sous-actifs** pour afficher les coûts associés aux sous-actifs comme lignes distinctes.</span><span class="sxs-lookup"><span data-stu-id="6f96c-118">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="6f96c-119">Pour limiter la recherche, vous pouvez sélectionner des actifs/postes techniques/ordres de travail sur l'organisateur **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="6f96c-119">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="6f96c-120">Cliquez sur **OK** pour démarrer le calcul.</span><span class="sxs-lookup"><span data-stu-id="6f96c-120">Click **OK** to start the calculation.</span></span>

10. <span data-ttu-id="6f96c-121">Sur la page **Contrôle des heures de l'actif**, cliquez sur le bouton **Grouper par**, cliquez sur les boutons appropriés à afficher le niveau requis de détail du calcul.</span><span class="sxs-lookup"><span data-stu-id="6f96c-121">On the **Asset hour control** page, click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="6f96c-122">Les boutons **Grouper par** sélectionnés sont mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="6f96c-122">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="6f96c-123">Cliquez sur un bouton pour l'activer ou le désactiver.</span><span class="sxs-lookup"><span data-stu-id="6f96c-123">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="6f96c-124">Exemple</span><span class="sxs-lookup"><span data-stu-id="6f96c-124">Example</span></span>

<span data-ttu-id="6f96c-125">La capture d'écran suivante présente un exemple de calcul de **contrôle des heures d'actif**.</span><span class="sxs-lookup"><span data-stu-id="6f96c-125">The screenshot below shows an example of an **Asset hour control** calculation.</span></span>

- <span data-ttu-id="6f96c-126">Le champ **Budget d'origine** indique les heures budgétaires à partir des prévisions de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="6f96c-126">The **Original budget** field shows budget hours from the work order forecast.</span></span> 
- <span data-ttu-id="6f96c-127">Le champ **Heures réelles** indique les heures validées sur les ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="6f96c-127">The **Actual hours** field shows posted hours on work orders.</span></span> 
- <span data-ttu-id="6f96c-128">Le champ **Heures engagées** indique les totaux horaires dans lesquels votre société s'engage en termes d'ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="6f96c-128">The **Committed hours** field shows total amount of hours that your company is committed to in relation to work orders.</span></span>

![Exemple de calcul de contrôle des heures de l'actif](media/04-controlling-and-reporting.png)

<span data-ttu-id="6f96c-130">Une autre manière d'effectuer un calcul d'heures est de choisir plusieurs actifs dans **Tous les actifs** ou **Actifs actifs**.</span><span class="sxs-lookup"><span data-stu-id="6f96c-130">Another way of making an hour calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="6f96c-131">Ensuite vous cliquez sur le bouton **Contrôle d'heure** sur l'organisateur **Général**.</span><span class="sxs-lookup"><span data-stu-id="6f96c-131">Then you click the **Hour control** button on the **General** FastTab.</span></span> <span data-ttu-id="6f96c-132">Les actifs sélectionnés sont insérés automatiquement dans le champ **Actif** sur l'organisateur **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="6f96c-132">The selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="6f96c-133">Cliquez sur **OK** dans la boîte de dialogue **Contrôle des heures d'actif**, et le calcul pour les actifs sélectionnés s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6f96c-133">Click **OK** in the **Asset hour control** dialog, and the calculation for the selected assets is shown.</span></span> <span data-ttu-id="6f96c-134">La même procédure peut être effectuée pour les postes techniques dans **Tous les postes techniques** ou **Postes techniques actifs**, et pour les ordres de travail dans **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="6f96c-134">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>


