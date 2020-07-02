---
title: Ajouter des recommandations produit sur PDV
description: Cette rubrique décrit l'utilisation de recommandations de produit sur un appareil de PDV.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fabf08e8dde1b9b6d27af3e42d3aaff904b467b0
ms.sourcegitcommit: ac47e8679fb104515f7dcca509294264bd05d2b1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2020
ms.locfileid: "3454531"
---
# <a name="add-product-recommendations-on-pos"></a><span data-ttu-id="f858b-103">Ajouter des recommandations produit sur PDV</span><span class="sxs-lookup"><span data-stu-id="f858b-103">Add product recommendations on POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f858b-104">Les recommandations de produit sont essentiellement une application métier transformative qui s'étend dans tous les espaces commerciaux pour créer des expériences de découverte de produit taillées sur mesure, stimulantes et riches.</span><span class="sxs-lookup"><span data-stu-id="f858b-104">At its core, product recommendations are a transformative business application that span across all commerce spaces to create rich, engaging, and tailored product discovery experiences.</span></span> <span data-ttu-id="f858b-105">Pour implémenter cette fonctionnalité au PDV, suivez les étapes [comment ajouter des recommandations à vos périphériques de PDV.](add-recommendations-control-pos-screen.md)</span><span class="sxs-lookup"><span data-stu-id="f858b-105">To implement this feature on POS, follow the steps on [how to add recommendations to your POS devices.](add-recommendations-control-pos-screen.md)</span></span> 

