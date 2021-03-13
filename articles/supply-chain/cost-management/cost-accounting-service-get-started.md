---
title: Prise en main du service de contrôle de gestion (version préliminaire privée)
description: Cette rubrique fournit des détails sur les licences et des instructions d'installation pour le service de contrôle de gestion.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 1f602116edabc424b6cbee541e268df017912d3c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011845"
---
# <a name="get-started-with-the-cost-accounting-service-private-preview"></a><span data-ttu-id="5e2bc-103">Prise en main du service de contrôle de gestion (version préliminaire privée)</span><span class="sxs-lookup"><span data-stu-id="5e2bc-103">Get started with the cost accounting service (private preview)</span></span>

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="5e2bc-104">La fonctionnalité décrite dans cette rubrique est accessible dans le cadre d'une préversion privée.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-104">The functionality that is described in this topic is available as part of a private preview release.</span></span> <span data-ttu-id="5e2bc-105">Le contenu de cette rubrique et les fonctionnalités qu'elle décrit sont susceptibles d'être modifiés.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-105">The content of this topic and the functionality that it describes are subject to change.</span></span> <span data-ttu-id="5e2bc-106">Pour plus d'informations sur les préversions, voir [FAQ sur les mises à jour de service à une version](../../fin-ops-core/fin-ops/get-started/one-version.md).</span><span class="sxs-lookup"><span data-stu-id="5e2bc-106">For more information about preview releases, see [One version service updates FAQ](../../fin-ops-core/fin-ops/get-started/one-version.md).</span></span>

<span data-ttu-id="5e2bc-107">Le service de contrôle de gestion vous permet d'effectuer la comptabilité de plusieurs stocks dans les comptabilités de contrôle de gestion que vous avez configurés.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-107">The cost accounting service lets you do multiple inventory accounting in the cost accounting ledgers that you've set up.</span></span> <span data-ttu-id="5e2bc-108">Vous associez chaque comptabilité de contrôle de gestion à une *convention*.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-108">You associate each cost accounting ledger with a *convention*.</span></span> <span data-ttu-id="5e2bc-109">Une convention est un ensemble des types de stratégies comptables suivants :</span><span class="sxs-lookup"><span data-stu-id="5e2bc-109">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="5e2bc-110">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="5e2bc-110">Cost object</span></span>
- <span data-ttu-id="5e2bc-111">Base de la mesure en entrée</span><span class="sxs-lookup"><span data-stu-id="5e2bc-111">Input measurement basis</span></span>
- <span data-ttu-id="5e2bc-112">Hypothèse de flux de coût</span><span class="sxs-lookup"><span data-stu-id="5e2bc-112">Cost flow assumption</span></span>
- <span data-ttu-id="5e2bc-113">Élément de coût</span><span class="sxs-lookup"><span data-stu-id="5e2bc-113">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="5e2bc-114">Même après avoir activé le service de contrôle de gestion, vous pouvez toujours effectuer la comptabilité de stock dans Microsoft Dynamics 365 Supply Chain Management, comme d'habitude.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-114">Even after you've turned on the cost accounting service, you can still do  inventory accounting in Microsoft Dynamics 365 Supply Chain Management, as usual.</span></span>

