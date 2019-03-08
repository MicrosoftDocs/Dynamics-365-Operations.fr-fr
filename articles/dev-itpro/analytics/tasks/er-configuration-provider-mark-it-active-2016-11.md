---
title: Créer des fournisseurs de configuration et les marquer comme actifs
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut créer un fournisseur de configuration pour la génération d'états électroniques (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13a27c2fec2a2b226e9ae8d5b8f9a61e8b79ceb0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "362232"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="9f978-103">Créer des fournisseurs de configuration et les marquer comme actifs</span><span class="sxs-lookup"><span data-stu-id="9f978-103">Create configuration providers and mark them as active</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9f978-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut créer un fournisseur de configuration pour la génération d'états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="9f978-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="9f978-105">Chaque configuration ER fait référence au fournisseur en tant que l'auteur de la configuration.</span><span class="sxs-lookup"><span data-stu-id="9f978-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="9f978-106">Dans cet exemple, vous allez créer un fournisseur de configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les fournisseurs de configurations ER sont partagés entre toutes les sociétés.</span><span class="sxs-lookup"><span data-stu-id="9f978-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="9f978-107">Créer un fournisseur</span><span class="sxs-lookup"><span data-stu-id="9f978-107">Create a provider</span></span>
1. <span data-ttu-id="9f978-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="9f978-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="9f978-109">Cliquez sur Fournisseurs de configuration.</span><span class="sxs-lookup"><span data-stu-id="9f978-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="9f978-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9f978-110">Click New.</span></span>
    * <span data-ttu-id="9f978-111">Un enregistrement fournisseur a un nom et une URL uniques.</span><span class="sxs-lookup"><span data-stu-id="9f978-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="9f978-112">Examinez le contenu de cette page et ignorez cette procédure si un enregistrement pour Litware, Inc. (http://www.litware.com) existe déjà.</span><span class="sxs-lookup"><span data-stu-id="9f978-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (http://www.litware.com) already exists.</span></span>  
4. <span data-ttu-id="9f978-113">Tapez Litware, Inc. dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="9f978-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="9f978-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="9f978-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="9f978-115">Dans le champ Adresse Internet, tapez « http://www.litware.com ».</span><span class="sxs-lookup"><span data-stu-id="9f978-115">In the Internet address field, type 'http://www.litware.com'.</span></span>
    * http://www.litware.com  
6. <span data-ttu-id="9f978-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9f978-116">Click Save.</span></span>
7. <span data-ttu-id="9f978-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9f978-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="9f978-118">Sélectionner en tant que fournisseur actif</span><span class="sxs-lookup"><span data-stu-id="9f978-118">Select as an active provider</span></span>
1. <span data-ttu-id="9f978-119">Sélectionnez le fournisseur Litware, Inc. .</span><span class="sxs-lookup"><span data-stu-id="9f978-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="9f978-120">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="9f978-120">Click Set active.</span></span>

