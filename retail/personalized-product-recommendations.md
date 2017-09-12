---
title: "Vue d'ensemble des recommandations produit personnalisées"
description: "Dans Dynamics 365 for Retail, les recommandations de produits peuvent être affichées sur le point de vente (PDV). Les recommandations sont des articles susceptibles d'intéresser les clients en fonction de leur historique d'achat, des articles de leur liste de souhaits et des articles achetés par d'autres clients en ligne ou dans des magasins traditionnels. Pour les détaillants ayant de gros catalogues, les recommandations personnalisées aident le client à découvrir les produits proposés. En mettant en avant des produits ciblés selon les intérêts et les habitudes d'achat des clients, les recommandations de produit peuvent aider les détaillants à réaliser des ventes de gamme supérieure/croisée, et à accroître la conservation des clients. Dans Dynamics 365 for Retail, les recommandations de produit sont fondées sur le Machine learning et les Cognitive Services de Microsoft Azure."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core, UnifiedOperations
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611, Retail Version
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: a3a3b5e87a797c29c13b180c248d1782805c4c31
ms.contentlocale: fr-fr
ms.lasthandoff: 06/29/2017


---

# <a name="personalized-product-recommendations-overview"></a><span data-ttu-id="2d1ec-107">Vue d'ensemble des recommandations produit personnalisées</span><span class="sxs-lookup"><span data-stu-id="2d1ec-107">Personalized product recommendations overview</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="2d1ec-108">Dans Dynamics 365 for Retail, les recommandations de produits peuvent être affichées sur le point de vente (PDV).</span><span class="sxs-lookup"><span data-stu-id="2d1ec-108">In Dynamics 365 for Retail, product recommendations can be displayed on the point of sale (POS) device.</span></span> <span data-ttu-id="2d1ec-109">Les recommandations sont des articles susceptibles d'intéresser les clients en fonction de leur historique d'achat, des articles de leur liste de souhaits et des articles achetés par d'autres clients en ligne ou dans des magasins traditionnels.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-109">The recommendations are items that the customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="2d1ec-110">Pour les détaillants ayant de gros catalogues, les recommandations personnalisées aident le client à découvrir les produits proposés.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-110">For retailers with large catalogs, recommendations help the customer with product discovery.</span></span> <span data-ttu-id="2d1ec-111">En mettant en avant des produits ciblés selon les intérêts et les habitudes d'achat des clients, les recommandations de produit peuvent aider les détaillants à réaliser des ventes de gamme supérieure/croisée, et à accroître la conservation des clients.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-111">By showcasing products targeted to a customer’s interests and buying habits, product recommendations can help retailers with up-sell and cross-sell, and can enhance customer retention.</span></span> <span data-ttu-id="2d1ec-112">Dans Dynamics 365 for Retail, les recommandations de produit sont fondées sur le Machine learning et les Cognitive Services de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-112">In Dynamics 365 for Retail, product recommendations are powered by cognitive services and Microsoft Azure machine learning.</span></span>

<a name="scenarios"></a><span data-ttu-id="2d1ec-113">Scénarios</span><span class="sxs-lookup"><span data-stu-id="2d1ec-113">Scenarios</span></span>
---------

<span data-ttu-id="2d1ec-114">Les recommandations de produit sont activées pour les scénarios de PDV suivants.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-114">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="2d1ec-115">Elles sont disponibles dans le Cloud POS ou Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="2d1ec-115">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1.  <span data-ttu-id="2d1ec-116">Sur la page **Détails de produit** :</span><span class="sxs-lookup"><span data-stu-id="2d1ec-116">On the **Product details** page:</span></span>

