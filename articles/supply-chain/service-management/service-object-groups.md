---
title: Groupes d'objets de service
description: Les groupes d'objets permettent de trier et de filtrer les données relatives à des objets pour générer des états et des statistiques.
author: ShylaThompson
manager: AnnBe
ms.date: 05/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc5b1bf93deaf60a3c6384671ad575c73871eb35
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1543328"
---
# <a name="service-object-groups"></a><span data-ttu-id="0ae9e-103">Groupes d'objets de service</span><span class="sxs-lookup"><span data-stu-id="0ae9e-103">Service object groups</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ae9e-104">Les groupes d'objets permettent de trier et de filtrer les données relatives à des objets pour générer des états et des statistiques.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-104">Object groups are useful for sorting and filtering the data about objects for reports and statistics.</span></span> <span data-ttu-id="0ae9e-105">Par exemple, vous pouvez regrouper des objets par emplacement géographique ou par type.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-105">For example, you can group objects by geographical location or by type.</span></span>

## <a name="group-by-geographical-location"></a><span data-ttu-id="0ae9e-106">Regroupement par emplacement géographique</span><span class="sxs-lookup"><span data-stu-id="0ae9e-106">Group by geographical location</span></span>

<span data-ttu-id="0ae9e-107">Cette méthode de regroupement permet d'afficher l'emplacement des différents objets pour lesquels votre société offre un service.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-107">You can use this grouping method to show where the various different objects that your company services are located.</span></span> <span data-ttu-id="0ae9e-108">Le regroupement d'objets par emplacement géographique peut également être utile, par exemple, si vous devez identifier les objets pour lesquels votre société offre déjà un service dans une région ou un pays particulier.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-108">Grouping objects by geographical location can also be useful if, for example, you must identify the objects that your company already provides services for in a particular country/region.</span></span>

## <a name="example"></a><span data-ttu-id="0ae9e-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="0ae9e-109">Example</span></span>

<span data-ttu-id="0ae9e-110">Un client basé en Belgique désireux de créer une accord de service pour un objet ABC appelle votre centre de service.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-110">A customer from Belgium calls your service center and wants to create a service agreement for an object, ABC.</span></span> <span data-ttu-id="0ae9e-111">Vous avez associé un groupe d'objets pour un emplacement géographique nommé Belgique à tous les objets bénéficiant d'un service en Belgique.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-111">You have attached an object group for geographical location, Belgium, to all objects that are serviced in Belgium.</span></span> <span data-ttu-id="0ae9e-112">En utilisant ce groupe comme filtre, vous pouvez rapidement vérifier si ABC existe déjà en tant qu'enregistrement dans le programme ou si vous devez paramétrer un nouvel objet.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-112">By using this group as a filter, you can quickly search to see whether you already have a record for ABC in the program, or whether you must set up a new object.</span></span> 

## <a name="group-by-type"></a><span data-ttu-id="0ae9e-113">Regroupement par type</span><span class="sxs-lookup"><span data-stu-id="0ae9e-113">Group by type</span></span>

<span data-ttu-id="0ae9e-114">Cette méthode de regroupement permet d'afficher les types d'objets pour lesquels votre société offre un service.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-114">You can use this grouping method to show the types of objects that your company services.</span></span> <span data-ttu-id="0ae9e-115">Le regroupement d'objets par type peut également être utile, par exemple, pour créer un objet basé sur des objets similaires existants dans le programme.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-115">Grouping objects by type can also be useful if, for example, you want to create a new object based on similar objects that already exist in the program.</span></span>

## <a name="example"></a><span data-ttu-id="0ae9e-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="0ae9e-116">Example</span></span>

<span data-ttu-id="0ae9e-117">Un client appelle pour conclure un accord de service concernant un appareil de conditionnement d'air, HIJ.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-117">A customer calls and wants to set up a service agreement for an air conditioning machine, HIJ.</span></span> <span data-ttu-id="0ae9e-118">Vous n'avez pas encore d'enregistrement pour cet appareil.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-118">You do not already have a record for this machine.</span></span> <span data-ttu-id="0ae9e-119">Toutefois, vous avez paramétré un groupe d'objets nommé Conditionnement d'air que vous avez associé à tous les objets de conditionnement d'air.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-119">However, you have set up an object group titled Air Conditioners, and you have attached this group to all air conditioning objects.</span></span> <span data-ttu-id="0ae9e-120">Vous pouvez donc rapidement rechercher et identifier tous les autres appareils de conditionnement d'air et utiliser les informations modèles de ces derniers comme base pour les lignes d'accord de service de HIJ.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-120">Therefore, you can quickly search for and identify all other air conditioning machines and use the template information from these objects to create service agreement lines for HIJ.</span></span> <span data-ttu-id="0ae9e-121">L'utilisation de groupes d'objets de cette manière permet de paramétrer rapidement de nouveaux objets et de déterminer les tâches de service à exécuter sur ces derniers.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-121">By using object groups in this manner, you can quickly set up new objects and determine the service tasks that must be performed on them.</span></span> 

## <a name="create-service-object-groups"></a><span data-ttu-id="0ae9e-122">Créer des groupes d'objets de service</span><span class="sxs-lookup"><span data-stu-id="0ae9e-122">Create service object groups</span></span>

<span data-ttu-id="0ae9e-123">Créez des groupes auxquels vous pouvez affecter des objets de service.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-123">Create groups that you can assign service objects to.</span></span> <span data-ttu-id="0ae9e-124">Les objets de service sont des articles en stock et d'autres produits pour lesquels des services sont assurés.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-124">Service objects are inventory items and other products for which services are performed.</span></span> <span data-ttu-id="0ae9e-125">En regroupant des objets de service, vous pouvez créer des états pour des objets de service similaires et connexes.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-125">By grouping service objects, you can create reports for similar and related service objects.</span></span> <span data-ttu-id="0ae9e-126">Par exemple, un groupe d'objets de service peut comporter deux objets de service : un objet de service qui correspond à un kit, et un deuxième objet de service qui est le service d'installation du kit.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-126">For example, a service object group might consist of two service objects: One service object is a kit, and the second service object is the service to install the kit.</span></span>

<span data-ttu-id="0ae9e-127">Pour créer des groupes d'objets de service, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0ae9e-127">To create service object groups, follow these steps:</span></span>

1. <span data-ttu-id="0ae9e-128">Cliquez sur **Gestion des services > Paramétrage > Objets du service > Groupes d'objets de service**.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-128">Click **Service management > Setup > Service objects > Service object groups**.</span></span>

2. <span data-ttu-id="0ae9e-129">Cliquez sur **Nouveau** pour créer un groupe d'objets de service.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-129">Click **New** to create a new service object group.</span></span>

3. <span data-ttu-id="0ae9e-130">Entrez un nom unique pour le groupe d'objets de service, et éventuellement une description.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-130">Enter a unique name for the service object group and, optionally, a description.</span></span>

<span data-ttu-id="0ae9e-131">Vous pouvez affecter des objets de service au groupe à l'aide de l'écran **Objets de service**.</span><span class="sxs-lookup"><span data-stu-id="0ae9e-131">You can assign service objects to the group by using the **Service objects** form.</span></span> 

## <a name="see-also"></a><span data-ttu-id="0ae9e-132">Voir également :</span><span class="sxs-lookup"><span data-stu-id="0ae9e-132">See also</span></span>

[<span data-ttu-id="0ae9e-133">Créer des objets de service</span><span class="sxs-lookup"><span data-stu-id="0ae9e-133">Create service objects</span></span>](create-service-objects.md)


