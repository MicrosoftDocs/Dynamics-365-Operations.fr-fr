---
title: Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce
description: Cette rubrique explique comment activer et tester Azure Data Lake Storage pour un environnement Dynamics 365 Commerce, ce qui est une condition préalable à l'activation des recommandations de produits.
author: bebeale
manager: AnnBe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5887ae7983fd817a929a185327671b301808b354
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478234"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="6a334-103">Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6a334-103">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6a334-104">Cette rubrique explique comment activer et tester Azure Data Lake Storage pour un environnement Dynamics 365 Commerce, ce qui est une condition préalable à l'activation des recommandations de produits.</span><span class="sxs-lookup"><span data-stu-id="6a334-104">This topic explains how to enable and test Azure Data Lake Storage for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

<span data-ttu-id="6a334-105">Dans la solution Dynamics 365 Commerce, toutes les informations sur les produits et les transactions sont suivies dans le magasin des entités de l'environnement.</span><span class="sxs-lookup"><span data-stu-id="6a334-105">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="6a334-106">Pour rendre ces données accessibles à d'autres services Dynamics 365, tels que l'analyse de données, le décisionnel et les recommandations personnalisées, il est nécessaire de connecter l'environnement à une solution appartenant au client Azure Data Lake Storage Gen 2.</span><span class="sxs-lookup"><span data-stu-id="6a334-106">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 solution.</span></span>

<span data-ttu-id="6a334-107">Comme Azure Data Lake Storage est configuré dans un environnement, toutes les données nécessaires sont reflétées à partir du magasin d'entités tout en étant protégées et sous le contrôle du client.</span><span class="sxs-lookup"><span data-stu-id="6a334-107">As Azure Data Lake Storage is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="6a334-108">Si des recommandations de produits ou des recommandations personnalisées sont également activées dans l'environnement, la pile de recommandations de produits se verra accorder l'accès au dossier dédié dans Azure Data Lake Storage pour récupérer les données du client et calculer des recommandations en fonction de celles-ci.</span><span class="sxs-lookup"><span data-stu-id="6a334-108">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in Azure Data Lake Storage to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6a334-109">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="6a334-109">Prerequisites</span></span>

<span data-ttu-id="6a334-110">Les clients doivent avoir Azure Data Lake Storage configuré dans un abonnement Azure qu'ils possèdent.</span><span class="sxs-lookup"><span data-stu-id="6a334-110">Customers need to have Azure Data Lake Storage configured in an Azure subscription that they own.</span></span> <span data-ttu-id="6a334-111">Cette rubrique ne couvre pas l'achat d'un abonnement Azure ni la configuration d'un compte de stockage compatible Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="6a334-111">This topic does not cover the purchase of an Azure subscription or the setup of an Azure Data Lake Storage-enabled storage account.</span></span>

