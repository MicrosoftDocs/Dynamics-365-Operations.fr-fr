---
title: "Contraintes de table définies par l'utilisateur et par le système"
description: "Cet article explique les deux types de contraintes de table pour les composants d'un modèle de configuration de produit : définie par l'utilisateur et définie par le système. Les contraintes de table représentent des matrices des combinaisons d'attributs autorisées dans lesquelles chaque ligne définit un ensemble de valeurs d'attribut possibles."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 954c7bb6d9d78b1908331c2bb660fdfb35f5f986
ms.contentlocale: fr-fr
ms.lasthandoff: 01/17/2018

---

# <a name="system-defined-and-user-defined-table-constraints"></a><span data-ttu-id="721fe-104">Contraintes de table définies par l'utilisateur et par le système</span><span class="sxs-lookup"><span data-stu-id="721fe-104">System-defined and user-defined table constraints</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="721fe-105">Cet article explique les deux types de contraintes de table pour les composants d'un modèle de configuration de produit : définie par l'utilisateur et définie par le système.</span><span class="sxs-lookup"><span data-stu-id="721fe-105">This article explains the two types of table constraints for components in a product configuration model -  user-defined and system-defined.</span></span> <span data-ttu-id="721fe-106">Les contraintes de table représentent des matrices des combinaisons d'attributs autorisées dans lesquelles chaque ligne définit un ensemble de valeurs d'attribut possibles.</span><span class="sxs-lookup"><span data-stu-id="721fe-106">Table constraints represent matrices of the allowed attribute combinations, where each row defines one set of possible attribute values.</span></span>

<span data-ttu-id="721fe-107">Les contraintes de table représentent les matrices des combinaisons d'attributs autorisées pour les composants d'un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="721fe-107">Table constraints represent matrices of the combinations of attributes that are allowed for components in a product configuration model.</span></span> <span data-ttu-id="721fe-108">Chaque ligne de la table définit un ensemble de valeurs d'attribut possibles.</span><span class="sxs-lookup"><span data-stu-id="721fe-108">Each row in the table defines one set of possible attribute values.</span></span> <span data-ttu-id="721fe-109">Il existe deux types de contraintes que vous pouvez déclarer dans un modèle de configuration de produit :</span><span class="sxs-lookup"><span data-stu-id="721fe-109">You can declare two types of constraints in a product configuration model:</span></span>

-   <span data-ttu-id="721fe-110">**Contrainte d'expression** – Créez une expression qui définit les relations entre les attributs pour s'assurer que seules les valeurs compatibles peuvent être sélectionnées lors de la configuration d'un produit.</span><span class="sxs-lookup"><span data-stu-id="721fe-110">**Expression constraint** – Create an expression that defines relations between attributes to guarantee that only compatible values can be selected during product configuration.</span></span>
-   <span data-ttu-id="721fe-111">**Contrainte de table** – Créez une table qui définit les combinaisons autorisées pour un ensemble spécifié d'attributs.</span><span class="sxs-lookup"><span data-stu-id="721fe-111">**Table constraint** – Create a table that defines all the combinations that are allowed for a specified set of attributes.</span></span> <span data-ttu-id="721fe-112">Il existe deux types de contraintes de table : les contraintes de table définies par l'utilisateur et les contraintes de table définies par le système.</span><span class="sxs-lookup"><span data-stu-id="721fe-112">Two types of table constraints are available: user-defined table constraints and system-defined table constraints.</span></span>

<span data-ttu-id="721fe-113">Cet article décrit les contraintes de table définies par l'utilisateur et par le système pour les composants d'un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="721fe-113">This article describes user-defined and system-defined table constraints for components in a product configuration model.</span></span>

