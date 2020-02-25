---
title: Refuser les recommandations personnalisées
description: Cette rubrique explique comment vous pouvez laisser les clients refuser la réception des recommandations personnalisées dans Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 01/28/2020
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
ms.openlocfilehash: 8e7b800218f68167901d86d61ae483680a04cfab
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3025246"
---
# <a name="opt-out-of-personalized-recommendations"></a><span data-ttu-id="4a89f-103">Refuser les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="4a89f-103">Opt out of personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4a89f-104">Cette rubrique explique comment vous pouvez laisser les clients refuser la réception des recommandations personnalisées dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4a89f-104">This topic explains how you can let customers opt out of receiving personalized recommendations in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4a89f-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="4a89f-105">Overview</span></span>

<span data-ttu-id="4a89f-106">Lors de la création d'un compte, la réception des recommandations personnalisées est automatiquement configurée pour les nouveaux clients.</span><span class="sxs-lookup"><span data-stu-id="4a89f-106">During account creation, new customers are automatically set up to receive personalized recommendations.</span></span> <span data-ttu-id="4a89f-107">Toutefois, Dynamics 365 Commerce offre aux détaillants diverses manières d'autoriser les utilisateurs à refuser de recevoir ces recommandations et de limiter le traitement de leurs données personnelles.</span><span class="sxs-lookup"><span data-stu-id="4a89f-107">However, Dynamics 365 Commerce provides various ways for retailers to let users opt out of receiving these recommendations and restrict the processing of their personal data.</span></span> <span data-ttu-id="4a89f-108">Les utilisateurs authentifiés qui refusent de recevoir les recommandations personnalisées cessent immédiatement de voir les listes personnalisées.</span><span class="sxs-lookup"><span data-stu-id="4a89f-108">Authenticated users who opt out of receiving personalized recommendations will immediately stop seeing personalized lists.</span></span> <span data-ttu-id="4a89f-109">De plus, toutes les données personnelles collectées pour la personnalisation sont supprimées des modèles de recommandations personnalisées.</span><span class="sxs-lookup"><span data-stu-id="4a89f-109">Additionally, all personal data that is collected for personalization will be removed from personalized recommendations models.</span></span>

<span data-ttu-id="4a89f-110">Pour plus d'informations sur les recommandations de produit personnalisées, voir [Activer les recommandations personnalisées](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="4a89f-110">For more information about personalized product recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a><span data-ttu-id="4a89f-111">Méthodes de mise en œuvre d'une expérience de désinscription côté détaillants</span><span class="sxs-lookup"><span data-stu-id="4a89f-111">Ways for retailers to implement an opt-out experience</span></span>

<span data-ttu-id="4a89f-112">Les détaillants disposent de 3 méthodes pour mettre en œuvre d'une expérience de désinscription.</span><span class="sxs-lookup"><span data-stu-id="4a89f-112">Retailers have three ways to implement an opt-out experience.</span></span>

### <a name="opting-out-on-behalf-of-users"></a><span data-ttu-id="4a89f-113">Refus pour le compte des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4a89f-113">Opting out on behalf of users</span></span>

<span data-ttu-id="4a89f-114">Dans la gestion de compte dans le back office Commerce, les détaillants peuvent refuser au nom des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4a89f-114">In Account management in Commerce back office, retailers can opt out on behalf of users.</span></span>

1. <span data-ttu-id="4a89f-115">Depuis la page d'accueil du back-office, recherchez **tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="4a89f-115">From the back-office home page, search for **all customers**.</span></span>
1. <span data-ttu-id="4a89f-116">Recherchez et sélectionnez un client, puis sélectionnez l'organisateur **Vente au détail**.</span><span class="sxs-lookup"><span data-stu-id="4a89f-116">Search for and select a customer, and then select the **Retail** FastTab.</span></span>

    ![Organisateur Vente au détail](./media/Disablepersonalizationpart1.png)

