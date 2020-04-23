---
title: Activer et configurer les frais automatiques par canal
description: Cette rubrique explique comment activer et configurer les frais automatiques par canal dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 1be07c754e563298d82f6ca54f09ae3aa9118602
ms.sourcegitcommit: 4e9b3746790355f9f72bbfddc099c4065a49ad63
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2020
ms.locfileid: "3175421"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a><span data-ttu-id="74392-103">Activer et configurer les frais automatiques par canal</span><span class="sxs-lookup"><span data-stu-id="74392-103">Enable and configure auto charges by channel</span></span>

<span data-ttu-id="74392-104">Cette rubrique explique comment activer et configurer les frais automatiques par canal dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="74392-104">This topic explains how to enable and configure automatic charges (auto charges) by channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="74392-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="74392-105">Overview</span></span>

<span data-ttu-id="74392-106">Vous pouvez avoir des scénarios dans lesquels des frais de recyclage ou d'autres frais doivent être appliqués à un groupe de produits qui sont vendus dans tous ou certains magasins dans un état spécifique (par exemple, la Californie).</span><span class="sxs-lookup"><span data-stu-id="74392-106">You might have scenarios where recycling fees or other fees must be applied to a group of products that are sold in all or some stores in a specific state (for example, California).</span></span> <span data-ttu-id="74392-107">La fonction **Activer le filtrage des frais automatiques par canal** dans Commerce vous permet de spécifier les frais automatiques par canal (par exemple, un canal physique spécifique).</span><span class="sxs-lookup"><span data-stu-id="74392-107">The **Enable filter auto charges by channel** feature in Commerce lets you specify auto charges by channel (for example, a specific brick-and-mortar channel).</span></span> <span data-ttu-id="74392-108">Cette fonction est disponible dans Dynamics 365 Commerce (version 10.0.10 et ultérieure).</span><span class="sxs-lookup"><span data-stu-id="74392-108">This feature is available in Dynamics 365 Commerce version 10.0.10 and later.</span></span>

<span data-ttu-id="74392-109">Pour activer et configurer les frais automatiques par canal, vous devez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="74392-109">To enable and configure auto charges by channel, you must complete the following tasks:</span></span>

- <span data-ttu-id="74392-110">Activez la fonction **Activer le filtrage des frais automatiques par canal**.</span><span class="sxs-lookup"><span data-stu-id="74392-110">Turn on the **Enable filter auto charges by channel** feature.</span></span>
- <span data-ttu-id="74392-111">Configurez l'objectif de la hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="74392-111">Configure the organization hierarchy purpose.</span></span>
- <span data-ttu-id="74392-112">Définissez les frais automatiques par canal.</span><span class="sxs-lookup"><span data-stu-id="74392-112">Define auto charges by channel.</span></span>

