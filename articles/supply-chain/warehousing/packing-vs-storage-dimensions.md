---
title: Définir différentes dimensions pour l’emballage et le stockage
description: Cette rubrique montre comment spécifier le processus (emballage, stockage ou emballage imbriqué) pour lequel chaque dimension spécifiée est utilisée.
author: mirzaab
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResPhysicalProductDimensions, WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: aa5cbf807e809238489c539d3ad8c0bc34421774
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501292"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a><span data-ttu-id="60818-103">Définir différentes dimensions pour l’emballage et le stockage</span><span class="sxs-lookup"><span data-stu-id="60818-103">Set different dimensions for packing and storage</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="60818-104">Certains articles sont emballés ou stockés de telle sorte que vous devrez peut-être effectuer le suivi des dimensions physiques de manière différente pour chacun des différents processus.</span><span class="sxs-lookup"><span data-stu-id="60818-104">Some items are packed or stored in such a way that you may need to track physical dimensions differently for each of several different processes.</span></span> <span data-ttu-id="60818-105">La fonctionnalité *Dimensions d’emballage du produit* vous permet de configurer un ou plusieurs types de dimensions pour chaque produit.</span><span class="sxs-lookup"><span data-stu-id="60818-105">The *Packaging product dimensions* feature lets you set up one or several types of dimensions for each product.</span></span> <span data-ttu-id="60818-106">Chaque type de dimension fournit un ensemble de mesures physiques (poids, largeur, profondeur et hauteur) et établit le processus dans lequel ces valeurs de mesure physique s’appliquent.</span><span class="sxs-lookup"><span data-stu-id="60818-106">Each dimension type provides a set of physical measurements (weight, width, depth, and height), and establishes the process where those physical measurement values apply.</span></span> <span data-ttu-id="60818-107">Lorsque cette fonctionnalité est activée, votre système prend en charge les types de dimensions suivants :</span><span class="sxs-lookup"><span data-stu-id="60818-107">When this feature is enabled, your system will support the following types of dimensions:</span></span>

- <span data-ttu-id="60818-108">*Stockage* : les dimensions de stockage sont utilisées avec la volumétrie de l’emplacement pour déterminer quelle quantité de chaque article peut être stockée dans divers emplacements de l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="60818-108">*Storage* - Storage dimensions are used along with location volumetrics to determine how many of each item can be stored in various warehouse locations.</span></span>
- <span data-ttu-id="60818-109">*Emballage* : les dimensions d’emballage sont utilisées pendant la mise en conteneur et le processus d’emballage manuel pour déterminer quelle quantité de chaque article peut contenir dans divers types de conteneurs.</span><span class="sxs-lookup"><span data-stu-id="60818-109">*Packing* - Packing dimensions are used during containerization and the manual packing process to determine how many of each item will fit in various container types.</span></span>
- <span data-ttu-id="60818-110">*Emballage imbriqué* : les dimensions d’emballage imbriqué sont utilisées lorsque le processus d’emballage contient plusieurs niveaux.</span><span class="sxs-lookup"><span data-stu-id="60818-110">*Nested packing* - Nested packing dimensions are used when the packing process contains multiple levels.</span></span>

<span data-ttu-id="60818-111">Les dimensions de *stockage* sont prises en charge même lorsque la fonctionnalité *Dimensions d’emballage du produit* n’est pas activée.</span><span class="sxs-lookup"><span data-stu-id="60818-111">*Storage* dimensions are supported even when the *Packaging product dimensions* feature isn't enabled.</span></span> <span data-ttu-id="60818-112">Vous configurez ces dimensions dans la page **Dimension physique** de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="60818-112">You set these up using the **Physical dimension** page in Supply Chain Management.</span></span> <span data-ttu-id="60818-113">Ces dimensions sont utilisées par tous les processus dans lesquels les dimensions d’emballage et d’emballage imbriqué ne sont pas spécifiées.</span><span class="sxs-lookup"><span data-stu-id="60818-113">These dimensions are used by all processes where the packing and nested packing dimensions aren't specified.</span></span>

<span data-ttu-id="60818-114">Les dimensions d’*emballage* et d’*emballage imbriqué* sont configurées dans la page **Dimensions physiques du produit**, qui est ajoutée lorsque vous activez la fonctionnalité *Dimensions d’emballage du produit*.</span><span class="sxs-lookup"><span data-stu-id="60818-114">*Packing* and *nested packing* dimensions are set up using the **Physical product dimensions** page, which is added when you enable the *Packaging product dimensions* feature.</span></span>
<span data-ttu-id="60818-115">Cette rubrique présente un scénario qui illustre comment utiliser cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="60818-115">This topic provides a scenario that illustrates how to use this feature.</span></span>

