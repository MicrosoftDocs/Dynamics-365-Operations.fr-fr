---
title: Exécution planifiée
description: Cette rubrique explique l'exécution planifiée dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
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
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 976155b685498456952f7d715779d20191712103
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215514"
---
# <a name="scheduled-execution"></a><span data-ttu-id="1331c-103">Exécution planifiée</span><span class="sxs-lookup"><span data-stu-id="1331c-103">Scheduled execution</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="1331c-104">Vous pouvez utiliser les niveaux de service de l'ordre de travail pour configurer l'exécution planifiée.</span><span class="sxs-lookup"><span data-stu-id="1331c-104">You can use work order service levels to set up scheduled execution.</span></span> <span data-ttu-id="1331c-105">(Pour plus d'informations sur les niveaux de service de l'ordre de travail, consultez [Niveau de service et description](service-level-and-description.md).) L'exécution planifiée fournit la flexibilité de la planification du travail pour les agents de maintenance, car vous pouvez paramétrer des exigences plus ou moins détaillées pour l'intervalle pendant lequel un ordre de travail doit être effectué.</span><span class="sxs-lookup"><span data-stu-id="1331c-105">(For more information about work order service levels, see [Service level and description](service-level-and-description.md).) Scheduled execution provides flexibility in work planning for maintenance workers, because you can set up more detailed or less detailed requirements for the interval that a work order should be completed during.</span></span> <span data-ttu-id="1331c-106">Par exemple, un agent de maintenance qui exécute une tâche plus rapidement que prévue dans un site de production peut être en mesure de passer à une autre tâche à proximité planifiée pour la semaine actuelle, mais pas nécessairement pour le jour actuel.</span><span class="sxs-lookup"><span data-stu-id="1331c-106">For example, a maintenance worker who completes a job faster than expected in a production facility might be able to move on to another nearby job that was planned for the current week but not necessarily for the current day.</span></span> <span data-ttu-id="1331c-107">Cette approche permet l'optimisation de la planification de l'agent et de l'exécution de la tâche.</span><span class="sxs-lookup"><span data-stu-id="1331c-107">This approach allows for optimization of worker planning and job completion.</span></span>

<span data-ttu-id="1331c-108">La configuration de l'exécution planifiée, qui est associée aux ordres de travail, peut être générique ou spécifique.</span><span class="sxs-lookup"><span data-stu-id="1331c-108">Scheduled execution setup, which is related to work orders, can be generic or specific.</span></span> <span data-ttu-id="1331c-109">Vous pouvez paramétrer les lignes génériques qui ne sont pas limitées aux types d'ordre de travail, types d'actif spécifiques, etc.</span><span class="sxs-lookup"><span data-stu-id="1331c-109">You can set up generic lines that aren't limited to specific work order types, asset types, and so on.</span></span> <span data-ttu-id="1331c-110">Sinon, vous pouvez créer des lignes d'exécution planifiées qui s'appliquent à un type d'ordre de travail, type d'actif, type de tâche de maintenance spécifique, etc.</span><span class="sxs-lookup"><span data-stu-id="1331c-110">Alternatively, you can create scheduled execution lines that apply to a specific work order type, asset type, maintenance job type, and so on.</span></span>

1. <span data-ttu-id="1331c-111">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **Exécution planifiée**.</span><span class="sxs-lookup"><span data-stu-id="1331c-111">Select **Asset management** \> **Setup** \> **Work orders** \> **Scheduled execution**.</span></span>
2. <span data-ttu-id="1331c-112">Sélectionnez **Nouveau** pour créer une ligne d'exécution planifiée.</span><span class="sxs-lookup"><span data-stu-id="1331c-112">Select **New** to create a scheduled execution line.</span></span>
3. <span data-ttu-id="1331c-113">Dans les champs **Poste technique**, **Type d'ordre d'exécution**, **Type d'actif**, **Fabricant**, **Modèle**, **Catégorie du type de tâche de maintenance**, **Type de tâche de maintenance**, **Variante du type de tâche de maintenance** et **Transaction**, sélectionnez les valeurs telles que vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="1331c-113">In the **Functional location**, **Work order type**, **Asset type**, **Manufacturer**, **Model**, **Maintenance job type category**, **Maintenance job type**, **Maintenance job type variant**, and **Trade** fields, select values as you require.</span></span>
4. <span data-ttu-id="1331c-114">Dans le champ **Niveau de service**, sélectionnez un niveau de service de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="1331c-114">In the **Service level** field, select a work order service level.</span></span> <span data-ttu-id="1331c-115">Si vous laissez ce champ vide, vous effectuez le type le plus générique de la ligne d'exécution prévue.</span><span class="sxs-lookup"><span data-stu-id="1331c-115">If you leave this field blank, you make the most generic type of scheduled execution line.</span></span> <span data-ttu-id="1331c-116">Pour un exemple d'une ligne générique, consultez le premier enregistrement dans l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="1331c-116">For an example of a generic line, see the first record in the illustration that follows.</span></span> <span data-ttu-id="1331c-117">Cette ligne active tous les ordres de travail qui n'ont pas de niveau de service à planifier pour une date et une heure spécifiques.</span><span class="sxs-lookup"><span data-stu-id="1331c-117">That line enables all work orders that have no work order service level to be scheduled for a specific date and time.</span></span>
5. <span data-ttu-id="1331c-118">Dans le champ **Exécution planifiée**, sélectionnez l'intervalle de temps.</span><span class="sxs-lookup"><span data-stu-id="1331c-118">In the **Scheduled execution** field, select the time interval.</span></span>
6. <span data-ttu-id="1331c-119">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1331c-119">Select **Save**.</span></span>

![Exécution planifiée](media/20-setup-for-work-orders.png)
