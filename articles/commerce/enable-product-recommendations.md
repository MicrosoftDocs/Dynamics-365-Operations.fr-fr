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
ms.openlocfilehash: 2d3f1bc2526eeacb4bd6338a0679eadd95a75989
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024954"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="511bf-103">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="511bf-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="511bf-104">Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l'Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="511bf-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="511bf-105">Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d'ensemble des recommandations produit.](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="511bf-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="511bf-106">Recommandations avant contrôle</span><span class="sxs-lookup"><span data-stu-id="511bf-106">Recommendations pre-check</span></span>

<span data-ttu-id="511bf-107">Avant l'activation, notez que les recommandations de produit sont uniquement prises en charge pour les clients Commerce qui ont migré leur stockage pour utiliser Azure Data Lake Storage (ADLS).</span><span class="sxs-lookup"><span data-stu-id="511bf-107">Before enabling, please note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="511bf-108">Pour connaître les étapes d'activation d'ADLS, consultez [Comment activer ADLS dans un environnement Dynamics 365](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="511bf-108">For steps on enabling ADLS, see [How to enable ADLS in a Dynamics 365 environment](enable-ADLS-environment.md).</span></span>

<span data-ttu-id="511bf-109">En outre, assurez-vous que les mesures RetailSale ont été activées.</span><span class="sxs-lookup"><span data-stu-id="511bf-109">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="511bf-110">Pour en savoir plus sur ce processus de paramétrage, allez [ici.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="511bf-110">To learn more about this set up process, go [here.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="511bf-111">Activer les recommandations</span><span class="sxs-lookup"><span data-stu-id="511bf-111">Turn on recommendations</span></span>

<span data-ttu-id="511bf-112">Pour activer les recommandations de produit, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="511bf-112">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="511bf-113">Accédez à **Commerce et vente au détail &gt; Recommandations de produit &gt; Paramètres des recommandations**.</span><span class="sxs-lookup"><span data-stu-id="511bf-113">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="511bf-114">Dans la liste des paramètres partagés, sélectionnez **Listes des recommandations**.</span><span class="sxs-lookup"><span data-stu-id="511bf-114">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="511bf-115">Définissez l'option **Activer les recommandations** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="511bf-115">Set the **Enable recommendations** option to **Yes**.</span></span>

![activer les recommandations produit](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="511bf-117">Cette procédure démarre le processus de génération de listes de recommandations de produit.</span><span class="sxs-lookup"><span data-stu-id="511bf-117">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="511bf-118">Cette opération peut nécessiter jusqu'à plusieurs heures avant que les listes soient disponibles et puissent s'affichent sur point de vente (PDV) ou dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="511bf-118">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="511bf-119">Configuration des paramètres de la liste des recommandations</span><span class="sxs-lookup"><span data-stu-id="511bf-119">Configure recommendation list parameters</span></span>

<span data-ttu-id="511bf-120">Par défaut, la liste des recommandations de produit basée sur Machine Learning - Intelligence artificielle fournit des valeurs suggérées.</span><span class="sxs-lookup"><span data-stu-id="511bf-120">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="511bf-121">Vous pouvez modifier les valeurs suggérées par défaut pour les adapter au flux de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="511bf-121">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="511bf-122">Pour en savoir plus sur la manière de modifier les paramètres par défaut, accédez à [Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="511bf-122">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="511bf-123">Afficher les recommandations sur les appareils PDV</span><span class="sxs-lookup"><span data-stu-id="511bf-123">Show recommendations on POS devices</span></span>

<span data-ttu-id="511bf-124">Après avoir activé les recommandations dans le back-office Commerce, le volet de recommandations doit être ajouté à l'écran du PDV de contrôle à l'aide de l'outil de disposition.</span><span class="sxs-lookup"><span data-stu-id="511bf-124">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="511bf-125">Pour en savoir plus sur ce processus, voir [Ajouter un contrôle de recommandations à l'écran de transaction sur les périphériques de PDV](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="511bf-125">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="511bf-126">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="511bf-126">Enable personalized recommendations</span></span>

<span data-ttu-id="511bf-127">Pour plus d'informations sur la manière de recevoir des recommandations personnalisées, voir [Activer les recommandations personnalisées](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="511bf-127">To learn more about how to receive personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="511bf-128">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="511bf-128">Additional resources</span></span>

[<span data-ttu-id="511bf-129">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="511bf-129">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="511bf-130">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="511bf-130">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="511bf-131">Ajouter des listes de recommandation produit aux pages</span><span class="sxs-lookup"><span data-stu-id="511bf-131">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="511bf-132">Ajouter le panneau de recommandations aux appareils PDV</span><span class="sxs-lookup"><span data-stu-id="511bf-132">Add recommendations panel to POS devices</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="511bf-133">Vue d'ensemble du module de collecte de produits</span><span class="sxs-lookup"><span data-stu-id="511bf-133">Product collection module overview</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="511bf-134">Activer ADLS dans un environnement Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="511bf-134">Enable ADLS in Dynamics 365 environment</span></span>](enable-ADLS-environment.md)

