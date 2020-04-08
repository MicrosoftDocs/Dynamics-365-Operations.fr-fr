---
title: Activer ADLS dans un environnement Dynamics 365 Commerce
description: Cette rubrique explique comment activer et tester Azure Data Lake Storage (ADLS) pour un environnement Dynamics 365 Commerce, ce qui est une condition préalable à l'activation des recommandations de produits.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3c037f5603af5af84917084eefa1edd508891c0d
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154434"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="3e1d7-103">Activer ADLS dans un environnement Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3e1d7-103">Enable ADLS in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3e1d7-104">Cette rubrique explique comment activer et tester Azure Data Lake Storage (ADLS) pour un environnement Dynamics 365 Commerce, ce qui est une condition préalable à l'activation des recommandations de produits.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-104">This topic explains how to enable and test Azure Data Lake Storage (ADLS) for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

## <a name="overview"></a><span data-ttu-id="3e1d7-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="3e1d7-105">Overview</span></span>

<span data-ttu-id="3e1d7-106">Dans la solution Dynamics 365 Commerce, toutes les informations sur les produits et les transactions sont suivies dans le magasin des entités de l'environnement.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-106">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="3e1d7-107">Pour rendre ces données accessibles à d'autres services Dynamics 365, tels que l'analyse de données, le décisionnel et les recommandations personnalisées, il est nécessaire de connecter l'environnement à une solution appartenant au client Azure Data Lake Storage Gen 2 (ADLS).</span><span class="sxs-lookup"><span data-stu-id="3e1d7-107">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 (ADLS) solution.</span></span>

<span data-ttu-id="3e1d7-108">Comme ADLS est configuré dans un environnement, toutes les données nécessaires sont reflétées à partir du magasin d'entités tout en étant protégées et sous le contrôle du client.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-108">As ADLS is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="3e1d7-109">Si des recommandations de produits ou des recommandations personnalisées sont également activées dans l'environnement, la pile de recommandations de produits se verra accorder l'accès au dossier dédié dans ADLS pour récupérer les données du client et calculer des recommandations en fonction de celles-ci.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-109">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in ADLS to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3e1d7-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="3e1d7-110">Prerequisites</span></span>

<span data-ttu-id="3e1d7-111">Les clients doivent avoir ADLS configuré dans un abonnement Azure qu'ils possèdent.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-111">Customers need to have ADLS configured in an Azure subscription that they own.</span></span> <span data-ttu-id="3e1d7-112">Cette rubrique ne couvre pas l'achat d'un abonnement Azure ni la configuration d'un compte de stockage compatible ADLS.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-112">This topic does not cover the purchase of an Azure subscription or the setup of an ADLS-enabled storage account.</span></span>

<span data-ttu-id="3e1d7-113">Pour plus d'informations sur ADLS, voir [Documentation ADLS officielle](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="3e1d7-113">For more information about ADLS, see [ADLS official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="3e1d7-114">Étapes de configuration</span><span class="sxs-lookup"><span data-stu-id="3e1d7-114">Configuration steps</span></span>

<span data-ttu-id="3e1d7-115">Cette section couvre les étapes de configuration nécessaires pour activer ADLS dans un environnement.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-115">This section covers the configuration steps necessary for enabling ADLS in an environment.</span></span>

### <a name="enable-adls-in-the-environment"></a><span data-ttu-id="3e1d7-116">Activer ADLS dans l'environnement</span><span class="sxs-lookup"><span data-stu-id="3e1d7-116">Enable ADLS in the environment</span></span>