## <a name="turn-on-the-packaging-product-dimensions-feature"></a><span data-ttu-id="60818-116">Activer la fonctionnalité Dimensions d’emballage du produit</span><span class="sxs-lookup"><span data-stu-id="60818-116">Turn on the packaging product dimensions feature</span></span>

<span data-ttu-id="60818-117">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="60818-117">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="60818-118">Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="60818-118">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="60818-119">Là, la fonctionnalité est répertoriée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="60818-119">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="60818-120">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="60818-120">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="60818-121">**Nom de la fonctionnalité :** *Dimensions d’emballage du produit*</span><span class="sxs-lookup"><span data-stu-id="60818-121">**Feature name:** *Packaging product dimensions*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="60818-122">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="60818-122">Example scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="60818-123">Paramétrage du scénario</span><span class="sxs-lookup"><span data-stu-id="60818-123">Set up the scenario</span></span>

<span data-ttu-id="60818-124">Avant de pouvoir exécuter l’exemple de scénario, vous devez préparer votre système comme décrit dans cette section.</span><span class="sxs-lookup"><span data-stu-id="60818-124">Before you can run the example scenario, you must prepare your system as described in this section.</span></span>

#### <a name="enable-demo-data"></a><span data-ttu-id="60818-125">Activer les données de démonstration</span><span class="sxs-lookup"><span data-stu-id="60818-125">Enable demo data</span></span>

<span data-ttu-id="60818-126">Pour exécuter ce scénario en utilisant les enregistrements et les valeurs de démonstration spécifiés ici, vous devez utiliser un système dans lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées.</span><span class="sxs-lookup"><span data-stu-id="60818-126">To work through this scenario using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="60818-127">En outre, vous devez sélectionner l’entité juridique *USMF* avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="60818-127">Additionally, you must select the *USMF* legal entity before you begin.</span></span>

#### <a name="add-a-new-physical-dimension-to-a-product"></a><span data-ttu-id="60818-128">Ajouter une nouvelle dimension physique à un produit</span><span class="sxs-lookup"><span data-stu-id="60818-128">Add a new physical dimension to a product</span></span>

<span data-ttu-id="60818-129">Ajoutez une nouvelle dimension physique à un produit en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="60818-129">Add a new physical dimension for a product by doing the following:</span></span>

1. <span data-ttu-id="60818-130">Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="60818-130">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="60818-131">Sélectionnez le produit avec le **Numéro d’article** *A0001*.</span><span class="sxs-lookup"><span data-stu-id="60818-131">Select the product with **Item number** *A0001*.</span></span>
1. <span data-ttu-id="60818-132">Dans le volet Actions, ouvrez l’onglet **Gérer le stock** et, dans le groupe **Entrepôt**, sélectionnez **Dimensions physiques du produit**.</span><span class="sxs-lookup"><span data-stu-id="60818-132">On the Action Pane, open the **Manage inventory** tab and, from the **Warehouse** group, select **Physical product dimensions**.</span></span>
1. <span data-ttu-id="60818-133">La page **Dimensions physiques du produit** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="60818-133">The **Physical product dimensions** page opens.</span></span> <span data-ttu-id="60818-134">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une nouvelle dimension à la grille avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="60818-134">On the Action Pane, select **New** to add a new dimension to the grid with the following settings:</span></span>
    - <span data-ttu-id="60818-135">**Type de dimension physique** - *Emballage*</span><span class="sxs-lookup"><span data-stu-id="60818-135">**Physical dimension type** - *Packing*</span></span>
    - <span data-ttu-id="60818-136">**Unité physique** - *pcs*</span><span class="sxs-lookup"><span data-stu-id="60818-136">**Physical unit** - *pcs*</span></span>
    - <span data-ttu-id="60818-137">**Poids** - *4*</span><span class="sxs-lookup"><span data-stu-id="60818-137">**Weight** - *4*</span></span>
    - <span data-ttu-id="60818-138">**Unité de poids** - *kg*</span><span class="sxs-lookup"><span data-stu-id="60818-138">**Weight unit** - *kg*</span></span>
    - <span data-ttu-id="60818-139">**Profondeur** - *3*</span><span class="sxs-lookup"><span data-stu-id="60818-139">**Depth** - *3*</span></span>
    - <span data-ttu-id="60818-140">**Hauteur** - *4*</span><span class="sxs-lookup"><span data-stu-id="60818-140">**Height** - *4*</span></span>
    - <span data-ttu-id="60818-141">**Largeur** - *3*</span><span class="sxs-lookup"><span data-stu-id="60818-141">**Width** - *3*</span></span>
    - <span data-ttu-id="60818-142">**Longueur** - *cm*</span><span class="sxs-lookup"><span data-stu-id="60818-142">**Length** - *cm*</span></span>
    - <span data-ttu-id="60818-143">**Unité de volume** - *cm3*</span><span class="sxs-lookup"><span data-stu-id="60818-143">**Volume unit** - *cm3*</span></span>

