---
title: Créer les attributs de lot pour un produit
description: Cette procédure décrit comment créer un attribut de lot, affecter des plages de valeur par défaut et inclure l’attribut à un groupe.
author: ShylaThompson
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PdsBatchAttrib
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5deb35028ee499633fb6b0bb5155df2fd91e643a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820104"
---
# <a name="create-batch-attributes-for-a-product"></a><span data-ttu-id="67d38-103">Créer les attributs de lot pour un produit</span><span class="sxs-lookup"><span data-stu-id="67d38-103">Create batch attributes for a product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="67d38-104">Cette procédure décrit comment créer un attribut de lot, affecter des plages de valeur par défaut et inclure l’attribut à un groupe.</span><span class="sxs-lookup"><span data-stu-id="67d38-104">This procedure shows how to create a batch attribute, assign default value ranges, and include the attribute in a group.</span></span> <span data-ttu-id="67d38-105">La société fictive de démonstration utilisée pour créer cette procédure s’appelle USP2.</span><span class="sxs-lookup"><span data-stu-id="67d38-105">The demo data company used to create this procedure is the USP2 Company.</span></span>

1. <span data-ttu-id="67d38-106">Accédez à Gestion des stocks > Configuration > Lot > Attributs du lot.</span><span class="sxs-lookup"><span data-stu-id="67d38-106">Go to Inventory management > Setup > Batch > Batch attributes.</span></span>
2. <span data-ttu-id="67d38-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="67d38-107">Click New.</span></span>
3. <span data-ttu-id="67d38-108">Dans le champ Attribut, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="67d38-108">In the Attribute field, type a value.</span></span>
4. <span data-ttu-id="67d38-109">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="67d38-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="67d38-110">Dans le champ Type d’attribut, sélectionnez « Fraction ».</span><span class="sxs-lookup"><span data-stu-id="67d38-110">In the Attribute type field, select 'Fraction'.</span></span>
    * <span data-ttu-id="67d38-111">Cette procédure utilise le type Fraction pour activer les valeurs décimales.</span><span class="sxs-lookup"><span data-stu-id="67d38-111">This procedure uses the Fraction type to enable decimal values.</span></span> <span data-ttu-id="67d38-112">Vous pouvez sélectionner d’autres types d’attributs.</span><span class="sxs-lookup"><span data-stu-id="67d38-112">You can select other attribute types.</span></span> <span data-ttu-id="67d38-113">Si vous sélectionnez le type Énumération, vous devez entrer des valeurs contenues dans la liste d’énumération avant de pouvoir entrer une valeur dans le champ Cible.</span><span class="sxs-lookup"><span data-stu-id="67d38-113">If you select the Enumeration type, you must enter values in the enumeration list before you can enter a value in the Target field.</span></span>  
6. <span data-ttu-id="67d38-114">Dans le champ Minimum, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="67d38-114">In the Minimum field, enter a number.</span></span>
7. <span data-ttu-id="67d38-115">Dans le champ Maximum, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="67d38-115">In the Maximum field, enter a number.</span></span>
8. <span data-ttu-id="67d38-116">Dans le champ Incrémenter, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="67d38-116">In the Increment field, enter a number.</span></span>
9. <span data-ttu-id="67d38-117">Dans le champ Cible, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="67d38-117">In the Target field, type a value.</span></span>
10. <span data-ttu-id="67d38-118">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="67d38-118">Click Save.</span></span>
11. <span data-ttu-id="67d38-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="67d38-119">Close the page.</span></span>
12. <span data-ttu-id="67d38-120">Accédez à Gestion des stocks > Configuration > Lot > Groupes d’attributs de lots.</span><span class="sxs-lookup"><span data-stu-id="67d38-120">Go to Inventory management > Setup > Batch > Batch attribute groups.</span></span>
13. <span data-ttu-id="67d38-121">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="67d38-121">Click New.</span></span>
14. <span data-ttu-id="67d38-122">Dans le champ Groupe d’attributs, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="67d38-122">In the Attribute group field, type a value.</span></span>
15. <span data-ttu-id="67d38-123">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="67d38-123">In the Description field, type a value.</span></span>
16. <span data-ttu-id="67d38-124">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="67d38-124">Click Save.</span></span>
17. <span data-ttu-id="67d38-125">Cliquez sur Attributs de groupe.</span><span class="sxs-lookup"><span data-stu-id="67d38-125">Click Group attributes.</span></span>
18. <span data-ttu-id="67d38-126">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="67d38-126">Click New.</span></span>
19. <span data-ttu-id="67d38-127">Dans le champ Attributs, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="67d38-127">In the Attribute field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="67d38-128">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="67d38-128">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="67d38-129">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="67d38-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="67d38-130">Un attribut peut être inclus dans n’importe quel groupe.</span><span class="sxs-lookup"><span data-stu-id="67d38-130">An attribute can be included in any of the groups.</span></span>  
22. <span data-ttu-id="67d38-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="67d38-131">Click Save.</span></span>
23. <span data-ttu-id="67d38-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="67d38-132">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]