1. <span data-ttu-id="3e1d7-117">Connectez-vous au portail de back-office de l'environnement.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-117">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="3e1d7-118">Recherchez **Paramètres système** et accédez à l'onglet **Connexions de données**.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-118">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="3e1d7-119">Paramétrez **Activer l'intégration de Data Lake** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-119">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="3e1d7-120">Paramétrez **Actualiser le Data Lake** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-120">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="3e1d7-121">Puis entrez les informations requises suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e1d7-121">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="3e1d7-122">**ID d'application** // **Secret de l'application** // **Nom DNS** - Nécessaire pour se connecter à KeyVault où le secret ADLS est stocké.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-122">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the ADLS secret is stored.</span></span>
    1. <span data-ttu-id="3e1d7-123">**Nom du secret** - Le nom du secret stocké dans KeyVault et utilisé pour s'authentifier auprès d'ADLS.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-123">**Secret name** - The secret name stored in KeyVault and used to authenticate with ADLS.</span></span>
1. <span data-ttu-id="3e1d7-124">Enregistrez vos modifications dans le coin supérieur gauche de la page.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-124">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="3e1d7-125">L'image suivante présente un exemple de configuration ADLS.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-125">The following image shows an example ADLS configuration.</span></span>

![Exemple de configuration ADLS](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a><span data-ttu-id="3e1d7-127">Tester la connexion ADLS</span><span class="sxs-lookup"><span data-stu-id="3e1d7-127">Test the ADLS connection</span></span>

1. <span data-ttu-id="3e1d7-128">Testez la connexion à KeyVault à l'aide du lien **Tester Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-128">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="3e1d7-129">Testez la connexion à ADLS à l'aide du lien **Tester Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-129">Test the connection to ADLS using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="3e1d7-130">Si les tests échouent, vérifiez que toutes les informations KeyVault ajoutées ci-dessus sont correctes, puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-130">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="3e1d7-131">Une fois les tests de connexion réussis, vous devez activer l'actualisation automatique pour le magasin d'entités.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-131">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="3e1d7-132">Pour activer l'actualisation automatique pour le magasin d'entités, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-132">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="3e1d7-133">Recherchez **Magasin d'entités**.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-133">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="3e1d7-134">Dans la liste de gauche, accédez à l'entrée **RetailSales**, puis sélectionnez **Éditer**.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-134">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="3e1d7-135">Veillez à ce que l'option **Actualisation automatique activée** soit réglée sur **Oui**, sélectionnez **Actualiser**, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-135">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="3e1d7-136">L'image suivante montre un exemple de magasin d'entités avec l'actualisation automatique activée.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-136">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Exemple de magasin d'entités avec l'actualisation automatique activée](./media/exampleADLSConfig2.png)

<span data-ttu-id="3e1d7-138">ADLS est maintenant configuré pour l'environnement.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-138">ADLS is now configured for the environment.</span></span> 

<span data-ttu-id="3e1d7-139">Si ce n'est déjà fait, suivez les étapes pour l'[activation des recommandations de produits et de la personnalisation](enable-product-recommendations.md) pour l'environnement.</span><span class="sxs-lookup"><span data-stu-id="3e1d7-139">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e1d7-140">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3e1d7-140">Additional resources</span></span>

[<span data-ttu-id="3e1d7-141">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="3e1d7-141">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="3e1d7-142">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="3e1d7-142">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="3e1d7-143">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="3e1d7-143">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="3e1d7-144">Désactiver les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="3e1d7-144">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="3e1d7-145">Ajouter des recommandations produit sur PDV</span><span class="sxs-lookup"><span data-stu-id="3e1d7-145">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="3e1d7-146">Ajouter des recommandations à l'écran de transaction</span><span class="sxs-lookup"><span data-stu-id="3e1d7-146">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="3e1d7-147">Ajuster des résultats des recommandations AI-ML</span><span class="sxs-lookup"><span data-stu-id="3e1d7-147">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="3e1d7-148">Créer manuellement des recommandations sélectionnées</span><span class="sxs-lookup"><span data-stu-id="3e1d7-148">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="3e1d7-149">Créer des recommandations avec des données de démonstration</span><span class="sxs-lookup"><span data-stu-id="3e1d7-149">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="3e1d7-150">FAQ sur les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="3e1d7-150">Product recommendations FAQ</span></span>](faq-recommendations.md)


