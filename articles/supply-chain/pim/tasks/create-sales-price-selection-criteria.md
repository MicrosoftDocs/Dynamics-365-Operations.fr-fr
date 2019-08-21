---
title: Créer des critères de sélection de prix de vente
description: Cette procédure indique comment créer un critère de sélection de prix de vente pour les modèles de prix de vente basés sur des attributs.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72940f719baca5e8042c2f2caa8abbacb7d8264e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844487"
---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="24d72-103">Créer des critères de sélection de prix de vente</span><span class="sxs-lookup"><span data-stu-id="24d72-103">Create sales price selection criteria</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="24d72-104">Cette procédure indique comment créer un critère de sélection de prix de vente pour les modèles de prix de vente basés sur des attributs.</span><span class="sxs-lookup"><span data-stu-id="24d72-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="24d72-105">Cette procédure nécessite qu'au moins un modèle de prix de vente soit disponible.</span><span class="sxs-lookup"><span data-stu-id="24d72-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="24d72-106">Cet exemple utilise le modèle de prix du modèle de prix de vente de la solution Haut-parleur dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="24d72-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="24d72-107">Généralement, un responsable de produit utilise cette procédure.</span><span class="sxs-lookup"><span data-stu-id="24d72-107">Typically, a product manager uses this procedure.</span></span>


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="24d72-108">Ajouter un nouveau critère pour un modèle de prix de vente existant</span><span class="sxs-lookup"><span data-stu-id="24d72-108">Add a new criterion for an existing sales price model</span></span>
1. <span data-ttu-id="24d72-109">Cliquez sur Définition du modèle de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="24d72-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="24d72-110">Cliquez sur Modèles de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="24d72-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="24d72-111">Dans la liste, sélectionnez la ligne du modèle de produit de la solution Haut-parleur, mais ne cliquez pas sur le lien du nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="24d72-111">In the list, select the row for the Speaker solution product model, but don’t click the link for the model name.</span></span>
4. <span data-ttu-id="24d72-112">Dans le volet Actions, cliquez sur Modèle.</span><span class="sxs-lookup"><span data-stu-id="24d72-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="24d72-113">Cliquez sur Critères de modèle de prix.</span><span class="sxs-lookup"><span data-stu-id="24d72-113">Click Price model criteria.</span></span>
6. <span data-ttu-id="24d72-114">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="24d72-114">Click New.</span></span>
7. <span data-ttu-id="24d72-115">Dans le champ Nom, tapez « Groupe de clients 10 ».</span><span class="sxs-lookup"><span data-stu-id="24d72-115">In the Name field, type ‘Customer group 10’.</span></span>
    * <span data-ttu-id="24d72-116">Le nom du critère de modèle de prix permet d'identifier les critères de sélection sous-jacents.</span><span class="sxs-lookup"><span data-stu-id="24d72-116">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
8. <span data-ttu-id="24d72-117">Dans le champ Modèle de prix, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="24d72-117">In the Price model field, enter or select a value.</span></span>
9. <span data-ttu-id="24d72-118">Dans le champ Type de commande, sélectionnez Commande client.</span><span class="sxs-lookup"><span data-stu-id="24d72-118">In the Order type field, select Sales order.</span></span>
    * <span data-ttu-id="24d72-119">Le type de commande détermine les champs de base de données disponibles pour la requête de sélection.</span><span class="sxs-lookup"><span data-stu-id="24d72-119">The order type determines the database fields that will be available for the selection query.</span></span>  
10. <span data-ttu-id="24d72-120">Dans le champ Début de validité, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="24d72-120">In the Valid from field, enter a date.</span></span>
11. <span data-ttu-id="24d72-121">Dans le champ Expiration, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="24d72-121">In the Expire by field, enter a date.</span></span>
12. <span data-ttu-id="24d72-122">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="24d72-122">Click Save.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="24d72-123">Créer la requête pour les critères de sélection</span><span class="sxs-lookup"><span data-stu-id="24d72-123">Create the query for the selection criteria</span></span>
1. <span data-ttu-id="24d72-124">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="24d72-124">Click Edit.</span></span>
2. <span data-ttu-id="24d72-125">Dans le champ Table, sélectionnez Clients.</span><span class="sxs-lookup"><span data-stu-id="24d72-125">In the Table field, select Customers.</span></span> 
3. <span data-ttu-id="24d72-126">Dans le champ Champ, sélectionnez un groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="24d72-126">In the Field field, select Customer group.</span></span>
    * <span data-ttu-id="24d72-127">Dans cet exemple, nous utilisons un groupe de clients spécifique pour les critères de sélection.</span><span class="sxs-lookup"><span data-stu-id="24d72-127">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="24d72-128">Dans le champ Critères, sélectionnez Groupe de clients 10.</span><span class="sxs-lookup"><span data-stu-id="24d72-128">In the Criteria field, select Customer group 10.</span></span> 
5. <span data-ttu-id="24d72-129">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="24d72-129">Click OK.</span></span>

