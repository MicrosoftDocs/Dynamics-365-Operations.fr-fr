---
title: Synchroniser la liste des projets entre Finance and Operations et Field Service
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: ea5c188891bb97ba73d2d022e86bbff50897381b
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1525875"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="322ee-103">Synchroniser la liste des projets entre Finance and Operations et Field Service</span><span class="sxs-lookup"><span data-stu-id="322ee-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="322ee-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="322ee-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="322ee-105">[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="322ee-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="322ee-106">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="322ee-106">Templates and tasks</span></span>
<span data-ttu-id="322ee-107">Le modèle suivant et les tâches sous-jacentes sont utilisées pour exécuter la synchronisation des projets de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="322ee-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="322ee-108">**Modèle dans l'intégration de données**</span><span class="sxs-lookup"><span data-stu-id="322ee-108">**Template in Data integration**</span></span>
- <span data-ttu-id="322ee-109">Projets (Fin and Ops vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="322ee-109">Projects (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="322ee-110">**Tâche du projet d'intégration des données**</span><span class="sxs-lookup"><span data-stu-id="322ee-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="322ee-111">Projets</span><span class="sxs-lookup"><span data-stu-id="322ee-111">Projects</span></span>

<span data-ttu-id="322ee-112">Les tâches de synchronisation suivantes sont requises avant que la synchronisation de la liste de projets puisse avoir lieu :</span><span class="sxs-lookup"><span data-stu-id="322ee-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="322ee-113">Comptes (Sales vers Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="322ee-113">Accounts (Sales to Fin and Ops)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="322ee-114">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="322ee-114">Entity set</span></span>
| <span data-ttu-id="322ee-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="322ee-115">Field Service</span></span>           | <span data-ttu-id="322ee-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="322ee-116">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="322ee-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="322ee-117">msdynce_externalprojects</span></span> | <span data-ttu-id="322ee-118">Projets</span><span class="sxs-lookup"><span data-stu-id="322ee-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="322ee-119">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="322ee-119">Entity flow</span></span>
<span data-ttu-id="322ee-120">Les projets sont créés dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="322ee-120">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="322ee-121">Les projets avec un **Type de projet** défini sur **Régie** et **Stade de projet** défini sur **En cours** se synchroniseront sur l'entité **Projet externe** de Field Service, notamment le numéro de projet, le nom du projet, le stade du projet et des informations sur le compte client.</span><span class="sxs-lookup"><span data-stu-id="322ee-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="322ee-122">La liste **Projet externe** est utilisée pour jumeler les ordres d'exécution Field Service aux projets Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="322ee-122">The **External Project** list is used to pair Field service work orders with Finance and Operations projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="322ee-123">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="322ee-123">Field Service CRM solution</span></span>
<span data-ttu-id="322ee-124">L'entité **Projet externe** reçoit tous les projets depuis Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="322ee-124">The **External Project** entity gets all the projects from Finance and Operations.</span></span> <span data-ttu-id="322ee-125">Le champ **Projet externe** a été ajouté à l'entité **Ordre d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="322ee-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="322ee-126">Ce champ est un champ de recherche et en référençant votre ordre d'exécution avec un projet, la commande client est ensuite connectée à un projet dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="322ee-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Finance and Operations.</span></span> <span data-ttu-id="322ee-127">Une fois que le **statut du système** passe d'**En cours - En cours(690,970,000)** à un statut plus élevé, le champ **Projet externe** est verrouillé et vous ne pouvez plus ajouter, supprimer ou modifier la valeur.</span><span class="sxs-lookup"><span data-stu-id="322ee-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="322ee-128">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="322ee-128">Prerequisites and mapping setup</span></span>
### <a name="finance-and-operations"></a><span data-ttu-id="322ee-129">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="322ee-129">Finance and Operations</span></span>
<span data-ttu-id="322ee-130">Activer le suivi des modifications pour les projets d'entité de données</span><span class="sxs-lookup"><span data-stu-id="322ee-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="322ee-131">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="322ee-131">Template mapping in Data integration</span></span>


### <a name="projects-fin-and-ops-to-field-service-projects"></a><span data-ttu-id="322ee-132">Projets (Fin and Ops vers Field Service) : Projets</span><span class="sxs-lookup"><span data-stu-id="322ee-132">Projects (Fin and Ops to Field Service): Projects</span></span>

<span data-ttu-id="322ee-133">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="322ee-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
