---
title: "Paramètres de couverture"
description: "Le calcul PDP/MRP utilise les paramètres de couverture pour calculer les demandes d'articles."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bd85f89917659ac9c94590bace765b2123d6e556
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="coverage-settings"></a><span data-ttu-id="757a0-103">Paramètres de couverture</span><span class="sxs-lookup"><span data-stu-id="757a0-103">Coverage settings</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="757a0-104">Le calcul PDP/MRP utilise les paramètres de couverture pour calculer les demandes d'articles.</span><span class="sxs-lookup"><span data-stu-id="757a0-104">Master scheduling uses coverage settings to calculate item requirements.</span></span> 

<span data-ttu-id="757a0-105">Vous pouvez spécifier des paramètres de couverture de plusieurs façons :</span><span class="sxs-lookup"><span data-stu-id="757a0-105">You can specify coverage settings in several ways:</span></span>

-   <span data-ttu-id="757a0-106">Spécifiez des paramètres de couverture pour un groupe de couverture.</span><span class="sxs-lookup"><span data-stu-id="757a0-106">Specify coverage settings for a coverage group.</span></span> <span data-ttu-id="757a0-107">Vous pouvez créer un groupe de couverture contenant des paramètres pour tous les produits qui lui sont liés.</span><span class="sxs-lookup"><span data-stu-id="757a0-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="757a0-108">Cliquez sur **Planification &gt; Paramétrage &gt; Couverture &gt; Groupes de couverture** pour créer un groupe de couverture.</span><span class="sxs-lookup"><span data-stu-id="757a0-108">Click **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups** to create a coverage group.</span></span> <span data-ttu-id="757a0-109">Vous pouvez lier un groupe de couverture à un produit.</span><span class="sxs-lookup"><span data-stu-id="757a0-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="757a0-110">Si le lien est spécifique à un site, un entrepôt ou une dimension de produit, utilisez le champ **Groupe de couverture** dans la page **Couverture de l'article**.</span><span class="sxs-lookup"><span data-stu-id="757a0-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="757a0-111">Si le lien est générique, indépendamment des dimensions de produit, utilisez le champ **Groupe de couverture** sous l'organisateur **Plan** de la page **Détails de produit**.</span><span class="sxs-lookup"><span data-stu-id="757a0-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** on the **Plan** FastTab on the **Product details** page.</span></span> <span data-ttu-id="757a0-112">Si vous ne liez pas de groupe de couverture à un produit, la planification utilise par défaut le **Groupe de couverture général** spécifié dans la page **Paramètres de planification**.</span><span class="sxs-lookup"><span data-stu-id="757a0-112">If you do not link a coverage group to a product, master planning uses the **General coverage group** that is specified on the **Master planning parameters** page as the default.</span></span>

-   <span data-ttu-id="757a0-113">Spécifiez des paramètres de couverture pour un produit.</span><span class="sxs-lookup"><span data-stu-id="757a0-113">Specify coverage settings for a product.</span></span> <span data-ttu-id="757a0-114">Vous pouvez créer des paramètres de couverture pour un produit spécifique.</span><span class="sxs-lookup"><span data-stu-id="757a0-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="757a0-115">Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="757a0-115">Click **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="757a0-116">Sélectionnez le produit, dans le **volet Actions**, sous l'onglet **Plan**, dans le champ **Groupe de couverture**, cliquez sur **Couverture de l'article** pour ouvrir la page **Couverture de l'article**.</span><span class="sxs-lookup"><span data-stu-id="757a0-116">Select the product, on the **Action Pane**, on the **Plan** tab, in the **Coverage group**, click **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="757a0-117">Si le produit est déjà lié à un groupe de couverture, vous pouvez remplacer les paramètres de groupe de couverture à l'aide du champ **Remplacer**.</span><span class="sxs-lookup"><span data-stu-id="757a0-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="757a0-118">Les paramètres de couverture de la page**Couverture de l'article** prévalent sur les paramètres de la page **Groupe de couverture**.</span><span class="sxs-lookup"><span data-stu-id="757a0-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

<!-- -->

-   <span data-ttu-id="757a0-119">Spécifiez des paramètres de couverture pour un produit à l'aide d'un Assistant.</span><span class="sxs-lookup"><span data-stu-id="757a0-119">Specify coverage settings for a product by using a wizard.</span></span> <span data-ttu-id="757a0-120">L'Assistant fournit des instructions détaillées sur la définition des principaux paramètres de couverture de l'article.</span><span class="sxs-lookup"><span data-stu-id="757a0-120">The wizard is a step-by-step guide to help you set up the primary item coverage parameters.</span></span> <span data-ttu-id="757a0-121">Dans la page **Couverture de l'article**, cliquez sur **Assistant** pour ouvrir l'**Assistant Couverture d'article**.</span><span class="sxs-lookup"><span data-stu-id="757a0-121">On the **Item coverage** page, click **Wizard** to open the **Item Coverage Wizard**.</span></span>

<!-- -->

-   <span data-ttu-id="757a0-122">Spécifiez des paramètres de couverture pour un groupe de dimensions.</span><span class="sxs-lookup"><span data-stu-id="757a0-122">Specify coverage settings for a dimension group.</span></span> <span data-ttu-id="757a0-123">Cliquez sur **Gestion des informations sur les produits &gt; Commun &gt; Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="757a0-123">Click **Product information management &gt; Common &gt; Released products**.</span></span> <span data-ttu-id="757a0-124">Dans la page **Détails des produits lancés**, sous l'onglet **Général**, dans le groupe **Administration**, cliquez sur le lien **Groupe de dimension de stockage**.</span><span class="sxs-lookup"><span data-stu-id="757a0-124">On the **Released product detail **page, on the **General** tab, in the **Administration** group, click the **Storage dimension group** link.</span></span> <span data-ttu-id="757a0-125">Dans la page **Groupe de dimensions de stockage**, sélectionnez le champ **Plan de couverture par dimension** pour créer les paramètres de couverture d'une dimension dans le groupe de dimensions de stockage.</span><span class="sxs-lookup"><span data-stu-id="757a0-125">On the **Storage dimension group** page, select the **Coverage plan by dimension** field to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="757a0-126">Le champ **Plan de couverture par dimension** doit être sélectionné pour toutes les dimensions de produit, telles que la configuration, la couleur, la taille et le style.</span><span class="sxs-lookup"><span data-stu-id="757a0-126">All product dimensions, such as configuration, color, size, style, must have the **Coverage plan by dimension** field selected.</span></span>



<a name="see-also"></a><span data-ttu-id="757a0-127">Voir également :</span><span class="sxs-lookup"><span data-stu-id="757a0-127">See also</span></span>
--------

[<span data-ttu-id="757a0-128">Plans généraux</span><span class="sxs-lookup"><span data-stu-id="757a0-128">Master plans</span></span>](master-plans.md)




