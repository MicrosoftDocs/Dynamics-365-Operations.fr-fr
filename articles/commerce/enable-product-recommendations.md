---
title: Activer les recommandations produit
description: Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l'Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ecda571a356c6968196d09cc19923105cf4544ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770137"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="d4e0e-103">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="d4e0e-103">Enable product recommendations</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="d4e0e-104">Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l'Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d4e0e-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="d4e0e-105">Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d'ensemble des recommandations produit.](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="d4e0e-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="d4e0e-106">Recommandations avant contrôle</span><span class="sxs-lookup"><span data-stu-id="d4e0e-106">Recommendations pre-check</span></span>
<span data-ttu-id="d4e0e-107">Avant l'activation, notez-vous que les recommandations de produit sont uniquement prises en charge par les clients de F&O prenant en charge la version 10.0.6 et ayant migré leur stockage pour utiliser BDL.</span><span class="sxs-lookup"><span data-stu-id="d4e0e-107">Before enabling, please note that product recommendations are only supported for F&O customers supporting build 10.0.6 and have migrated their storage to using BDL.</span></span> 

<span data-ttu-id="d4e0e-108">En outre, assurez-vous que les mesures RetailSale ont été activées.</span><span class="sxs-lookup"><span data-stu-id="d4e0e-108">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="d4e0e-109">Pour en savoir plus sur ce processus de paramétrage, allez [ici.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="d4e0e-109">To Learn more about this set up process, go [here.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="d4e0e-110">Activer les recommandations</span><span class="sxs-lookup"><span data-stu-id="d4e0e-110">Turn on recommendations</span></span>

<span data-ttu-id="d4e0e-111">Pour activer les recommandations de produit, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d4e0e-111">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="d4e0e-112">Accédez à **Vente au détail** &gt; **Recommandations de produits** &gt; **Paramètres des recommandations**.</span><span class="sxs-lookup"><span data-stu-id="d4e0e-112">Go to **Retail** &gt; **Product recommendations** &gt; **Recommendation parameters**.</span></span>
1. <span data-ttu-id="d4e0e-113">Dans la liste des paramètres partagés de vente au détail, sélectionnez **Listes des recommandations**.</span><span class="sxs-lookup"><span data-stu-id="d4e0e-113">In the list of retail shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="d4e0e-114">Définissez l'option **Activer les recommandations** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="d4e0e-114">Set the **Enable recommendations** option to **Yes**.</span></span>

![activer les recommandations produit](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="d4e0e-116">Cette procédure démarre le processus de génération de listes de recommandations de produit.</span><span class="sxs-lookup"><span data-stu-id="d4e0e-116">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="d4e0e-117">Cette opération peut nécessiter jusqu'à plusieurs heures avant que les listes soient disponibles et puissent s'affichent sur point de vente (PDV) ou dans Dynamics 365 for Commerce.</span><span class="sxs-lookup"><span data-stu-id="d4e0e-117">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 for Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="d4e0e-118">Configuration des paramètres de la liste des recommandations</span><span class="sxs-lookup"><span data-stu-id="d4e0e-118">Configure recommendation list parameters</span></span>
<span data-ttu-id="d4e0e-119">Par défaut, la liste des recommandations de produit basée sur Machine Learning - Intelligence artificielle fournit des valeurs suggérées.</span><span class="sxs-lookup"><span data-stu-id="d4e0e-119">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="d4e0e-120">Vous pouvez modifier les valeurs suggérées par défaut pour les adapter au flux de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="d4e0e-120">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="d4e0e-121">Pour en savoir plus sur la manière de modifier les paramètres par défaut, accédez à [Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="d4e0e-121">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="d4e0e-122">Afficher les recommandations sur les appareils PDV</span><span class="sxs-lookup"><span data-stu-id="d4e0e-122">Show recommendations on POS devices</span></span>
<span data-ttu-id="d4e0e-123">Après avoir activé les recommandations dans back-office, le panneau de recommandations doit être ajouté à l'écran du PDV de contrôle via l'outil de disposition.</span><span class="sxs-lookup"><span data-stu-id="d4e0e-123">After enabling recommendations in the back office, the recommendations pannel must be added to the control POS screen via the layout tool.</span></span> <span data-ttu-id="d4e0e-124">Pour en savoir plus sur ce processus, allez [ici.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span><span class="sxs-lookup"><span data-stu-id="d4e0e-124">To learn about this process, go [here.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span></span>


## <a name="additional-resources"></a><span data-ttu-id="d4e0e-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d4e0e-125">Additional resources</span></span>

[<span data-ttu-id="d4e0e-126">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="d4e0e-126">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="d4e0e-127">Ajouter des listes de recommandation produit aux pages</span><span class="sxs-lookup"><span data-stu-id="d4e0e-127">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="d4e0e-128">Ajouter le panneau de recommandations aux appareils PDV</span><span class="sxs-lookup"><span data-stu-id="d4e0e-128">Add recommendations panel to POS devices</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


