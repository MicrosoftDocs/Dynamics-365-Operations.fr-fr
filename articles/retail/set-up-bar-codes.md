---
title: "Paramétrer les codes-barres"
description: "Cet article décrit l'utilisation des codes-barres dans Microsoft Dynamics 365 for Retail."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bfb47e653cc3ef36135fd7c4f60771a354699af7
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-bar-codes"></a><span data-ttu-id="6c5a1-103">Paramétrer les codes-barres</span><span class="sxs-lookup"><span data-stu-id="6c5a1-103">Set up bar codes</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="6c5a1-104">Cet article décrit l'utilisation des codes-barres dans Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-104">This article describes how to use bar codes in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="6c5a1-105">Vous pouvez utiliser les codes-barres pour acheter et vendre des articles, des variantes de produit de suivi, et paramétrer les clients et les employés.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-105">You can use bar codes to purchase and sell products, track product variants, and set up customers and employees.</span></span> <span data-ttu-id="6c5a1-106">Vous pouvez également utiliser les codes-barres pour émettre et endosser des coupons, des cartes cadeaux et des avoirs.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-106">You can also use bar codes to issue and endorse coupons, gift cards, and credit memos.</span></span> <span data-ttu-id="6c5a1-107">Vous pouvez paramétrer les produits vendus au détail de façon à ce qu'ils disposent de codes-barres standard ou de codes-barres internes personnalisés.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-107">You can set up retail products so that they have standard bar codes or custom, in-house bar codes.</span></span> <span data-ttu-id="6c5a1-108">Les produits peuvent avoir plusieurs codes-barres.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-108">Products can have more than one bar code.</span></span> <span data-ttu-id="6c5a1-109">Par exemple, un produit peut avoir plusieurs codes-barres si celui-ci provient de différents fabricants ou s'il comporte des variantes de taille, de style ou de couleur.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-109">For example, a product might have multiple bar codes if it comes from various manufacturers, or if it has variants that are based on size, style, or color.</span></span> <span data-ttu-id="6c5a1-110">Les codes-barres peuvent inclure le poids ou le prix du produit.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-110">Bar codes can include the weight or price of the product.</span></span> <span data-ttu-id="6c5a1-111">Les masques de codes-barres sont des modèles qui sont utilisés pour créer des codes-barres.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-111">Bar code masks are templates that are used to create bar codes.</span></span> <span data-ttu-id="6c5a1-112">**Remarque :** Si vous attribuez un code-barres unique à chaque combinaison de variantes vous pouvez scanner le code-barres au niveau de la caisse enregistreuse et laisser le programme déterminer quelle variante du produit est vendue.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-112">**Note:** If you assign a unique bar code to each variant combination, you can scan the bar code at the register and let the program determine which variant of the product is being sold.</span></span> <span data-ttu-id="6c5a1-113">Vous pouvez également obtenir et consulter des statistiques de vente par variante.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-113">You can also collect and view statistics about sales by variant.</span></span> <span data-ttu-id="6c5a1-114">Chaque groupe de tailles, de couleurs et de styles peut se voir affecter un numéro unique qui identifie ce groupe dans le code-barres.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-114">Each size, color, and style group can be assigned a unique number that identifies that group in the bar code.</span></span> <span data-ttu-id="6c5a1-115">Dynamics 365 for Retail utilise le masque de code-barres pour générer automatiquement des codes-barres pour chaque combinaison de variantes.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-115">Dynamics 365 for Retail uses the bar code mask to automatically generate bar codes for each variant combination.</span></span> <span data-ttu-id="6c5a1-116">Cette fonctionnalité peut être utile s'il y a beaucoup de tailles, de couleurs et de styles, car le nombre de combinaisons augmente significativement à l'ajout de chaque nouveau code variante.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-116">This functionality can be useful if there are many sizes, colors, and styles, because the number of combinations increases significantly as each variant code is added.</span></span> <span data-ttu-id="6c5a1-117">Si cette fonctionnalité n'est pas utilisée, les codes-barres doivent être affectés manuellement à chaque combinaison représentant une variante de produit.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-117">If this functionality isn't used, bar codes must be manually assigned to each combination that represents a product variant.</span></span> <span data-ttu-id="6c5a1-118">Vous pouvez créer les codes-barres manuellement ou automatiquement.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-118">You can create bar codes manually or automatically.</span></span> <span data-ttu-id="6c5a1-119">Pour créer des codes-barres, effectuez les tâches suivantes dans l'ordre dans lequel elles sont répertoriées.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-119">To create bar codes, complete the following tasks in the order in which they are listed.</span></span>

1.  <span data-ttu-id="6c5a1-120">[Paramétrage des caractères de masque de code-barres](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="6c5a1-120">[Set up bar code mask characters](set-up-bar-code-masks.md).</span></span>
2.  <span data-ttu-id="6c5a1-121">[Paramétrage de masques de codes-barres](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="6c5a1-121">[Set up bar code masks](set-up-bar-code-masks.md).</span></span>
3.  <span data-ttu-id="6c5a1-122">Configurez les paramétrages des codes-barres.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-122">Configure bar code setups.</span></span>
4.  <span data-ttu-id="6c5a1-123">Créez les codes-barres pour les produits spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6c5a1-123">Create bar codes for products.</span></span>


<a name="see-also"></a><span data-ttu-id="6c5a1-124">Voir également :</span><span class="sxs-lookup"><span data-stu-id="6c5a1-124">See also</span></span>
--------

[<span data-ttu-id="6c5a1-125">Paramétrage de masques de codes-barres</span><span class="sxs-lookup"><span data-stu-id="6c5a1-125">Set up bar code masks</span></span>](set-up-bar-code-masks.md)




