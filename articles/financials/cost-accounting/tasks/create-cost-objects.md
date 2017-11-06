--- 
title: "Créer des objets de coût"
description: "Cette procédure indique comment créer des objets de coût en important la dimension financière Centre de coût Dynamics 365 for Finance and Operations, Enterprise Edition dans le contrôle de gestion via un connecteur de données."
author: YuyuScheller
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5d43274aed2edbb91fd4e399cb8d45e91646b055
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-cost-objects"></a><span data-ttu-id="52d76-103">Créer des objets de coût</span><span class="sxs-lookup"><span data-stu-id="52d76-103">Create cost objects</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="52d76-104">Cette procédure indique comment créer des objets de coût en important la dimension financière Centre de coût Dynamics 365 for Finance and Operations, Enterprise Edition dans le contrôle de gestion via un connecteur de données.</span><span class="sxs-lookup"><span data-stu-id="52d76-104">This procedure shows how to create cost objects by importing the Dynamics 365 for Finance and Operations, Enterprise edition cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="52d76-105">La société fictive USMF a été utilisée pour créer cette procédure.</span><span class="sxs-lookup"><span data-stu-id="52d76-105">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="52d76-106">Cette procédure s'applique à une fonction Contrôle de gestion qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="52d76-106">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-objects"></a><span data-ttu-id="52d76-107">Créer des objets de coût</span><span class="sxs-lookup"><span data-stu-id="52d76-107">Create new cost objects</span></span>
1. <span data-ttu-id="52d76-108">Accédez à Contrôle de gestion > Dimensions > Dimensions d'objet de coût.</span><span class="sxs-lookup"><span data-stu-id="52d76-108">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="52d76-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="52d76-109">Click New.</span></span>
3. <span data-ttu-id="52d76-110">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="52d76-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="52d76-111">Dans le champ Connecteur de données pour les membres de la dimension, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="52d76-111">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="52d76-112">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="52d76-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="52d76-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="52d76-113">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="52d76-114">Configurer le connecteur de données</span><span class="sxs-lookup"><span data-stu-id="52d76-114">Configure the data connector</span></span>
1. <span data-ttu-id="52d76-115">Cliquez sur Configurer le fournisseur du membre de dimension.</span><span class="sxs-lookup"><span data-stu-id="52d76-115">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="52d76-116">Sélectionnez CostCenter pour importer la dimension CostCenter dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="52d76-116">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="52d76-117">Dans le champ Nom de dimension, sélectionnez Centre de coût.</span><span class="sxs-lookup"><span data-stu-id="52d76-117">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="52d76-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="52d76-118">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="52d76-119">Importer les centres de coût</span><span class="sxs-lookup"><span data-stu-id="52d76-119">Import cost centers</span></span>
1. <span data-ttu-id="52d76-120">Cliquez sur Importer les membres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="52d76-120">Click Import dimension members.</span></span>
2. <span data-ttu-id="52d76-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="52d76-121">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="52d76-122">Afficher les centres de coût importés</span><span class="sxs-lookup"><span data-stu-id="52d76-122">View the imported cost centers</span></span>
1. <span data-ttu-id="52d76-123">Cliquez sur Afficher les membres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="52d76-123">Click View dimension members.</span></span>


