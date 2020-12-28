---
title: Ajouter une contrainte d'expression à un modèle de configuration de produit
description: Cette procédure montre comment ajouter une nouvelle expression de contrainte à un modèle de configuration de produit.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c43d7f768069c5ef201a2823a9aa626b38220073
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427902"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="9dbf1-103">Ajouter une contrainte d'expression à un modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="9dbf1-103">Add an expression constraint to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9dbf1-104">Cette procédure montre comment ajouter une nouvelle expression de contrainte à un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="9dbf1-105">Elle indique la manière dont vous pouvez demander que la protection des coins soit appliquée à un haut-parleur si l'utilisateur a sélectionné une grille avant métallique.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="9dbf1-106">Cette procédure utilise le composant Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="create-an-expression-constraint"></a><span data-ttu-id="9dbf1-107">Création d'un contrainte d'expression</span><span class="sxs-lookup"><span data-stu-id="9dbf1-107">Create an expression constraint</span></span>
1. <span data-ttu-id="9dbf1-108">Cliquez sur Définition du modèle de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-108">Click Product variant model definition.</span></span>
2. <span data-ttu-id="9dbf1-109">Cliquez sur Modèles de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-109">Click Product configuration models.</span></span>
3. <span data-ttu-id="9dbf1-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9dbf1-111">Cet exemple utilise le modèle de Haut-parleur haut de gamme.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-111">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="9dbf1-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-112">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="9dbf1-113">Développez la section Contraintes.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-113">Expand the Constraints section.</span></span>
6. <span data-ttu-id="9dbf1-114">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-114">Click Add.</span></span>
7. <span data-ttu-id="9dbf1-115">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-115">Click Create.</span></span>
8. <span data-ttu-id="9dbf1-116">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-116">In the Name field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="9dbf1-117">Entrer une expression</span><span class="sxs-lookup"><span data-stu-id="9dbf1-117">Enter expression</span></span>
1. <span data-ttu-id="9dbf1-118">Cliquez sur Modifier l'expression.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-118">Click Edit expression.</span></span>
    * <span data-ttu-id="9dbf1-119">Si vous déverrouillez l'interface utilisateur dans l'enregistreur de tâche à cette étape, vous pouvez utiliser IntelliSense et la liste des symboles pour établir l'expression de contrainte.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-119">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="9dbf1-120">Dans le champ ConstraintBody, entrez 'Implies[FrontGrill=="Metal", CornerProtection] '.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-120">In the ConstraintBody field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="9dbf1-121">Cette expression logique stipule : si la grille avant est en métal, il faut sélectionner l'option de protection des coins.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-121">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="9dbf1-122">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-122">Click Validate.</span></span>
    * <span data-ttu-id="9dbf1-123">La fonction de validation fonctionne via l'expression de contrainte et vérifie les erreurs de syntaxe.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-123">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="9dbf1-124">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-124">Click Close.</span></span>
5. <span data-ttu-id="9dbf1-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-125">Click OK.</span></span>

