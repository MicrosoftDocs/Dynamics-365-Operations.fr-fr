--- 
title: "Ajouter un calcul à un modèle de configuration de produit"
description: "Cette procédure montre comment ajouter un nouveau calcul à un modèle de configuration de produit."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 01434e8dbd1e66ae04d0b7910ef2be582297ac84
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="62ef6-103">Ajouter un calcul à un modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="62ef6-103">Add a calculation to a product configuration model</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="62ef6-104">Cette procédure montre comment ajouter un nouveau calcul à un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="62ef6-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="62ef6-105">Elle montre comment créer une expression logique utilisant l'opérateur « Si » pour définir une hauteur de haut-parleur de 10 pour les haut-parleurs blancs et de 15 pour les autres finitions.</span><span class="sxs-lookup"><span data-stu-id="62ef6-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="62ef6-106">Cette procédure utilise le composant Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="62ef6-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="62ef6-107">Ajouter un calcul</span><span class="sxs-lookup"><span data-stu-id="62ef6-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="62ef6-108">Créer une expression de calcul</span><span class="sxs-lookup"><span data-stu-id="62ef6-108">Create calculation expression</span></span>
1. <span data-ttu-id="62ef6-109">Cliquez sur Modifier l'expression.</span><span class="sxs-lookup"><span data-stu-id="62ef6-109">Click Edit expression.</span></span>
2. <span data-ttu-id="62ef6-110">Dans le champ ConstraintBody, entrez « If[CabinetFinish=="White", 10, 15] ».</span><span class="sxs-lookup"><span data-stu-id="62ef6-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="62ef6-111">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="62ef6-111">Click Validate.</span></span>
4. <span data-ttu-id="62ef6-112">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="62ef6-112">Click Close.</span></span>
5. <span data-ttu-id="62ef6-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="62ef6-113">Click OK.</span></span>


