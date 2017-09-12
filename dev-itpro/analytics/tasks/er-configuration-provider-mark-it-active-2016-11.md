--- 
title: "Créer un fournisseur de configuration et le marquer comme actif pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut créer un fournisseur de configuration pour la génération d'états électroniques (ER)."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: bdb3a3857a7293828a7766b6988c123a43e0673c
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-configuration-providand-mark-it-as-active-for-electronic-reporting-er"></a><span data-ttu-id="7fdf9-103">Créer un fournisseur de configuration et le marquer comme actif pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="7fdf9-103">Create a configuration providand mark it as active for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7fdf9-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut créer un fournisseur de configuration pour la génération d'états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="7fdf9-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="7fdf9-105">Chaque configuration ER fait référence au fournisseur en tant que l'auteur de la configuration.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="7fdf9-106">Dans cet exemple, vous allez créer un fournisseur de configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les fournisseurs de configurations ER sont partagés entre toutes les sociétés.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="7fdf9-107">Créer un fournisseur</span><span class="sxs-lookup"><span data-stu-id="7fdf9-107">Create a provider</span></span>
1. <span data-ttu-id="7fdf9-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="7fdf9-109">Cliquez sur Fournisseurs de configuration.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="7fdf9-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-110">Click New.</span></span>
    * <span data-ttu-id="7fdf9-111">Un enregistrement fournisseur a un nom et une URL uniques.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="7fdf9-112">Consultez le contenu de cette page et ignorez cette procédure si un enregistrement pour Litware, Inc.(http://www.litware.com) existe déjà.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (http://www.litware.com) already exists.</span></span>  
4. <span data-ttu-id="7fdf9-113">Tapez Litware, Inc. dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="7fdf9-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="7fdf9-115">Tapez http://www.litware.com dans le champ d'adresse Internet.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-115">In the Internet address field, type 'http://www.litware.com'.</span></span>
    * <span data-ttu-id="7fdf9-116">http://www.litware.com</span><span class="sxs-lookup"><span data-stu-id="7fdf9-116">http://www.litware.com</span></span>  
6. <span data-ttu-id="7fdf9-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-117">Click Save.</span></span>
7. <span data-ttu-id="7fdf9-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-118">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="7fdf9-119">Sélectionner en tant que fournisseur actif</span><span class="sxs-lookup"><span data-stu-id="7fdf9-119">Select as an active provider</span></span>
1. <span data-ttu-id="7fdf9-120">Sélectionnez le fournisseur Litware, Inc. .</span><span class="sxs-lookup"><span data-stu-id="7fdf9-120">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="7fdf9-121">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-121">Click Set active.</span></span>