-   <span data-ttu-id="2d1ec-117">Si un associé du magasin visite une page **Détails de produit** lorsque vous regardez des transactions antérieures sur différents canaux, le moteur de recommandation propose des éléments supplémentaires susceptibles d'être achetés ensemble.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-117">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendation engine suggests additional items that are likely to be purchased together.</span></span>
-   <span data-ttu-id="2d1ec-118">Si l'associé du magasin ajoute un client à la transaction et qu'il visite une page **Détails de produit**, le moteur de recommandation fournit des recommandations personnalisées à l'aide de l'historique des transactions du client.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-118">If the store associate adds a customer to the transaction and then visits a **Product details** page, the recommendation engine provides personalized recommendations using the customer's transaction history.</span></span>

<span data-ttu-id="2d1ec-119">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="2d1ec-119">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span></span>

2.  <span data-ttu-id="2d1ec-120">Sur la page **Transaction** :</span><span class="sxs-lookup"><span data-stu-id="2d1ec-120">On the **Transaction** page:</span></span>

-   <span data-ttu-id="2d1ec-121">Le moteur de recommandation suggère des articles selon la liste entière d'articles du panier.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-121">The recommendation engine suggests items based on the entire list of items in the basket.</span></span>
-   <span data-ttu-id="2d1ec-122">Si l'associé du magasin ajoute un client à la transaction, le moteur de recommandation fournit des recommandations personnelles en utilisant l'historique des transactions du client et la liste des éléments dans le panier.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-122">If the store associate adds a customer to the transaction, the recommendation engine provides personal recommendations using the customer’s transaction history and the list of items in the basket.</span></span>

<span data-ttu-id="2d1ec-123">**Remarque**  Pour afficher les recommandations sur la page **Transaction**, le détaillant doit actualiser la mise en page de l'écran dans Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-123">**Note**  To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="2d1ec-124">Le contrôle **Recommandations** doit être déposé sur la page **Transaction**.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-124">The **Recommendations** control must be dropped on to the **Transaction** page.</span></span> <span data-ttu-id="2d1ec-125">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="2d1ec-125">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

3.  <span data-ttu-id="2d1ec-126">Sur la page **Détails du client** :</span><span class="sxs-lookup"><span data-stu-id="2d1ec-126">On the **Customer details** page:</span></span>
    -   <span data-ttu-id="2d1ec-127">Le moteur de recommandation propose des éléments basés sur l'ID utilisateur et les éléments dans la liste de souhaits du client.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-127">The recommendation engine suggests items based on the user ID and items in the customer’s wish list.</span></span>

<span data-ttu-id="2d1ec-128">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span><span class="sxs-lookup"><span data-stu-id="2d1ec-128">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span></span>

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a><span data-ttu-id="2d1ec-129">Configurer Dynamics 365 for Retail pour proposer des recommandations de PDV</span><span class="sxs-lookup"><span data-stu-id="2d1ec-129">Configure Dynamics 365 for Retail to enable POS recommendations</span></span>
<span data-ttu-id="2d1ec-130">Pour paramétrer des recommandations de produit, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-130">To set up product recommendations, you need to do the following.</span></span>