> [!NOTE]
> <span data-ttu-id="74392-113">La fonction **Activer le filtrage des frais automatiques par canal** ne fonctionne que si la fonction de frais automatiques avancés est également activée.</span><span class="sxs-lookup"><span data-stu-id="74392-113">The **Enable filter auto charges by channel** feature works only if the advanced auto charges feature is also turned on.</span></span> <span data-ttu-id="74392-114">Pour plus d'informations sur l'activation de la fonction de frais automatiques avancés, consultez [Frais automatiques avancés omnicanaux](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="74392-114">For information about how to turn on the advanced auto charges feature, see [Omni-channel advanced auto charges](omni-auto-charges.md).</span></span>

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a><span data-ttu-id="74392-115">Activer la fonction Activer le filtrage des frais automatiques par canal</span><span class="sxs-lookup"><span data-stu-id="74392-115">Turn on the Enable filter auto charges by channel feature</span></span>

<span data-ttu-id="74392-116">Pour activer les frais automatiques par canal dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="74392-116">To enable auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="74392-117">Accédez à **Administrateur système \> Espaces de travail \> Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="74392-117">Go to **System administrator \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="74392-118">Sur l'onglet **Non activé**, dans la liste **Nom de la fonctionnalité**, recherchez et sélectionnez **Activer le filtrage des frais automatiques par canal**.</span><span class="sxs-lookup"><span data-stu-id="74392-118">On the **Not enabled** tab, in the **Feature name** list, find and select **Enable filter auto charges by channel**.</span></span>
1. <span data-ttu-id="74392-119">Dans l'angle inférieur droit, sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="74392-119">In the lower-right corner, select **Enable now**.</span></span> <span data-ttu-id="74392-120">Une fois la fonctionnalité activée, elle apparaît dans la liste sur l'onglet **Tout**.</span><span class="sxs-lookup"><span data-stu-id="74392-120">After the feature has been turned on, it will appear in the list on the **All** tab.</span></span>
1. <span data-ttu-id="74392-121">Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.</span><span class="sxs-lookup"><span data-stu-id="74392-121">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="74392-122">Dans le volet gauche, recherchez et sélectionnez la tâche **1110** (**Configuration globale**).</span><span class="sxs-lookup"><span data-stu-id="74392-122">In the left pane, find and select the **1110** (**Global configuration**) job.</span></span>
1. <span data-ttu-id="74392-123">Dans le volet Actions, sélectionnez **Exécuter maintenant** pour propager les changements de configuration.</span><span class="sxs-lookup"><span data-stu-id="74392-123">On the Action Pane, select **Run now** to propagate the configuration changes.</span></span>

> [!WARNING]
> <span data-ttu-id="74392-124">Si vous désactivez la fonctionnalité **Activer le filtrage des frais automatiques par canal** après l'avoir déjà utilisée, le champ **Relation avec les canaux de vente au détail** sous **Frais automatiques** n'apparaît plus et vous perdez toutes les configurations existantes.</span><span class="sxs-lookup"><span data-stu-id="74392-124">If you turn off the **Enable filter auto charges by channel** feature after you've already used it, the **Retail channel relation** field under **Auto charges** will no longer appear, and you will lose all existing configurations.</span></span> <span data-ttu-id="74392-125">Si la suppression des configurations **Relation avec les canaux de vente au détail** entraîne la duplication des règles de frais automatiques, il est impossible de désactiver la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="74392-125">If removal of the **Retail channel relation** configurations will cause auto charges rules to be duplicated, an attempt to turn off the feature will fail.</span></span> <span data-ttu-id="74392-126">Avant de désactiver la fonctionnalité, assurez-vous de consulter tous les frais automatiques et apportez les modifications requises.</span><span class="sxs-lookup"><span data-stu-id="74392-126">Before you turn off the feature, be sure to review all auto charges rules and make any required changes.</span></span>

## <a name="configure-the-organization-hierarchy-purpose"></a><span data-ttu-id="74392-127">Configurer l'objectif de la hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="74392-127">Configure the organization hierarchy purpose</span></span>

<span data-ttu-id="74392-128">Un nouvel objectif de hiérarchie d'organisation nommé **Frais automatiques de vente au détail** a été créé pour gérer la hiérarchie des frais automatiques par canal.</span><span class="sxs-lookup"><span data-stu-id="74392-128">A new organization hierarchy purpose that is named **Retail auto charge** has been created to manage the hierarchy for auto charges by channel.</span></span>

<span data-ttu-id="74392-129">Pour affecter une hiérarchie par défaut à un objectif de hiérarchie d'organisation dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="74392-129">To assign a default hierarchy to an organization hierarchy purpose in Commerce, follow these steps.</span></span>
        
1. <span data-ttu-id="74392-130">Accédez à **Administration d'organisation \> Organisations \> Objectifs de hiérarchies d'organisation**.</span><span class="sxs-lookup"><span data-stu-id="74392-130">Go to **Organization administration \> Organizations \> Organization hierarchy purposes**.</span></span>
1. <span data-ttu-id="74392-131">Dans le volet gauche, sélectionnez **Frais automatiques de vente au détail**.</span><span class="sxs-lookup"><span data-stu-id="74392-131">In the left pane, select **Retail auto charge**.</span></span>
1. <span data-ttu-id="74392-132">Sous **Hiérarchies affectées**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="74392-132">Under **Assigned hierarchies**, select **Add**.</span></span>
1. <span data-ttu-id="74392-133">Dans la boîte de dialogue **Hiérarchies d'organisation**, sélectionnez une hiérarchie d'organisation (par exemple, **Magasins de vente au détail par région**), puis **OK**.</span><span class="sxs-lookup"><span data-stu-id="74392-133">In the **Organization hierarchies** dialog box, select an organization hierarchy (for example, **Retail Stores by Region**), and then select **OK**.</span></span>
1. <span data-ttu-id="74392-134">Sous **Hiérarchies affectées**, sélectionnez **Définir par défaut**.</span><span class="sxs-lookup"><span data-stu-id="74392-134">Under **Assigned hierarchies**, select **Set as default**.</span></span>
1. <span data-ttu-id="74392-135">Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.</span><span class="sxs-lookup"><span data-stu-id="74392-135">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="74392-136">Dans le volet gauche, recherchez et sélectionnez la tâche **1040** (**Produits**).</span><span class="sxs-lookup"><span data-stu-id="74392-136">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="74392-137">Dans le volet Actions, sélectionnez **Exécuter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="74392-137">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="74392-138">Répétez les deux étapes précédentes pour exécuter les tâches **1070** (**Configuration des canaux**) et **1110** (**Configuration globale**).</span><span class="sxs-lookup"><span data-stu-id="74392-138">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>

![Configuration de l'objectif de hiérarchies d'organisation des frais automatiques de la vente au détail](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a><span data-ttu-id="74392-140">Définir les frais automatiques par canal</span><span class="sxs-lookup"><span data-stu-id="74392-140">Define auto charges by channel</span></span>

<span data-ttu-id="74392-141">Après avoir activé la fonctionnalité **Activer le filtrage des frais automatiques par canal** et configuré l'objectif de hiérarchies d'organisation **Frais automatiques de la vente au détail**, les frais automatiques par canal peuvent être définis au niveau de l'en-tête de la commande ou au niveau de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="74392-141">After you've turned on the **Enable filter auto charges by channel** feature and configured the **Retail auto charge** organization hierarchy purpose, auto charges by channel can be defined at either the order header level or the order line level.</span></span>

<span data-ttu-id="74392-142">Pour définir les frais automatiques par canal dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="74392-142">To define auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="74392-143">Accédez à  **Comptabilité client \> Paramétrage des frais \> Frais automatiques**.</span><span class="sxs-lookup"><span data-stu-id="74392-143">Go to **Accounts receivable \> Charges setup \> Auto charges**.</span></span>
1. <span data-ttu-id="74392-144">Dans le volet gauche, dans le champ **Niveau**, sélectionnez **En-tête** ou **Ligne**, en fonction des besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="74392-144">In the left pane, in the **Level** field, select either **Header** or **Line**, depending on your business requirements.</span></span>
1. <span data-ttu-id="74392-145">Dans le champ **Code du canal de vente au détail**, sélectionnez le code de canal approprié (par exemple, **Table** ou **Groupe**).</span><span class="sxs-lookup"><span data-stu-id="74392-145">In the **Retail channel code** field, select the appropriate channel code (for example, **Table** or **Group**).</span></span> <span data-ttu-id="74392-146">Si le paramètre par défaut, **Tout**, est utilisé, les règles de facturation sont appliquées à tous les canaux.</span><span class="sxs-lookup"><span data-stu-id="74392-146">If the default setting, **All**, is used, charge rules are applied to all channels.</span></span>

    - <span data-ttu-id="74392-147">Si vous sélectionnez **Groupe**, assurez-vous qu'un groupe de frais de canal de vente au détail est créé à **Vente au détail et commerce\>Paramétrage du canal \>Frais \>Groupes de frais du canal de vente au détail**.</span><span class="sxs-lookup"><span data-stu-id="74392-147">If you select **Group**, make sure that a retail channel charges group is created at **Retail and Commerce \> Channel setup \> Charges \> Retail channel charge groups**.</span></span>
    - <span data-ttu-id="74392-148">Si vous sélectionnez **Table**, vous pouvez sélectionner une chaîne spécifique (par exemple, **San Francisco**) dans le champ **Relation avec les canaux de vente au détail**.</span><span class="sxs-lookup"><span data-stu-id="74392-148">If you select **Table**, you can select a specific channel (for example, **San Francisco**) in the **Retail channel relation** field.</span></span>

1. <span data-ttu-id="74392-149">Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.</span><span class="sxs-lookup"><span data-stu-id="74392-149">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="74392-150">Dans le volet gauche, recherchez et sélectionnez la tâche **1040** (**Produits**).</span><span class="sxs-lookup"><span data-stu-id="74392-150">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="74392-151">Dans le volet Actions, sélectionnez **Exécuter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="74392-151">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="74392-152">Répétez les deux étapes précédentes pour exécuter les tâches **1070** (**Configuration des canaux**) et **1110** (**Configuration globale**).</span><span class="sxs-lookup"><span data-stu-id="74392-152">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>
    
![Frais automatiques définis par canal](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a><span data-ttu-id="74392-154">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="74392-154">Example scenario</span></span>

<span data-ttu-id="74392-155">L'exemple suivant décrit les étapes requises pour configurer un produit afin que des frais de recyclage soient facturés lorsque le produit est vendu via un canal physique à San Francisco.</span><span class="sxs-lookup"><span data-stu-id="74392-155">The following example outlines the steps that are required to configure a product so that recycling fees are charged when the product is sold through a San Francisco brick-and-mortar channel.</span></span> <span data-ttu-id="74392-156">L'exemple montre également comment les frais automatiques apparaissent dans l'application de point de vente (PDV) Commerce.</span><span class="sxs-lookup"><span data-stu-id="74392-156">The example also shows how the auto charges appear in the Commerce point of sale (POS) application.</span></span>

<span data-ttu-id="74392-157">L'organisation définit un code de frais nommé **RECYCLER**, comme indiqué dans l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="74392-157">The organization defines a charges code that is named **RECYCLE**, as shown in the following illustration.</span></span>

![Code de frais RECYCLER](media/Auto-charges-charge-code.png)

<span data-ttu-id="74392-159">Des frais automatiques sont créés au niveau de la ligne.</span><span class="sxs-lookup"><span data-stu-id="74392-159">An auto charge is created at the line level.</span></span> <span data-ttu-id="74392-160">Ils présentent la configuration suivante :</span><span class="sxs-lookup"><span data-stu-id="74392-160">It has the following configuration:</span></span>

- <span data-ttu-id="74392-161">Le champ **Code de compte** est défini sur **Tout**.</span><span class="sxs-lookup"><span data-stu-id="74392-161">The **Account code** field is set to **All**.</span></span>
- <span data-ttu-id="74392-162">Le champ **Code article** est défini sur **Table**.</span><span class="sxs-lookup"><span data-stu-id="74392-162">The **Item code** field is set to **Table**.</span></span>
- <span data-ttu-id="74392-163">Le champ **Relation d'article** est défini sur l'ID du produit **91001**.</span><span class="sxs-lookup"><span data-stu-id="74392-163">The **Item relation** field is set to product ID **91001**.</span></span>
- <span data-ttu-id="74392-164">Le champ **Code de mode de livraison** est défini sur **Tout**.</span><span class="sxs-lookup"><span data-stu-id="74392-164">The **Mode of delivery code** field is set to **All**.</span></span>
- <span data-ttu-id="74392-165">Le champ **Code de canal de vente au détail** est défini sur **Table**.</span><span class="sxs-lookup"><span data-stu-id="74392-165">The **Retail channel code** field is set to **Table**.</span></span>
- <span data-ttu-id="74392-166">Le champ **Relation avec les canaux de vente au détail** est défini sur le magasin de **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="74392-166">The **Retail channel relation** field is set to the **San Francisco** store.</span></span>

<span data-ttu-id="74392-167">Une ligne de frais automatiques est créée.</span><span class="sxs-lookup"><span data-stu-id="74392-167">An auto charges line is created.</span></span> <span data-ttu-id="74392-168">Ils présentent la configuration suivante :</span><span class="sxs-lookup"><span data-stu-id="74392-168">It has the following configuration:</span></span>

- <span data-ttu-id="74392-169">Le champ **Devise** est défini sur **USD**.</span><span class="sxs-lookup"><span data-stu-id="74392-169">The **Currency** field is set to **USD**.</span></span>
- <span data-ttu-id="74392-170">Le champ **Code de frais** est défini sur **RECYCLER**.</span><span class="sxs-lookup"><span data-stu-id="74392-170">The **Charges code** field is set to **RECYCLE**.</span></span>
- <span data-ttu-id="74392-171">Le champ **Catégorie** est défini sur **Fixe**.</span><span class="sxs-lookup"><span data-stu-id="74392-171">The **Category** field is set to **Fixed**.</span></span>
- <span data-ttu-id="74392-172">Le champ **Frais** est défini sur **6,25 USD**.</span><span class="sxs-lookup"><span data-stu-id="74392-172">The **Charges** field is set to **$6.25**.</span></span>

![Configuration des frais automatiques au niveau de la ligne et de la ligne de frais automatiques](media/Auto-charges-recyclingfee-line-fee.png)

<span data-ttu-id="74392-174">Dans l'application PDV, une commande client est créée dans le canal de magasin **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="74392-174">In the POS application, a sales order is created in the **San Francisco** store channel.</span></span> <span data-ttu-id="74392-175">La ligne **Frais** indique les frais de recyclage de **6,25 USD**.</span><span class="sxs-lookup"><span data-stu-id="74392-175">The **Charges** line shows the recycling fee of **$6.25**.</span></span>

<span data-ttu-id="74392-176">En sélectionnant **Options de transaction \>Frais \>Gérer les frais** dans l'application de PDV, vous pouvez afficher le code des frais et la description des frais de recyclage.</span><span class="sxs-lookup"><span data-stu-id="74392-176">By selecting **Transaction options \> Charges \> Manage charges** in the POS application, you can view the charges code and description for the recycling fee.</span></span>

![Frais de recyclage dans l'application de PDV](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a><span data-ttu-id="74392-178">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="74392-178">Additional resources</span></span>

[<span data-ttu-id="74392-179">Frais automatiques avancés omnicanaux</span><span class="sxs-lookup"><span data-stu-id="74392-179">Omni-channel advanced auto charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="74392-180">Calcul au prorata des frais d'en-tête pour les lignes de vente correspondantes</span><span class="sxs-lookup"><span data-stu-id="74392-180">Prorate header charges to matching sales lines</span></span>](pro-rate-charges-matching-lines.md)