<span data-ttu-id="f858b-106">Pour en savoir plus sur les fonctionnalités de recommandations produit, consultez la [vue d'ensemble des recommandations produit.](../commerce/product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="f858b-106">For more information about product recommendations features, read the [product recommendations overview.](../commerce/product-recommendations.md)</span></span> 

## <a name="scenarios"></a><span data-ttu-id="f858b-107">Scénarios</span><span class="sxs-lookup"><span data-stu-id="f858b-107">Scenarios</span></span>

<span data-ttu-id="f858b-108">Les recommandations de produit sont activées pour les scénarios de PDV suivants.</span><span class="sxs-lookup"><span data-stu-id="f858b-108">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="f858b-109">Elles sont disponibles dans le Cloud POS ou Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="f858b-109">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1. <span data-ttu-id="f858b-110">Sur la page **Détails de produit** :</span><span class="sxs-lookup"><span data-stu-id="f858b-110">On the **Product details** page:</span></span>

    - <span data-ttu-id="f858b-111">Si un associé du magasin visite une page **Détails de produit** lorsque vous regardez des transactions antérieures sur différents canaux, le service de recommandation propose des éléments supplémentaires susceptibles d'être achetés ensemble.</span><span class="sxs-lookup"><span data-stu-id="f858b-111">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendations service suggests additional items that are likely to be purchased together.</span></span>

    <span data-ttu-id="f858b-112">[![Recommandations sur la page de Détails du produit](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="f858b-112">[![Recommendations on the Product details page](./media/proddetails.png)](./media/proddetails.png)</span></span>

2. <span data-ttu-id="f858b-113">Sur la page **Transaction** :</span><span class="sxs-lookup"><span data-stu-id="f858b-113">On the **Transaction** page:</span></span>

    - <span data-ttu-id="f858b-114">Le moteur de recommandation suggère des articles selon la liste entière d'articles du panier qui sont fréquemment achetés ensemble.</span><span class="sxs-lookup"><span data-stu-id="f858b-114">The recommendation engine suggests items based on the entire list of items in the basket that are frequently bought together.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f858b-115">Pour afficher les recommandations sur la page **Transaction**, le détaillant doit actualiser la mise en page de l'écran dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f858b-115">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 Commerce.</span></span> <span data-ttu-id="f858b-116">Le contrôle **Recommandations** doit être déposé sur la page **Transaction**.</span><span class="sxs-lookup"><span data-stu-id="f858b-116">The **Recommendations** control must be dropped onto the **Transaction** page.</span></span>

    <span data-ttu-id="f858b-117">[![Recommandations sur la page Transaction](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="f858b-117">[![Recommendations on the Transaction page](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

## <a name="configure-commerce-to-enable-pos-recommendations"></a><span data-ttu-id="f858b-118">Configurer Commerce pour activer les recommandations de PDV</span><span class="sxs-lookup"><span data-stu-id="f858b-118">Configure Commerce to enable POS recommendations</span></span>

<span data-ttu-id="f858b-119">Pour paramétrer les recommandations de produit, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f858b-119">To set up product recommendations, follow these steps:</span></span>

1. <span data-ttu-id="f858b-120">Veillez à ce que votre service ait été mis à jour avec la **version 10.0.6.**</span><span class="sxs-lookup"><span data-stu-id="f858b-120">Ensure your service has been updated to the **10.0.6 build.**</span></span>
2. <span data-ttu-id="f858b-121">Suivez les instructions sur la procédure pour [activer les recommandations de produit](../commerce/enable-product-recommendations.md) pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="f858b-121">Follow the instructions on how to [enable product recommendations](../commerce/enable-product-recommendations.md) for your business.</span></span>
3. <span data-ttu-id="f858b-122">Facultatif : Pour afficher les recommandations dans l'écran de transaction, allez dans **Mise en page de l'écran**, choisissez une mise en page d'écran, lancez le **Concepteur de mise en page de l'écran**, puis faites glisser-déplacer le contrôle de **recommandations** à l'emplacement souhaité.</span><span class="sxs-lookup"><span data-stu-id="f858b-122">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>
4. <span data-ttu-id="f858b-123">Accédez à **Paramètres de commerce**, sélectionnez **Apprentissage machine**, sélectionnez **Oui** sous **Activer les recommandations de PDV**.</span><span class="sxs-lookup"><span data-stu-id="f858b-123">Go to **Commerce parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5. <span data-ttu-id="f858b-124">Pour afficher les recommandations sur le PDV, exécutez une tâche de configuration globale **1110**.</span><span class="sxs-lookup"><span data-stu-id="f858b-124">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="f858b-125">Pour refléter les modifications effectuées dans le concepteur de mise en page de l'écran du PDV, exécutez la tâche de configuration des canaux **1070**.</span><span class="sxs-lookup"><span data-stu-id="f858b-125">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>

## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a><span data-ttu-id="f858b-126">Résoudre les problèmes que vous rencontrez lorsque vous avez des recommandations produit déjà activées</span><span class="sxs-lookup"><span data-stu-id="f858b-126">Troubleshoot issues where you have Product recommendations already enabled</span></span>

- <span data-ttu-id="f858b-127">Accédez à **Paramètres de commerce** \> **Listes de recommandation** \> **Désactiver les recommandations produit** et exécutez **Tâche de configuration globale \[9999\]**.</span><span class="sxs-lookup"><span data-stu-id="f858b-127">Navigate to **Commerce Parameters** \> **Recommendation lists** \> **Disable product recommendations** and run **Global configuration job \[9999\]**.</span></span> 
- <span data-ttu-id="f858b-128">Si vous avez ajouté le **Contrôle de recommandations** à votre écran de transaction à l'aide du **Concepteur de mise en page de l'écran**, supprimez-le également.</span><span class="sxs-lookup"><span data-stu-id="f858b-128">If you added the **Recommendations control** to your transaction screen using the **Screen layout designer**, please remove that as well.</span></span>
- <span data-ttu-id="f858b-129">Si vous avez des questions supplémentaires, vérifiez [FAQ de recommandations du produit](../commerce/faq-recommendations.md) pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="f858b-129">If you have additional questions, check out the [Product recommendations FAQ](../commerce/faq-recommendations.md) for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f858b-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f858b-130">Additional resources</span></span>

[<span data-ttu-id="f858b-131">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="f858b-131">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="f858b-132">Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f858b-132">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="f858b-133">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="f858b-133">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="f858b-134">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="f858b-134">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="f858b-135">Désactiver les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="f858b-135">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="f858b-136">Ajouter des recommandations à l'écran de transaction</span><span class="sxs-lookup"><span data-stu-id="f858b-136">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="f858b-137">Ajuster des résultats des recommandations AI-ML</span><span class="sxs-lookup"><span data-stu-id="f858b-137">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="f858b-138">Créer manuellement des recommandations sélectionnées</span><span class="sxs-lookup"><span data-stu-id="f858b-138">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="f858b-139">Créer des recommandations avec des données de démonstration</span><span class="sxs-lookup"><span data-stu-id="f858b-139">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="f858b-140">FAQ sur les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="f858b-140">Product recommendations FAQ</span></span>](faq-recommendations.md)
