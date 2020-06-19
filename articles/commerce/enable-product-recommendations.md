---
title: Activer les recommandations produit
description: Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l'Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
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
ms.openlocfilehash: 694e5a451b8e25f3729364dfaed0adc7d242f2fe
ms.sourcegitcommit: fdc5dd9eb784c7d8e75692c8cdba083fe0dd87ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/26/2020
ms.locfileid: "3404207"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="cbcc2-103">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="cbcc2-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cbcc2-104">Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l'Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="cbcc2-105">Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d'ensemble des recommandations produit.](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="cbcc2-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="cbcc2-106">Recommandations avant contrôle</span><span class="sxs-lookup"><span data-stu-id="cbcc2-106">Recommendations pre-check</span></span>

<span data-ttu-id="cbcc2-107">Avant l'activation, notez que les recommandations de produit sont uniquement prises en charge pour les clients Commerce qui ont migré leur stockage pour utiliser Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-107">Before enabling, note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage.</span></span> 

<span data-ttu-id="cbcc2-108">Les configurations suivantes doivent être activées dans le back-office avant d'activer les recommandations :</span><span class="sxs-lookup"><span data-stu-id="cbcc2-108">The following configurations must be enabled in the back office before enabling recommendations:</span></span>

1. <span data-ttu-id="cbcc2-109">Assurez-vous qu'Azure Data Lake Storage a été acheté et validé avec succès dans l'environnement.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-109">Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment.</span></span> <span data-ttu-id="cbcc2-110">Pour en savoir plus, voir [S'assurer qu'Azure Data Lake Storage a été acheté et validé avec succès dans l'environnement](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="cbcc2-110">For more information, see [Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment](enable-ADLS-environment.md).</span></span>
2. <span data-ttu-id="cbcc2-111">Assurez-vous que l'actualisation du magasin d'entités a été automatisée.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-111">Ensure that the entity store refresh has been automated.</span></span> <span data-ttu-id="cbcc2-112">Pour plus d'informations, voir [S'assurer que l'actualisation du magasin d'entités a été automatisée](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="cbcc2-112">For more information, see [Ensure that the Entity store refresh has been automated](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>
3. <span data-ttu-id="cbcc2-113">Confirmez que la configuration d'identité Azure AD contient une entrée pour les recommandations.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-113">Confirm that Azure AD Identity configuration contains an entry for Recommendations.</span></span> <span data-ttu-id="cbcc2-114">Vous trouverez ci-dessous plus d'informations sur la façon d'effectuer cette action.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-114">More information on how to do this action is below.</span></span>

<span data-ttu-id="cbcc2-115">En outre, assurez-vous que les mesures RetailSale ont été activées.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-115">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="cbcc2-116">Pour en savoir plus sur ce processus de configuration, consultez [Utiliser les mesures](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span><span class="sxs-lookup"><span data-stu-id="cbcc2-116">To learn more about this set up process, see [Work with measures](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span></span>

## <a name="azure-ad-identity-configuration"></a><span data-ttu-id="cbcc2-117">Configuration de l'identité Azure AD</span><span class="sxs-lookup"><span data-stu-id="cbcc2-117">Azure AD Identity configuration</span></span>

<span data-ttu-id="cbcc2-118">Cette étape est requise pour tous les clients exécutant une configuration d'infrastructure en tant que service (IaaS).</span><span class="sxs-lookup"><span data-stu-id="cbcc2-118">This step is required for all customers running an infra-structure as a service (IaaS) configuration.</span></span> <span data-ttu-id="cbcc2-119">Pour les clients exécutant la structure de service (SF), cette étape doit être automatique et nous vous recommandons de vérifier que le paramètre est configuré comme prévu.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-119">For customers running on service fabric (SF), this step should be automatic and we recommend verifying the setting is configured as expected.</span></span>

### <a name="setup"></a><span data-ttu-id="cbcc2-120">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="cbcc2-120">Setup</span></span>

1. <span data-ttu-id="cbcc2-121">Depuis le back office, recherchez la page **Applications Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-121">From the back office, search for the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="cbcc2-122">Vérifiez s'il existe une entrée pour « RecommendationSystemApplication-1 ».</span><span class="sxs-lookup"><span data-stu-id="cbcc2-122">Verify if an entry exists for "RecommendationSystemApplication-1".</span></span>

<span data-ttu-id="cbcc2-123">Si l'entrée n'existe pas, ajoutez-en une nouvelle avec les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbcc2-123">If the entry does not exist, add a new entry with the following information:</span></span>

- <span data-ttu-id="cbcc2-124">**ID client** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span><span class="sxs-lookup"><span data-stu-id="cbcc2-124">**Client Id** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span></span>
- <span data-ttu-id="cbcc2-125">**Nom** - RecommendationSystemApplication-1</span><span class="sxs-lookup"><span data-stu-id="cbcc2-125">**Name** - RecommendationSystemApplication-1</span></span>
- <span data-ttu-id="cbcc2-126">**Identifiant d'utilisateur** - RetailServiceAccount</span><span class="sxs-lookup"><span data-stu-id="cbcc2-126">**User Id** - RetailServiceAccount</span></span>

<span data-ttu-id="cbcc2-127">Sauvegardez et fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-127">Save and close the page.</span></span> 

## <a name="turn-on-recommendations"></a><span data-ttu-id="cbcc2-128">Activer les recommandations</span><span class="sxs-lookup"><span data-stu-id="cbcc2-128">Turn on recommendations</span></span>

<span data-ttu-id="cbcc2-129">Pour activer les recommandations de produit, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-129">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="cbcc2-130">Accédez à **Commerce et vente au détail &gt; Recommandations de produit &gt; Paramètres des recommandations**.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-130">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="cbcc2-131">Dans la liste des paramètres partagés, sélectionnez **Listes des recommandations**.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-131">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="cbcc2-132">Définissez l'option **Activer les recommandations** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-132">Set the **Enable recommendations** option to **Yes**.</span></span>

![Activer les recommandations](./media/enablepersonalization.png)

> [!NOTE]
> <span data-ttu-id="cbcc2-134">Cette procédure démarre le processus de génération de listes de recommandations de produit.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-134">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="cbcc2-135">Cette opération peut nécessiter jusqu'à plusieurs heures avant que les listes soient disponibles et puissent s'affichent sur point de vente (PDV) ou dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-135">It may take several hours before the lists are available and can be viewed at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="cbcc2-136">Configuration des paramètres de la liste des recommandations</span><span class="sxs-lookup"><span data-stu-id="cbcc2-136">Configure recommendation list parameters</span></span>

<span data-ttu-id="cbcc2-137">Par défaut, la liste des recommandations de produit basée sur Machine Learning - Intelligence artificielle fournit des valeurs suggérées.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-137">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="cbcc2-138">Vous pouvez modifier les valeurs suggérées par défaut pour les adapter au flux de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-138">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="cbcc2-139">Pour en savoir plus sur la manière de modifier les paramètres par défaut, accédez à [Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="cbcc2-139">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="cbcc2-140">Afficher les recommandations sur les appareils PDV</span><span class="sxs-lookup"><span data-stu-id="cbcc2-140">Show recommendations on POS devices</span></span>

<span data-ttu-id="cbcc2-141">Après avoir activé les recommandations dans le back-office Commerce, le volet de recommandations doit être ajouté à l'écran du PDV de contrôle à l'aide de l'outil de disposition.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-141">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="cbcc2-142">Pour en savoir plus sur ce processus, voir [Ajouter un contrôle de recommandations à l'écran de transaction sur les périphériques de PDV](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="cbcc2-142">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="cbcc2-143">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="cbcc2-143">Enable personalized recommendations</span></span>

<span data-ttu-id="cbcc2-144">Dans Dynamics 365 Commerce, les détaillants peuvent proposer des recommandations de produit personnalisées (également appelées personnalisation).</span><span class="sxs-lookup"><span data-stu-id="cbcc2-144">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="cbcc2-145">Ainsi, des recommandations personnalisées peuvent être intégrées dans l'expérience client en ligne et au point de vente.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-145">In this way, personalized recommendations can be incorporated into the online customer experience and at the point of sale.</span></span> <span data-ttu-id="cbcc2-146">Si la fonctionnalité de personnalisation est activée, le système peut associer les informations d'achat et de produit d'un utilisateur pour générer des recommandations de produit individualisées.</span><span class="sxs-lookup"><span data-stu-id="cbcc2-146">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

<span data-ttu-id="cbcc2-147">Pour plus d'informations sur les recommandations personnalisées, voir [Activer les recommandations personnalisées](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="cbcc2-147">To learn more about personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cbcc2-148">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="cbcc2-148">Additional resources</span></span>

[<span data-ttu-id="cbcc2-149">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="cbcc2-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="cbcc2-150">Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="cbcc2-150">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="cbcc2-151">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="cbcc2-151">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="cbcc2-152">Désactiver les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="cbcc2-152">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="cbcc2-153">Ajouter des recommandations produit sur PDV</span><span class="sxs-lookup"><span data-stu-id="cbcc2-153">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="cbcc2-154">Ajouter des recommandations à l'écran de transaction</span><span class="sxs-lookup"><span data-stu-id="cbcc2-154">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="cbcc2-155">Ajuster des résultats des recommandations AI-ML</span><span class="sxs-lookup"><span data-stu-id="cbcc2-155">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="cbcc2-156">Créer manuellement des recommandations sélectionnées</span><span class="sxs-lookup"><span data-stu-id="cbcc2-156">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="cbcc2-157">Créer des recommandations avec des données de démonstration</span><span class="sxs-lookup"><span data-stu-id="cbcc2-157">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="cbcc2-158">FAQ sur les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="cbcc2-158">Product recommendations FAQ</span></span>](faq-recommendations.md)

