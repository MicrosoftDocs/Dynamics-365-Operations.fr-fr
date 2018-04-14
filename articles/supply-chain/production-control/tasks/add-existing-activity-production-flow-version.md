--- 
title: "Ajouter une activité existante à une version de flux de production"
description: "Lors de la création de nouvelles versions des flux de production, vous pouvez choisir d'ajouter des activités créées pour les versions antérieures, à la nouvelle version."
author: cvocph
manager: AnnBe
ms.date: 10/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d151f68de574f362e14001c98655429e82f3b2c0
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a><span data-ttu-id="d4d90-103">Ajouter une activité existante à une version de flux de production</span><span class="sxs-lookup"><span data-stu-id="d4d90-103">Add an existing activity to a production flow version</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d4d90-104">Lors de la création de nouvelles versions des flux de production, vous pouvez choisir d'ajouter des activités créées pour les versions antérieures, à la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="d4d90-104">When creating new versions of production flows, you can choose to add activities created for the older versions, to the new version.</span></span> <span data-ttu-id="d4d90-105">Cette procédure décrit la manière dont une version est créée pour un flux de production existant, sans copier les activités.</span><span class="sxs-lookup"><span data-stu-id="d4d90-105">This procedure shows how a new version is created for an existing production flow, without copying the activities.</span></span> <span data-ttu-id="d4d90-106">Dans l'étape suivante, une activité existante est ajoutée à la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="d4d90-106">In the next step, an existing activity is added to the new version.</span></span> 

<span data-ttu-id="d4d90-107">Cette tâche nécessite un flux de production avec une version et des activités déjà créées.</span><span class="sxs-lookup"><span data-stu-id="d4d90-107">This task requires production flow with version and activities already created.</span></span>


## <a name="create-a-new-production-flow-version"></a><span data-ttu-id="d4d90-108">Créer une nouvelle version de flux de production</span><span class="sxs-lookup"><span data-stu-id="d4d90-108">Create a new production flow version</span></span>
1. <span data-ttu-id="d4d90-109">Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.</span><span class="sxs-lookup"><span data-stu-id="d4d90-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="d4d90-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d4d90-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d4d90-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d4d90-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d4d90-112">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="d4d90-112">Click Edit.</span></span>
5. <span data-ttu-id="d4d90-113">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d4d90-113">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="d4d90-114">Entrez une date et une heure dans le champ Date d'expiration.</span><span class="sxs-lookup"><span data-stu-id="d4d90-114">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="d4d90-115">Notez qu'avant de créer une version du flux de production, veillez à vérifier la date et l'heure d'expiration de la version active.</span><span class="sxs-lookup"><span data-stu-id="d4d90-115">Note that before you create a new production flow version, make sure to check the expiration date and time of the active version.</span></span> <span data-ttu-id="d4d90-116">La nouvelle version est créée avec une date de début effective, qui se connecte à la date d'expiration de la version sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d4d90-116">The new version will be created with an effective start date, which connects to the expiry date of the selected version.</span></span>  
7. <span data-ttu-id="d4d90-117">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d4d90-117">Click Add.</span></span>
8. <span data-ttu-id="d4d90-118">Sélectionnez Non dans le champ Copier à partir de la version.</span><span class="sxs-lookup"><span data-stu-id="d4d90-118">Select No in the Copy from version field.</span></span>
    * <span data-ttu-id="d4d90-119">Sélectionnez Non pour démarrer avec une version vide si la plupart des activités de la version copiée sont remplacées par de nouvelles activités.</span><span class="sxs-lookup"><span data-stu-id="d4d90-119">Select No to start with an empty version if most of the activities of the copied version will be replaced by new activities.</span></span> <span data-ttu-id="d4d90-120">Ajoutez manuellement les activités inchangées à la fonction Ajouter existant de l'écran d'activité.</span><span class="sxs-lookup"><span data-stu-id="d4d90-120">Add the unchanged activities to the Add existing function in the activity form manually.</span></span>  
9. <span data-ttu-id="d4d90-121">Sélectionnez Non dans le champ Dupliquer les règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="d4d90-121">Select No in the Duplicate kanban rules field.</span></span>
    * <span data-ttu-id="d4d90-122">Lorsque les activités ne sont pas copiées vers la nouvelle version, il n'est pas possible de copier les règles de kanban au moment de la création de la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="d4d90-122">When the activities are not copied to the new version, it is not possible to copy the kanban rules at the time of creation of the new version.</span></span>   <span data-ttu-id="d4d90-123">Vous pouvez utiliser la fonction de création de règles de kanban de remplacement dans l'écran de règle de kanban pour remplacer les règles de kanban de l'ancienne version du flux de production par des règles de kanban utilisant les activités de la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="d4d90-123">Instead you will use the create replacement kanban function later in the kanban rule form, to replace kanban rules of the old production flow version with kanban rules using the activities of the new version.</span></span>  
10. <span data-ttu-id="d4d90-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d4d90-124">Click OK.</span></span>
11. <span data-ttu-id="d4d90-125">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d4d90-125">In the list, find and select the desired record.</span></span>

## <a name="add-an-existing-activity"></a><span data-ttu-id="d4d90-126">Ajouter une activité existante</span><span class="sxs-lookup"><span data-stu-id="d4d90-126">Add an existing activity</span></span>
1. <span data-ttu-id="d4d90-127">Cliquez sur Activités.</span><span class="sxs-lookup"><span data-stu-id="d4d90-127">Click Activities.</span></span>
2. <span data-ttu-id="d4d90-128">Cliquez sur Ajouter existant pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d4d90-128">Click Add existing to open the drop dialog.</span></span>
    * <span data-ttu-id="d4d90-129">Recherchez et sélectionnez une activité existante à ajouter à la nouvelle version du flux de production.</span><span class="sxs-lookup"><span data-stu-id="d4d90-129">Find and select an existing activity to be added to the new production flow version.</span></span>  <span data-ttu-id="d4d90-130">Notez que la liste répertorie toutes les activités créées pour ce flux de production pour toutes les versions précédentes du flux.</span><span class="sxs-lookup"><span data-stu-id="d4d90-130">Note that the list shows all activities that have been created for this production flow for all previous versions of the flow.</span></span>  
3. <span data-ttu-id="d4d90-131">Dans le champ Activité, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d4d90-131">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="d4d90-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d4d90-132">Click OK.</span></span>


