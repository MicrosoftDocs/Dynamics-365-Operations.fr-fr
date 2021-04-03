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
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6e23d33c6911310cca6aac0df4589e909568a86a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258069"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="e4eaf-103">Ajouter un calcul à un modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="e4eaf-103">Add a calculation to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e4eaf-104">Cette procédure montre comment ajouter un nouveau calcul à un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="e4eaf-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="e4eaf-105">Elle montre comment créer une expression logique utilisant l’opérateur « Si » pour définir une hauteur de haut-parleur de 10 pour les haut-parleurs blancs et de 15 pour les autres finitions.</span><span class="sxs-lookup"><span data-stu-id="e4eaf-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="e4eaf-106">Cette procédure utilise le composant Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="e4eaf-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="e4eaf-107">Ajouter un calcul</span><span class="sxs-lookup"><span data-stu-id="e4eaf-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="e4eaf-108">Créer une expression de calcul</span><span class="sxs-lookup"><span data-stu-id="e4eaf-108">Create calculation expression</span></span>
1. <span data-ttu-id="e4eaf-109">Cliquez sur Modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="e4eaf-109">Click Edit expression.</span></span>
2. <span data-ttu-id="e4eaf-110">Dans le champ ConstraintBody, entrez « If[CabinetFinish=="White", 10, 15] ».</span><span class="sxs-lookup"><span data-stu-id="e4eaf-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="e4eaf-111">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="e4eaf-111">Click Validate.</span></span>
4. <span data-ttu-id="e4eaf-112">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="e4eaf-112">Click Close.</span></span>
5. <span data-ttu-id="e4eaf-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e4eaf-113">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]