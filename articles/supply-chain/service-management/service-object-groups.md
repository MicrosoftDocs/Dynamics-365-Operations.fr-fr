---
title: Groupes d'objets de service
description: "Les groupes d'objets permettent de trier et de filtrer les données relatives à des objets pour générer des états et des statistiques."
author: YuyuScheller
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e539d92753bbbc4ac0ca88cec83c4d15135c388b
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="service-object-groups"></a><span data-ttu-id="248c6-103">Groupes d'objets de service</span><span class="sxs-lookup"><span data-stu-id="248c6-103">Service object groups</span></span> 

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="248c6-104">Les groupes d'objets permettent de trier et de filtrer les données relatives à des objets pour générer des états et des statistiques.</span><span class="sxs-lookup"><span data-stu-id="248c6-104">Object groups are useful for sorting and filtering the data about objects for reports and statistics.</span></span> <span data-ttu-id="248c6-105">Par exemple, vous pouvez regrouper des objets par emplacement géographique ou par type.</span><span class="sxs-lookup"><span data-stu-id="248c6-105">For example, you can group objects by geographical location or by type.</span></span>

## <a name="group-by-geographical-location"></a><span data-ttu-id="248c6-106">Regroupement par emplacement géographique</span><span class="sxs-lookup"><span data-stu-id="248c6-106">Group by geographical location</span></span>

<span data-ttu-id="248c6-107">Cette méthode de regroupement permet d'afficher l'emplacement des différents objets pour lesquels votre société offre un service.</span><span class="sxs-lookup"><span data-stu-id="248c6-107">You can use this grouping method to show where the various different objects that your company services are located.</span></span> <span data-ttu-id="248c6-108">Le regroupement d'objets par emplacement géographique peut également être utile, par exemple, si vous devez identifier les objets pour lesquels votre société offre déjà un service dans une région ou un pays particulier.</span><span class="sxs-lookup"><span data-stu-id="248c6-108">Grouping objects by geographical location can also be useful if, for example, you must identify the objects that your company already provides services for in a particular country/region.</span></span>

## <a name="example"></a><span data-ttu-id="248c6-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="248c6-109">Example</span></span>

<span data-ttu-id="248c6-110">Un client basé en Belgique désireux de créer une accord de service pour un objet ABC appelle votre centre de service.</span><span class="sxs-lookup"><span data-stu-id="248c6-110">A customer from Belgium calls your service center and wants to create a service agreement for an object, ABC.</span></span> <span data-ttu-id="248c6-111">Vous avez associé un groupe d'objets pour un emplacement géographique nommé Belgique à tous les objets bénéficiant d'un service en Belgique.</span><span class="sxs-lookup"><span data-stu-id="248c6-111">You have attached an object group for geographical location, Belgium, to all objects that are serviced in Belgium.</span></span> <span data-ttu-id="248c6-112">En utilisant ce groupe comme filtre, vous pouvez rapidement vérifier si ABC existe déjà en tant qu'enregistrement dans le programme ou si vous devez paramétrer un nouvel objet.</span><span class="sxs-lookup"><span data-stu-id="248c6-112">By using this group as a filter, you can quickly search to see whether you already have a record for ABC in the program, or whether you must set up a new object.</span></span> 

## <a name="group-by-type"></a><span data-ttu-id="248c6-113">Regroupement par type</span><span class="sxs-lookup"><span data-stu-id="248c6-113">Group by type</span></span>

<span data-ttu-id="248c6-114">Cette méthode de regroupement permet d'afficher les types d'objets pour lesquels votre société offre un service.</span><span class="sxs-lookup"><span data-stu-id="248c6-114">You can use this grouping method to show the types of objects that your company services.</span></span> <span data-ttu-id="248c6-115">Le regroupement d'objets par type peut également être utile, par exemple, pour créer un objet basé sur des objets similaires existants dans le programme.</span><span class="sxs-lookup"><span data-stu-id="248c6-115">Grouping objects by type can also be useful if, for example, you want to create a new object based on similar objects that already exist in the program.</span></span>

## <a name="example"></a><span data-ttu-id="248c6-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="248c6-116">Example</span></span>

<span data-ttu-id="248c6-117">Un client appelle pour conclure un accord de service concernant un appareil de conditionnement d'air, HIJ.</span><span class="sxs-lookup"><span data-stu-id="248c6-117">A customer calls and wants to set up a service agreement for an air conditioning machine, HIJ.</span></span> <span data-ttu-id="248c6-118">Vous n'avez pas encore d'enregistrement pour cet appareil.</span><span class="sxs-lookup"><span data-stu-id="248c6-118">You do not already have a record for this machine.</span></span> <span data-ttu-id="248c6-119">Toutefois, vous avez paramétré un groupe d'objets nommé Conditionnement d'air que vous avez associé à tous les objets de conditionnement d'air.</span><span class="sxs-lookup"><span data-stu-id="248c6-119">However, you have set up an object group titled Air Conditioners, and you have attached this group to all air conditioning objects.</span></span> <span data-ttu-id="248c6-120">Vous pouvez donc rapidement rechercher et identifier tous les autres appareils de conditionnement d'air et utiliser les informations modèles de ces derniers comme base pour les lignes d'accord de service de HIJ.</span><span class="sxs-lookup"><span data-stu-id="248c6-120">Therefore, you can quickly search for and identify all other air conditioning machines and use the template information from these objects to create service agreement lines for HIJ.</span></span> <span data-ttu-id="248c6-121">L'utilisation de groupes d'objets de cette manière permet de paramétrer rapidement de nouveaux objets et de déterminer les tâches de service à exécuter sur ces derniers.</span><span class="sxs-lookup"><span data-stu-id="248c6-121">By using object groups in this manner, you can quickly set up new objects and determine the service tasks that must be performed on them.</span></span> 