<span data-ttu-id="60818-144">Le champ **Volume** est automatiquement calculé en fonction de vos paramètres de **Profondeur**, **Hauteur** et **Largeur**.</span><span class="sxs-lookup"><span data-stu-id="60818-144">The **Volume** field is automatically calculated based on your **Depth**, **Height**, and **Width** settings.</span></span>

#### <a name="create-a-new-container-type"></a><span data-ttu-id="60818-145">Créer un type de conteneur</span><span class="sxs-lookup"><span data-stu-id="60818-145">Create a new container type</span></span>

<span data-ttu-id="60818-146">Accédez à **Gestion des entrepôts \> Configuration \> Conteneurs \> Types de conteneurs** et créez un enregistrement avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="60818-146">Go to **Warehouse management \> Setup \> Containers \> Container types** and create a new record with the following settings:</span></span>

- <span data-ttu-id="60818-147">**Code type de conteneur** - *Boîte courte*</span><span class="sxs-lookup"><span data-stu-id="60818-147">**Container type code** - *Short Box*</span></span>
- <span data-ttu-id="60818-148">**Description** - *Boîte courte*</span><span class="sxs-lookup"><span data-stu-id="60818-148">**Description** - *Short Box*</span></span>
- <span data-ttu-id="60818-149">**Poids net maximal** - *50*</span><span class="sxs-lookup"><span data-stu-id="60818-149">**Maximum net weight** - *50*</span></span>
- <span data-ttu-id="60818-150">**Volume** - *144*</span><span class="sxs-lookup"><span data-stu-id="60818-150">**Volume** - *144*</span></span>
- <span data-ttu-id="60818-151">**Longueur** - *6*</span><span class="sxs-lookup"><span data-stu-id="60818-151">**Length** - *6*</span></span>
- <span data-ttu-id="60818-152">**Largeur** - *6*</span><span class="sxs-lookup"><span data-stu-id="60818-152">**Width** - *6*</span></span>
- <span data-ttu-id="60818-153">**Hauteur** - *4*</span><span class="sxs-lookup"><span data-stu-id="60818-153">**Height** - *4*</span></span>

#### <a name="create-a-container-group"></a><span data-ttu-id="60818-154">Créer un groupe de conteneurs</span><span class="sxs-lookup"><span data-stu-id="60818-154">Create a container group</span></span>

<span data-ttu-id="60818-155">Accédez à **Gestion des entrepôts \> Configuration \> Conteneurs \> Groupes de conteneurs** et créez un enregistrement avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="60818-155">Go to **Warehouse management \> Setup \> Containers \> Container groups** and create a new record with the following settings:</span></span>

- <span data-ttu-id="60818-156">**ID groupe de conteneurs** - *Boîte courte*</span><span class="sxs-lookup"><span data-stu-id="60818-156">**Container group ID** - *Short Box*</span></span>
- <span data-ttu-id="60818-157">**Description** - *Boîte courte*</span><span class="sxs-lookup"><span data-stu-id="60818-157">**Description** - *Short Box*</span></span>

<span data-ttu-id="60818-158">Ajoutez une nouvelle ligne à la section **Détails**.</span><span class="sxs-lookup"><span data-stu-id="60818-158">Add a new line to the **Details** section.</span></span> <span data-ttu-id="60818-159">Définissez le **Type de conteneur** sur *Boîte courte*.</span><span class="sxs-lookup"><span data-stu-id="60818-159">Set the **Container type** to *Short Box*.</span></span>

#### <a name="set-up-a-container-build-template"></a><span data-ttu-id="60818-160">Paramétrer un modèle de création de conteneur</span><span class="sxs-lookup"><span data-stu-id="60818-160">Set up a container build template</span></span>

<span data-ttu-id="60818-161">Accédez à **Gestion des entrepôts \> Configuration \> Conteneurs \> Modèles de création de conteneur** et sélectionnez **Boîtes**.</span><span class="sxs-lookup"><span data-stu-id="60818-161">Go to **Warehouse management \> Setup \> Containers \> Container build templates** and select **Boxes**.</span></span> <span data-ttu-id="60818-162">Modifiez l’**ID groupe de conteneurs** en *Boîte courte*.</span><span class="sxs-lookup"><span data-stu-id="60818-162">Change the **Container group ID** to *Short Box*.</span></span>

### <a name="run-the-scenario"></a><span data-ttu-id="60818-163">Exécuter le scénario</span><span class="sxs-lookup"><span data-stu-id="60818-163">Run the scenario</span></span>

<span data-ttu-id="60818-164">Une fois que vous avez préparé votre système comme décrit dans la section précédente, vous êtes prêt à exécuter le scénario comme décrit dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="60818-164">After you have prepared your system as described in the previous section, you are ready to run the scenario as described in the next section.</span></span>

