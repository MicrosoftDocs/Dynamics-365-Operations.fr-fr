--- 
title: "Créer un fournisseur de configuration et le marquer comme actif pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut créer un fournisseur de configuration pour la génération d'états électroniques (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9ed6f62318cd6806de1b4c9d6aa314c5f0a25500
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-configuration-provider-and-mark-it-as-active-for-electronic-reporting-er"></a><span data-ttu-id="da5e5-103">Créer un fournisseur de configuration et le marquer comme actif pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="da5e5-103">Create a configuration provider and mark it as active for electronic reporting (ER)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="da5e5-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut créer un fournisseur de configuration pour la génération d'états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="da5e5-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="da5e5-105">Chaque configuration ER fait référence au fournisseur en tant que l'auteur de la configuration.</span><span class="sxs-lookup"><span data-stu-id="da5e5-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="da5e5-106">Dans cet exemple, vous allez créer un fournisseur de configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les fournisseurs de configurations ER sont partagés entre toutes les sociétés.</span><span class="sxs-lookup"><span data-stu-id="da5e5-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="da5e5-107">Créer un fournisseur</span><span class="sxs-lookup"><span data-stu-id="da5e5-107">Create a provider</span></span>
1. <span data-ttu-id="da5e5-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="da5e5-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="da5e5-109">Cliquez sur Fournisseurs de configuration.</span><span class="sxs-lookup"><span data-stu-id="da5e5-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="da5e5-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="da5e5-110">Click New.</span></span>
    * <span data-ttu-id="da5e5-111">Un enregistrement fournisseur a un nom et une URL uniques.</span><span class="sxs-lookup"><span data-stu-id="da5e5-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="da5e5-112">Examinez le contenu de cette page et ignorez cette procédure s'il s'agit d'un enregistrement pour Litware, Inc. (`http://www.litware.com`) qui existe déjà.</span><span class="sxs-lookup"><span data-stu-id="da5e5-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (`http://www.litware.com`) already exists.</span></span>  
4. <span data-ttu-id="da5e5-113">Tapez Litware, Inc. dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="da5e5-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="da5e5-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="da5e5-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="da5e5-115">Dans le champ Adresse Internet, tapez `http://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="da5e5-115">In the Internet address field, type `http://www.litware.com`.</span></span>
6. <span data-ttu-id="da5e5-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="da5e5-116">Click Save.</span></span>
7. <span data-ttu-id="da5e5-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="da5e5-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="da5e5-118">Sélectionner en tant que fournisseur actif</span><span class="sxs-lookup"><span data-stu-id="da5e5-118">Select as an active provider</span></span>
1. <span data-ttu-id="da5e5-119">Sélectionnez le fournisseur Litware, Inc. .</span><span class="sxs-lookup"><span data-stu-id="da5e5-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="da5e5-120">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="da5e5-120">Click Set active.</span></span>


