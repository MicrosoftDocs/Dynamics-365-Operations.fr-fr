---
title: Paramétrer la tarification par attribut pour les produits configurables
description: Cette rubrique explique comment paramétrer la tarification basée sur des attributs.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c30c520e7265c2676937f5191844f6789c364e6
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921239"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="107f4-103">Paramétrer la tarification par attribut pour les produits configurables</span><span class="sxs-lookup"><span data-stu-id="107f4-103">Set up attribute-based pricing for configurable products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="107f4-104">Cette rubrique explique comment paramétrer la tarification basée sur des attributs.</span><span class="sxs-lookup"><span data-stu-id="107f4-104">This topic explains how to set up attribute-based pricing.</span></span> <span data-ttu-id="107f4-105">Comme condition préalable, vous devez avoir un modèle de configuration de produit contenant un ou plusieurs composants et attributs.</span><span class="sxs-lookup"><span data-stu-id="107f4-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="107f4-106">Cet exemple utilise le modèle de produit Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="107f4-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="107f4-107">Généralement, un responsable de produit utilise cette procédure.</span><span class="sxs-lookup"><span data-stu-id="107f4-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="107f4-108">Créer un modèle de prix</span><span class="sxs-lookup"><span data-stu-id="107f4-108">Create a new price model</span></span>

1. <span data-ttu-id="107f4-109">Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.</span><span class="sxs-lookup"><span data-stu-id="107f4-109">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="107f4-110">Dans la liste, sélectionnez la ligne **Haut-parleur haut de gamme**, mais ne cliquez pas sur le lien du nom.</span><span class="sxs-lookup"><span data-stu-id="107f4-110">In the list, select the **High End Speaker** line, but don't select the link for the name.</span></span>
1. <span data-ttu-id="107f4-111">Dans le volet Actions, sélectionnez **Modèle**.</span><span class="sxs-lookup"><span data-stu-id="107f4-111">On the Action Pane, select **Model**.</span></span>
1. <span data-ttu-id="107f4-112">Sélectionnez **Modèles de prix**.</span><span class="sxs-lookup"><span data-stu-id="107f4-112">Select **Price models**.</span></span>
1. <span data-ttu-id="107f4-113">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="107f4-113">Select **New**.</span></span>
1. <span data-ttu-id="107f4-114">Dans le champ **Nom du modèle de prix**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="107f4-114">In the **Price model name** field, type a value.</span></span> <span data-ttu-id="107f4-115">Utilisez un nom qui permet d’identifier facilement le modèle.</span><span class="sxs-lookup"><span data-stu-id="107f4-115">Use a name that makes the model easy to identify.</span></span>  
1. <span data-ttu-id="107f4-116">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="107f4-116">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="107f4-117">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="107f4-117">Select **Save**.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="107f4-118">Ajouter des éléments de prix</span><span class="sxs-lookup"><span data-stu-id="107f4-118">Add price elements</span></span>

1. <span data-ttu-id="107f4-119">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="107f4-119">Select **Edit**.</span></span> <span data-ttu-id="107f4-120">Chaque composant d’un modèle de produit peut avoir un élément de prix de base et plusieurs règles d’expression de prix.</span><span class="sxs-lookup"><span data-stu-id="107f4-120">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="107f4-121">Vous pouvez également ajouter des prix dans différentes devises.</span><span class="sxs-lookup"><span data-stu-id="107f4-121">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="107f4-122">Dans le champ **Expression de prix de base**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="107f4-122">In the **Base price expression** field, type a value.</span></span> <span data-ttu-id="107f4-123">Entrez 100, par exemple.</span><span class="sxs-lookup"><span data-stu-id="107f4-123">For example, type 100.</span></span> <span data-ttu-id="107f4-124">Une expression de prix de base peut être une valeur numérique, ou elle peut consister en un calcul arithmétique qui implique un ou plusieurs attributs.</span><span class="sxs-lookup"><span data-stu-id="107f4-124">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="107f4-125">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="107f4-125">Select **Add**.</span></span>
4. <span data-ttu-id="107f4-126">Dans le champ **Nom**, saisissez `Rosewood`.</span><span class="sxs-lookup"><span data-stu-id="107f4-126">In the **Name** field, type `Rosewood`.</span></span> <span data-ttu-id="107f4-127">Le nom de l’expression de prix permet d’identifier ce que représente l’élément de prix.</span><span class="sxs-lookup"><span data-stu-id="107f4-127">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="107f4-128">Dans cet exemple, nous créons un élément de prix pour l’option Finitions du meuble pour haut-parleur en bois de rose.</span><span class="sxs-lookup"><span data-stu-id="107f4-128">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="107f4-129">Sélectionnez **Modifier la condition**.</span><span class="sxs-lookup"><span data-stu-id="107f4-129">Select **Edit condition**.</span></span> <span data-ttu-id="107f4-130">Une condition de prix permet de garantir qu’un élément d’expression de prix est inclus dans le prix de vente uniquement si une combinaison spécifique d’attributs est présente.</span><span class="sxs-lookup"><span data-stu-id="107f4-130">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="107f4-131">Dans le champ **ConstraintBody**, saisissez `CabinetFinish=="Rosewood"`.</span><span class="sxs-lookup"><span data-stu-id="107f4-131">In the **ConstraintBody** field, enter `CabinetFinish=="Rosewood"`.</span></span>
7. <span data-ttu-id="107f4-132">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="107f4-132">Select **OK**.</span></span>
8. <span data-ttu-id="107f4-133">Dans le champ **Expression**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="107f4-133">In the **Expression** field, type a value.</span></span> <span data-ttu-id="107f4-134">Par exemple, saisissez `50`.</span><span class="sxs-lookup"><span data-stu-id="107f4-134">For example, type `50`.</span></span> 
9. <span data-ttu-id="107f4-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="107f4-135">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]