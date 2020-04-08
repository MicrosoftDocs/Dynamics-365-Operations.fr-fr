---
title: Activer les recommandations produit
description: Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l'Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
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
ms.openlocfilehash: d8a579be5df3c5e7718a6fb4720341f3bd01a64c
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154411"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="e13f6-103">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="e13f6-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e13f6-104">Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l'Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e13f6-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="e13f6-105">Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d'ensemble des recommandations produit.](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="e13f6-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="e13f6-106">Recommandations avant contrôle</span><span class="sxs-lookup"><span data-stu-id="e13f6-106">Recommendations pre-check</span></span>

<span data-ttu-id="e13f6-107">Avant l'activation, notez que les recommandations de produit sont uniquement prises en charge pour les clients Commerce qui ont migré leur stockage pour utiliser Azure Data Lake Storage (ADLS).</span><span class="sxs-lookup"><span data-stu-id="e13f6-107">Before enabling, please note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="e13f6-108">Pour connaître les étapes d'activation d'ADLS, consultez [Comment activer ADLS dans un environnement Dynamics 365](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e13f6-108">For steps on enabling ADLS, see [How to enable ADLS in a Dynamics 365 environment](enable-ADLS-environment.md).</span></span>

<span data-ttu-id="e13f6-109">En outre, assurez-vous que les mesures RetailSale ont été activées.</span><span class="sxs-lookup"><span data-stu-id="e13f6-109">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="e13f6-110">Pour en savoir plus sur ce processus de paramétrage, allez [ici.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="e13f6-110">To learn more about this set up process, go [here.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="e13f6-111">Activer les recommandations</span><span class="sxs-lookup"><span data-stu-id="e13f6-111">Turn on recommendations</span></span>

<span data-ttu-id="e13f6-112">Pour activer les recommandations de produit, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e13f6-112">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="e13f6-113">Accédez à **Commerce et vente au détail &gt; Recommandations de produit &gt; Paramètres des recommandations**.</span><span class="sxs-lookup"><span data-stu-id="e13f6-113">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="e13f6-114">Dans la liste des paramètres partagés, sélectionnez **Listes des recommandations**.</span><span class="sxs-lookup"><span data-stu-id="e13f6-114">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="e13f6-115">Définissez l'option **Activer les recommandations** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="e13f6-115">Set the **Enable recommendations** option to **Yes**.</span></span>

![activer les recommandations produit](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="e13f6-117">Cette procédure démarre le processus de génération de listes de recommandations de produit.</span><span class="sxs-lookup"><span data-stu-id="e13f6-117">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="e13f6-118">Cette opération peut nécessiter jusqu'à plusieurs heures avant que les listes soient disponibles et puissent s'affichent sur point de vente (PDV) ou dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e13f6-118">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="e13f6-119">Configuration des paramètres de la liste des recommandations</span><span class="sxs-lookup"><span data-stu-id="e13f6-119">Configure recommendation list parameters</span></span>

<span data-ttu-id="e13f6-120">Par défaut, la liste des recommandations de produit basée sur Machine Learning - Intelligence artificielle fournit des valeurs suggérées.</span><span class="sxs-lookup"><span data-stu-id="e13f6-120">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="e13f6-121">Vous pouvez modifier les valeurs suggérées par défaut pour les adapter au flux de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="e13f6-121">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="e13f6-122">Pour en savoir plus sur la manière de modifier les paramètres par défaut, accédez à [Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="e13f6-122">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="e13f6-123">Afficher les recommandations sur les appareils PDV</span><span class="sxs-lookup"><span data-stu-id="e13f6-123">Show recommendations on POS devices</span></span>

<span data-ttu-id="e13f6-124">Après avoir activé les recommandations dans le back-office Commerce, le volet de recommandations doit être ajouté à l'écran du PDV de contrôle à l'aide de l'outil de disposition.</span><span class="sxs-lookup"><span data-stu-id="e13f6-124">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="e13f6-125">Pour en savoir plus sur ce processus, voir [Ajouter un contrôle de recommandations à l'écran de transaction sur les périphériques de PDV](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="e13f6-125">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="e13f6-126">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="e13f6-126">Enable personalized recommendations</span></span>

<span data-ttu-id="e13f6-127">Pour plus d'informations sur la manière de recevoir des recommandations personnalisées, voir [Activer les recommandations personnalisées](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="e13f6-127">To learn more about how to receive personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e13f6-128">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e13f6-128">Additional resources</span></span>

[<span data-ttu-id="e13f6-129">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="e13f6-129">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="e13f6-130">Activer ADLS dans un environnement Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e13f6-130">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="e13f6-131">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="e13f6-131">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="e13f6-132">Désactiver les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="e13f6-132">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="e13f6-133">Ajouter des recommandations produit sur PDV</span><span class="sxs-lookup"><span data-stu-id="e13f6-133">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="e13f6-134">Ajouter des recommandations à l'écran de transaction</span><span class="sxs-lookup"><span data-stu-id="e13f6-134">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="e13f6-135">Ajuster des résultats des recommandations AI-ML</span><span class="sxs-lookup"><span data-stu-id="e13f6-135">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="e13f6-136">Créer manuellement des recommandations sélectionnées</span><span class="sxs-lookup"><span data-stu-id="e13f6-136">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="e13f6-137">Créer des recommandations avec des données de démonstration</span><span class="sxs-lookup"><span data-stu-id="e13f6-137">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="e13f6-138">FAQ sur les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="e13f6-138">Product recommendations FAQ</span></span>](faq-recommendations.md)

