---
title: Expédition de petits colis
description: Cette rubrique fournit des informations sur la fonctionnalité d’expédition de petits colis (SPS). Cette fonctionnalité permet à Microsoft Dynamics 365 Supply Chain Management d’envoyer des détails sur un conteneur emballé au transporteur, puis de recevoir une étiquette d’expédition, des frais d’expédition et un numéro de suivi de ce transporteur.
author: Mirzaab
manager: tfehr
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 37f07139853c30da25c067a3d736b4b9bf4eb361
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501172"
---
# <a name="small-parcel-shipping"></a><span data-ttu-id="4c583-104">Expédition de petits colis</span><span class="sxs-lookup"><span data-stu-id="4c583-104">Small parcel shipping</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="4c583-105">La fonctionnalité d’expédition de petits colis (SPS) permet à Microsoft Dynamics 365 Supply Chain Management d’interagir directement avec les transporteurs en fournissant un cadre de communication via les API du transporteur.</span><span class="sxs-lookup"><span data-stu-id="4c583-105">The small parcel shipping (SPS) feature enables Microsoft Dynamics 365 Supply Chain Management to interact directly with shipping carriers by providing a framework for communication through carrier APIs.</span></span> <span data-ttu-id="4c583-106">Cette fonctionnalité est utile lorsque vous expédiez des commandes client individuelles via des transporteurs commerciaux au lieu d’utiliser l’expédition par conteneur ou l’expédition par chargement partiel (LTL).</span><span class="sxs-lookup"><span data-stu-id="4c583-106">This functionality is useful when you're shipping individual sales orders via commercial shipping carriers instead of using container shipping or less-than-truckload (LTL) shipping.</span></span>

<span data-ttu-id="4c583-107">La fonctionnalité SPS interagit avec votre transporteur via un *moteur de frais* dédié.</span><span class="sxs-lookup"><span data-stu-id="4c583-107">The SPS feature interacts with your shipping carrier through a dedicated *rate engine*.</span></span> <span data-ttu-id="4c583-108">Votre organisation doit développer ce moteur de frais en collaboration avec votre transporteur ou votre service de transport.</span><span class="sxs-lookup"><span data-stu-id="4c583-108">Your organization must develop this rate engine in collaboration with your carrier or carrier hub service.</span></span> <span data-ttu-id="4c583-109">Le moteur de frais permet à Supply Chain Management d’envoyer des détails sur un conteneur emballé à votre transporteur, puis de recevoir une étiquette d’expédition, des frais d’expédition et un numéro de suivi de ce transporteur.</span><span class="sxs-lookup"><span data-stu-id="4c583-109">The rate engine enables Supply Chain Management to submit details about a packed container to your carrier, and then receive a shipping label, shipping rate, and tracking number back from that carrier.</span></span>

<span data-ttu-id="4c583-110">Les frais d’expédition renvoyés sont ajoutés à la commande client associée en tant que frais divers.</span><span class="sxs-lookup"><span data-stu-id="4c583-110">The shipping rate that is returned is added to the associated sales order as a miscellaneous charge.</span></span> <span data-ttu-id="4c583-111">L’étiquette d’expédition renvoyée peut ensuite être imprimée automatiquement à l’aide d’une imprimante Zebra Programming Language (ZPL) et appliquée à l’expédition.</span><span class="sxs-lookup"><span data-stu-id="4c583-111">The shipping label that is returned can then automatically be printed by using a Zebra Programming Language (ZPL) printer and applied to the shipment.</span></span> <span data-ttu-id="4c583-112">Le transporteur scanne cette étiquette d’expédition lorsqu’il récupère les colis dans votre entrepôt.</span><span class="sxs-lookup"><span data-stu-id="4c583-112">The carrier will scan this shipping label when it picks up the packages at your warehouse.</span></span>

## <a name="prepare-your-system-to-support-sps"></a><span data-ttu-id="4c583-113">Préparer votre système pour prendre en charge SPS</span><span class="sxs-lookup"><span data-stu-id="4c583-113">Prepare your system to support SPS</span></span>

<span data-ttu-id="4c583-114">Avant de pouvoir commencer à utiliser la fonctionnalité SPS, vous devez l’activer dans le module Gestion des fonctionnalités, ajouter votre moteur de frais et configurer les modules **Gestion du transport** et **Gestion des entrepôts** pour la prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="4c583-114">Before you can start to use SPS functionality, you must turn on the SPS feature in Feature management, add your rate engine, and set up the **Transportation management** and **Warehouse management** modules to support it.</span></span>

### <a name="turn-on-the-sps-feature"></a><span data-ttu-id="4c583-115">Activer la fonctionnalité SPS</span><span class="sxs-lookup"><span data-stu-id="4c583-115">Turn on the SPS feature</span></span>

<span data-ttu-id="4c583-116">Avant de pouvoir utiliser la fonctionnalité SPS, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="4c583-116">Before you can use the SPS feature, it must be turned on in your system.</span></span> <span data-ttu-id="4c583-117">Les administrateurs peuvent utiliser l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4c583-117">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="4c583-118">Là, la fonctionnalité est répertoriée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="4c583-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="4c583-119">**Module :** *Vidéos sur la gestion du transport*</span><span class="sxs-lookup"><span data-stu-id="4c583-119">**Module:** *Transportation management*</span></span>
- <span data-ttu-id="4c583-120">**Nom de la fonctionnalité :** *Expédition de petits colis*</span><span class="sxs-lookup"><span data-stu-id="4c583-120">**Feature name:** *Small parcel shipping*</span></span>

### <a name="deploy-and-set-up-rate-engines"></a><span data-ttu-id="4c583-121">Déployer et configurer les moteurs de frais</span><span class="sxs-lookup"><span data-stu-id="4c583-121">Deploy and set up rate engines</span></span>