## <a name="user-defined-table-constraints"></a><span data-ttu-id="721fe-114">Contraintes de table définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="721fe-114">User-defined table constraints</span></span>
<span data-ttu-id="721fe-115">Une contrainte de table définie par l'utilisateur est un type de matrice utilisé pour décrire les combinaisons de valeurs d'attribut définies par les types d'attributs.</span><span class="sxs-lookup"><span data-stu-id="721fe-115">A user-defined table constraint is a type of matrix that is used to describe the combinations of attribute values that are defined by attribute types.</span></span> <span data-ttu-id="721fe-116">Par exemple, si vous produisez des haut-parleurs, vous pouvez inclure des colonnes pour les finitions du meuble et la grille avant dans la contrainte de table définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="721fe-116">For example, if you produce speakers, you can include columns for the cabinet finish and the front grill in the user-defined table constraint.</span></span> <span data-ttu-id="721fe-117">Le type d'attribut pour les finitions du meuble a quatre valeurs, et le type d'attribut pour la grille avant a trois valeurs.</span><span class="sxs-lookup"><span data-stu-id="721fe-117">The attribute type for the cabinet finish has four values, and the attribute type for the front grill has three values.</span></span> <span data-ttu-id="721fe-118">Par conséquent, si les contraintes ne sont pas utilisées, il existe 4 × 3 = 12 combinaisons possibles.</span><span class="sxs-lookup"><span data-stu-id="721fe-118">Therefore, if constraints aren't used, there are 4 × 3 = 12 possible combinations.</span></span> <span data-ttu-id="721fe-119">Toutefois, dans cet exemple, seules six combinaisons sont autorisées, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="721fe-119">However, in this example, only six combinations are allowed, as shown in the following table.</span></span> <span data-ttu-id="721fe-120">Ces informations sont affichées sous l'onglet **Combinaisons autorisées** de la page **Modifier une contrainte de table**.</span><span class="sxs-lookup"><span data-stu-id="721fe-120">This information is displayed on the **Allowed combinations** tab on the **Edit table constraint** page.</span></span>

| <span data-ttu-id="721fe-121">Finitions du meuble</span><span class="sxs-lookup"><span data-stu-id="721fe-121">Cabinet finish</span></span> | <span data-ttu-id="721fe-122">Grille avant</span><span class="sxs-lookup"><span data-stu-id="721fe-122">Front grill</span></span> |
|----------------|-------------|
| <span data-ttu-id="721fe-123">Noir</span><span class="sxs-lookup"><span data-stu-id="721fe-123">Black</span></span>          | <span data-ttu-id="721fe-124">Noir</span><span class="sxs-lookup"><span data-stu-id="721fe-124">Black</span></span>       |
| <span data-ttu-id="721fe-125">Noir</span><span class="sxs-lookup"><span data-stu-id="721fe-125">Black</span></span>          | <span data-ttu-id="721fe-126">Métal</span><span class="sxs-lookup"><span data-stu-id="721fe-126">Metal</span></span>       |
| <span data-ttu-id="721fe-127">Chêne</span><span class="sxs-lookup"><span data-stu-id="721fe-127">Oak</span></span>            | <span data-ttu-id="721fe-128">Noir</span><span class="sxs-lookup"><span data-stu-id="721fe-128">Black</span></span>       |
| <span data-ttu-id="721fe-129">Bois de rose</span><span class="sxs-lookup"><span data-stu-id="721fe-129">Rosewood</span></span>       | <span data-ttu-id="721fe-130">Blanc</span><span class="sxs-lookup"><span data-stu-id="721fe-130">White</span></span>       |
| <span data-ttu-id="721fe-131">Blanc</span><span class="sxs-lookup"><span data-stu-id="721fe-131">White</span></span>          | <span data-ttu-id="721fe-132">Noir</span><span class="sxs-lookup"><span data-stu-id="721fe-132">Black</span></span>       |
| <span data-ttu-id="721fe-133">Blanc</span><span class="sxs-lookup"><span data-stu-id="721fe-133">White</span></span>          | <span data-ttu-id="721fe-134">Blanc</span><span class="sxs-lookup"><span data-stu-id="721fe-134">White</span></span>       |

