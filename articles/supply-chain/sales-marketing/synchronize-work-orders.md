---
title: Synchroniser les ordres de travail avec un projet entre Field Service et Finance and Operations
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les ordres d'exécution avec un nombre de projets depuis Microsoft Dynamics 365 for Field Service vers la commande client dans Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 5ca01b085315d916a18c512af28fc7534ce76ee8
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2019
ms.locfileid: "836440"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="2eda5-103">Synchroniser les ordres de travail avec un projet entre Field Service et Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2eda5-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2eda5-104">Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les ordres d'exécution avec un nombre de projets depuis Microsoft Dynamics 365 for Field Service vers la commande client dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2eda5-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="2eda5-105">[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="2eda5-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="2eda5-106">Le modèle **Ordres de travail avec projet (Field Service vers Finance and Operations)** utilisé est basé sur le modèle **Ordres de travail (Field Service vers Finance and Operations)**.</span><span class="sxs-lookup"><span data-stu-id="2eda5-106">The used **Work Orders with Project (Field Service to Fin and Ops)** template is based on the **Work Orders (Field Service to Fin and Ops)** template.</span></span> <span data-ttu-id="2eda5-107">Pour en savoir plus, voir [Synchroniser les ordres d'exécution de Field Service sur les commandes client de Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="2eda5-107">For more information, see [Synchronize work orders in Field Service to sales orders in Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

<span data-ttu-id="2eda5-108">Cette rubrique décrit uniquement les différences entre les deux modèles :</span><span class="sxs-lookup"><span data-stu-id="2eda5-108">This topic only describes the differences between the two templates:</span></span>
- <span data-ttu-id="2eda5-109">**Ordres de travail avec projet (Field Service vers Finance and Operations)**</span><span class="sxs-lookup"><span data-stu-id="2eda5-109">**Work Orders with Project (Field Service to Fin and Ops)**</span></span>
- <span data-ttu-id="2eda5-110">**Ordres de travail (Field Service vers Finance and Operations)**</span><span class="sxs-lookup"><span data-stu-id="2eda5-110">**Work Orders (Field Service to Fin and Ops)**</span></span>

<span data-ttu-id="2eda5-111">La différence principale est que ce modèle inclut la mise en correspondance du numéro de projet affect à l'ordre de travail dans Field Service, en vérifiant que la commande client créée dans Finance and Operations incluent le numéro de projet et que la facturation peut se produire dans le projet associé.</span><span class="sxs-lookup"><span data-stu-id="2eda5-111">The main difference is that this template includes mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="2eda5-112">Outre cela, ce modèle utilise la fonctionnalité Requête et filtrage avancés.</span><span class="sxs-lookup"><span data-stu-id="2eda5-112">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="2eda5-113">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="2eda5-113">Templates and tasks</span></span>

<span data-ttu-id="2eda5-114">**Nom du modèle dans l'intégration des données :**</span><span class="sxs-lookup"><span data-stu-id="2eda5-114">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="2eda5-115">Ordres de travail avec projet (Field Service vers Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="2eda5-115">Work Orders with Project (Field Service to Fin and Ops)</span></span>

<span data-ttu-id="2eda5-116">**Nom de la tâche dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="2eda5-116">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="2eda5-117">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="2eda5-117">WorkOrderHeader</span></span>
- <span data-ttu-id="2eda5-118">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="2eda5-118">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="2eda5-119">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="2eda5-119">WorkOrderProduct</span></span>
- <span data-ttu-id="2eda5-120">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="2eda5-120">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="2eda5-121">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="2eda5-121">Field Service CRM solution</span></span>
<span data-ttu-id="2eda5-122">Le champ **Projet externe** a été ajouté à l'entité Ordre d'exécution.</span><span class="sxs-lookup"><span data-stu-id="2eda5-122">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="2eda5-123">Ce champ est un champ de recherche et en référençant votre ordre d'exécution avec un projet, la commande client est ensuite connectée à un projet dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2eda5-123">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="2eda5-124">Une fois que le **statut du système** passe d'En cours - En cours(690,970,000) à un statut plus élevé, le champ **Projet externe** est verrouillé et vous ne pouvez pas ajouter, supprimer ou modifier la valeur.</span><span class="sxs-lookup"><span data-stu-id="2eda5-124">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="2eda5-125">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="2eda5-125">Template mapping in Data integration</span></span>

<span data-ttu-id="2eda5-126">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="2eda5-126">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a><span data-ttu-id="2eda5-127">Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="2eda5-127">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeader</span></span>

<span data-ttu-id="2eda5-128">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="2eda5-128">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a><span data-ttu-id="2eda5-129">Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="2eda5-129">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeaderProject</span></span>

<span data-ttu-id="2eda5-130">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="2eda5-130">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a><span data-ttu-id="2eda5-131">Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="2eda5-131">Work Orders with Project (Field Service to Fin and Ops): WorkOrderProduct</span></span>

<span data-ttu-id="2eda5-132">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="2eda5-132">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a><span data-ttu-id="2eda5-133">Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="2eda5-133">Work Orders with Project (Field Service to Fin and Ops): WorkOrderService</span></span>

<span data-ttu-id="2eda5-134">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="2eda5-134">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