<span data-ttu-id="6a334-112">Pour plus d'informations sur Azure Data Lake Storage, voir [Documentation officielle d'Azure Data Lake Storage Gen2](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="6a334-112">For more information about Azure Data Lake Storage, see [Azure Data Lake Storage Gen2 official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="6a334-113">Étapes de configuration</span><span class="sxs-lookup"><span data-stu-id="6a334-113">Configuration steps</span></span>

<span data-ttu-id="6a334-114">Cette section couvre les étapes de configuration nécessaires pour activer Azure Data Lake Storage dans un environnement en ce qui concerne les recommandations de produits.</span><span class="sxs-lookup"><span data-stu-id="6a334-114">This section covers the configuration steps necessary for enabling Azure Data Lake Storage in an environment as it relates to product recommendations.</span></span>
<span data-ttu-id="6a334-115">Pour une vue d'ensemble plus approfondie des étapes requises pour activer Azure Data Lake Storage, voir [Rendre le magasin des entités disponible en tant que Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="6a334-115">For a more in-depth overview of the steps required to enable Azure Data Lake Storage, see [Make entity store available as a Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>

### <a name="enable-azure-data-lake-storage-in-the-environment"></a><span data-ttu-id="6a334-116">Activer Azure Data Lake Storage dans l'environnement</span><span class="sxs-lookup"><span data-stu-id="6a334-116">Enable Azure Data Lake Storage in the environment</span></span>

1. <span data-ttu-id="6a334-117">Connectez-vous au portail de back-office de l'environnement.</span><span class="sxs-lookup"><span data-stu-id="6a334-117">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="6a334-118">Recherchez **Paramètres système** et accédez à l'onglet **Connexions de données**.</span><span class="sxs-lookup"><span data-stu-id="6a334-118">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="6a334-119">Paramétrez **Activer l'intégration de Data Lake** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="6a334-119">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="6a334-120">Paramétrez **Actualiser le Data Lake** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="6a334-120">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="6a334-121">Puis entrez les informations requises suivantes :</span><span class="sxs-lookup"><span data-stu-id="6a334-121">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="6a334-122">**ID d'application** // **Secret de l'application** // **Nom DNS** - Nécessaire pour se connecter à KeyVault où le secret Azure Data Lake Storage est stocké.</span><span class="sxs-lookup"><span data-stu-id="6a334-122">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the Azure Data Lake Storage secret is stored.</span></span>
    1. <span data-ttu-id="6a334-123">**Nom du secret** - Le nom du secret stocké dans KeyVault et utilisé pour s'authentifier auprès d'Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="6a334-123">**Secret name** - The secret name stored in KeyVault and used to authenticate with Azure Data Lake Storage.</span></span>
1. <span data-ttu-id="6a334-124">Enregistrez vos modifications dans le coin supérieur gauche de la page.</span><span class="sxs-lookup"><span data-stu-id="6a334-124">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="6a334-125">L'image suivante présente un exemple de configuration Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="6a334-125">The following image shows an example Azure Data Lake Storage configuration.</span></span>

![Exemple de configuration Azure Data Lake Storage](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a><span data-ttu-id="6a334-127">Tester la connexion Azure Data Lake Storage</span><span class="sxs-lookup"><span data-stu-id="6a334-127">Test the Azure Data Lake Storage connection</span></span>

1. <span data-ttu-id="6a334-128">Testez la connexion à KeyVault à l'aide du lien **Tester Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="6a334-128">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="6a334-129">Testez la connexion à Azure Data Lake Storage à l'aide du lien **Tester le stockage Azure**.</span><span class="sxs-lookup"><span data-stu-id="6a334-129">Test the connection to Azure Data Lake Storage using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="6a334-130">Si les tests échouent, vérifiez que toutes les informations KeyVault ajoutées ci-dessus sont correctes, puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="6a334-130">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="6a334-131">Une fois les tests de connexion réussis, vous devez activer l'actualisation automatique pour le magasin d'entités.</span><span class="sxs-lookup"><span data-stu-id="6a334-131">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="6a334-132">Pour activer l'actualisation automatique pour le magasin d'entités, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6a334-132">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="6a334-133">Recherchez **Magasin d'entités**.</span><span class="sxs-lookup"><span data-stu-id="6a334-133">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="6a334-134">Dans la liste de gauche, accédez à l'entrée **RetailSales**, puis sélectionnez **Éditer**.</span><span class="sxs-lookup"><span data-stu-id="6a334-134">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="6a334-135">Veillez à ce que l'option **Actualisation automatique activée** soit réglée sur **Oui**, sélectionnez **Actualiser**, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6a334-135">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="6a334-136">L'image suivante montre un exemple de magasin d'entités avec l'actualisation automatique activée.</span><span class="sxs-lookup"><span data-stu-id="6a334-136">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Exemple de magasin d'entités avec l'actualisation automatique activée](./media/exampleADLSConfig2.png)

<span data-ttu-id="6a334-138">Azure Data Lake Storage est maintenant configuré pour l'environnement.</span><span class="sxs-lookup"><span data-stu-id="6a334-138">Azure Data Lake Storage is now configured for the environment.</span></span> 

<span data-ttu-id="6a334-139">Si ce n'est déjà fait, suivez les étapes pour l'[activation des recommandations de produits et de la personnalisation](enable-product-recommendations.md) pour l'environnement.</span><span class="sxs-lookup"><span data-stu-id="6a334-139">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6a334-140">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6a334-140">Additional resources</span></span>

[<span data-ttu-id="6a334-141">Rendre le magasin des entités disponible en tant que Data Lake</span><span class="sxs-lookup"><span data-stu-id="6a334-141">Make entity store available as a data lake</span></span>](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[<span data-ttu-id="6a334-142">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="6a334-142">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="6a334-143">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="6a334-143">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="6a334-144">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="6a334-144">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="6a334-145">Désactiver les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="6a334-145">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="6a334-146">Activer les recommandations « acheter des aspects similaires »</span><span class="sxs-lookup"><span data-stu-id="6a334-146">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="6a334-147">Ajouter des recommandations produit sur PDV</span><span class="sxs-lookup"><span data-stu-id="6a334-147">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="6a334-148">Ajouter des recommandations à l’écran de transaction</span><span class="sxs-lookup"><span data-stu-id="6a334-148">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="6a334-149">Ajuster des résultats des recommandations AI-ML</span><span class="sxs-lookup"><span data-stu-id="6a334-149">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="6a334-150">Créer manuellement des recommandations sélectionnées</span><span class="sxs-lookup"><span data-stu-id="6a334-150">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="6a334-151">Créer des recommandations avec des données de démonstration</span><span class="sxs-lookup"><span data-stu-id="6a334-151">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="6a334-152">FAQ sur les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="6a334-152">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
