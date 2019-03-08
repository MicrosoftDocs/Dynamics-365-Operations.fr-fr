---
title: Créer des objets de coût
description: Cette procédure indique comment créer des objets de coût en important la dimension financière Centre de coût Dynamics 365 for Finance and Operations, Enterprise Edition dans le contrôle de gestion via un connecteur de données.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e12de1d51658092fb19f652cef7c1cc78b255b5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "322672"
---
# <a name="create-cost-objects"></a><span data-ttu-id="e635f-103">Créer des objets de coût</span><span class="sxs-lookup"><span data-stu-id="e635f-103">Create cost objects</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e635f-104">Cette procédure indique comment créer des objets de coût en important la dimension financière Centre de coût Dynamics 365 for Finance and Operations, Enterprise Edition dans le contrôle de gestion via un connecteur de données.</span><span class="sxs-lookup"><span data-stu-id="e635f-104">This procedure shows how to create cost objects by importing the Dynamics 365 for Finance and Operations, Enterprise edition cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="e635f-105">La société fictive USMF a été utilisée pour créer cette procédure.</span><span class="sxs-lookup"><span data-stu-id="e635f-105">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="e635f-106">Cette procédure s'applique à une fonction du contrôle de gestion qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="e635f-106">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-objects"></a><span data-ttu-id="e635f-107">Créer des objets de coût</span><span class="sxs-lookup"><span data-stu-id="e635f-107">Create new cost objects</span></span>
1. <span data-ttu-id="e635f-108">Accédez à Contrôle de gestion > Dimensions > Dimensions d'objet de coût.</span><span class="sxs-lookup"><span data-stu-id="e635f-108">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="e635f-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e635f-109">Click New.</span></span>
3. <span data-ttu-id="e635f-110">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e635f-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="e635f-111">Dans le champ Connecteur de données pour les membres de la dimension, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e635f-111">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="e635f-112">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e635f-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="e635f-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e635f-113">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="e635f-114">Configurer le connecteur de données</span><span class="sxs-lookup"><span data-stu-id="e635f-114">Configure the data connector</span></span>
1. <span data-ttu-id="e635f-115">Cliquez sur Configurer le fournisseur du membre de dimension.</span><span class="sxs-lookup"><span data-stu-id="e635f-115">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="e635f-116">Sélectionnez CostCenter pour importer la dimension CostCenter dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="e635f-116">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="e635f-117">Dans le champ Nom de dimension, sélectionnez Centre de coût.</span><span class="sxs-lookup"><span data-stu-id="e635f-117">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="e635f-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e635f-118">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="e635f-119">Importer les centres de coût</span><span class="sxs-lookup"><span data-stu-id="e635f-119">Import cost centers</span></span>
1. <span data-ttu-id="e635f-120">Cliquez sur Importer les membres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="e635f-120">Click Import dimension members.</span></span>
2. <span data-ttu-id="e635f-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e635f-121">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="e635f-122">Afficher les centres de coût importés</span><span class="sxs-lookup"><span data-stu-id="e635f-122">View the imported cost centers</span></span>
1. <span data-ttu-id="e635f-123">Cliquez sur Afficher les membres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="e635f-123">Click View dimension members.</span></span>

