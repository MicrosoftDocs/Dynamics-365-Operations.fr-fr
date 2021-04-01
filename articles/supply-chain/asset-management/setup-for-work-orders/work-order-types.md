---
title: Types d’ordre d’exécution
description: Cette rubrique explique les types d’ordre de travail dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 561ca87740d90590262716f0042fca6b59dafc69
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223528"
---
# <a name="work-order-types"></a><span data-ttu-id="b3d28-103">Types d’ordre d’exécution</span><span class="sxs-lookup"><span data-stu-id="b3d28-103">Work order types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="b3d28-104">Les types d’ordre de travail sont utilisés pour classer les ordres de travail par catégorie.</span><span class="sxs-lookup"><span data-stu-id="b3d28-104">Work order types are used to categorize work orders.</span></span> <span data-ttu-id="b3d28-105">Par exemple, des ordres de travail peuvent être associés à la maintenance préventive ou à la maintenance corrective.</span><span class="sxs-lookup"><span data-stu-id="b3d28-105">For example, you might have work orders that are related to preventive maintenance or corrective maintenance.</span></span>

<span data-ttu-id="b3d28-106">Un type d’ordre de travail définit une affiliation au modèle du cycle de vie de l’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="b3d28-106">A work order type defines an affiliation with a work order lifecycle model.</span></span> <span data-ttu-id="b3d28-107">Un modèle de cycle de vie de l’ordre de travail définit les états du cycle de vie de l’ordre de travail qui peuvent être définis sur un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="b3d28-107">A work order lifecycle model defines the work order lifecycle states that can be set on a work order.</span></span> <span data-ttu-id="b3d28-108">(Parmi des exemples d’états du cycle de vie de l’ordre de travail figurent **Créé**, **En cours** et **Terminé**.)</span><span class="sxs-lookup"><span data-stu-id="b3d28-108">(Examples of work order lifecycle states include **Created**, **In Process**, and **Finished**.)</span></span>

<span data-ttu-id="b3d28-109">Pour plus d’informations sur les états du cycle de vie de l’ordre de travail et les étapes du projet, consultez [États du cycle de vie de l’ordre de travail](work-order-lifecycle-states.md).</span><span class="sxs-lookup"><span data-stu-id="b3d28-109">For more information about work order lifecycle states and project stages, see [Work order lifecycle states](work-order-lifecycle-states.md).</span></span>

1. <span data-ttu-id="b3d28-110">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **Types d’ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="b3d28-110">Select **Asset management** \> **Setup** \> **Work orders** \> **Work order types**.</span></span>
2. <span data-ttu-id="b3d28-111">Sélectionnez **Nouveau** pour créer un type d’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="b3d28-111">Select **New** to create a work order type.</span></span>
3. <span data-ttu-id="b3d28-112">Dans le champ **Type d’ordre de travail**, saisissez un ID pour le type d’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="b3d28-112">In the **Work order type** field, enter an ID for the work order type.</span></span>
4. <span data-ttu-id="b3d28-113">Dans le champ **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="b3d28-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="b3d28-114">Dans le champ **Modèle du cycle de vie de l’ordre de travail**, sélectionnez un modèle de cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="b3d28-114">In the **Work order lifecycle model** field, select a lifecycle model.</span></span>
5. <span data-ttu-id="b3d28-115">Définissez l’option **Un agent de maintenance** sur **Oui** si toutes les tâches de l’ordre de travail associées à un ordre de travail de ce type doivent être planifiées au même agent de maintenance.</span><span class="sxs-lookup"><span data-stu-id="b3d28-115">Set the **One maintenance worker** option to **Yes** if all work order jobs that are related to a work order of this type should be scheduled to the same maintenance worker.</span></span>
6. <span data-ttu-id="b3d28-116">Dans le champ **Type de coût**, sélectionnez **Correctif**, **Préventif** ou **Investissement**, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="b3d28-116">In the **Cost type** field, select **Corrective**, **Preventive**, or **Investment**, as appropriate.</span></span> <span data-ttu-id="b3d28-117">Toutes les tâches de l’ordre de travail sur un ordre de travail doivent avoir le même type de coût.</span><span class="sxs-lookup"><span data-stu-id="b3d28-117">All work order jobs on a work order must have the same cost type.</span></span>
7. <span data-ttu-id="b3d28-118">Dans la section **Obligatoire**, définissez les options appropriées sur **Oui** pour spécifier que les informations relatives au temps d’arrêt pour maintenance ou à une panne sont ajoutées à un ordre de travail de ce type.</span><span class="sxs-lookup"><span data-stu-id="b3d28-118">In the **Mandatory** section, set the relevant options to **Yes** to specify which fault-related or maintenance downtime–related information is added to a work order of this type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3d28-119">Les options de la section **Obligatoire** sont associées aux options sur l’organisateur **Valider** de la page **États du cycle de vie de l’ordre de travail** (**Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **États du cycle de vie**).</span><span class="sxs-lookup"><span data-stu-id="b3d28-119">The options in the **Mandatory** section are related to the options on the **Validate** FastTab of the **Work order lifecycle states** page (**Asset management** \> **Setup** \> **Work orders** \> **Lifecycle states**).</span></span>

8. <span data-ttu-id="b3d28-120">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b3d28-120">Select **Save**.</span></span>

![Types d’ordre de travail](media/16-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]