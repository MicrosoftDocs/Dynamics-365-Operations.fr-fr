---
title: Ajouter un calcul à un modèle de configuration de produit
description: Cette procédure montre comment ajouter un nouveau calcul à un modèle de configuration de produit.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 268baa4b518f6df52d4393f7278a79cbe1733844
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812670"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="510e2-103">Ajouter un calcul à un modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="510e2-103">Add a calculation to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="510e2-104">Cette procédure montre comment ajouter un nouveau calcul à un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="510e2-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="510e2-105">Elle montre comment créer une expression logique utilisant l’opérateur « Si » pour définir une hauteur de haut-parleur de 10 pour les haut-parleurs blancs et de 15 pour les autres finitions.</span><span class="sxs-lookup"><span data-stu-id="510e2-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="510e2-106">Cette procédure utilise le composant Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="510e2-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="510e2-107">Ajouter un calcul</span><span class="sxs-lookup"><span data-stu-id="510e2-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="510e2-108">Créer une expression de calcul</span><span class="sxs-lookup"><span data-stu-id="510e2-108">Create calculation expression</span></span>
1. <span data-ttu-id="510e2-109">Cliquez sur Modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="510e2-109">Click Edit expression.</span></span>
2. <span data-ttu-id="510e2-110">Dans le champ ConstraintBody, entrez « If[CabinetFinish=="White", 10, 15] ».</span><span class="sxs-lookup"><span data-stu-id="510e2-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="510e2-111">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="510e2-111">Click Validate.</span></span>
4. <span data-ttu-id="510e2-112">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="510e2-112">Click Close.</span></span>
5. <span data-ttu-id="510e2-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="510e2-113">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]