1. <span data-ttu-id="4a89f-118">Sous **Confidentialité**, définissez l'option **Désactiver la personnalisation** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="4a89f-118">Under **Privacy**, set the **Disable personalization** option to **Yes**.</span></span>

    ![Paramètres de confidentialité](./media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="4a89f-120">Cliquez sur **Enregistrer**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4a89f-120">Select **Save**, and close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="4a89f-121">Expérience de désinscription basée sur les modules</span><span class="sxs-lookup"><span data-stu-id="4a89f-121">Module-based opt-out experience</span></span>

<span data-ttu-id="4a89f-122">Les détaillants peuvent laisser les utilisateurs authentifiés refuser par eux-mêmes les recommandations personnalisées.</span><span class="sxs-lookup"><span data-stu-id="4a89f-122">Retailers can let authenticated users opt out of personalized recommendations by themselves.</span></span> <span data-ttu-id="4a89f-123">Pour proposer cette expérience de désinscription, ajoutez le module de refus utilisateur aux pages du profil de compte client.</span><span class="sxs-lookup"><span data-stu-id="4a89f-123">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="4a89f-124">Extensions personnalisées</span><span class="sxs-lookup"><span data-stu-id="4a89f-124">Custom extensions</span></span>

<span data-ttu-id="4a89f-125">Les détaillants peuvent créer leurs propres extensions pour gérer l'expérience de désinscription pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4a89f-125">Retailers can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="4a89f-126">Pour plus d'informations, voir [Appeler les API Retail Server](e-commerce-extensibility/call-retail-server-apis.md) et [Extensibilité des canaux en ligne](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="4a89f-126">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a><span data-ttu-id="4a89f-127">Obtenir une copie numérique des données de recommandations personnalisées pour le compte d'un utilisateur authentifié</span><span class="sxs-lookup"><span data-stu-id="4a89f-127">Obtain a digital copy of personalized recommendations data on behalf of an authenticated user</span></span>

<span data-ttu-id="4a89f-128">Les clients peuvent souhaiter obtenir une copie numérique de leurs données personnelles et afficher également une vue exportée des résultats de leurs recommandations.</span><span class="sxs-lookup"><span data-stu-id="4a89f-128">Customers might want to obtain a digital copy of their personal data and also see an exported view of their recommendations results.</span></span> <span data-ttu-id="4a89f-129">Si un client demande ces informations, le détaillant doit créer une extension personnalisée qui appelle l'interface de programmation d'application (API) de Retail Server et demande les résultats complets à partir de la liste **Des choix pour vous**, basée sur l'ID du client.</span><span class="sxs-lookup"><span data-stu-id="4a89f-129">If a customer requests this information, the retailer must create a customized extension that calls the Retail Server application programming interface (API) and queries for the full results from the **Picks for you** list, based on the customer's customer ID.</span></span> <span data-ttu-id="4a89f-130">Les résultats peuvent ensuite être exportés au format CSV (valeurs séparées par des virgules) et partagés avec le client.</span><span class="sxs-lookup"><span data-stu-id="4a89f-130">The results can then be exported in comma-separated values (CSV) format and shared with the customer.</span></span>

<span data-ttu-id="4a89f-131">L'exemple suivant montre comment un détaillant peut réaliser cette tâche.</span><span class="sxs-lookup"><span data-stu-id="4a89f-131">The following example shows how a retailer can accomplish this task.</span></span>

1. <span data-ttu-id="4a89f-132">Le détaillant crée une extension personnalisée pour extraire les données de recommandations personnelles pour le compte de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4a89f-132">The retailer creates a custom extension to pull personal recommendations data on behalf of the user.</span></span> <span data-ttu-id="4a89f-133">Pour des informations sur la création de modules, le clonage des modules existants, l'appel des API Retail Server et l'appel des actions de données, voir [Extensibilité des canaux en ligne](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="4a89f-133">For information about how to create modules, clone existing modules, call Retail Server APIs, and call data actions, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>
2. <span data-ttu-id="4a89f-134">L'extension personnalisée appelle l'action de données essentielles **get-recommendations** et lui transmet les informations requises selon les exigences de la liste.</span><span class="sxs-lookup"><span data-stu-id="4a89f-134">The custom extension makes a call to the **get-recommendations** core data action and passes the required information to it, based on the requirements of the list.</span></span> <span data-ttu-id="4a89f-135">Pour la liste **Des choix pour vous**, l'extension doit transmettre le nom de liste et l'ID client corrects à l'action de données.</span><span class="sxs-lookup"><span data-stu-id="4a89f-135">In the case of the **Picks for you** list, the extension must pass the correct list name and customer ID to the data action.</span></span>

    <span data-ttu-id="4a89f-136">Une façon de créer l'extension personnalisée consiste à cloner le module de collecte de produits existant qui est utilisé pour renvoyer les résultats des recommandations.</span><span class="sxs-lookup"><span data-stu-id="4a89f-136">One way to create the custom extension is to clone the existing product collection module that is used to return recommendations results.</span></span> <span data-ttu-id="4a89f-137">En clonant ce module existant, un détaillant peut modifier le code existant et ajouter un nouveau bouton qui exporte les résultats des recommandations vers un fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="4a89f-137">By cloning this existing module, a retailer can modify the existing code and add a new button that exports the recommendations results to a CSV file.</span></span> <span data-ttu-id="4a89f-138">Pour plus d'informations, voir [Cloner un module de kit de démarrage](e-commerce-extensibility/clone-starter-module.md) et [Modules de collecte de produits](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4a89f-138">For more information, see [Clone a starter kit module](e-commerce-extensibility/clone-starter-module.md) and [Product collection modules](product-collection-module-overview.md).</span></span>

    <span data-ttu-id="4a89f-139">Pour une vue complète de la bibliothèque des API Retail Server, voir [API client et client de Retail Server](dev-itpro/retail-server-customer-consumer-api.md).</span><span class="sxs-lookup"><span data-stu-id="4a89f-139">For a full view of the Retail Server API library, see [Retail Server Customer and Consumer APIs](dev-itpro/retail-server-customer-consumer-api.md).</span></span>

3. <span data-ttu-id="4a89f-140">Après la création de l'extension personnalisée, le détaillant peut exporter un fichier CSV de tous les résultats des recommandations, en fonction de l'ID client unique de l'utilisateur authentifié.</span><span class="sxs-lookup"><span data-stu-id="4a89f-140">After the custom extension is created, the retailer can export a CSV file of all recommendations results, based on the unique customer ID of the authenticated user.</span></span>
4. <span data-ttu-id="4a89f-141">Le détaillant peut partager le fichier CSV exporté qui contient la liste personnalisée complète des produits recommandés avec l'utilisateur authentifié.</span><span class="sxs-lookup"><span data-stu-id="4a89f-141">The retailer can share the exported CSV file that contains the full personalized list of recommended products with the authenticated user.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4a89f-142">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4a89f-142">Additional resources</span></span>

[<span data-ttu-id="4a89f-143">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="4a89f-143">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="4a89f-144">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="4a89f-144">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="4a89f-145">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="4a89f-145">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="4a89f-146">Ajouter des listes de recommandation produit aux pages</span><span class="sxs-lookup"><span data-stu-id="4a89f-146">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="4a89f-147">Ajouter le panneau de recommandations aux appareils PDV</span><span class="sxs-lookup"><span data-stu-id="4a89f-147">Add recommendations panel to POS devices</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="4a89f-148">Vue d'ensemble du module de collecte de produits</span><span class="sxs-lookup"><span data-stu-id="4a89f-148">Product collection module overview</span></span>](product-collection-module-overview.md)
