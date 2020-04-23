---
title: Coût du programme de maintenance
description: Cette rubrique explique le coût du programme de maintenance dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
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
ms.openlocfilehash: 8feea75bb223bdbd013b11cdf3a63d504afb04f5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208200"
---
# <a name="maintenance-schedule-cost"></a><span data-ttu-id="03177-103">Coût du programme de maintenance</span><span class="sxs-lookup"><span data-stu-id="03177-103">Maintenance schedule cost</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="03177-104">Dans le module Gestion des actifs, vous pouvez calculer les coûts budgétaires sur les lignes du programme de maintenance.</span><span class="sxs-lookup"><span data-stu-id="03177-104">In Asset Management, you can calculate budget costs on maintenance schedule lines.</span></span> <span data-ttu-id="03177-105">Cela est utile si vous souhaitez obtenir une vue d'ensemble des coûts prévisionnels, par exemple, les coûts associés aux tâches de maintenance préventive planifiées pour l'an prochain.</span><span class="sxs-lookup"><span data-stu-id="03177-105">This is useful if you want to get an overview of expected costs, for example, costs relating to planned preventive maintenance jobs for the next year.</span></span> <span data-ttu-id="03177-106">Les calculs sont basés sur les lignes de programme de maintenance du type « Plans de maintenance » et « Visites de maintenance » et « Demandes de maintenance ».</span><span class="sxs-lookup"><span data-stu-id="03177-106">The calculations are based on existing maintenance schedule lines of type "Maintenance plans" and "Maintenance rounds" and "Maintenance requests".</span></span>

1. <span data-ttu-id="03177-107">Cliquez sur **Gestion des actifs** > **Recherches** > **Actifs** > **Coût du programme de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="03177-107">Click **Asset management** > **Inquiries** > **Assets** > **Maintenance schedule cost**.</span></span>

2. <span data-ttu-id="03177-108">Dans la boîte de dialogue **Coût du programme de maintenance**, vous pouvez sélectionner un **Ensemble de dimensions financières** si vous souhaitez afficher les coûts regroupés dans les dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="03177-108">In the **Maintenance schedule cost** dialog, you can select a **Financial dimension set** if you want to see costs grouped in financial dimensions.</span></span>

>[!NOTE]
><span data-ttu-id="03177-109">Les ensembles de dimensions financières sont paramétrés dans **Comptabilité générale** > **Plan de comptes** > **Dimensions** > **Ensembles de dimensions financières**.</span><span class="sxs-lookup"><span data-stu-id="03177-109">Financial dimension sets are set up in **General ledger** > **Chart of accounts** > **Dimensions** > **Financial dimension sets**.</span></span>

3. <span data-ttu-id="03177-110">Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes du programme de maintenance en fonction des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="03177-110">You can use the **Level** field to indicate how detailed you want the maintenance schedule lines to be regarding functional locations.</span></span> <span data-ttu-id="03177-111">Par exemple, si vous insérez le chiffre « 1 » dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes du programme de maintenance pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter des heures sur une ligne à partir des postes techniques situés à un niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="03177-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="03177-112">Par exemple, si vous insérez le chiffre « 0 » dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes du programme de maintenance sur tous les niveaux du poste technique auxquels ils sont liés.</span><span class="sxs-lookup"><span data-stu-id="03177-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="03177-113">Si vous souhaitez effectuer un calcul pour les actifs spécifiques, cliquez sur **Filtre** sur l'organisateur **Enregistrements à inclure**, et sélectionnez les actifs appropriés.</span><span class="sxs-lookup"><span data-stu-id="03177-113">If you want to make a calculation for specific assets, click **Filter** on the **Records to include** FastTab, and select the relevant assets.</span></span> <span data-ttu-id="03177-114">Si nécessaire, vous pouvez également spécifier une date de **Début prévu** pour le calcul du coût ou sélectionner un autre **Statut** pour le calcul du coût</span><span class="sxs-lookup"><span data-stu-id="03177-114">If required, you can also specify an **Expected start** date for the cost calculation or select a different **Status** for the cost calculation</span></span>

5. <span data-ttu-id="03177-115">Cliquez sur **OK** pour démarrer le calcul des coûts.</span><span class="sxs-lookup"><span data-stu-id="03177-115">Click **OK** to start the cost calculation.</span></span>

6. <span data-ttu-id="03177-116">Sur l'onglet **Coût du programme de maintenance** des groupes du volet d'action **Regrouper par…**, cliquez sur les boutons appropriés pour afficher le niveau requis de détail du calcul des coûts.</span><span class="sxs-lookup"><span data-stu-id="03177-116">On the **Maintenance schedule cost** tab > in the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the cost calculation.</span></span> <span data-ttu-id="03177-117">Les boutons sélectionnés du groupe du volet Actions sont mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="03177-117">The selected action pane group buttons are highlighted.</span></span> <span data-ttu-id="03177-118">Cliquez sur un bouton pour l'activer ou le désactiver.</span><span class="sxs-lookup"><span data-stu-id="03177-118">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="03177-119">Cliquez sur le bouton **Calculez le coût** si vous souhaitez effectuer un nouveau calcul des coûts.</span><span class="sxs-lookup"><span data-stu-id="03177-119">Click the **Calculate cost** button if you want to make a new cost calculation.</span></span>

<span data-ttu-id="03177-120">L'illustration ci-dessous affiche les résultats d'un calcul de coût du programme de maintenance.</span><span class="sxs-lookup"><span data-stu-id="03177-120">The illustration below shows the results of a maintenance schedule cost calculation.</span></span>

![Figure 1](media/17-preventive-maintenance.png)