<span data-ttu-id="4c583-122">Supply Chain Management n’inclut aucun moteur de frais.</span><span class="sxs-lookup"><span data-stu-id="4c583-122">Supply Chain Management doesn't include any rate engines.</span></span> <span data-ttu-id="4c583-123">Vous devez obtenir ou créer tous les moteurs de frais nécessaires, puis les ajouter à votre système.</span><span class="sxs-lookup"><span data-stu-id="4c583-123">You must obtain or create any rate engines that you require, and then add them to your system.</span></span> <span data-ttu-id="4c583-124">Cependant, Microsoft fournit un moteur de frais de démonstration que vous pouvez utiliser pour les tests.</span><span class="sxs-lookup"><span data-stu-id="4c583-124">However, Microsoft provides a demo rate engine that you can use for testing.</span></span>

#### <a name="download-and-deploy-the-demo-rate-engine"></a><span data-ttu-id="4c583-125">Télécharger et déployer le moteur de frais de démonstration</span><span class="sxs-lookup"><span data-stu-id="4c583-125">Download and deploy the demo rate engine</span></span>

<span data-ttu-id="4c583-126">Procédez comme suit pour obtenir le moteur de frais de démonstration.</span><span class="sxs-lookup"><span data-stu-id="4c583-126">Follow these steps to get the demo rate engine.</span></span>

