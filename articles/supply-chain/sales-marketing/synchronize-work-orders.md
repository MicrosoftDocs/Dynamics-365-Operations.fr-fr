---
title: Synchroniser les ordres de travail avec un projet entre Field Service et Finance and Operations
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les ordres d'exécution avec un nombre de projets depuis Microsoft Dynamics 365 for Field Service vers la commande client dans Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: 6b61411a5a235e2d0aad8bb25ae4a3bfcf1248d1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "329848"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="6ca1f-103">Synchroniser les ordres de travail avec un projet entre Field Service et Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6ca1f-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="6ca1f-104">Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les ordres d'exécution avec un nombre de projets depuis Microsoft Dynamics 365 for Field Service vers la commande client dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="6ca1f-105">[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="6ca1f-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="6ca1f-106">Le modèle **Produits Field Service (Finance and Operations vers Field Service)** utilisé est basé sur le modèle **Produits (Finance and Operations vers Sales) – Direct** de Prospect en disponibilités.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="6ca1f-107">Pour plus d'informations, voir [Produits (entre Finance and Operations et Sales) - Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="6ca1f-107">For more information, see [Products (Finance and Operations to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="6ca1f-108">Cette rubrique décrit les différences entre les modèles **Produits Field Service (Finance and Operations vers Field Service)** et **Produits Field Service (Finance and Operations vers Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

<span data-ttu-id="6ca1f-109">La différence principale est que ce modèle inclut la mise en correspondance du numéro de projet affect à l'ordre de travail dans Field Service, en vérifiant que la commande client créée dans Finance and Operations incluent le numéro de projet et que la facturation peut se produire dans le projet associé.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-109">The main difference is that this template includes mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="6ca1f-110">Outre cela, ce modèle utilise la fonctionnalité Requête et filtrage avancés.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-110">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="6ca1f-111">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="6ca1f-111">Templates and tasks</span></span>

<span data-ttu-id="6ca1f-112">**Nom du modèle dans l'intégration des données :**</span><span class="sxs-lookup"><span data-stu-id="6ca1f-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="6ca1f-113">Ordres de travail avec projet (Field Service vers Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="6ca1f-113">Work Orders with Project (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="6ca1f-114">**Nom de la tâche dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="6ca1f-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="6ca1f-115">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="6ca1f-115">WorkOrderHeader</span></span>
- <span data-ttu-id="6ca1f-116">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="6ca1f-116">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="6ca1f-117">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="6ca1f-117">WorkOrderProduct</span></span>
- <span data-ttu-id="6ca1f-118">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="6ca1f-118">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="6ca1f-119">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="6ca1f-119">Field Service CRM solution</span></span>
<span data-ttu-id="6ca1f-120">Le champ **Projet externe** a été ajouté à l'entité Ordre d'exécution.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-120">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="6ca1f-121">Ce champ est un champ de recherche et en référençant votre ordre d'exécution avec un projet, la commande client est ensuite connectée à un projet dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-121">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="6ca1f-122">Une fois que le **statut du système** passe d'En cours - En cours(690,970,000) à un statut plus élevé, le champ **Projet externe** est verrouillé et vous ne pouvez pas ajouter, supprimer ou modifier la valeur.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-122">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="6ca1f-123">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="6ca1f-123">Template mapping in Data integration</span></span>

<span data-ttu-id="6ca1f-124">Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-124">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a><span data-ttu-id="6ca1f-125">Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="6ca1f-125">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeader</span></span>

<span data-ttu-id="6ca1f-126">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="6ca1f-126">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a><span data-ttu-id="6ca1f-127">Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="6ca1f-127">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeaderProject</span></span>

<span data-ttu-id="6ca1f-128">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="6ca1f-128">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a><span data-ttu-id="6ca1f-129">Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="6ca1f-129">Work Orders with Project (Field Service to Finance and Operations): WorkOrderProduct</span></span>

<span data-ttu-id="6ca1f-130">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="6ca1f-130">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a><span data-ttu-id="6ca1f-131">Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="6ca1f-131">Work Orders with Project (Field Service to Finance and Operations): WorkOrderService</span></span>

<span data-ttu-id="6ca1f-132">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="6ca1f-132">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