1.  <span data-ttu-id="2d1ec-131">Vérifiez que vous avez sélectionné la bonne **entité juridique**.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-131">Make sure that you have selected the correct **Legal entity**.</span></span>
2.  <span data-ttu-id="2d1ec-132">Accédez au **Magasin des entités**, sélectionnez **Ventes au détail**, puis cliquez sur **Actualiser**.** **Les données (ou vos données) de démonstration issues de votre base de données opérationnelle seront utilisées et déplacées vers le magasin des entités.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-132">Navigate to **Entity store**, select **Retail sales**, and then click **Refresh**.** **This will use the demo data (or your data) from your operational database and move it to Entity store.</span></span>
3.  <span data-ttu-id="2d1ec-133">Facultatif : Pour afficher les recommandations dans l'écran de transaction, allez dans **Mise en page de l'écran, **choisissez une mise en page d'écran, lancez le **Concepteur de mise en page de l'écran**,** **puis faites glisser-déplacer le ** contrôle de recommandations **à l'emplacement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-133">Optional: To display recommendations on the transaction screen, go to **Screen Layout, **choose your screen layout, launch the **Screen layout designer**,** **and then drop the **recommendations control **where needed.</span></span>
4.  <span data-ttu-id="2d1ec-134">Accédez à **Paramètres des ventes au détail**, sélectionnez **Machine-learning**, sélectionnez **Oui **sous **Accepter des recommandations de PDV**.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-134">Go to **Retail parameters**, select **Machine-learning**, select **Yes **under **Enable POS recommendations**.</span></span>
5.  <span data-ttu-id="2d1ec-135">Pour afficher les recommandations sur le PDV, exécutez une tâche de configuration globale **1110**.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-135">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="2d1ec-136">Pour refléter les modifications effectuées dans le concepteur de mise en page de l'écran du PDV, exécutez la tâche de configuration des canaux **1070**.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-136">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="2d1ec-137">[]()Comment ça fonctionne ?</span><span class="sxs-lookup"><span data-stu-id="2d1ec-137">[]()How does it work?</span></span>
<span data-ttu-id="2d1ec-138">Lorsque vous actualisez l'entité **Magasin des entités**, les actions suivantes ont lieu.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-138">When you refresh the **Entity store** entity, the following actions take place.</span></span>

-   <span data-ttu-id="2d1ec-139">Les données au format requis par les services cognitifs sont extraites de la base de données Dynamics 365 for Retail et envoyées au magasin des entités.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-139">Data in the format required by the Cognitive services is extracted from the Dynamics 365 for Retail operational database and sent to the Entity store.</span></span>
-   <span data-ttu-id="2d1ec-140">Les données sont utilisées par Azure Data Factory (ADF) pour nettoyer les données à l'aide des scripts de ruche dans le cadre des activités ADF.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-140">The data is used by Azure Data Factory (ADF) to cleanse the data using Hive scripts as part of ADF activities.</span></span> <span data-ttu-id="2d1ec-141">Les données nettoyées sont enregistrées en stock d'objets blob.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-141">Cleansed data is stored in blob storage.</span></span>
-   <span data-ttu-id="2d1ec-142">Les données du stockage d'objets blob sont utilisées par l'API de Microsoft Cognitive Services pour tester un modèle de recommandation.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-142">Data from blob storage is used by the Cognitive services API to train a recommendation model.</span></span>

<span data-ttu-id="2d1ec-143">Lorsque vous sélectionnez **Activer les recommandations** et exécutez les tâches de configuration, les actions suivantes ont lieu.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-143">When you turn on **Enable recommendations** and run the configuration jobs, the following actions take place.</span></span>

-   <span data-ttu-id="2d1ec-144">Les informations d'identification et l'ID du modèle sont prélevés de l'API et enregistrés dans la base de données Dynamics 365 for Retail, dans le web.config pour AOS, ainsi que le serveur de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-144">Model credentials and ID are picked up from the API and stored in the Dynamics 365 for Retail operational database, in the web.config for AOS, and also in the retail server.</span></span>
-   <span data-ttu-id="2d1ec-145">Les informations d'identification et l'ID du modèle sont mis à la disposition de CRT afin que les appels de recommandations de produits de Cloud POS et MPOS en mode en ligne puissent être respectés.</span><span class="sxs-lookup"><span data-stu-id="2d1ec-145">Model credentials and ID are made available to CRT so that calls for product recommendations from Cloud POS and MPOS in online mode can be honored.</span></span>


<a name="see-also"></a><span data-ttu-id="2d1ec-146">Voir également :</span><span class="sxs-lookup"><span data-stu-id="2d1ec-146">See also</span></span>
--------

[<span data-ttu-id="2d1ec-147">Ajouter un contrôle de recommandations à la page de transaction sur un périphérique de PDV</span><span class="sxs-lookup"><span data-stu-id="2d1ec-147">Add a recommendations control to the transaction page on a POS device</span></span>](add-recommendations-control-pos-screen.md)




