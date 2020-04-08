---
title: Créer des objets de coût
description: Cette procédure indique comment créer des objets de coût en important la dimension financière Centre de coût dans le contrôle de gestion via un connecteur de données.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed020348e50158362fda7b6b36dcdb17c48b4532
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142315"
---
# <a name="create-cost-objects"></a><span data-ttu-id="08cd8-103">Créer des objets de coût</span><span class="sxs-lookup"><span data-stu-id="08cd8-103">Create cost objects</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="08cd8-104">Cette procédure indique comment créer des objets de coût en important la dimension financière Centre de coût dans le contrôle de gestion via un connecteur de données.</span><span class="sxs-lookup"><span data-stu-id="08cd8-104">This procedure shows how to create cost objects by importing the cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="08cd8-105">La société fictive USMF a été utilisée pour créer cette procédure.</span><span class="sxs-lookup"><span data-stu-id="08cd8-105">The USMF demo company was used to create this procedure.</span></span> 


## <a name="create-new-cost-objects"></a><span data-ttu-id="08cd8-106">Créer des objets de coût</span><span class="sxs-lookup"><span data-stu-id="08cd8-106">Create new cost objects</span></span>
1. <span data-ttu-id="08cd8-107">Accédez à Contrôle de gestion > Dimensions > Dimensions d'objet de coût.</span><span class="sxs-lookup"><span data-stu-id="08cd8-107">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="08cd8-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="08cd8-108">Click New.</span></span>
3. <span data-ttu-id="08cd8-109">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="08cd8-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="08cd8-110">Dans le champ Connecteur de données pour les membres de la dimension, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="08cd8-110">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="08cd8-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="08cd8-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="08cd8-112">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="08cd8-112">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="08cd8-113">Configurer le connecteur de données</span><span class="sxs-lookup"><span data-stu-id="08cd8-113">Configure the data connector</span></span>
1. <span data-ttu-id="08cd8-114">Cliquez sur Configurer le fournisseur du membre de dimension.</span><span class="sxs-lookup"><span data-stu-id="08cd8-114">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="08cd8-115">Sélectionnez CostCenter pour importer la dimension CostCenter dans le contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="08cd8-115">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="08cd8-116">Dans le champ Nom de dimension, sélectionnez Centre de coût.</span><span class="sxs-lookup"><span data-stu-id="08cd8-116">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="08cd8-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="08cd8-117">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="08cd8-118">Importer les centres de coût</span><span class="sxs-lookup"><span data-stu-id="08cd8-118">Import cost centers</span></span>
1. <span data-ttu-id="08cd8-119">Cliquez sur Importer les membres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="08cd8-119">Click Import dimension members.</span></span>
2. <span data-ttu-id="08cd8-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="08cd8-120">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="08cd8-121">Afficher les centres de coût importés</span><span class="sxs-lookup"><span data-stu-id="08cd8-121">View the imported cost centers</span></span>
1. <span data-ttu-id="08cd8-122">Cliquez sur Afficher les membres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="08cd8-122">Click View dimension members.</span></span>