<span data-ttu-id="721fe-135">Les contraintes de table définies par l'utilisateur sont définies par une entrée de table statique qui fonctionne de la même manière qu'une contrainte d'expression.</span><span class="sxs-lookup"><span data-stu-id="721fe-135">User-defined table constraints are defined by static table input that works the same way as an expression constraint.</span></span> <span data-ttu-id="721fe-136">Lorsque vous utilisez une contrainte de table définie par l'utilisateur, l'avantage est que les tables sont souvent plus facile à créer, à comprendre et à tenir à jour que de longues contraintes d'expression.</span><span class="sxs-lookup"><span data-stu-id="721fe-136">When you use a user-defined table constraint, the advantage is that tables are often easier to create, understand, and maintain than long expression constraints.</span></span>

## <a name="system-defined-table-constraints"></a><span data-ttu-id="721fe-137">Contraintes de table définies par le système</span><span class="sxs-lookup"><span data-stu-id="721fe-137">System-defined table constraints</span></span>
<span data-ttu-id="721fe-138">Une contrainte de table définie par le système crée une mise en correspondance dynamique entre un type d'attribut et un champ dans une table.</span><span class="sxs-lookup"><span data-stu-id="721fe-138">A system-defined table constraint creates a dynamic mapping between an attribute type and a field in a table.</span></span> <span data-ttu-id="721fe-139">Lorsqu'une contrainte de table définie par le système est incluse dans un modèle de configuration de produit, la mise en correspondance garantit que les données de la table s'affichent à la place des valeurs du type d'attribut.</span><span class="sxs-lookup"><span data-stu-id="721fe-139">When a system-defined table constraint is included in a product configuration model, the mapping guarantees that the data in the table is shown instead of the values of the attribute type.</span></span> <span data-ttu-id="721fe-140">Le résultat crée une contrainte dynamique, car le contenu de la table peut être modifié, par exemple, par d'autres modules.</span><span class="sxs-lookup"><span data-stu-id="721fe-140">The result is a dynamic constraint, because the table contents can be modified (for example, by other modules).</span></span>  

<span data-ttu-id="721fe-141">Lorsque vous créez une contrainte de table définie par le système, sélectionnez une table, définissez éventuellement la requête à utiliser, puis associez les types d'attributs aux champs de la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="721fe-141">When you create a system-defined table constraint, you select a table, optionally define the query to use, and then associate attribute types to the fields in the selected table.</span></span> <span data-ttu-id="721fe-142">Les types de champs doivent faire correspondre aux types des types d'attributs.</span><span class="sxs-lookup"><span data-stu-id="721fe-142">The types of fields must match the types of attribute types.</span></span>  

<span data-ttu-id="721fe-143">Avant qu'une contrainte de table puisse prendre effet dans un modèle de configuration de produit, elle doit être incluse dans une contrainte de l'un des composants du modèle.</span><span class="sxs-lookup"><span data-stu-id="721fe-143">Before a table constraint can take effect on a product configuration model, the table constraint must be included in a constraint on one of the model's components.</span></span> <span data-ttu-id="721fe-144">La procédure consiste à créer une nouvelle contrainte, sélectionner le type de contrainte de table, puis sélectionner la définition de contrainte de table à utiliser.</span><span class="sxs-lookup"><span data-stu-id="721fe-144">The procedure is to create a new constraint, select the table constraint type, and then select the table constraint definition to use.</span></span> <span data-ttu-id="721fe-145">Enfin, tous les champs de la contrainte de table doivent être mis en correspondance avec les attributs du modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="721fe-145">Finally, all fields in the table constraint must be mapped to attributes in the product configuration model.</span></span>

<a name="see-also"></a><span data-ttu-id="721fe-146">Voir également :</span><span class="sxs-lookup"><span data-stu-id="721fe-146">See also</span></span>
--------

[<span data-ttu-id="721fe-147">Concepts clés en matière de modèles de configuration du produit</span><span class="sxs-lookup"><span data-stu-id="721fe-147">Key concepts in product configuration models</span></span>](product-configuration-models.md)




