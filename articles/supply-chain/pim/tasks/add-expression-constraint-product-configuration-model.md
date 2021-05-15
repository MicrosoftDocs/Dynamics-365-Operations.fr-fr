---
title: Ajouter une contrainte d’expression à un modèle de configuration de produit
description: Cette procédure montre comment ajouter une nouvelle expression de contrainte à un modèle de configuration de produit.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cd5475e48cbcd8dcee6b228297f58e364ac503d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920879"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="8251a-103">Ajouter une contrainte d’expression à un modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="8251a-103">Add an expression constraint to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8251a-104">Cette procédure montre comment ajouter une nouvelle expression de contrainte à un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="8251a-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="8251a-105">Elle indique la manière dont vous pouvez demander que la protection des coins soit appliquée à un haut-parleur si l’utilisateur a sélectionné une grille avant métallique.</span><span class="sxs-lookup"><span data-stu-id="8251a-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="8251a-106">Cette procédure utilise le composant Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="8251a-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>

## <a name="create-an-expression-constraint"></a><span data-ttu-id="8251a-107">Création d’un contrainte d’expression</span><span class="sxs-lookup"><span data-stu-id="8251a-107">Create an expression constraint</span></span>

1. <span data-ttu-id="8251a-108">Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.</span><span class="sxs-lookup"><span data-stu-id="8251a-108">Go to **Product information management \> Products \> Product configuration models**.</span></span>
3. <span data-ttu-id="8251a-109">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="8251a-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8251a-110">Cet exemple utilise le modèle de Haut-parleur haut de gamme.</span><span class="sxs-lookup"><span data-stu-id="8251a-110">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="8251a-111">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8251a-111">In the list, select the link in the selected row.</span></span>
5. <span data-ttu-id="8251a-112">Développez la section **Contraintes**.</span><span class="sxs-lookup"><span data-stu-id="8251a-112">Expand the **Constraints** section.</span></span>
6. <span data-ttu-id="8251a-113">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="8251a-113">Select **Add**.</span></span>
7. <span data-ttu-id="8251a-114">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="8251a-114">Select **Create**.</span></span>
8. <span data-ttu-id="8251a-115">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="8251a-115">In the **Name** field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="8251a-116">Entrer une expression</span><span class="sxs-lookup"><span data-stu-id="8251a-116">Enter expression</span></span>

1. <span data-ttu-id="8251a-117">Sélectionnez **Modifier l’expression**.</span><span class="sxs-lookup"><span data-stu-id="8251a-117">Select **Edit expression**.</span></span>
    * <span data-ttu-id="8251a-118">Si vous déverrouillez l’interface utilisateur dans l’enregistreur de tâche à cette étape, vous pouvez utiliser IntelliSense et la liste des symboles pour établir l’expression de contrainte.</span><span class="sxs-lookup"><span data-stu-id="8251a-118">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="8251a-119">Dans le champ **ConstraintBody**, entrez « Implies[FrontGrill=="Métal", CornerProtection] ».</span><span class="sxs-lookup"><span data-stu-id="8251a-119">In the **ConstraintBody** field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="8251a-120">Cette expression logique stipule : si la grille avant est en métal, il faut sélectionner l’option de protection des coins.</span><span class="sxs-lookup"><span data-stu-id="8251a-120">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="8251a-121">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8251a-121">Select **Validate**.</span></span>
    * <span data-ttu-id="8251a-122">La fonction de validation fonctionne via l’expression de contrainte et vérifie les erreurs de syntaxe.</span><span class="sxs-lookup"><span data-stu-id="8251a-122">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="8251a-123">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="8251a-123">Select **Close**.</span></span>
5. <span data-ttu-id="8251a-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8251a-124">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]