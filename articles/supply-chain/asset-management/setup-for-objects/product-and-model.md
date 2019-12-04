---
title: Fabricants et modèles d'actif
description: Cette rubrique explique comment paramétrer des fabricants d'actif et des modèles associés dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b77605070387871335c480e25cbe23af1155d6e8
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812166"
---
# <a name="asset-manufacturers-and-models"></a><span data-ttu-id="4d8ca-103">Fabricants et modèles d'actif</span><span class="sxs-lookup"><span data-stu-id="4d8ca-103">Asset manufacturers and models</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="4d8ca-104">Cette rubrique explique comment paramétrer des fabricants d'actif et des modèles associés dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-104">This topic explains how to set up asset manufacturers and related models in Asset Management.</span></span> <span data-ttu-id="4d8ca-105">Les modèles peuvent être associés à des types d'actif.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-105">Models can be related to asset types.</span></span>

## <a name="set-up-product-model-relations"></a><span data-ttu-id="4d8ca-106">Définir les relations entre le produit et le modèle</span><span class="sxs-lookup"><span data-stu-id="4d8ca-106">Set up product-model relations</span></span>

1. <span data-ttu-id="4d8ca-107">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Actifs** \> **Fabricant et modèle**.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-107">Select **Asset management** \> **Setup** \> **Assets** \> **Manufacturer and model**.</span></span>
2. <span data-ttu-id="4d8ca-108">Sélectionnez **Nouveau** pour créer un produit.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-108">Select **New** to create a new product.</span></span>
3. <span data-ttu-id="4d8ca-109">Dans le champ **Fabricant**, entrez un nom pour le fabricant d'actif.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-109">In the **Manufacturer** field, enter a name for the asset manufacturer.</span></span>
4. <span data-ttu-id="4d8ca-110">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-110">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="4d8ca-111">Dans le raccourci **Modèles**, sélectionnez **Ajouter** pour créer un modèle d'actif qui doit être associé au fabricant d'actif.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-111">On the **Models** FastTab, select **Add** to create an asset model that should be related to the asset manufacturer.</span></span>
6. <span data-ttu-id="4d8ca-112">Dans le champ **Modèle**, entrez un nom pour le modèle d'actif.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-112">In the **Model** field, enter a name for the asset model.</span></span>
7. <span data-ttu-id="4d8ca-113">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-113">In the **Description** field, enter a description.</span></span>
8. <span data-ttu-id="4d8ca-114">Dans le champ **Type d'actif**, sélectionnez le type d'actif auquel le modèle de fabricant doit être associé.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-114">In the **Asset type** field, select the asset type that the manufacturer model should be related to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4d8ca-115">Vous pouvez également définir des relations pour les types, les fabricants et les modèles d'actif dans la recherche **Types d'actif**.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-115">You can also set up relations for asset types, manufacturers, and models in the **Asset types** lookup.</span></span> <span data-ttu-id="4d8ca-116">Pour plus d'informations, voir [Types d'actif](../setup-for-objects/object-types.md).</span><span class="sxs-lookup"><span data-stu-id="4d8ca-116">For more information, see [Asset types](../setup-for-objects/object-types.md).</span></span>

    <span data-ttu-id="4d8ca-117">Dans le raccourci **Détails**, le champ **Modèles** affiche le nombre de modèles d'actif qui sont paramétrés sur le fabricant d'actif sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-117">In the **Details** FastTab, the **Models** field shows the number of asset models that are set up on the selected asset manufacturer.</span></span> <span data-ttu-id="4d8ca-118">Le champ **Actifs** affiche le nombre d'actifs qui utilisent le fabricant sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-118">The **Assets** field shows the number of assets that are using the selected manufacturer.</span></span>
    
    <span data-ttu-id="4d8ca-119">Le champ **Actifs** affiche le nombre d'objets qui utilisent le modèle de fabricant.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-119">The **Assets** field shows the number of objects that are using the manufacturer model.</span></span>

> [!NOTE]
> <span data-ttu-id="4d8ca-120">Un type d'actif peut ne pas avoir de relations de modèle de fabricant, il peut être associé à un modèle de fabricant d'actif ou il peut être associé à plusieurs modèles de fabricant d'actif.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-120">An asset type can have no asset manufacturer model relations, it can be related to one asset manufacturer model, or it can be related multiple asset manufacturer models.</span></span> <span data-ttu-id="4d8ca-121">Si un type d'actif est associé à au moins un modèle de fabricant, seules les combinaisons paramétrées dans la recherche **Modèle de fabricant** peuvent être sélectionnées dans les pages Gestion des actifs où une combinaison d'un type, d'un fabricant et d'un modèle d'actif peut être paramétrée.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-121">If an asset type is related to at least one manufacturer model, only the combinations that are set up in the **Manufacturer model** lookup can be selected on those Asset Management pages where a combination of an asset type, manufacturer, and model can be set up.</span></span> <span data-ttu-id="4d8ca-122">Ces pages incluent **Tous les actifs**, **Niveaux de service d'actifs**, **Valeurs par défaut du type de tâche** et **Lignes de budget de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-122">These pages include **All assets**, **Asset service levels**, **Job type defaults**, and **Maintenance budget lines**.</span></span> <span data-ttu-id="4d8ca-123">Si certains types d'actif ne sont associés à aucun modèle de fabricant, seuls les types d'actif et les modèles de fabricant qui n'ont aucun relation avec les types d'actif, s'affichent sur les pages.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-123">If some asset types aren't related to any manufacturer model, only those asset types, and manufacturer models that also have no relation to asset types, are shown on the pages.</span></span>

## <a name="select-a-manufacturer-and-model-on-an-object"></a><span data-ttu-id="4d8ca-124">Sélectionnez un fabricant et un modèle sur un objet</span><span class="sxs-lookup"><span data-stu-id="4d8ca-124">Select a manufacturer and model on an object</span></span>

1. <span data-ttu-id="4d8ca-125">Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les actifs**.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-125">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="4d8ca-126">Dans la colonne **Actif**, sélectionnez le lien de l'actif.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-126">In the **Asset** column, select the link for the asset.</span></span> <span data-ttu-id="4d8ca-127">La page **Détails** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-127">The **Details** page appears.</span></span>
3. <span data-ttu-id="4d8ca-128">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-128">Select **Edit**.</span></span>
4. <span data-ttu-id="4d8ca-129">Dans le raccourci **Général**, sélectionnez des valeurs dans les champs **Fabricant** et **Modèle**.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-129">On the **General** FastTab, select values in the **Manufacturer** and **Model** fields.</span></span>
