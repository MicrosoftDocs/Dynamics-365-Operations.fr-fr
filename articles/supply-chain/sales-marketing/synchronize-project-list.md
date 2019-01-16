---
title: Synchroniser la liste des projets entre Finance and Operations et Field Service
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: fr-fr
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="06a2a-103">Synchroniser la liste des projets entre Finance and Operations et Field Service</span><span class="sxs-lookup"><span data-stu-id="06a2a-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="06a2a-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="06a2a-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="06a2a-105">[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="06a2a-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="06a2a-106">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="06a2a-106">Templates and tasks</span></span>
<span data-ttu-id="06a2a-107">Les modèle et les tâches sous-jacentes suivants sont utilisés pour exécuter la synchronisation des projets de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="06a2a-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="06a2a-108">**Nom du modèle dans l'intégration des données :**</span><span class="sxs-lookup"><span data-stu-id="06a2a-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="06a2a-109">Projets (Finance and Operations vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="06a2a-109">Projects (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="06a2a-110">**Noms des tâches dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="06a2a-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="06a2a-111">Projets</span><span class="sxs-lookup"><span data-stu-id="06a2a-111">Projects</span></span>

<span data-ttu-id="06a2a-112">Les tâches de synchronisation suivantes sont requises avant que la synchronisation de la liste de projets puisse avoir lieu :</span><span class="sxs-lookup"><span data-stu-id="06a2a-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="06a2a-113">Comptes (Sales vers Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="06a2a-113">Accounts (Sales to Finance and Operations)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="06a2a-114">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="06a2a-114">Entity set</span></span>
<span data-ttu-id="06a2a-115">Field Service   Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="06a2a-115">Field Service   Finance and Operations</span></span>

| <span data-ttu-id="06a2a-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="06a2a-116">Field Service</span></span>           | <span data-ttu-id="06a2a-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="06a2a-117">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="06a2a-118">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="06a2a-118">msdynce_externalprojects</span></span> | <span data-ttu-id="06a2a-119">Projets</span><span class="sxs-lookup"><span data-stu-id="06a2a-119">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="06a2a-120">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="06a2a-120">Entity flow</span></span>
<span data-ttu-id="06a2a-121">Les projets sont créés dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="06a2a-121">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="06a2a-122">Les projets avec un **Type de projet** Régie et un **Stade de projet** En cours se synchroniseront sur l'entité **Projet externe** de Field Service, notamment le numéro de projet, le nom du projet, le stade du projet et des informations sur le compte client.</span><span class="sxs-lookup"><span data-stu-id="06a2a-122">Projects with **Project type** Time and material and **Project stage** In process will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage and Customer account information.</span></span> <span data-ttu-id="06a2a-123">La liste **Projet externe** est utilisée pour jumeler les ordres d'exécution Field Service aux projets Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="06a2a-123">The list of **External Project** is used to pair Field service Work orders with Finance and Operations projects.</span></span>
<span data-ttu-id="06a2a-124">Solution Field Service CRM Le projet externe est une nouvelle entité qui reçoit tous les projets d'Operations.</span><span class="sxs-lookup"><span data-stu-id="06a2a-124">Field Service CRM solution The External Project is a new entity that gets all the Projects from Operations.</span></span>
<span data-ttu-id="06a2a-125">Le champ Projet externe a été ajouté à l'entité Ordre d'exécution.</span><span class="sxs-lookup"><span data-stu-id="06a2a-125">The External Project field has been added to the Work Order entity.</span></span> <span data-ttu-id="06a2a-126">Ce champ est un champ de recherche et en référençant votre ordre d'exécution avec un projet, la commande client est ensuite connectée à un projet dans Operations.</span><span class="sxs-lookup"><span data-stu-id="06a2a-126">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Operations.</span></span> <span data-ttu-id="06a2a-127">Une fois que le statut du système passe d'En cours - En cours(690,970,000) à un statut plus élevé, le champ Projet externe est verrouillé et vous ne pouvez pas ajouter, supprimer ou modifier la valeur.</span><span class="sxs-lookup"><span data-stu-id="06a2a-127">Ones the System Status changes Open – In Progress(690,970,000) to a higher status the External Project field will be locked and you can't add, remove or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="06a2a-128">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="06a2a-128">Prerequisites and mapping setup</span></span>
### <a name="in-finance-and-operations"></a><span data-ttu-id="06a2a-129">Dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="06a2a-129">In Finance and Operations</span></span>
<span data-ttu-id="06a2a-130">Activer le suivi des modifications pour les projets d'entité de données</span><span class="sxs-lookup"><span data-stu-id="06a2a-130">Enable change tracking for Data entity Projects</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="06a2a-131">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="06a2a-131">Template mapping in Data integration</span></span>


### <a name="projects-finance-and-operations-to-field-service-projects"></a><span data-ttu-id="06a2a-132">Projets (Finance and Operations vers Field Service) : Projets</span><span class="sxs-lookup"><span data-stu-id="06a2a-132">Projects (Finance and Operations to Field Service): Projects</span></span>

<span data-ttu-id="06a2a-133">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="06a2a-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>

