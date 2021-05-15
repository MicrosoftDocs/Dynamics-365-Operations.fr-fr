---
title: Créer les configurations basées sur les dimensions
description: Cette procédure permet d’indiquer comment définir une configuration pour un produit fondé sur les dimensions.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, EcoResDimensionBasedConfiguration, ConfigChooseFromRoute, ConfigChooseFromGroup, ConfigChoiceApprove
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 584bb558ee0afeaffaeb003e9f1d1b0bca42d19d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920679"
---
# <a name="create-dimension-based-configurations"></a><span data-ttu-id="db848-103">Créer les configurations basées sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="db848-103">Create dimension-based configurations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="db848-104">Cette procédure permet d’indiquer comment définir une configuration pour un produit fondé sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="db848-104">This procedure shows how to define a configuration for a dimension-based product.</span></span> <span data-ttu-id="db848-105">Il s’agit de la dernière procédure de la série qui explique comment créer des combinaisons pour la configuration basée sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="db848-105">This is the last procedure in the series that explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="db848-106">L’exécution de cette procédure dépend des données créées dans les sept enregistrements précédents.</span><span class="sxs-lookup"><span data-stu-id="db848-106">The execution of this procedure is dependent on the data created in the previous seven recordings.</span></span> <span data-ttu-id="db848-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="db848-107">The demo data company used to create this procedure is USMF.</span></span>

## <a name="find-the-dimension-based-product-master"></a><span data-ttu-id="db848-108">Rechercher le produit générique fondé sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="db848-108">Find the dimension-based product master</span></span>

1. <span data-ttu-id="db848-109">Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="db848-109">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="db848-110">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="db848-110">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="db848-111">Sélectionnez le produit générique fondé sur les dimensions créé dans le premier enregistrement de cette séquence de 8 enregistrements.</span><span class="sxs-lookup"><span data-stu-id="db848-111">Select the dimension-based product master that you created in the first recording in this sequence of 8 recordings.</span></span>  

## <a name="create-configurations"></a><span data-ttu-id="db848-112">Créer des configurations</span><span class="sxs-lookup"><span data-stu-id="db848-112">Create configurations</span></span>

1. <span data-ttu-id="db848-113">Cliquez sur **Tenir à jour les configurations** dans le volet Actions **Ingénierie**.</span><span class="sxs-lookup"><span data-stu-id="db848-113">On the **Engineering** Action Pane, select **Maintain configurations**.</span></span>
1. <span data-ttu-id="db848-114">Sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="db848-114">Select **Configure**.</span></span>
1. <span data-ttu-id="db848-115">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="db848-115">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="db848-116">Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.</span><span class="sxs-lookup"><span data-stu-id="db848-116">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="db848-117">Sélectionnez l’un des articles du premier groupe de configurations.</span><span class="sxs-lookup"><span data-stu-id="db848-117">Select any of the items in the first configuration group.</span></span>  
1. <span data-ttu-id="db848-118">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="db848-118">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="db848-119">Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.</span><span class="sxs-lookup"><span data-stu-id="db848-119">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="db848-120">Sélectionnez l’un des articles du deuxième groupe de configurations.</span><span class="sxs-lookup"><span data-stu-id="db848-120">Select any item from the second configuration group.</span></span>  
1. <span data-ttu-id="db848-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="db848-121">Select **OK**.</span></span>
1. <span data-ttu-id="db848-122">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="db848-122">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="db848-123">Tapez une valeur dans le champ **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="db848-123">In the **Configuration** field, type a value.</span></span>
    * <span data-ttu-id="db848-124">Entrez un nom de configuration qui rendra la configuration simple à identifier.</span><span class="sxs-lookup"><span data-stu-id="db848-124">Enter a configuration name that will make it easy to identify the configuration.</span></span>  
1. <span data-ttu-id="db848-125">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="db848-125">In the **Description** field, type a value.</span></span>
    * <span data-ttu-id="db848-126">Entrez une description de la configuration pour expliquer ce qu’elle contient.</span><span class="sxs-lookup"><span data-stu-id="db848-126">Enter a description of the configuration to explain what it contains.</span></span>  
1. <span data-ttu-id="db848-127">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="db848-127">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]