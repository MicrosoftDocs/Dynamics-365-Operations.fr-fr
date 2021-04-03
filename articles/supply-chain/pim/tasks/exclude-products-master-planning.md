---
title: Créer un état du cycle de vie des produits pour exclure des produits de la planification
description: Cette procédure décrit comment créer un état du cycle de vie des produits qui exclut les produits de la planification et du calcul au niveau de la nomenclature.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fc24aad05499adf9bfb2db3613c7f134c3a70770
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5264696"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a><span data-ttu-id="6cbb4-103">Créer un état du cycle de vie des produits pour exclure des produits de la planification</span><span class="sxs-lookup"><span data-stu-id="6cbb4-103">Create a product lifecycle state to exclude products from Master planning</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6cbb4-104">Cette procédure décrit comment créer un état du cycle de vie des produits qui exclut les produits de la planification et du calcul au niveau de la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="6cbb4-104">This procedure shows how to create a new product lifecycle state that excludes the products from Master planning and BOM-level calculation.</span></span>


## <a name="create-an-obsolete-state"></a><span data-ttu-id="6cbb4-105">Créer un état obsolète</span><span class="sxs-lookup"><span data-stu-id="6cbb4-105">Create an obsolete state</span></span>
1. <span data-ttu-id="6cbb4-106">Accédez à Gestion des informations sur les produits > Paramétrage > État du cycle de vie des produits.</span><span class="sxs-lookup"><span data-stu-id="6cbb4-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="6cbb4-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6cbb4-107">Click New.</span></span>
3. <span data-ttu-id="6cbb4-108">Dans le champ État, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6cbb4-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="6cbb4-109">Sélectionnez Non dans le champ Est actif pour la planification.</span><span class="sxs-lookup"><span data-stu-id="6cbb4-109">Select No in the Is active for planning field.</span></span>
5. <span data-ttu-id="6cbb4-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6cbb4-110">In the Description field, type a value.</span></span>

## <a name="associate-the-obsolete-state-to-a-released-product"></a><span data-ttu-id="6cbb4-111">Associer l’état obsolète à un produit lancé</span><span class="sxs-lookup"><span data-stu-id="6cbb4-111">Associate the obsolete state to a released product</span></span>
1. <span data-ttu-id="6cbb4-112">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6cbb4-112">Close the page.</span></span>
2. <span data-ttu-id="6cbb4-113">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="6cbb4-113">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="6cbb4-114">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="6cbb4-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="6cbb4-115">Par exemple, filtrez le champ Nom de recherche avec la valeur « M00 ».</span><span class="sxs-lookup"><span data-stu-id="6cbb4-115">For example, filter on the Search name field with a value of 'M00'.</span></span>
4. <span data-ttu-id="6cbb4-116">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="6cbb4-116">Click Edit.</span></span>
5. <span data-ttu-id="6cbb4-117">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6cbb4-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="6cbb4-118">Dans le champ État du cycle de vie des produits, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6cbb4-118">In the Product lifecycle state field, enter or select a value.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]