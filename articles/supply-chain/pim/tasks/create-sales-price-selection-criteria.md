---
title: Créer des critères de sélection de prix de vente
description: Cette procédure indique comment créer un critère de sélection de prix de vente pour les modèles de prix de vente basés sur des attributs.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69d22c3321beaa2667ee20bff00acd746714b993
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920529"
---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="ce44b-103">Créer des critères de sélection de prix de vente</span><span class="sxs-lookup"><span data-stu-id="ce44b-103">Create sales price selection criteria</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ce44b-104">Cette procédure indique comment créer un critère de sélection de prix de vente pour les modèles de prix de vente basés sur des attributs.</span><span class="sxs-lookup"><span data-stu-id="ce44b-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="ce44b-105">Cette procédure nécessite qu’au moins un modèle de prix de vente soit disponible.</span><span class="sxs-lookup"><span data-stu-id="ce44b-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="ce44b-106">Cet exemple utilise le modèle de prix du modèle de prix de vente de la solution Haut-parleur dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="ce44b-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="ce44b-107">Généralement, un responsable de produit utilise cette procédure.</span><span class="sxs-lookup"><span data-stu-id="ce44b-107">Typically, a product manager uses this procedure.</span></span>

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="ce44b-108">Ajouter un nouveau critère pour un modèle de prix de vente existant</span><span class="sxs-lookup"><span data-stu-id="ce44b-108">Add a new criterion for an existing sales price model</span></span>

1. <span data-ttu-id="ce44b-109">Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.</span><span class="sxs-lookup"><span data-stu-id="ce44b-109">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="ce44b-110">Dans la liste, sélectionnez la ligne du modèle de produit de la solution Haut-parleur, mais ne cliquez pas sur le lien du nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="ce44b-110">In the list, select the row for the Speaker solution product model, but don't select the link for the model name.</span></span>
1. <span data-ttu-id="ce44b-111">Dans le volet Actions, sélectionnez **Modèle**.</span><span class="sxs-lookup"><span data-stu-id="ce44b-111">On the Action Pane, select **Model**.</span></span>
1. <span data-ttu-id="ce44b-112">Sélectionnez **Critères de modèle de prix**.</span><span class="sxs-lookup"><span data-stu-id="ce44b-112">Select **Price model criteria**.</span></span>
1. <span data-ttu-id="ce44b-113">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ce44b-113">Select **New**.</span></span>
1. <span data-ttu-id="ce44b-114">Dans le champ **Nom**, tapez « Groupe de clients 10 ».</span><span class="sxs-lookup"><span data-stu-id="ce44b-114">In the **Name** field, type 'Customer group 10'.</span></span>
    * <span data-ttu-id="ce44b-115">Le nom du critère de modèle de prix permet d’identifier les critères de sélection sous-jacents.</span><span class="sxs-lookup"><span data-stu-id="ce44b-115">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
1. <span data-ttu-id="ce44b-116">Dans le champ **Modèle de prix**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ce44b-116">In the **Price model** field, enter or select a value.</span></span>
1. <span data-ttu-id="ce44b-117">Dans le champ **Type de commande**, sélectionnez *Commande client*.</span><span class="sxs-lookup"><span data-stu-id="ce44b-117">In the **Order type** field, select *Sales order*.</span></span>
    * <span data-ttu-id="ce44b-118">Le type de commande détermine les champs de base de données disponibles pour la requête de sélection.</span><span class="sxs-lookup"><span data-stu-id="ce44b-118">The order type determines the database fields that will be available for the selection query.</span></span>  
1. <span data-ttu-id="ce44b-119">Dans le champ **Début de validité**, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="ce44b-119">In the **Valid from** field, enter a date.</span></span>
1. <span data-ttu-id="ce44b-120">Dans le champ **Expiration**, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="ce44b-120">In the **Expire by** field, enter a date.</span></span>
1. <span data-ttu-id="ce44b-121">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ce44b-121">Select **Save**.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="ce44b-122">Créer la requête pour les critères de sélection</span><span class="sxs-lookup"><span data-stu-id="ce44b-122">Create the query for the selection criteria</span></span>

1. <span data-ttu-id="ce44b-123">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="ce44b-123">Select **Edit**.</span></span>
2. <span data-ttu-id="ce44b-124">Dans le champ **Table**, sélectionnez *Clients*.</span><span class="sxs-lookup"><span data-stu-id="ce44b-124">In the **Table** field, select *Customers*.</span></span>
3. <span data-ttu-id="ce44b-125">Dans le champ **Champ**, sélectionnez *Groupe de clients*.</span><span class="sxs-lookup"><span data-stu-id="ce44b-125">In the **Field** field, select *Customer group*.</span></span>
    * <span data-ttu-id="ce44b-126">Dans cet exemple, nous utilisons un groupe de clients spécifique pour les critères de sélection.</span><span class="sxs-lookup"><span data-stu-id="ce44b-126">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="ce44b-127">Dans le champ **Critères**, sélectionnez *Groupe de clients 10*.</span><span class="sxs-lookup"><span data-stu-id="ce44b-127">In the **Criteria** field, select *Customer group 10*.</span></span>
5. <span data-ttu-id="ce44b-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce44b-128">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]