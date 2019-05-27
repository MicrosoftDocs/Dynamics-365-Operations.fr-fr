---
title: Paramètres de couverture
description: Cette rubrique fournit des informations sur les paramètres de couverture que le calcul PDP/MRP utilise pour calculer les demandes d'articles.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99e094a7131b6d3a299fc72abd0141529908ddd2
ms.sourcegitcommit: 9e50bee6a67f0fe2fa6f86e02c7e8de16d0e2482
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538892"
---
# <a name="coverage-settings"></a><span data-ttu-id="9f94b-103">Paramètres de couverture</span><span class="sxs-lookup"><span data-stu-id="9f94b-103">Coverage settings</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9f94b-104">Le calcul PDP/MRP utilise les paramètres de couverture pour calculer les demandes d'articles.</span><span class="sxs-lookup"><span data-stu-id="9f94b-104">Master scheduling uses coverage settings to calculate item requirements.</span></span>

<span data-ttu-id="9f94b-105">Vous pouvez spécifier des paramètres de couverture de plusieurs façons :</span><span class="sxs-lookup"><span data-stu-id="9f94b-105">You can specify coverage settings in several ways:</span></span>

- <span data-ttu-id="9f94b-106">Spécifiez des paramètres de couverture pour un groupe de couverture.</span><span class="sxs-lookup"><span data-stu-id="9f94b-106">Specify coverage settings for a coverage group.</span></span>

    <span data-ttu-id="9f94b-107">Vous pouvez créer un groupe de couverture contenant des paramètres pour tous les produits qui lui sont liés.</span><span class="sxs-lookup"><span data-stu-id="9f94b-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="9f94b-108">Pour créer un groupe de couverture, accédez à **Planification &gt; Paramétrage &gt; Couverture &gt; Groupes de couverture**.</span><span class="sxs-lookup"><span data-stu-id="9f94b-108">To create a coverage group, go to **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups**.</span></span> <span data-ttu-id="9f94b-109">Vous pouvez lier un groupe de couverture à un produit.</span><span class="sxs-lookup"><span data-stu-id="9f94b-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="9f94b-110">Si le lien est spécifique à un site, un entrepôt ou une dimension de produit, utilisez le champ **Groupe de couverture** dans la page **Couverture de l'article**.</span><span class="sxs-lookup"><span data-stu-id="9f94b-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="9f94b-111">Si le lien est générique, indépendamment des dimensions de produit, utilisez le champ **Groupe de couverture** sous l'organisateur **Plan** de la page **Détails de produit**.</span><span class="sxs-lookup"><span data-stu-id="9f94b-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** field on the **Plan** FastTab of the **Product details** page.</span></span> <span data-ttu-id="9f94b-112">Par défaut, si vous ne liez pas de groupe de couverture à un produit, la planification utilise le groupe de couverture général spécifié dans la page **Paramètres de planification**.</span><span class="sxs-lookup"><span data-stu-id="9f94b-112">By default, if you don't link a coverage group to a product, master planning uses the general coverage group that is specified on the **Master planning parameters** page.</span></span>

- <span data-ttu-id="9f94b-113">Spécifiez des paramètres de couverture pour un produit.</span><span class="sxs-lookup"><span data-stu-id="9f94b-113">Specify coverage settings for a product.</span></span>

    <span data-ttu-id="9f94b-114">Vous pouvez créer des paramètres de couverture pour un produit spécifique.</span><span class="sxs-lookup"><span data-stu-id="9f94b-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="9f94b-115">Allez à **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="9f94b-115">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="9f94b-116">Sélectionnez le produit, puis dans le volet Actions, sous l'onglet **Plan**, dans le champ **Groupe de couverture**, cliquez sur **Couverture de l'article** pour ouvrir la page **Couverture de l'article**.</span><span class="sxs-lookup"><span data-stu-id="9f94b-116">Select the product, and then, on the Action Pane, on the **Plan** tab, in the **Coverage** group, select **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="9f94b-117">Si le produit est déjà lié à un groupe de couverture, vous pouvez remplacer les paramètres de groupe de couverture à l'aide du champ **Remplacer**.</span><span class="sxs-lookup"><span data-stu-id="9f94b-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="9f94b-118">Les paramètres de couverture de la page**Couverture de l'article** prévalent sur les paramètres de la page **Groupe de couverture**.</span><span class="sxs-lookup"><span data-stu-id="9f94b-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

- <span data-ttu-id="9f94b-119">Spécifiez des paramètres de couverture pour un produit à l'aide d'un Assistant.</span><span class="sxs-lookup"><span data-stu-id="9f94b-119">Specify coverage settings for a product by using a wizard.</span></span>

    <span data-ttu-id="9f94b-120">L'Assistant vous guide étape par étape via le processus de paramétrage des principaux paramètres de couverture de l'article.</span><span class="sxs-lookup"><span data-stu-id="9f94b-120">The wizard guides you step by step through the process of setting up the primary item coverage parameters.</span></span> <span data-ttu-id="9f94b-121">Dans la page **Couverture de l'article**, dans le volet Action, cliquez sur **Assistant** pour ouvrir l'**Assistant Couverture d'article**.</span><span class="sxs-lookup"><span data-stu-id="9f94b-121">On the **Item coverage** page, on the Action Pane, select **Wizard** to open the **Item Coverage Wizard**.</span></span>

- <span data-ttu-id="9f94b-122">Spécifiez des paramètres de couverture pour un groupe de dimensions.</span><span class="sxs-lookup"><span data-stu-id="9f94b-122">Specify coverage settings for a dimension group.</span></span>

    <span data-ttu-id="9f94b-123">Allez à **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="9f94b-123">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="9f94b-124">Dans la page **Détail du produit lancé**, sous l'organisateur **Général**, dans la section **Administration**, sélectionnez le lien dans le champ **Groupe de dimension de stockage**.</span><span class="sxs-lookup"><span data-stu-id="9f94b-124">On the **Released product details** page, on the **General** FastTab, in the **Administration** section, select the link in the **Storage dimension group** field.</span></span> <span data-ttu-id="9f94b-125">Dans la page **Groupes de dimensions de stockage**, activez la case à cocher **Plan de couverture par dimension** pour créer les paramètres de couverture d'une dimension dans le groupe de dimensions de stockage.</span><span class="sxs-lookup"><span data-stu-id="9f94b-125">On the **Storage dimension groups** page, select the **Coverage plan by dimension** check box to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="9f94b-126">Le champ **Plan de couverture par dimension** doit être sélectionné pour toutes les dimensions de produit, telles que la configuration, la couleur, la taille et le style.</span><span class="sxs-lookup"><span data-stu-id="9f94b-126">The **Coverage plan by dimension** field must be selected for all product dimensions, such as configuration, color, size, and style.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9f94b-127">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9f94b-127">Additional resources</span></span>

[<span data-ttu-id="9f94b-128">Plans généraux</span><span class="sxs-lookup"><span data-stu-id="9f94b-128">Master plans</span></span>](master-plans.md)
