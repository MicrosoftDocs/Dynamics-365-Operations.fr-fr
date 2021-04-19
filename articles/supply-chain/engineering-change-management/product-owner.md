---
title: Propriétaires de produits
description: Cette rubrique fournit des informations sur la les propriétaires de produits. Un propriétaire de produit est un groupe d’utilisateurs qui sont responsables de produits spécifiques. Seuls les membres du groupe peuvent lancer ces produits. Le propriétaire du produit peut également être utilisé dans le workflow d’approbation.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 679712b2397f220e263da3df07ecd03c99bebf3f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842030"
---
# <a name="product-owners"></a><span data-ttu-id="1c092-106">Propriétaires de produits</span><span class="sxs-lookup"><span data-stu-id="1c092-106">Product owners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1c092-107">Le propriétaire de produit est un groupe d’utilisateurs qui sont responsables de produits spécifiques.</span><span class="sxs-lookup"><span data-stu-id="1c092-107">The product owner is a group of users who are responsible for specific products.</span></span> <span data-ttu-id="1c092-108">Lorsqu’un groupe de propriétaires de produit est affecté à un produit, seuls les membres de ce groupe peuvent valider le produit.</span><span class="sxs-lookup"><span data-stu-id="1c092-108">When a product owner group is assigned to a product, only the members of that group can release the product.</span></span> <span data-ttu-id="1c092-109">Le propriétaire du produit peut également être utilisé dans le workflow d’approbation de la gestion des modifications d’ingénierie.</span><span class="sxs-lookup"><span data-stu-id="1c092-109">The product owner can also be used in the approval workflow in engineering change management.</span></span>

<span data-ttu-id="1c092-110">Les propriétaires de produit sont des paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="1c092-110">Product owners are global settings.</span></span> <span data-ttu-id="1c092-111">Par conséquent, ils sont disponibles pour toutes les entité juridique.</span><span class="sxs-lookup"><span data-stu-id="1c092-111">Therefore, they are available to all legal entities.</span></span>

## <a name="create-a-product-owner-group"></a><span data-ttu-id="1c092-112">Créer un groupe de propriétaires de produit</span><span class="sxs-lookup"><span data-stu-id="1c092-112">Create a product owner group</span></span>

<span data-ttu-id="1c092-113">Pour créer un groupe de propriétaires de produit et y ajouter des membres, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1c092-113">To create a product owner group and add members to it, follow these steps.</span></span>

1. <span data-ttu-id="1c092-114">Aller à **Gestion des modifications d’ingénierie \> Configurer \> Propriétaires de produit**.</span><span class="sxs-lookup"><span data-stu-id="1c092-114">Go to **Engineering change management \> Setup \> Product owners**.</span></span>
2. <span data-ttu-id="1c092-115">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1c092-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="1c092-116">Dans le champ **Propriétaire de produit**, entrez un nom pour le groupe.</span><span class="sxs-lookup"><span data-stu-id="1c092-116">In the **Product owner** field, enter a name for the group.</span></span>
4. <span data-ttu-id="1c092-117">Dans le champ **Nom**, entrez une description du groupe.</span><span class="sxs-lookup"><span data-stu-id="1c092-117">In the **Name** field, enter a description of the group.</span></span>
5. <span data-ttu-id="1c092-118">Sur le raccourci **Membres**, ajoutez les nœuds de calcul qui doivent être membres du groupe.</span><span class="sxs-lookup"><span data-stu-id="1c092-118">On the **Members** FastTab, add the workers who should be members of the group.</span></span>

## <a name="assign-a-product-owner-to-a-product"></a><span data-ttu-id="1c092-119">Affecter un propriétaire de produits à un produit</span><span class="sxs-lookup"><span data-stu-id="1c092-119">Assign a product owner to a product</span></span>

<span data-ttu-id="1c092-120">Pour affecter un propriétaire de produit à un produit, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1c092-120">To assign a product owner to a product, follow these steps.</span></span>

1. <span data-ttu-id="1c092-121">Ouvrez la page **Détails du produit** pour le produit ou le produit générique concerné.</span><span class="sxs-lookup"><span data-stu-id="1c092-121">Open the **Product details** page for the relevant product or product master.</span></span>
1. <span data-ttu-id="1c092-122">Sur le raccourci **Général**, définissez le champ **Propriétaire du produit** sur le nom du groupe de propriétaires de produit concerné.</span><span class="sxs-lookup"><span data-stu-id="1c092-122">On the **General** FastTab, set the **Product owner** field to the name of the relevant product owner group.</span></span>