<span data-ttu-id="5e2bc-115">Le service de contrôle de gestion est un complément.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-115">The cost accounting service is an add-in.</span></span> <span data-ttu-id="5e2bc-116">Pour rendre ses fonctionnalités disponibles, vous devez l'installer à partir de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="5e2bc-116">To makes its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="5e2bc-117">Par conséquent, vous pouvez choisir de l'évaluer dans un environnement de test avant de l'activer pour les environnements de production.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-117">Therefore, you can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="5e2bc-118">Le service de contrôle de gestion ne prend actuellement pas en charge toutes les fonctionnalités de gestion des coûts intégrées Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-118">The cost accounting service doesn't currently support all the cost management features that are built into Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="5e2bc-119">Par conséquent, il est important d'évaluer si l'ensemble de fonctionnalités actuellement disponible répondra à vos attentes.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-119">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="how-to-get-the-cost-accounting-service-private-preview"></a><a name="sign-up"></a><span data-ttu-id="5e2bc-120">Obtenir le service de contrôle de gestion (version préliminaire privée)</span><span class="sxs-lookup"><span data-stu-id="5e2bc-120">How to get the cost accounting service (private preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e2bc-121">Pour utiliser le service de contrôle de gestion, vous devez disposer d'un environnement à haute disponibilité compatible LCS (et non d'un environnement OneBox), et vous devez exécuter Dynamics 365 Supply Chain Management version 10.0.11 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-121">To use the cost accounting service, you must have an LCS-enabled high-availability environment (not a OneBox environment), and you must be running Dynamics 365 Supply Chain Management version 10.0.11 or later.</span></span>

<span data-ttu-id="5e2bc-122">Pour vous inscrire à la version préliminaire privée du service de contrôle de gestion, veuillez envoyer votre identifiant d'environnement LCS par e-mail au [Service de contrôle de gestion (version préliminaire privée)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29).</span><span class="sxs-lookup"><span data-stu-id="5e2bc-122">To sign up for the cost accounting service private preview, please send your LCS environment ID by email to [Cost accounting service (private preview)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29).</span></span> <span data-ttu-id="5e2bc-123">Une fois que nous vous avons approuvé pour le programme, nous vous enverrons un e-mail de suivi contenant une clé bêta pour le service de contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-123">On approving you for the program, we will send you a follow up email that contains a cost accounting service beta key.</span></span> <span data-ttu-id="5e2bc-124">Après la réception de la clé bêta, vous pouvez [installer le complément](#install).</span><span class="sxs-lookup"><span data-stu-id="5e2bc-124">On receiving the beta key, you can proceed by [installing the add-in](#install).</span></span>

## <a name="licensing"></a><span data-ttu-id="5e2bc-125">Gestionnaire de licences</span><span class="sxs-lookup"><span data-stu-id="5e2bc-125">Licensing</span></span>

<span data-ttu-id="5e2bc-126">Le service de contrôle de gestion est concédé sous licence avec les fonctionnalités standard de la comptabilité des stocks disponibles pour Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-126">The cost accounting service is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="5e2bc-127">Vous n'avez pas besoin d'acheter une licence supplémentaire pour utiliser le service de contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-127">You don't have to purchase an additional license to use the cost accounting service.</span></span>

## <a name="install-the-add-in"></a><a name="install"></a><span data-ttu-id="5e2bc-128">Installer le complément</span><span class="sxs-lookup"><span data-stu-id="5e2bc-128">Install the add-in</span></span>

<span data-ttu-id="5e2bc-129">Pour utiliser le service de contrôle de gestion, installez le complément de service de contrôle de gestion pour Supply Chain Management comme décrit dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-129">To use the cost accounting service, install the cost accounting service add-in for Supply Chain Management as described in the following procedure.</span></span>

1. <span data-ttu-id="5e2bc-130">[Inscrivez-vous](#sign-up) au service de contrôle de gestion (version préliminaire privée).</span><span class="sxs-lookup"><span data-stu-id="5e2bc-130">[Sign up](#sign-up) for the cost accounting service (private preview).</span></span>

1. <span data-ttu-id="5e2bc-131">Connectez-vous à LCS.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-131">Sign in to LCS.</span></span>

1. <span data-ttu-id="5e2bc-132">Accédez à **Gestion des fonctionnalités d'aperçu**.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-132">Go to **Preview feature management**.</span></span>

1. <span data-ttu-id="5e2bc-133">Sélectionnez le signe plus (**+**).</span><span class="sxs-lookup"><span data-stu-id="5e2bc-133">Select the plus sign (**+**).</span></span>

1. <span data-ttu-id="5e2bc-134">Dans le **Code**, entrez votre clé bêta de complément pour le service de contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-134">In the **Code** field, enter your add-in beta key for the cost accounting service.</span></span> <span data-ttu-id="5e2bc-135">(Vous devriez avoir reçu votre clé par e-mail.)</span><span class="sxs-lookup"><span data-stu-id="5e2bc-135">(You should have received your key by email.)</span></span>

1. <span data-ttu-id="5e2bc-136">Sélectionnez **Débloquer**.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-136">Select **Unblock**.</span></span>

1. <span data-ttu-id="5e2bc-137">Ouvrez l'environnement LCS dans lequel vous souhaitez ajouter le service.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-137">Open the LCS environment where you want to add the service.</span></span>

1. <span data-ttu-id="5e2bc-138">Accédez à **Détails complets**.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-138">Go to **Full details**.</span></span>

1. <span data-ttu-id="5e2bc-139">Faites défiler jusqu'à l'organisateur **Compléments d'environnement**.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-139">Scroll down to the **Environment add-ins** FastTab.</span></span>

1. <span data-ttu-id="5e2bc-140">Sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-140">Select **Install a new add-in**.</span></span>

1. <span data-ttu-id="5e2bc-141">Sélectionnez **Service de contrôle de gestion**.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-141">Select **Cost accounting service**.</span></span>

1. <span data-ttu-id="5e2bc-142">Suivez le guide d'installation, et acceptez les conditions générales du contrat.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-142">Follow the installation guide, and agree to the terms and conditions.</span></span>

1. <span data-ttu-id="5e2bc-143">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-143">Select **Install**.</span></span>

1. <span data-ttu-id="5e2bc-144">Sur l'organisateur **Compléments d'environnement**, vous devriez voir que le service de contrôle de gestion est en cours d'installation.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-144">On the **Environment add-ins** FastTab, you should see that the cost accounting service is being installed.</span></span> <span data-ttu-id="5e2bc-145">Après quelques minutes, le statut devrait passer de **Installation** à **Installé**.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-145">After a few minutes, the status should change from **Installing** to **Installed**.</span></span> <span data-ttu-id="5e2bc-146">(Vous devrez peut-être actualiser la page pour voir cette modification.) À ce stade, le service de contrôle de gestion est prêt à être utilisé.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-146">(You might have to refresh the page to see this change.) At that point, the cost accounting service is ready for use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="5e2bc-147">Paramétrage de l'intégration</span><span class="sxs-lookup"><span data-stu-id="5e2bc-147">Set up the integration</span></span>

<span data-ttu-id="5e2bc-148">Mettre en place l'intégration entre le service de contrôle de gestion et Dynamics 365 Supply Chain Management :</span><span class="sxs-lookup"><span data-stu-id="5e2bc-148">To set up the integration between the cost accounting service and Dynamics 365 Supply Chain Management:</span></span>

1. <span data-ttu-id="5e2bc-149">Accédez à **Administration système > Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-149">Go to **System administration > Feature Management**.</span></span>

1. <span data-ttu-id="5e2bc-150">Sélectionnez **Rechercher des mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-150">Select **Check for updates**.</span></span>

1. <span data-ttu-id="5e2bc-151">Ouvrez l'onglet **Tous** et recherchez la fonctionnalité nommée *Service de contrôle de gestion*.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-151">Open the **All** tab and search for the feature named *Cost accounting service*.</span></span>

1. <span data-ttu-id="5e2bc-152">Sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-152">Select **Enable now**.</span></span>

1. <span data-ttu-id="5e2bc-153">Aller à **Gestion des coûts > Service de contrôle de gestion > Configuration > Paramètres du service de contrôle de gestion > Paramètres d'intégration**.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-153">Go to **Cost management > Cost accounting service > Setup > Cost accounting service parameters > Integrations parameters**.</span></span>

1. <span data-ttu-id="5e2bc-154">Dans le champ **ID application**, entrez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="5e2bc-154">In the **Application ID** field, enter the following code:</span></span><br> <span data-ttu-id="5e2bc-155">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span><span class="sxs-lookup"><span data-stu-id="5e2bc-155">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span></span>

1. <span data-ttu-id="5e2bc-156">Dans le champ **Point de terminaison du service de données**, entrez l'URL suivante :</span><span class="sxs-lookup"><span data-stu-id="5e2bc-156">In the **Data service endpoint** field, enter the following URL:</span></span><br>https://operationsdataservice.operations365.dynamics.com/

1. <span data-ttu-id="5e2bc-157">Dans le champ **Point de terminaison du service de contrôle de gestion**, entrez l'URL suivante :</span><span class="sxs-lookup"><span data-stu-id="5e2bc-157">In the **Cost accounting service endpoint** field, enter the following URL:</span></span><br>https://costaccountingservice.operations365.dynamics.com/

1. <span data-ttu-id="5e2bc-158">Le service de contrôle de gestion est maintenant prêt à l'emploi.</span><span class="sxs-lookup"><span data-stu-id="5e2bc-158">The cost accounting service is now ready for use.</span></span>

## <a name="related-resources"></a><span data-ttu-id="5e2bc-159">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="5e2bc-159">Related resources</span></span>

[<span data-ttu-id="5e2bc-160">Page d'accueil du service Contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="5e2bc-160">Cost accounting service home page</span></span>](cost-accounting-service-home.md)
