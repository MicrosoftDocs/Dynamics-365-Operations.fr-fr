---
title: Synchroniser la liste des projets entre Finance and Operations et Field Service
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
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
ms.openlocfilehash: b5aeb4c3925994d7488e8e113e88b9d06ee6b350
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "312506"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="79940-103">Synchroniser la liste des projets entre Finance and Operations et Field Service</span><span class="sxs-lookup"><span data-stu-id="79940-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="79940-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="79940-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="79940-105">[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="79940-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="79940-106">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="79940-106">Templates and tasks</span></span>
<span data-ttu-id="79940-107">Le modèle suivant et les tâches sous-jacentes sont utilisées pour exécuter la synchronisation des projets de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="79940-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="79940-108">**Modèle dans l'intégration de données**</span><span class="sxs-lookup"><span data-stu-id="79940-108">**Template in Data integration**</span></span>
- <span data-ttu-id="79940-109">Projets (Finance and Operations vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="79940-109">Projects (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="79940-110">**Tâche du projet d'intégration des données**</span><span class="sxs-lookup"><span data-stu-id="79940-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="79940-111">Projets</span><span class="sxs-lookup"><span data-stu-id="79940-111">Projects</span></span>

<span data-ttu-id="79940-112">Les tâches de synchronisation suivantes sont requises avant que la synchronisation de la liste de projets puisse avoir lieu :</span><span class="sxs-lookup"><span data-stu-id="79940-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="79940-113">Comptes (Sales vers Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="79940-113">Accounts (Sales to Finance and Operations)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="79940-114">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="79940-114">Entity set</span></span>
| <span data-ttu-id="79940-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="79940-115">Field Service</span></span>           | <span data-ttu-id="79940-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="79940-116">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="79940-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="79940-117">msdynce_externalprojects</span></span> | <span data-ttu-id="79940-118">Projets</span><span class="sxs-lookup"><span data-stu-id="79940-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="79940-119">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="79940-119">Entity flow</span></span>
<span data-ttu-id="79940-120">Les projets sont créés dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79940-120">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="79940-121">Les projets avec un **Type de projet** défini sur **Régie** et **Stade de projet** défini sur **En cours** se synchroniseront sur l'entité **Projet externe** de Field Service, notamment le numéro de projet, le nom du projet, le stade du projet et des informations sur le compte client.</span><span class="sxs-lookup"><span data-stu-id="79940-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="79940-122">La liste **Projet externe** est utilisée pour jumeler les ordres d'exécution Field Service aux projets Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79940-122">The **External Project** list is used to pair Field service work orders with Finance and Operations projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="79940-123">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="79940-123">Field Service CRM solution</span></span>
<span data-ttu-id="79940-124">L'entité **Projet externe** reçoit tous les projets depuis Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79940-124">The **External Project** entity gets all the projects from Finance and Operations.</span></span> <span data-ttu-id="79940-125">Le champ **Projet externe** a été ajouté à l'entité **Ordre d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="79940-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="79940-126">Ce champ est un champ de recherche et en référençant votre ordre d'exécution avec un projet, la commande client est ensuite connectée à un projet dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79940-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Finance and Operations.</span></span> <span data-ttu-id="79940-127">Une fois que le **statut du système** passe d'**En cours - En cours(690,970,000)** à un statut plus élevé, le champ **Projet externe** est verrouillé et vous ne pouvez plus ajouter, supprimer ou modifier la valeur.</span><span class="sxs-lookup"><span data-stu-id="79940-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="79940-128">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="79940-128">Prerequisites and mapping setup</span></span>
### <a name="finance-and-operations"></a><span data-ttu-id="79940-129">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="79940-129">Finance and Operations</span></span>
<span data-ttu-id="79940-130">Activer le suivi des modifications pour les projets d'entité de données</span><span class="sxs-lookup"><span data-stu-id="79940-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="79940-131">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="79940-131">Template mapping in Data integration</span></span>


### <a name="projects-finance-and-operations-to-field-service-projects"></a><span data-ttu-id="79940-132">Projets (Finance and Operations vers Field Service) : Projets</span><span class="sxs-lookup"><span data-stu-id="79940-132">Projects (Finance and Operations to Field Service): Projects</span></span>

<span data-ttu-id="79940-133">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="79940-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
