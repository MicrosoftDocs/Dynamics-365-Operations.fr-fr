--- 
title: "Ajouter une contrainte d'expression à un modèle de configuration de produit"
description: "Cette procédure montre comment ajouter une nouvelle expression de contrainte à un modèle de configuration de produit."
author: YuyuScheller
manager: AnnBe
ms.date: 10/27/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8db46c5b8361c96745b440c0d0684e18c06a6c6f
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="0d891-103">Ajouter une contrainte d'expression à un modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="0d891-103">Add an expression constraint to a product configuration model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0d891-104">Cette procédure montre comment ajouter une nouvelle expression de contrainte à un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="0d891-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="0d891-105">Elle indique la manière dont vous pouvez demander que la protection des coins soit appliquée à un haut-parleur si l'utilisateur a sélectionné une grille avant métallique.</span><span class="sxs-lookup"><span data-stu-id="0d891-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="0d891-106">Cette procédure utilise le composant Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="0d891-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="create-an-expression-constraint"></a><span data-ttu-id="0d891-107">Création d'un contrainte d'expression</span><span class="sxs-lookup"><span data-stu-id="0d891-107">Create an expression constraint</span></span>
1. <span data-ttu-id="0d891-108">Cliquez sur Définition du modèle de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="0d891-108">Click Product variant model definition.</span></span>
2. <span data-ttu-id="0d891-109">Cliquez sur Modèles de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="0d891-109">Click Product configuration models.</span></span>
3. <span data-ttu-id="0d891-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0d891-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="0d891-111">Cet exemple utilise le modèle de Haut-parleur haut de gamme.</span><span class="sxs-lookup"><span data-stu-id="0d891-111">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="0d891-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0d891-112">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="0d891-113">Développez la section Contraintes.</span><span class="sxs-lookup"><span data-stu-id="0d891-113">Expand the Constraints section.</span></span>
6. <span data-ttu-id="0d891-114">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0d891-114">Click Add.</span></span>
7. <span data-ttu-id="0d891-115">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="0d891-115">Click Create.</span></span>
8. <span data-ttu-id="0d891-116">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="0d891-116">In the Name field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="0d891-117">Entrer une expression</span><span class="sxs-lookup"><span data-stu-id="0d891-117">Enter expression</span></span>
1. <span data-ttu-id="0d891-118">Cliquez sur Modifier l'expression.</span><span class="sxs-lookup"><span data-stu-id="0d891-118">Click Edit expression.</span></span>
    * <span data-ttu-id="0d891-119">Si vous déverrouillez l'interface utilisateur dans l'enregistreur de tâche à cette étape, vous pouvez utiliser IntelliSense et la liste des symboles pour établir l'expression de contrainte.</span><span class="sxs-lookup"><span data-stu-id="0d891-119">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="0d891-120">Dans le champ ConstraintBody, entrez « Implies[FrontGrill=="Métal", CornerProtection] ».</span><span class="sxs-lookup"><span data-stu-id="0d891-120">In the ConstraintBody field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="0d891-121">Cette expression logique stipule : si la grille avant est en métal, il faut sélectionner l'option de protection des coins.</span><span class="sxs-lookup"><span data-stu-id="0d891-121">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="0d891-122">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="0d891-122">Click Validate.</span></span>
    * <span data-ttu-id="0d891-123">La fonction de validation fonctionne via l'expression de contrainte et vérifie les erreurs de syntaxe.</span><span class="sxs-lookup"><span data-stu-id="0d891-123">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="0d891-124">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="0d891-124">Click Close.</span></span>
5. <span data-ttu-id="0d891-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0d891-125">Click OK.</span></span>


