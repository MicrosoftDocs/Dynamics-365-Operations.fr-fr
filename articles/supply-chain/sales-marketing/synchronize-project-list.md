---
title: Synchroniser la liste de projet depuis Supply Chain Management vers Field Service
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: b74a7f0445b3bdad671da4c61e561bc0d9d80cd1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251590"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a><span data-ttu-id="671e9-103">Synchroniser la liste de projet depuis Supply Chain Management vers Field Service</span><span class="sxs-lookup"><span data-stu-id="671e9-103">Synchronize project list from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="671e9-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="671e9-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="671e9-105">[![Synchronisation des processus d'entreprise entre Supply Chain Management et Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="671e9-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="671e9-106">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="671e9-106">Templates and tasks</span></span>
<span data-ttu-id="671e9-107">Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les projets depuis Supply Chain Management vers Field Service.</span><span class="sxs-lookup"><span data-stu-id="671e9-107">The following template and underlying tasks are used to run synchronization of projects from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="671e9-108">**Modèle dans l'intégration de données**</span><span class="sxs-lookup"><span data-stu-id="671e9-108">**Template in Data integration**</span></span>
- <span data-ttu-id="671e9-109">Projets (Supply Chain Management vers Field Service)</span><span class="sxs-lookup"><span data-stu-id="671e9-109">Projects (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="671e9-110">**Tâche du projet d'intégration des données**</span><span class="sxs-lookup"><span data-stu-id="671e9-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="671e9-111">Projets</span><span class="sxs-lookup"><span data-stu-id="671e9-111">Projects</span></span>

<span data-ttu-id="671e9-112">Les tâches de synchronisation suivantes sont requises avant que la synchronisation de la liste de projets puisse avoir lieu :</span><span class="sxs-lookup"><span data-stu-id="671e9-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="671e9-113">Comptes (Sales vers Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="671e9-113">Accounts (Sales to Supply Chain Management)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="671e9-114">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="671e9-114">Entity set</span></span>
| <span data-ttu-id="671e9-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="671e9-115">Field Service</span></span>           | <span data-ttu-id="671e9-116">Gestion de la chaîne d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="671e9-116">Supply Chain Management</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="671e9-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="671e9-117">msdynce_externalprojects</span></span> | <span data-ttu-id="671e9-118">Projets</span><span class="sxs-lookup"><span data-stu-id="671e9-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="671e9-119">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="671e9-119">Entity flow</span></span>
<span data-ttu-id="671e9-120">Les projets sont créés dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="671e9-120">Projects are created in Supply Chain Management.</span></span> <span data-ttu-id="671e9-121">Les projets avec un **Type de projet** défini sur **Régie** et **Stade de projet** défini sur **En cours** se synchroniseront sur l'entité **Projet externe** de Field Service, notamment le numéro de projet, le nom du projet, le stade du projet et des informations sur le compte client.</span><span class="sxs-lookup"><span data-stu-id="671e9-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="671e9-122">La liste **Projet externe** est utilisée pour jumeler les ordres d'exécution Field Service aux projets Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="671e9-122">The **External Project** list is used to pair Field service work orders with Supply Chain Management projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="671e9-123">Solution Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="671e9-123">Field Service CRM solution</span></span>
<span data-ttu-id="671e9-124">L'entité **Projet externe** reçoit tous les projets depuis Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="671e9-124">The **External Project** entity gets all the projects from Supply Chain Management.</span></span> <span data-ttu-id="671e9-125">Le champ **Projet externe** a été ajouté à l'entité **Ordre d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="671e9-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="671e9-126">Ce champ est un champ de recherche et en référençant votre ordre d'exécution avec un projet, la commande client est ensuite connectée à un projet dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="671e9-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Supply Chain Management.</span></span> <span data-ttu-id="671e9-127">Une fois que le **statut du système** passe d'**En cours - En cours(690,970,000)** à un statut plus élevé, le champ **Projet externe** est verrouillé et vous ne pouvez plus ajouter, supprimer ou modifier la valeur.</span><span class="sxs-lookup"><span data-stu-id="671e9-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="671e9-128">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="671e9-128">Prerequisites and mapping setup</span></span>
### <a name="supply-chain-management"></a><span data-ttu-id="671e9-129">Gestion de la chaîne d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="671e9-129">Supply Chain Management</span></span>
<span data-ttu-id="671e9-130">Activer le suivi des modifications pour les projets d'entité de données</span><span class="sxs-lookup"><span data-stu-id="671e9-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="671e9-131">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="671e9-131">Template mapping in Data integration</span></span>


### <a name="projects-supply-chain-management-to-field-service-projects"></a><span data-ttu-id="671e9-132">Projets (Supply Chain Management vers Field Service) : Projets</span><span class="sxs-lookup"><span data-stu-id="671e9-132">Projects (Supply Chain Management to Field Service): Projects</span></span>

<span data-ttu-id="671e9-133">[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="671e9-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