<span data-ttu-id="1c092-123">Lorsqu’un propriétaire de produit est affecté à un produit, seuls les membres du groupe de propriétaires de produit peuvent modifier le paramètre **Propriétaire du produit**.</span><span class="sxs-lookup"><span data-stu-id="1c092-123">While a product owner is assigned to a product, only the members of the product owner group can edit the **Product owner** setting.</span></span>

<span data-ttu-id="1c092-124">Le propriétaire de produit est également visible sur la page **Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="1c092-124">The product owner is also visible on the **Released products** page.</span></span>

## <a name="product-owners-and-product-releases"></a><span data-ttu-id="1c092-125">Propriétaires de produits et versions de produits</span><span class="sxs-lookup"><span data-stu-id="1c092-125">Product owners and product releases</span></span>

<span data-ttu-id="1c092-126">Seuls les utilisateurs appartenant au groupe de propriétaires de produit d’un produit peuvent lancer ce produit.</span><span class="sxs-lookup"><span data-stu-id="1c092-126">Only users from a product's product owner group can release that product.</span></span> <span data-ttu-id="1c092-127">Cependant, il existe une exception lorsque le produit est un élément enfant et que son parent est libéré par le propriétaire du parent.</span><span class="sxs-lookup"><span data-stu-id="1c092-127">However, there is an exception when the product is a child item, and its parent is released by the parent's owner.</span></span> <span data-ttu-id="1c092-128">En d’autres termes, si le produit fait partie de la nomenclature d’un autre produit, le système ne vérifie pas le propriétaire du produit de chaque article de la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="1c092-128">In other words, if the product is part of the BOM of another product, the system doesn't check the product owner of each item in the BOM.</span></span> <span data-ttu-id="1c092-129">Il vérifie uniquement le propriétaire du produit de l’article parent.</span><span class="sxs-lookup"><span data-stu-id="1c092-129">It checks only the product owner of the parent item.</span></span>

<span data-ttu-id="1c092-130">Par exemple, le produit X est affecté au groupe de propriétaires de produits *Armoires design*.</span><span class="sxs-lookup"><span data-stu-id="1c092-130">For example, product X is assigned to the *Design cabinets* product owner group.</span></span> <span data-ttu-id="1c092-131">Le produit X fait également partie de la nomenclature du produit Y, qui est affectée au groupe de propriétaires de produits *Concevoir des haut-parleurs*.</span><span class="sxs-lookup"><span data-stu-id="1c092-131">Product X is also part of the BOM of product Y, which is assigned to the *Design Speakers* product owner group.</span></span> <span data-ttu-id="1c092-132">Si un utilisateur du groupe de propriétaires de produits *Concevoir des haut-parleurs* lance le produit Y et sa nomenclature, le produit X sera publié avec le produit Y.</span><span class="sxs-lookup"><span data-stu-id="1c092-132">If a user from the *Design Speakers* product owner group releases product Y and its BOM, product X will be released together with product Y.</span></span>

## <a name="product-owners-and-approvals"></a><span data-ttu-id="1c092-133">Propriétaires de produits et approbations</span><span class="sxs-lookup"><span data-stu-id="1c092-133">Product owners and approvals</span></span>

<span data-ttu-id="1c092-134">Étant donné que les propriétaires de produits savent si des modifications techniques spécifiques bénéficieront à leurs produits, il est souvent judicieux de les inclure dans le processus d’approbation de la gestion des modifications techniques.</span><span class="sxs-lookup"><span data-stu-id="1c092-134">Because product owners know whether specific engineering changes will benefit their products, it often makes sense to include them as part of the approval process in engineering change management.</span></span> <span data-ttu-id="1c092-135">Vous pouvez mettre en œuvre cette approche en configurant les propriétaires de produit en tant que fournisseurs participants dans les workflows utilisés pour la gestion des modifications techniques.</span><span class="sxs-lookup"><span data-stu-id="1c092-135">You can implement this approach by setting up the product owners as participant providers in the workflows that are used for engineering change management.</span></span> <span data-ttu-id="1c092-136">Le système attribuera ensuite des tâches d’approbation dans les workflows, en fonction des produits qui sont dans les demandes de modification technique et les ordres de modification technique.</span><span class="sxs-lookup"><span data-stu-id="1c092-136">The system will then assign approval tasks in the workflows, based on the products that are in engineering change requests and engineering change orders.</span></span> <span data-ttu-id="1c092-137">Pour plus d’informations, voir [Gérer modifications des produits techniques](engineering-change-management.md).</span><span class="sxs-lookup"><span data-stu-id="1c092-137">For more information, see [Manage changes to engineering products](engineering-change-management.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]