#### <a name="create-a-sales-order-and-create-a-shipment"></a><span data-ttu-id="60818-165">Créer une commande client et une expédition</span><span class="sxs-lookup"><span data-stu-id="60818-165">Create a sales order and create a shipment</span></span>

<span data-ttu-id="60818-166">Dans ce processus, vous allez créer une expédition basée sur les dimensions d’*emballage* de l’article, dont la hauteur est inférieure à 3.</span><span class="sxs-lookup"><span data-stu-id="60818-166">In this process you will create a shipment based on the item *packing* dimensions, for which the height is less than 3.</span></span>

1. <span data-ttu-id="60818-167">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="60818-167">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="60818-168">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="60818-168">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="60818-169">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="60818-169">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="60818-170">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="60818-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="60818-171">**Entrepôt :** *63*</span><span class="sxs-lookup"><span data-stu-id="60818-171">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="60818-172">Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="60818-172">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="60818-173">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="60818-173">The new sales order is opened.</span></span> <span data-ttu-id="60818-174">Elle doit inclure une nouvelle ligne vide dans la grille de l’organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="60818-174">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="60818-175">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="60818-175">On this line, set the following values:</span></span>

    - <span data-ttu-id="60818-176">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="60818-176">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="60818-177">**Quantité :** *5*</span><span class="sxs-lookup"><span data-stu-id="60818-177">**Quantity:** *5*</span></span>

1. <span data-ttu-id="60818-178">Sur l’organisateur **Lignes de commande client**, sélectionnez **Stock \> Réservation**.</span><span class="sxs-lookup"><span data-stu-id="60818-178">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="60818-179">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver le stock.</span><span class="sxs-lookup"><span data-stu-id="60818-179">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="60818-180">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="60818-180">Close the page.</span></span>
1. <span data-ttu-id="60818-181">Dans le volet Actions, ouvrez l’onglet **Entrepôt** et sélectionnez **Libérer dans l’entrepôt** pour créer un travail pour l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="60818-181">On the Action Pane, open the **Warehouse** tab and select **Release to warehouse** to create work for the warehouse.</span></span>
1. <span data-ttu-id="60818-182">Dans le raccourci **Lignes de commande client**, sélectionnez **Entrepôt \> Détails de l’expédition**.</span><span class="sxs-lookup"><span data-stu-id="60818-182">On the **Sales order lines** FastTab, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="60818-183">Dans le volet Actions, ouvrez l’onglet **Transport** et sélectionnez **Afficher les conteneurs**.</span><span class="sxs-lookup"><span data-stu-id="60818-183">On the Action Pane, open the **Transportation** tab and select **View containers**.</span></span> <span data-ttu-id="60818-184">Confirmez que l’article a été mis en conteneur dans les deux conteneurs *Boîte courte*.</span><span class="sxs-lookup"><span data-stu-id="60818-184">Confirm that the item was containerized into the two *Short Box* containers.</span></span>

#### <a name="place-an-item-into-storage"></a><span data-ttu-id="60818-185">Stocker un article</span><span class="sxs-lookup"><span data-stu-id="60818-185">Place an item into storage</span></span>

1. <span data-ttu-id="60818-186">Ouvrez l’appareil mobile, connectez-vous à l’entrepôt 63 et accédez à **Stock \> Ajuster dans**.</span><span class="sxs-lookup"><span data-stu-id="60818-186">Open the mobile device, sign in to warehouse 63 and go to **Inventory \> Adjust In**.</span></span>
1. <span data-ttu-id="60818-187">Entrez **Loc** = *SHORT-01*.</span><span class="sxs-lookup"><span data-stu-id="60818-187">Enter **Loc** = *SHORT-01*.</span></span> <span data-ttu-id="60818-188">Créez un contenant avec **Article** = *A0001* et **Quantité** = *1 pc*.</span><span class="sxs-lookup"><span data-stu-id="60818-188">Make a new license plate with **Item** = *A0001* and **Quantity** = *1 pcs*.</span></span>
1. <span data-ttu-id="60818-189">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="60818-189">Select **OK**.</span></span> <span data-ttu-id="60818-190">Vous recevrez l’erreur « L’emplacement SHORT-01 a échoué, car l’article A0001 ne correspond pas aux dimensions spécifiées de l’emplacement. »</span><span class="sxs-lookup"><span data-stu-id="60818-190">You will receive the error "Location SHORT-01 failed because item A0001 does not fit in location's specified dimensions."</span></span> <span data-ttu-id="60818-191">Les dimensions de type *Stockage* du produit sont plus grandes que les dimensions spécifiées sur le profil d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="60818-191">This is because the *Storage* type dimensions of the product are larger than the dimensions specified on the location profile.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]