1. <span data-ttu-id="4c583-127">Sur GitHub, téléchargez la [bibliothèque de liens dynamiques (DLL) pour le moteur de frais de démonstration](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span><span class="sxs-lookup"><span data-stu-id="4c583-127">On GitHub, download the [dynamic-link library (DLL) for the demo rate engine](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span></span>
1. <span data-ttu-id="4c583-128">Sur votre serveur Supply Chain Management, enregistrez la DLL dans le dossier **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin**.</span><span class="sxs-lookup"><span data-stu-id="4c583-128">On your Supply Chain Management server, save the DLL in the **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin** folder.</span></span>

#### <a name="create-and-deploy-functional-rate-engines"></a><span data-ttu-id="4c583-129">Créer et déployer des moteurs de frais fonctionnels</span><span class="sxs-lookup"><span data-stu-id="4c583-129">Create and deploy functional rate engines</span></span>

<span data-ttu-id="4c583-130">Pour plus d’informations sur la création et le déploiement de moteurs de frais fonctionnels afin qu’ils puissent être utilisés dans un environnement de production ou de test, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c583-130">For information about how to create and deploy functional rate engines so that they can be used in a production or test environment, see the following topics:</span></span>

- [<span data-ttu-id="4c583-131">Créer un moteur de gestion du transport</span><span class="sxs-lookup"><span data-stu-id="4c583-131">Create a new transportation management engine</span></span>](../transportation/create-new-transportation-management-engine.md)
- [<span data-ttu-id="4c583-132">Paramétrage de moteurs de gestion du transport</span><span class="sxs-lookup"><span data-stu-id="4c583-132">Set up transportation management engines</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

<span data-ttu-id="4c583-133">Pour plus d’informations sur la création d’un moteur de frais SPS, consultez le billet de blog suivant : [Expédition de petits colis : comment tirer parti de la fonctionnalité d’expédition de petits colis dans Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).</span><span class="sxs-lookup"><span data-stu-id="4c583-133">For more information about how to create an SPS rate engine, see the following blog post: [Small Parcel Shipping: How to leverage small parcel shipping functionality in Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).</span></span>

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a><span data-ttu-id="4c583-134">Configurer un moteur de frais dans Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="4c583-134">Set up a rate engine in Supply Chain Management</span></span>

<span data-ttu-id="4c583-135">Une fois que vous avez créé et déployé un moteur de frais pour SPS, procédez comme suit pour le configurer.</span><span class="sxs-lookup"><span data-stu-id="4c583-135">After you've created and deployed a rate engine for SPS, follow these steps to set it up.</span></span>

1. <span data-ttu-id="4c583-136">Accédez à **Gestion du transport \> Configuration \> Moteurs \> Moteur de frais**.</span><span class="sxs-lookup"><span data-stu-id="4c583-136">Go to **Transportation management \> Setup \> Engines \> Rate engine**.</span></span>
1. <span data-ttu-id="4c583-137">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="4c583-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="4c583-138">Dans la nouvelle ligne, définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="4c583-138">In the new row, set the following fields:</span></span>

    - <span data-ttu-id="4c583-139">**Moteur de frais** : entrez un nom unique pour le moteur de frais.</span><span class="sxs-lookup"><span data-stu-id="4c583-139">**Rating engine** – Enter a unique name for the rate engine.</span></span> <span data-ttu-id="4c583-140">Si vous utilisez le moteur de frais de démonstration, entrez *Moteur de frais de démonstration*.</span><span class="sxs-lookup"><span data-stu-id="4c583-140">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="4c583-141">**Nom** : entrez une brève description du moteur de frais.</span><span class="sxs-lookup"><span data-stu-id="4c583-141">**Name** – Enter a short description of the rate engine.</span></span> <span data-ttu-id="4c583-142">Si vous utilisez le moteur de frais de démonstration, entrez *Moteur de frais de démonstration*.</span><span class="sxs-lookup"><span data-stu-id="4c583-142">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="4c583-143">**ID des métadonnées de taux** : sélectionnez la base à utiliser pour calculer vos frais.</span><span class="sxs-lookup"><span data-stu-id="4c583-143">**Rating metadata ID** – Select the basis that should be used to calculate your rate.</span></span> <span data-ttu-id="4c583-144">Par exemple, vos frais peuvent être calculés en fonction de la distance.</span><span class="sxs-lookup"><span data-stu-id="4c583-144">For example, your rate might be calculated based on distance.</span></span> <span data-ttu-id="4c583-145">Si vous utilisez le moteur de frais de démonstration, vous pouvez laisser ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="4c583-145">If you're using the demo rate engine, you can leave this field blank.</span></span>
    - <span data-ttu-id="4c583-146">**Assembly de moteur** : entrez le nom de fichier du package DLL que vous avez déployé.</span><span class="sxs-lookup"><span data-stu-id="4c583-146">**Engine assembly** – Enter the file name of the DLL package that you deployed.</span></span> <span data-ttu-id="4c583-147">Si vous utilisez le moteur de frais de démonstration, entrez *TMSSmallParcelShippingEngine.dll*.</span><span class="sxs-lookup"><span data-stu-id="4c583-147">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.dll*.</span></span>
    - <span data-ttu-id="4c583-148">**Classe de moteur** : entrez le nom de la classe qui a été établi pour votre moteur de frais.</span><span class="sxs-lookup"><span data-stu-id="4c583-148">**Engine class** – Enter the class name that was established for your rate engine.</span></span> <span data-ttu-id="4c583-149">Si vous utilisez le moteur de frais de démonstration, entrez *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.</span><span class="sxs-lookup"><span data-stu-id="4c583-149">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="4c583-150">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="4c583-150">Example scenario</span></span>

<span data-ttu-id="4c583-151">Cet exemple de scénario montre comment configurer et utiliser SPS une fois que vous avez préparé votre système comme décrit plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4c583-151">This example scenario shows how to set up and use SPS after you've prepared your system as described earlier in this topic.</span></span> <span data-ttu-id="4c583-152">Ce scénario utilise le moteur de frais de démonstration mentionné précédemment.</span><span class="sxs-lookup"><span data-stu-id="4c583-152">This scenario uses the previously mentioned demo rate engine.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="4c583-153">Rendre les données de démonstration disponibles</span><span class="sxs-lookup"><span data-stu-id="4c583-153">Make demo data available</span></span>

<span data-ttu-id="4c583-154">Pour utiliser ce scénario avec les enregistrements et les valeurs de démonstration spécifiés ici, vous devez utiliser un système dans lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées.</span><span class="sxs-lookup"><span data-stu-id="4c583-154">To work through this scenario by using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="4c583-155">En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="4c583-155">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="4c583-156">Paramétrage du scénario</span><span class="sxs-lookup"><span data-stu-id="4c583-156">Set up the scenario</span></span>

<span data-ttu-id="4c583-157">Pour cet exemple de scénario, vous devez avoir un transporteur de démonstration, un groupe de transporteurs, une stratégie d’emballage et un profil d’emballage.</span><span class="sxs-lookup"><span data-stu-id="4c583-157">For this example scenario, you must have a demo carrier, carrier group, packing policy, and packing profile.</span></span> <span data-ttu-id="4c583-158">Les sous-sections suivantes expliquent comment préparer les enregistrements nécessaires pour le scénario.</span><span class="sxs-lookup"><span data-stu-id="4c583-158">The following subsections explain how to prepare the records that are required for the scenario.</span></span> <span data-ttu-id="4c583-159">Dans un scénario de production, le processus de configuration ressemble généralement au processus décrit ici.</span><span class="sxs-lookup"><span data-stu-id="4c583-159">In a production scenario, the setup process typically resembles the process that is described here.</span></span> <span data-ttu-id="4c583-160">Cependant, vous définirez des valeurs différentes.</span><span class="sxs-lookup"><span data-stu-id="4c583-160">However, you will set different values.</span></span>

#### <a name="set-up-carriers"></a><span data-ttu-id="4c583-161">Configurer des transporteurs</span><span class="sxs-lookup"><span data-stu-id="4c583-161">Set up carriers</span></span>

<span data-ttu-id="4c583-162">Procédez comme suit pour configurer un transporteur.</span><span class="sxs-lookup"><span data-stu-id="4c583-162">Follow these steps to set up a carrier.</span></span>

1. <span data-ttu-id="4c583-163">Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Transporteurs**.</span><span class="sxs-lookup"><span data-stu-id="4c583-163">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="4c583-164">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un transporteur.</span><span class="sxs-lookup"><span data-stu-id="4c583-164">On the Action Pane, select **New** to add a carrier.</span></span>
1. <span data-ttu-id="4c583-165">Dans l’en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c583-165">On the header, set the following values:</span></span>

    - <span data-ttu-id="4c583-166">**Transporteur :** *Transporteur de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-166">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="4c583-167">**Nom :** *Transporteur de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-167">**Name:** *Demo Carrier*</span></span>
    - <span data-ttu-id="4c583-168">**Mode :** *Terrestre*</span><span class="sxs-lookup"><span data-stu-id="4c583-168">**Mode:** *Ground*</span></span>

1. <span data-ttu-id="4c583-169">Dans l’organisateur **Vue d’ensemble**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c583-169">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="4c583-170">**Activer le transporteur :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="4c583-170">**Activate shipping carrier:** *Yes*</span></span>
    - <span data-ttu-id="4c583-171">**Activer le classement du transporteur :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="4c583-171">**Activate carrier rating:** *Yes*</span></span>

1. <span data-ttu-id="4c583-172">Dans le raccourci **Services**, sélectionnez **Nouveau** pour ajouter un service à la grille.</span><span class="sxs-lookup"><span data-stu-id="4c583-172">On the **Services** FastTab, select **New** to add a service to the grid.</span></span>
1. <span data-ttu-id="4c583-173">Définissez les valeurs suivantes pour le nouveau service :</span><span class="sxs-lookup"><span data-stu-id="4c583-173">Set the following values for the new service:</span></span>

    - <span data-ttu-id="4c583-174">**Service de transporteur :** *Service de transporteur de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-174">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="4c583-175">**Nom :** *Service de transporteur de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-175">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="4c583-176">**Mode de transport :** *Terrestre*</span><span class="sxs-lookup"><span data-stu-id="4c583-176">**Transportation method:** *Ground*</span></span>

    <span data-ttu-id="4c583-177">Entrez des valeurs arbitraires pour tous les autres champs, au besoin.</span><span class="sxs-lookup"><span data-stu-id="4c583-177">Enter arbitrary values for all the other fields, as required.</span></span> <span data-ttu-id="4c583-178">(Lorsque vous enregistrez le nouvel enregistrement de transporteur, un nouveau mode de livraison est créé et le champ **Mode de livraison** est défini automatiquement.)</span><span class="sxs-lookup"><span data-stu-id="4c583-178">(When you save the new shipping carrier record, a new mode of delivery will be created, and the **Mode of delivery** field will be set automatically.)</span></span>

1. <span data-ttu-id="4c583-179">Dans le raccourci **Profils de classement**, sélectionnez **Nouveau** pour ajouter un profil de classement à la grille.</span><span class="sxs-lookup"><span data-stu-id="4c583-179">On the **Rating profiles** FastTab, select **New** to add a rating profile to the grid.</span></span>
1. <span data-ttu-id="4c583-180">Définissez les valeurs suivantes pour le nouveau profil :</span><span class="sxs-lookup"><span data-stu-id="4c583-180">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="4c583-181">**Profil de classement :** *Service de transporteur de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-181">**Rating profile:** *Demo carrier service*</span></span>
    - <span data-ttu-id="4c583-182">**Nom :** *Service de transporteur de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-182">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="4c583-183">**Moteur de frais :** *Moteur de frais de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-183">**Rate engine:** *Demo rate engine*</span></span>

    <span data-ttu-id="4c583-184">Entrez des valeurs arbitraires pour tous les autres champs, au besoin.</span><span class="sxs-lookup"><span data-stu-id="4c583-184">Enter arbitrary values for all the other fields, as required.</span></span>

1. <span data-ttu-id="4c583-185">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4c583-185">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="4c583-186">Pour plus d’informations sur la configuration des transporteurs, voir [Paramétrer des transporteurs](../transportation/tasks/set-up-shipping-carriers.md).</span><span class="sxs-lookup"><span data-stu-id="4c583-186">For more information about how to set up carriers, see [Set up shipping carriers](../transportation/tasks/set-up-shipping-carriers.md).</span></span>

#### <a name="set-up-carrier-service-accounts"></a><span data-ttu-id="4c583-187">Configurer des comptes de service de transporteur</span><span class="sxs-lookup"><span data-stu-id="4c583-187">Set up carrier service accounts</span></span>

<span data-ttu-id="4c583-188">Procédez comme suit pour configurer un compte de service de transporteur.</span><span class="sxs-lookup"><span data-stu-id="4c583-188">Follow these steps to set up a carrier service account.</span></span>

1. <span data-ttu-id="4c583-189">Accédez à **Gestion du transport \> Configuration \> Classement \> Compte de service de transporteur**.</span><span class="sxs-lookup"><span data-stu-id="4c583-189">Go to **Transportation management \> Setup \> Rating \> Carrier service account**.</span></span>
1. <span data-ttu-id="4c583-190">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un compte de service de transporteur.</span><span class="sxs-lookup"><span data-stu-id="4c583-190">On the Action Pane, select **New** to add a carrier service account.</span></span>
1. <span data-ttu-id="4c583-191">Définissez les valeurs suivantes pour le nouveau compte :</span><span class="sxs-lookup"><span data-stu-id="4c583-191">Set the following values for the new account:</span></span>

    - <span data-ttu-id="4c583-192">**Transporteur :** *Transporteur de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-192">**Shipping Carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="4c583-193">**Service de transporteur :** *Service de transporteur de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-193">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="4c583-194">**Numéro de compte client du transporteur :** numéro de compte client du transporteur utilisé pour vérifier et authentifier la connexion au transporteur.</span><span class="sxs-lookup"><span data-stu-id="4c583-194">**Carrier customer account number:** The carrier customer account number that is used to verify and authenticate the connection to the shipping carrier.</span></span> <span data-ttu-id="4c583-195">Votre transporteur fournira cette valeur.</span><span class="sxs-lookup"><span data-stu-id="4c583-195">Your carrier will provide this value.</span></span> <span data-ttu-id="4c583-196">Si vous utilisez le service de démonstration, vous pouvez entrer une valeur arbitraire.</span><span class="sxs-lookup"><span data-stu-id="4c583-196">If you're using the demo service, you can enter an arbitrary value.</span></span>
    - <span data-ttu-id="4c583-197">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="4c583-197">**Site:** *6*</span></span>
    - <span data-ttu-id="4c583-198">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="4c583-198">**Warehouse:** *62*</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c583-199">Souvent, la valeur **Numéro de compte client du transporteur** est la seule valeur nécessaire pour authentifier la connexion.</span><span class="sxs-lookup"><span data-stu-id="4c583-199">Often, the **Carrier customer account number** value is the only value that is required to authenticate the connection.</span></span> <span data-ttu-id="4c583-200">Toutefois, si votre transporteur requiert des paramètres d’authentification supplémentaires, votre organisation doit personnaliser cette page pour ajouter des champs supplémentaires, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="4c583-200">However, if your carrier requires additional authentication parameters, your organization should customize this page to add extra fields as appropriate.</span></span>

#### <a name="set-up-a-container-packing-policy"></a><span data-ttu-id="4c583-201">Définir une stratégie d’emballage de conteneur</span><span class="sxs-lookup"><span data-stu-id="4c583-201">Set up a container packing policy</span></span>

<span data-ttu-id="4c583-202">Procédez comme suit pour définir une stratégie d’emballage de conteneur.</span><span class="sxs-lookup"><span data-stu-id="4c583-202">Follow these steps to set up a container packing policy.</span></span>

1. <span data-ttu-id="4c583-203">Si vous n’avez pas encore configuré de définition d’imprimante ZPL, utilisez l’application Agent d’acheminement de documents pour la configurer.</span><span class="sxs-lookup"><span data-stu-id="4c583-203">If you haven't already set up a ZPL printer definition, use the Document Routing Agent application to set it up.</span></span> <span data-ttu-id="4c583-204">Pour plus d’informations, voir [Vue d’ensemble de l’impression de documents](../../fin-ops-core/dev-itpro/analytics/print-documents.md) et les rubriques connexes.</span><span class="sxs-lookup"><span data-stu-id="4c583-204">For more information, see [Document printing overview](../../fin-ops-core/dev-itpro/analytics/print-documents.md) and related topics.</span></span>
1. <span data-ttu-id="4c583-205">Accédez à **Gestion des entrepôts \> Configuration \> Conteneurs \> Stratégies d’emballage de conteneur**.</span><span class="sxs-lookup"><span data-stu-id="4c583-205">Go to **Warehouse Management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="4c583-206">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une stratégie d’emballage de conteneur.</span><span class="sxs-lookup"><span data-stu-id="4c583-206">On the Action Pane, select **New** to add a container packing policy.</span></span>
1. <span data-ttu-id="4c583-207">Dans l’en-tête de la nouvelle stratégie, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c583-207">On the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="4c583-208">**Stratégie d’emballage de conteneur :** *Stratégie d’emballage de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-208">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="4c583-209">**Description :** description de la stratégie</span><span class="sxs-lookup"><span data-stu-id="4c583-209">**Description:** A description of the policy</span></span>

1. <span data-ttu-id="4c583-210">Dans l’organisateur **Vue d’ensemble**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c583-210">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="4c583-211">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="4c583-211">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="4c583-212">**Emplacement par défaut pour l’expédition finale :** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="4c583-212">**Default location for final shipment:** *Baydoor*</span></span>
    - <span data-ttu-id="4c583-213">**Unité de poids :** *KG*</span><span class="sxs-lookup"><span data-stu-id="4c583-213">**Weight unit:** *KG*</span></span>
    - <span data-ttu-id="4c583-214">**Stratégie de fermeture des conteneurs :** *Libération automatique*</span><span class="sxs-lookup"><span data-stu-id="4c583-214">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="4c583-215">**Stratégie de libération des conteneurs :** *Rendre disponible à l’emplacement d’expédition final*</span><span class="sxs-lookup"><span data-stu-id="4c583-215">**Container release policy:** *Make available at final shipping location*</span></span>

1. <span data-ttu-id="4c583-216">Dans le raccourci **Manifeste du conteneur**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c583-216">On the **Container manifest** FastTab, set the following values:</span></span>

    - <span data-ttu-id="4c583-217">**Manifeste automatique à la fermeture du conteneur :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="4c583-217">**Automatic manifest at container close:** *Yes*</span></span>
    - <span data-ttu-id="4c583-218">**Conditions requises du manifeste pour le conteneur :** *Gestion du transport*</span><span class="sxs-lookup"><span data-stu-id="4c583-218">**Manifest requirements for container:** *Transportation management*</span></span>
    - <span data-ttu-id="4c583-219">**Imprimer le contenu du conteneur :** *Non*</span><span class="sxs-lookup"><span data-stu-id="4c583-219">**Print container contents:** *No*</span></span>

1. <span data-ttu-id="4c583-220">Dans le raccourci **Impression de l’étiquette du transporteur**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c583-220">On the **Carrier label printing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="4c583-221">**Imprimer l’étiquette d’expédition du conteneur :** *Toujours*</span><span class="sxs-lookup"><span data-stu-id="4c583-221">**Print container shipping label:** *Always*</span></span>
    - <span data-ttu-id="4c583-222">**Nom de l’imprimante :** Nom de l’imprimante ZPL qui doit imprimer les étiquettes d’expédition</span><span class="sxs-lookup"><span data-stu-id="4c583-222">**Printer name:** The name of the ZPL printer that should print shipping labels</span></span>

#### <a name="set-up-a-packing-profile"></a><span data-ttu-id="4c583-223">Configurer un profil d’emballage</span><span class="sxs-lookup"><span data-stu-id="4c583-223">Set up a packing profile</span></span>

<span data-ttu-id="4c583-224">Procédez comme suit pour configurer un profil d’emballage.</span><span class="sxs-lookup"><span data-stu-id="4c583-224">Follow these steps to set up a packing profile.</span></span>

1. <span data-ttu-id="4c583-225">Accédez à **Gestion des entrepôts \> Configuration \> Emballage \> Profils d’emballage**.</span><span class="sxs-lookup"><span data-stu-id="4c583-225">Go to **Warehouse Management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="4c583-226">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un profil d’emballage à la grille.</span><span class="sxs-lookup"><span data-stu-id="4c583-226">On the Action Pane, select **New** to add a packing profile to the grid.</span></span>
1. <span data-ttu-id="4c583-227">Définissez les valeurs suivantes pour le nouveau profil :</span><span class="sxs-lookup"><span data-stu-id="4c583-227">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="4c583-228">**ID profil d’emballage :** *Profil d’emballage de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-228">**Packing profile ID:** *Demo packing profile*</span></span>
    - <span data-ttu-id="4c583-229">**Description :** description du profil</span><span class="sxs-lookup"><span data-stu-id="4c583-229">**Description:** A description of the profile</span></span>
    - <span data-ttu-id="4c583-230">**Stratégie d’emballage de conteneur :** *Stratégie d’emballage de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-230">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="4c583-231">**Mode d’identification du conteneur :** *Auto*</span><span class="sxs-lookup"><span data-stu-id="4c583-231">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="4c583-232">**Type de conteneur :** *Petite boîte*</span><span class="sxs-lookup"><span data-stu-id="4c583-232">**Container type:** *SmallBox*</span></span>

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a><span data-ttu-id="4c583-233">Configurer un client pour utiliser le transporteur SPS</span><span class="sxs-lookup"><span data-stu-id="4c583-233">Set up a customer to use the SPS carrier</span></span>

<span data-ttu-id="4c583-234">Suivez ces étapes pour configurer un client afin qu’il puisse utiliser le transporteur que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="4c583-234">Follow these steps to set up a customer so that it can use the carrier that you created.</span></span>

1. <span data-ttu-id="4c583-235">Accédez à **Comptabilité client \> Clients \> Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="4c583-235">Go to **Accounts receivable \> customers \> All customers**.</span></span>
1. <span data-ttu-id="4c583-236">Dans la grille, recherchez et sélectionnez le client *US-027*.</span><span class="sxs-lookup"><span data-stu-id="4c583-236">In the grid, find and select customer *US-027*.</span></span>
1. <span data-ttu-id="4c583-237">Dans le volet Actions, sous l’onglet **Général**, dans le groupe **Configuration**, sélectionnez **Comptes client du transporteur**.</span><span class="sxs-lookup"><span data-stu-id="4c583-237">On the Action Pane, on the **General** tab, in the **Set up** group, select **Carrier customer accounts**.</span></span>
1. <span data-ttu-id="4c583-238">Sur la page **Comptes client du transporteur**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter un compte à la grille.</span><span class="sxs-lookup"><span data-stu-id="4c583-238">On the **Carrier customer accounts** page, on the Action Pane, select **New** to add an account to the grid.</span></span>
1. <span data-ttu-id="4c583-239">Définissez les valeurs suivantes pour le nouveau compte :</span><span class="sxs-lookup"><span data-stu-id="4c583-239">Set the following values for the new account:</span></span>

    - <span data-ttu-id="4c583-240">**Transporteur :** *Transporteur de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-240">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="4c583-241">**Numéro de compte client du transporteur :** *12345* (La valeur n’est pas importante pour ce scénario, mais elle est mentionnée dans la section suivante.)</span><span class="sxs-lookup"><span data-stu-id="4c583-241">**Carrier customer account number:** *12345* (The value isn't important for this scenario, but it will be referred to in the next section.)</span></span>

### <a name="go-through-the-example-scenario"></a><span data-ttu-id="4c583-242">Exécuter l’exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="4c583-242">Go through the example scenario</span></span>

<span data-ttu-id="4c583-243">Une fois que vous avez configuré tous les exemples de données comme décrit dans la section précédente, vous êtes prêt à exécuter l’exemple de scénario.</span><span class="sxs-lookup"><span data-stu-id="4c583-243">After you've set up all the sample data as described in the previous section, you're ready to go through the example scenario.</span></span>

#### <a name="create-a-sales-order-and-process-the-work"></a><span data-ttu-id="4c583-244">Créer une commande client et traiter le travail</span><span class="sxs-lookup"><span data-stu-id="4c583-244">Create a sales order and process the work</span></span>

<span data-ttu-id="4c583-245">Procédez comme suit pour créer une commande client.</span><span class="sxs-lookup"><span data-stu-id="4c583-245">Follow these steps to create a sales order.</span></span>

1. <span data-ttu-id="4c583-246">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="4c583-246">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="4c583-247">Sélectionnez **Nouveau** pour créer une commande client.</span><span class="sxs-lookup"><span data-stu-id="4c583-247">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="4c583-248">Dans la boîte de dialogue **Créer une commande client**, définissez le champ **Compte client** sur *US-027*.</span><span class="sxs-lookup"><span data-stu-id="4c583-248">In the **Create sales order** dialog box, set the **Customer account** field to *US-027*.</span></span>
1. <span data-ttu-id="4c583-249">Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="4c583-249">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="4c583-250">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="4c583-250">The new sales order is opened.</span></span> <span data-ttu-id="4c583-251">Dans le raccourci **En-tête de commande client**, définissez le champ **Numéro de compte client du transporteur** sur la valeur que vous avez précédemment sélectionnée pour ce client (*12345*).</span><span class="sxs-lookup"><span data-stu-id="4c583-251">On the **Sales order header** FastTab, set the **Carrier customer account number** field to the value that you selected for this customer earlier (*12345*).</span></span>
1. <span data-ttu-id="4c583-252">Dans la section **Lignes de commande client**, ajoutez une ligne de vente et définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c583-252">In the **Sales order lines** section, add a sales line, and set the following values for it:</span></span>

    - <span data-ttu-id="4c583-253">**Numéro d’article :** *A0002*</span><span class="sxs-lookup"><span data-stu-id="4c583-253">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="4c583-254">**Quantité :** *1*</span><span class="sxs-lookup"><span data-stu-id="4c583-254">**Quantity:** *1*</span></span>
    - <span data-ttu-id="4c583-255">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="4c583-255">**Site:** *6*</span></span>
    - <span data-ttu-id="4c583-256">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="4c583-256">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="4c583-257">Basculez sur la vue **En-tête**.</span><span class="sxs-lookup"><span data-stu-id="4c583-257">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="4c583-258">Dans le raccourci **Livraison**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c583-258">On the **Delivery** FastTab, set the following values:</span></span>

    - <span data-ttu-id="4c583-259">**Transporteur :** *Transporteur de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-259">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="4c583-260">**Service de transporteur :** *Service de transporteur de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-260">**Carrier service:** *Demo carrier service*</span></span>

1. <span data-ttu-id="4c583-261">Revenez à la vue **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="4c583-261">Switch back to the **Lines** view.</span></span> <span data-ttu-id="4c583-262">Si vous êtes invité à mettre à jour le mode de livraison des lignes de vente, sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="4c583-262">If you're prompted to update the mode of delivery for the sales lines, select **Yes**.</span></span>
1. <span data-ttu-id="4c583-263">Dans la section **Lignes de commande client**, sélectionnez la ligne de commande que vous avez configurée précédemment, puis sélectionnez **Stock \> Réservation**.</span><span class="sxs-lookup"><span data-stu-id="4c583-263">In the **Sales order lines** section, select the order line that you set up earlier, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="4c583-264">Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver la quantité totale de la ligne sélectionnée dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="4c583-264">On the **Reservation** page, select **Reserve lot** to reserve the selected line's full quantity in the warehouse.</span></span>
1. <span data-ttu-id="4c583-265">Fermez la page **Réservation** pour revenir à la commande client.</span><span class="sxs-lookup"><span data-stu-id="4c583-265">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="4c583-266">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="4c583-266">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="4c583-267">Le travail est créé pour déplacer les articles de l’emplacement de prélèvement vers la station de conditionnement.</span><span class="sxs-lookup"><span data-stu-id="4c583-267">Work is created to move items from the picking location to the packing station.</span></span>

1. <span data-ttu-id="4c583-268">Dans la section **Lignes de commande client**, sélectionnez **Entrepôt \> Détails de l’expédition**.</span><span class="sxs-lookup"><span data-stu-id="4c583-268">In the **Sales order lines** section, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="4c583-269">Sur la page **Détails de l’expédition**, notez l’ID d’expédition.</span><span class="sxs-lookup"><span data-stu-id="4c583-269">On the **Shipment details** page, make a note of the shipment ID.</span></span> <span data-ttu-id="4c583-270">Vous en aurez besoin lorsque vous emballerez l’expédition à la station de conditionnement.</span><span class="sxs-lookup"><span data-stu-id="4c583-270">You will need it when you pack the pack the shipment at the packing station.</span></span>
1. <span data-ttu-id="4c583-271">Fermez la page **Détails de l’expédition** pour revenir à la commande client.</span><span class="sxs-lookup"><span data-stu-id="4c583-271">Close the **Shipment details** page to return to the sales order.</span></span>
1. <span data-ttu-id="4c583-272">Notez le numéro de la commande client, puis accédez à **Gestion des entrepôts \> Travail \> Tout le travail**.</span><span class="sxs-lookup"><span data-stu-id="4c583-272">Make a note of the sales order number, and then go to **Warehouse management \> Work \> All work**.</span></span>
1. <span data-ttu-id="4c583-273">Utilisez le numéro de commande client pour rechercher et sélectionner le travail qui a été créé pour la commande.</span><span class="sxs-lookup"><span data-stu-id="4c583-273">Use the sales order number to find and select the work that was created for the order.</span></span>
1. <span data-ttu-id="4c583-274">Dans le volet Actions, sous l’onglet **Travail**, sélectionnez **Terminer le travail**.</span><span class="sxs-lookup"><span data-stu-id="4c583-274">On the Action Pane, on the **Work** tab, select **Complete work**.</span></span>
1. <span data-ttu-id="4c583-275">Sur la page **Achèvement du travail**, dans le champ **ID utilisateur**, sélectionnez un ID utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4c583-275">On the **Work completion** page, in the **User ID** field, select a user ID.</span></span> <span data-ttu-id="4c583-276">Ensuite, dans le volet Actions, sélectionnez **Valider le travail**.</span><span class="sxs-lookup"><span data-stu-id="4c583-276">Then, on the Action Pane, select **Validate work**.</span></span>
1. <span data-ttu-id="4c583-277">Si le travail réussit la validation, sélectionnez **Terminer le travail** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="4c583-277">If the work passes validation, select **Complete work** on the Action Pane.</span></span>

    <span data-ttu-id="4c583-278">Le travail est marqué comme terminé pour simuler le mouvement des articles vers la station de conditionnement.</span><span class="sxs-lookup"><span data-stu-id="4c583-278">The work is marked as completed to simulate the movement of items to the packing station.</span></span>

#### <a name="pack-the-shipment"></a><span data-ttu-id="4c583-279">Emballer l’expédition</span><span class="sxs-lookup"><span data-stu-id="4c583-279">Pack the shipment</span></span>

<span data-ttu-id="4c583-280">Procédez comme suit pour emballer l’expédition.</span><span class="sxs-lookup"><span data-stu-id="4c583-280">Follow these steps to pack the shipment.</span></span>

1. <span data-ttu-id="4c583-281">Accédez à **Gestion des entrepôts \> Configuration \> Collaborateur** et assurez-vous que votre compte d’utilisateur est associé à un compte de collaborateur pour la gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="4c583-281">Go to **Warehouse management \> Setup \> Worker**, and make sure that your user account is associated with a worker account for warehouse management.</span></span>
1. <span data-ttu-id="4c583-282">Accédez à **Gestion des entrepôts \> Prélèvement et mise en conteneur \> Emballage**.</span><span class="sxs-lookup"><span data-stu-id="4c583-282">Go to **Warehouse management \> Picking and containerization \> Pack**.</span></span>
1. <span data-ttu-id="4c583-283">Dans la boîte de dialogue **Sélectionner une station de conditionnement**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c583-283">In the **Select packing station** dialog box, set the following values:</span></span>

    - <span data-ttu-id="4c583-284">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="4c583-284">**Site:** *6*</span></span>
    - <span data-ttu-id="4c583-285">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="4c583-285">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="4c583-286">**Emplacement :** *Emballer*</span><span class="sxs-lookup"><span data-stu-id="4c583-286">**Location:** *Pack*</span></span>
    - <span data-ttu-id="4c583-287">**ID profil d’emballage :** *Profil d’emballage de démonstration*</span><span class="sxs-lookup"><span data-stu-id="4c583-287">**Packing profile ID:** *Demo packing profile*</span></span>

1. <span data-ttu-id="4c583-288">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c583-288">Select **OK**.</span></span>
1. <span data-ttu-id="4c583-289">La page **Emballage** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="4c583-289">The **Pack** page appears.</span></span> <span data-ttu-id="4c583-290">Dans un scénario de production, un collaborateur numérise un contenant ou un ID d’expédition.</span><span class="sxs-lookup"><span data-stu-id="4c583-290">In a production scenario, a worker will scan a license plate or shipment ID.</span></span> <span data-ttu-id="4c583-291">Cependant, pour ce scénario, ouvrez la page **Toutes les expéditions** et recherchez le numéro de l’expédition que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="4c583-291">However, for this scenario, open the **All shipments** page, and look up the shipment number for the shipment that you just created.</span></span> <span data-ttu-id="4c583-292">Ensuite, entrez cette valeur dans le champ **Contenant ou expédition** de la page **Emballage**.</span><span class="sxs-lookup"><span data-stu-id="4c583-292">Then enter this value in the **License plate or shipment** field on the **Pack** page.</span></span> <span data-ttu-id="4c583-293">Vous pouvez également entrer l’ID d’expédition que vous avez noté précédemment.</span><span class="sxs-lookup"><span data-stu-id="4c583-293">Alternatively, enter the shipment ID that you made a note of earlier.</span></span>
1. <span data-ttu-id="4c583-294">Dans le volet Actions, sélectionnez **Nouveau conteneur**.</span><span class="sxs-lookup"><span data-stu-id="4c583-294">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="4c583-295">La boîte de dialogue qui apparaît affiche des détails sur le nouveau conteneur.</span><span class="sxs-lookup"><span data-stu-id="4c583-295">The dialog box that appears shows details about the new container.</span></span> <span data-ttu-id="4c583-296">Conservez les valeurs par défaut, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c583-296">Leave the default values, and then select **OK**.</span></span>
1. <span data-ttu-id="4c583-297">Sur la page **Emballage**, dans le raccourci **Emballage de l’article**, dans le champ **Identifiant**, sélectionnez *A0002* pour emballer cet article.</span><span class="sxs-lookup"><span data-stu-id="4c583-297">On the **Pack** page, on the **Item packing** FastTab, in the **Identifier** field, select *A0002* to pack that item.</span></span> <span data-ttu-id="4c583-298">L’article est ajouté au conteneur.</span><span class="sxs-lookup"><span data-stu-id="4c583-298">The item is added to the container.</span></span>
1. <span data-ttu-id="4c583-299">Dans le volet Actions, sélectionnez **Conteneur pour expédition**.</span><span class="sxs-lookup"><span data-stu-id="4c583-299">On the Action Pane, select **Containers for shipment**.</span></span>

    <span data-ttu-id="4c583-300">La page **Conteneurs pour expédition** qui apparaît a une ligne pour le conteneur que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="4c583-300">The **Containers for shipment** page that appears has a row for the container that you just created.</span></span> <span data-ttu-id="4c583-301">Cependant, le champ **ID manifeste du conteneur** de cette ligne est actuellement vide, car vous n’avez pas encore reçu l’étiquette d’expédition et le numéro de suivi du transporteur.</span><span class="sxs-lookup"><span data-stu-id="4c583-301">However, the **Container manifest ID** field in that row is currently blank, because you haven't yet received the shipping label and tracking number from the carrier.</span></span>

1. <span data-ttu-id="4c583-302">Dans le volet Actions, sélectionnez **Fermer le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="4c583-302">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="4c583-303">Dans la boîte de dialogue **Fermer le conteneur**, définissez le champ **Poids brut** sur *1 kg*, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c583-303">In the **Close container** dialog box, set the **Gross weight** field to *1 kg*, and then select **OK**.</span></span>

    <span data-ttu-id="4c583-304">L’étiquette d’expédition doit maintenant être imprimée sur l’imprimante ZPL que vous avez sélectionnée précédemment.</span><span class="sxs-lookup"><span data-stu-id="4c583-304">The shipping label should now be printed on the ZPL printer that you selected earlier.</span></span> <span data-ttu-id="4c583-305">Elle doit ressembler à l’exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4c583-305">It should resemble the following example.</span></span>

    <span data-ttu-id="4c583-306">![Exemple d’étiquette d’expédition](media/sps-label-example.png "Exemple d’étiquette d’expédition")</span><span class="sxs-lookup"><span data-stu-id="4c583-306">![Example shipping label](media/sps-label-example.png "Example shipping label")</span></span>

1. <span data-ttu-id="4c583-307">Notez que les valeurs **ID manifeste du conteneur** et **Transport total** ont été ajoutées telles qu’elles ont été reçues du transporteur.</span><span class="sxs-lookup"><span data-stu-id="4c583-307">Notice that the **Container manifest ID** and **Total freight** values have been added as received from the carrier.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]