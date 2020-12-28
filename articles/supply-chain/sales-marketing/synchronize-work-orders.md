---
title: Synchroniser les ordres de travail avec un projet entre Field Service et Supply Chain Management
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les ordres d'exécution avec un nombre de projets depuis Dynamics 365 Field Service vers la commande client dans Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 5ebf23c5c831e9dad5d13c72f82eb3eeb30da853
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427697"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a><span data-ttu-id="c28e7-103">Synchroniser les ordres de travail avec un projet entre Field Service et Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c28e7-103">Synchronize work orders with project from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c28e7-104">Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les ordres d'exécution avec un nombre de projets depuis Dynamics 365 Field Service vers la commande client dans Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c28e7-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Dynamics 365 Field Service to Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="c28e7-105">[![Synchronisation des processus d'entreprise entre Supply Chain Management et Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="c28e7-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="c28e7-106">Le modèle **Ordres de travail avec projet (Field Service vers Supply Chain Management)** utilisé est basé sur le modèle **Ordres de travail (Field Service vers Supply Chain Management)**.</span><span class="sxs-lookup"><span data-stu-id="c28e7-106">The used **Work Orders with Project (Field Service to Supply Chain Management)** template is based on the **Work Orders (Field Service to Supply Chain Management)** template.</span></span> <span data-ttu-id="c28e7-107">Pour en savoir plus, voir [Synchroniser les ordres de travail de Field Service avec les commandes client dans Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="c28e7-107">For more information, see [Synchronize work orders in Field Service to sales orders in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

<span data-ttu-id="c28e7-108">Cette rubrique décrit uniquement les différences entre les deux modèles :</span><span class="sxs-lookup"><span data-stu-id="c28e7-108">This topic only describes the differences between the two templates:</span></span>
- <span data-ttu-id="c28e7-109">**Ordres de travail avec Projet (Field Service vers Supply Chain Management)**</span><span class="sxs-lookup"><span data-stu-id="c28e7-109">**Work Orders with Project (Field Service to Supply Chain Management)**</span></span>
- <span data-ttu-id="c28e7-110">**Ordres de travail (Field Service vers Supply Chain Management)**</span><span class="sxs-lookup"><span data-stu-id="c28e7-110">**Work Orders (Field Service to Supply Chain Management)**</span></span>

<span data-ttu-id="c28e7-111">La différence principale réside dans le fait que ce modèle inclut la mise en correspondance du numéro de projet attribué à l'ordre de travail dans Field Service, en vérifiant que la commande client créée dans Supply Chain Management comporte bien le numéro de projet et que la facturation peut avoir lieu dans le projet associé.</span><span class="sxs-lookup"><span data-stu-id="c28e7-111">The main difference is that this template includes mapping of the project number assigned to the Work order in Field Service, ensuring that the Sales order created in Supply Chain Management include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="c28e7-112">Outre cela, ce modèle utilise la fonctionnalité Requête et filtrage avancés.</span><span class="sxs-lookup"><span data-stu-id="c28e7-112">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="c28e7-113">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="c28e7-113">Templates and tasks</span></span>

<span data-ttu-id="c28e7-114">**Nom du modèle dans l'intégration des données :**</span><span class="sxs-lookup"><span data-stu-id="c28e7-114">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="c28e7-115">Ordres de travail avec Projet (Field Service vers Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="c28e7-115">Work Orders with Project (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="c28e7-116">**Nom de la tâche dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="c28e7-116">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="c28e7-117">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="c28e7-117">WorkOrderHeader</span></span>
- <span data-ttu-id="c28e7-118">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="c28e7-118">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="c28e7-119">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="c28e7-119">WorkOrderProduct</span></span>
- <span data-ttu-id="c28e7-120">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="c28e7-120">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="c28e7-121">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="c28e7-121">Field Service CRM solution</span></span>
<span data-ttu-id="c28e7-122">Le champ **Projet externe** a été ajouté à l'entité Ordre d'exécution.</span><span class="sxs-lookup"><span data-stu-id="c28e7-122">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="c28e7-123">Ce champ est un champ de recherche et, en référençant votre ordre de travail avec un projet, la commande client est ensuite connectée à un projet dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c28e7-123">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Supply Chain Management.</span></span> <span data-ttu-id="c28e7-124">Une fois que le **Statut du système** passe d'En cours - En cours (690,970,000) à un statut plus élevé, le champ **Projet externe** est verrouillé et vous ne pouvez pas ajouter, supprimer ou modifier la valeur.</span><span class="sxs-lookup"><span data-stu-id="c28e7-124">When the **System Status** changes from Open – In Progress(690,970,000) to a higher status, the **External Project** field will be locked and you can't add, remove, or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="c28e7-125">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="c28e7-125">Template mapping in Data integration</span></span>

<span data-ttu-id="c28e7-126">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="c28e7-126">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a><span data-ttu-id="c28e7-127">Ordres de travail avec Projet (Field Service vers Supply Chain Management) : WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="c28e7-127">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderHeader</span></span>

<span data-ttu-id="c28e7-128">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="c28e7-128">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a><span data-ttu-id="c28e7-129">Ordres de travail avec Projet (Field Service vers Supply Chain Management) : WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="c28e7-129">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderHeaderProject</span></span>

<span data-ttu-id="c28e7-130">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="c28e7-130">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a><span data-ttu-id="c28e7-131">Ordres de travail avec Projet (Field Service vers Supply Chain Management) : WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="c28e7-131">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderProduct</span></span>

<span data-ttu-id="c28e7-132">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="c28e7-132">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a><span data-ttu-id="c28e7-133">Ordres de travail avec Projet (Field Service vers Supply Chain Management) : WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="c28e7-133">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderService</span></span>

<span data-ttu-id="c28e7-134">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="c28e7-134">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
