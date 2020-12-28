---
title: Ajouter un calcul à un modèle de configuration de produit
description: Cette procédure montre comment ajouter un nouveau calcul à un modèle de configuration de produit.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e703c6d505f1e2e77f454732301de7a6c130c58a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427903"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="cce0e-103">Ajouter un calcul à un modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="cce0e-103">Add a calculation to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cce0e-104">Cette procédure montre comment ajouter un nouveau calcul à un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="cce0e-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="cce0e-105">Elle montre comment créer une expression logique utilisant l'opérateur « Si » pour définir une hauteur de haut-parleur de 10 pour les haut-parleurs blancs et de 15 pour les autres finitions.</span><span class="sxs-lookup"><span data-stu-id="cce0e-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="cce0e-106">Cette procédure utilise le composant Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="cce0e-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="cce0e-107">Ajouter un calcul</span><span class="sxs-lookup"><span data-stu-id="cce0e-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="cce0e-108">Créer une expression de calcul</span><span class="sxs-lookup"><span data-stu-id="cce0e-108">Create calculation expression</span></span>
1. <span data-ttu-id="cce0e-109">Cliquez sur Modifier l'expression.</span><span class="sxs-lookup"><span data-stu-id="cce0e-109">Click Edit expression.</span></span>
2. <span data-ttu-id="cce0e-110">Dans le champ ConstraintBody, entrez 'If[CabinetFinish=="White", 10, 15]'.</span><span class="sxs-lookup"><span data-stu-id="cce0e-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="cce0e-111">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="cce0e-111">Click Validate.</span></span>
4. <span data-ttu-id="cce0e-112">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="cce0e-112">Click Close.</span></span>
5. <span data-ttu-id="cce0e-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cce0e-113">Click OK.</span></span>

