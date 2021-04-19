---
title: Facture de maintenance sur les actifs appartenant au client
description: Cette rubrique explique comment créer, traiter et facturer les tâches de maintenance effectuées sur les actifs appartenant à vos clients.
author: johanhoffmann
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjInvoiceTable, ProjProjectsListPage, ProjTable, EntAssetWorkOrderType, EntAssetWorkOrderProjectSetup, EntAssetObjectTable, EntAssetWorkOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5532f1ce14239002022f487f227286efe10abf12
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813795"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a><span data-ttu-id="82438-103">Facture de maintenance sur les actifs appartenant au client</span><span class="sxs-lookup"><span data-stu-id="82438-103">Bill for maintenance on customer-owned assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="82438-104">La fonctionnalité *Facturation des ordres de travail* vous permet de créer, traiter et facturer les tâches de maintenance effectuées sur les actifs appartenant à vos clients.</span><span class="sxs-lookup"><span data-stu-id="82438-104">The *Work order billing* feature lets you create, process, and bill maintenance work that is done on assets that your customers own.</span></span> <span data-ttu-id="82438-105">Cette fonctionnalité vous permet d’effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="82438-105">This feature lets you perform the following tasks:</span></span>

- <span data-ttu-id="82438-106">Connectez les clients aux actifs dont ils sont propriétaires.</span><span class="sxs-lookup"><span data-stu-id="82438-106">Connect customers to the assets that they own.</span></span>
- <span data-ttu-id="82438-107">Sélectionnez un client et affichez les actifs qu’il possède lorsque vous créez un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="82438-107">Select a customer and view the assets that customer owns when you create a work order.</span></span>
- <span data-ttu-id="82438-108">Configurez un projet parent pour chaque client.</span><span class="sxs-lookup"><span data-stu-id="82438-108">Set up a parent project for each customer.</span></span>
- <span data-ttu-id="82438-109">Enregistrez les heures, les articles, les dépenses et les frais par rapport à l’ordre de travail, puis créez une proposition de facture pour le client ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="82438-109">Register hours, items, expenses, and fees against the work order, and then create an invoice proposal for the customer later.</span></span>

<span data-ttu-id="82438-110">En outre, la fonctionnalité offre les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="82438-110">In addition, the feature provides the following functionality:</span></span>

- <span data-ttu-id="82438-111">Le contrat de projet du projet parent d’un client est automatiquement copié dans le projet d’ordre de travail correspondant.</span><span class="sxs-lookup"><span data-stu-id="82438-111">The project contract from a customer's parent project is automatically copied to the relevant work order project.</span></span>
- <span data-ttu-id="82438-112">La gestion des actifs peut désormais utiliser la transaction de projet de type *frais* sur les prévisions des ordres de travail et les journaux des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="82438-112">Asset management can now use the *fee* project transaction type on both work order forecasts and work order journals.</span></span>

## <a name="turn-on-the-customer-billing-feature"></a><span data-ttu-id="82438-113">Activer la fonctionnalité Facturation client</span><span class="sxs-lookup"><span data-stu-id="82438-113">Turn on the customer billing feature</span></span>

<span data-ttu-id="82438-114">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="82438-114">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="82438-115">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="82438-115">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="82438-116">Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="82438-116">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="82438-117">**Module :** *Gestion et comptabilité des projets*</span><span class="sxs-lookup"><span data-stu-id="82438-117">**Module:** *Project management and accounting*</span></span>
- <span data-ttu-id="82438-118">**Nom de la fonctionnalité :** *Facturation des ordres de travail*</span><span class="sxs-lookup"><span data-stu-id="82438-118">**Feature name:** *Work order billing*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="82438-119">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="82438-119">Example scenario</span></span>

<span data-ttu-id="82438-120">Pour savoir comment cette fonctionnalité fonctionne, suivez l’exemple de scénario suivant.</span><span class="sxs-lookup"><span data-stu-id="82438-120">To learn how this feature works, work through the following example scenario.</span></span>

<span data-ttu-id="82438-121">Pour utiliser ce scénario à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées.</span><span class="sxs-lookup"><span data-stu-id="82438-121">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="82438-122">Vous devez sélectionner l’entité juridique **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="82438-122">You must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="82438-123">Vous pouvez également utiliser ce scénario comme orientation pour utiliser la fonctionnalité lorsque vous travaillez sur un système de production.</span><span class="sxs-lookup"><span data-stu-id="82438-123">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="82438-124">Cependant, dans ce cas, vous devez remplacer vos propres valeurs, et il se peut que certains types d’enregistrements requis que les données de démonstration standard fournissent manquent.</span><span class="sxs-lookup"><span data-stu-id="82438-124">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a><span data-ttu-id="82438-125">Étape 1 : Créer un contrat de projet pour le client</span><span class="sxs-lookup"><span data-stu-id="82438-125">Step 1: Create a new project contract for the customer</span></span>

1. <span data-ttu-id="82438-126">Accédez à **Gestion et comptabilité des projets \> Projets \> Contrats de projets**.</span><span class="sxs-lookup"><span data-stu-id="82438-126">Go to **Project management and accounting \> Projects \> Project contracts**.</span></span>
1. <span data-ttu-id="82438-127">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="82438-127">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="82438-128">Dans la boîte de dialogue **Nouveau contrat de projet**, sélectionnez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="82438-128">In the **New project contract** dialog box, set the following values:</span></span>

    - <span data-ttu-id="82438-129">**Nom :** *Pelican Wholesales*</span><span class="sxs-lookup"><span data-stu-id="82438-129">**Name:** *Pelican Wholesales*</span></span>
    - <span data-ttu-id="82438-130">**Type de financement :** *Client*</span><span class="sxs-lookup"><span data-stu-id="82438-130">**Funding type:** *Customer*</span></span>
    - <span data-ttu-id="82438-131">**Source de financement :** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="82438-131">**Funding source:** *US-013* (*Pelican Wholesales*)</span></span>

1. <span data-ttu-id="82438-132">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="82438-132">Select **OK**.</span></span>

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a><span data-ttu-id="82438-133">Étape 2 : Créer un projet parent pour le client</span><span class="sxs-lookup"><span data-stu-id="82438-133">Step 2: Create a new parent project for the customer</span></span>

<span data-ttu-id="82438-134">Le projet parent que vous créez ici sera utilisé lors de la création des ordres de travail pour le client.</span><span class="sxs-lookup"><span data-stu-id="82438-134">The parent project that you create here will be used when work orders for the customer are created.</span></span>

1. <span data-ttu-id="82438-135">Accédez à **Gestion et comptabilité des projets \> Projets \> Tous les projets**.</span><span class="sxs-lookup"><span data-stu-id="82438-135">Go to **Project management and accounting \> Projects \> All projects**.</span></span>
1. <span data-ttu-id="82438-136">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="82438-136">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="82438-137">Dans la boîte de dialogue **Nouveau projet**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="82438-137">In the **New project** dialog box, set the following values:</span></span>

    - <span data-ttu-id="82438-138">**Type de projet :** *Régie*</span><span class="sxs-lookup"><span data-stu-id="82438-138">**Project type:** *Time and material*</span></span>
    - <span data-ttu-id="82438-139">**Nom du projet :** *Ordres de travail Pelican Wholesales*</span><span class="sxs-lookup"><span data-stu-id="82438-139">**Project name:** *Pelican Wholesales work orders*</span></span>
    - <span data-ttu-id="82438-140">**Groupe de projets :** *TM*</span><span class="sxs-lookup"><span data-stu-id="82438-140">**Project group:** *TM*</span></span>
    - <span data-ttu-id="82438-141">**ID du contrat de projet :** *Pelican Wholesales* (le contrat que vous avez créé précédemment)</span><span class="sxs-lookup"><span data-stu-id="82438-141">**Project contract ID:** *Pelican Wholesales* (the contract that you created earlier)</span></span>
    - <span data-ttu-id="82438-142">**Date de début :** sélectionnez la date d’aujourd’hui.</span><span class="sxs-lookup"><span data-stu-id="82438-142">**Start date:** Select today's date.</span></span>

1. <span data-ttu-id="82438-143">Sélectionnez **Créer un projet**.</span><span class="sxs-lookup"><span data-stu-id="82438-143">Select **Create project**.</span></span>
1. <span data-ttu-id="82438-144">Le nouveau projet est ouvert.</span><span class="sxs-lookup"><span data-stu-id="82438-144">The new project is opened.</span></span> <span data-ttu-id="82438-145">Prenez note de la valeur **ID de projet**.</span><span class="sxs-lookup"><span data-stu-id="82438-145">Make a note of the **Project ID** value.</span></span> <span data-ttu-id="82438-146">Vous devrez le saisir plus tard.</span><span class="sxs-lookup"><span data-stu-id="82438-146">You will have to enter it later.</span></span>

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a><span data-ttu-id="82438-147">Étape 3 : Créer un nouveau type d’ordre de travail dans Gestion des actifs</span><span class="sxs-lookup"><span data-stu-id="82438-147">Step 3: Create a new work order type in Asset management</span></span>

1. <span data-ttu-id="82438-148">Accédez à **Gestion des actifs \> Paramétrage \> Ordre de travail \> Types d’ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="82438-148">Go to **Asset management \> Setup \> Work order \> Work order types**.</span></span>
1. <span data-ttu-id="82438-149">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="82438-149">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="82438-150">Un nouvel enregistrement est ajouté à la liste.</span><span class="sxs-lookup"><span data-stu-id="82438-150">A new record is added to the list.</span></span> <span data-ttu-id="82438-151">Définissez les valeurs suivantes pour cette ligne :</span><span class="sxs-lookup"><span data-stu-id="82438-151">Set the following values for it:</span></span>

    - <span data-ttu-id="82438-152">**Type d’ordre d’exécution :** *Service*</span><span class="sxs-lookup"><span data-stu-id="82438-152">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="82438-153">**Nom :** *Ordres de travail de service*</span><span class="sxs-lookup"><span data-stu-id="82438-153">**Name:** *Service work orders*</span></span>
    - <span data-ttu-id="82438-154">**État du cycle de vie de l’ordre de travail :** *Standard*</span><span class="sxs-lookup"><span data-stu-id="82438-154">**Work order lifecycle state:** *Standard*</span></span>

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a><span data-ttu-id="82438-155">Étape 4 : Associer le compte client au projet parent</span><span class="sxs-lookup"><span data-stu-id="82438-155">Step 4: Link the customer account to the parent project</span></span>

<span data-ttu-id="82438-156">Vous devez maintenant associer le compte client au projet parent dans la configuration du projet dans Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="82438-156">You must now link the customer account to the parent project in the project setup in Asset management.</span></span>

1. <span data-ttu-id="82438-157">Accédez à **Gestion des actifs \> Paramétrage \> Ordres de travail \> Paramétrage du projet**.</span><span class="sxs-lookup"><span data-stu-id="82438-157">Go to **Asset management \> Setup \> Work orders \> Project setup**.</span></span>
1. <span data-ttu-id="82438-158">Sous l’onglet **Projet parent**, sélectionnez **Ajouter** pour ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="82438-158">On the **Parent project** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="82438-159">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="82438-159">On the new line, set the following values:</span></span>

    - <span data-ttu-id="82438-160">**Compte client :** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="82438-160">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="82438-161">**ID de projet** : saisissez l’ID de projet que vous avez noté précédemment.</span><span class="sxs-lookup"><span data-stu-id="82438-161">**Project ID:** Enter the project ID that you made a note of earlier.</span></span>

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a><span data-ttu-id="82438-162">Étape 5 : Associer le groupe de projets et le type au projet d’ordre de travail</span><span class="sxs-lookup"><span data-stu-id="82438-162">Step 5: Link the project group and type to the work order project</span></span>

<span data-ttu-id="82438-163">Vous devriez toujours être sur la page **Configuration du projet** (**Gestion des actifs \> Configurer \> Ordres de travail \> Configuration du projet**).</span><span class="sxs-lookup"><span data-stu-id="82438-163">You should still be on the **Project setup** page (**Asset management \> Setup \> Work orders \> Project setup**).</span></span>

1. <span data-ttu-id="82438-164">Sous l’onglet **Groupe de projets**, sélectionnez **Ajouter** pour ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="82438-164">On the **Project group** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="82438-165">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="82438-165">On the new line, set the following values:</span></span>

    - <span data-ttu-id="82438-166">**Type d’ordre de travail :** *Service* (le type d’ordre de travail que vous avez créé précédemment)</span><span class="sxs-lookup"><span data-stu-id="82438-166">**Work order type:** *Service* (the work order type that you created earlier)</span></span>
    - <span data-ttu-id="82438-167">**Groupe de projets :** *TM*</span><span class="sxs-lookup"><span data-stu-id="82438-167">**Project group:** *TM*</span></span>

> [!NOTE]
> <span data-ttu-id="82438-168">Le contrat de projet sur le projet d’ordre de travail est toujours hérité du projet parent.</span><span class="sxs-lookup"><span data-stu-id="82438-168">The project contract on the work order project is always inherited from the parent project.</span></span>

### <a name="step-6-link-an-asset-to-the-customer-id"></a><span data-ttu-id="82438-169">Étape 6 : Associer un élément à l’identifiant client</span><span class="sxs-lookup"><span data-stu-id="82438-169">Step 6: Link an asset to the customer ID</span></span>

1. <span data-ttu-id="82438-170">Accédez à **Gestion des actifs \> Actifs \> Tous les Actifs (ou Actifs actifs)**.</span><span class="sxs-lookup"><span data-stu-id="82438-170">Go to **Asset management \> Assets \> Active assets**.</span></span>
1. <span data-ttu-id="82438-171">Dans le champ **Filtre**, entrez *VE-102*, et sélectionnez pour filtrer par **Actif**.</span><span class="sxs-lookup"><span data-stu-id="82438-171">In the **Filter** field, enter *VE-102*, and select to filter by **Asset**.</span></span>
1. <span data-ttu-id="82438-172">Sélectionnez l’actif pour ouvrir ses paramètres.</span><span class="sxs-lookup"><span data-stu-id="82438-172">Select the asset to open its settings.</span></span>
1. <span data-ttu-id="82438-173">Dans l’organisateur **Client**, définissez le champ **Compte client** sur *US-013* (*Pelican Wholesales*).</span><span class="sxs-lookup"><span data-stu-id="82438-173">On the **Customer** FastTab, set the **Customer account** field to *US-013* (*Pelican Wholesales*).</span></span>

    <span data-ttu-id="82438-174">Le champ **Nom** est automatiquement mis à jour pour *Pelican Wholesales*.</span><span class="sxs-lookup"><span data-stu-id="82438-174">The **Name** field is automatically updated to *Pelican Wholesales*.</span></span>

### <a name="step-7-create-a-new-work-order-on-the-asset"></a><span data-ttu-id="82438-175">Étape 7 : Créer un nouveau type d’ordre de travail sur l’actif</span><span class="sxs-lookup"><span data-stu-id="82438-175">Step 7: Create a new work order on the asset</span></span>

1. <span data-ttu-id="82438-176">Accédez à **Gestion des actifs \> Ordres de travail \> Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="82438-176">Go to **Asset management \> Work orders \> Active work orders**.</span></span>
1. <span data-ttu-id="82438-177">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="82438-177">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="82438-178">Dans la boîte de dialogue **Créer un ordre de travail**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="82438-178">In the **Create work order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="82438-179">**Type d’ordre d’exécution :** *Service*</span><span class="sxs-lookup"><span data-stu-id="82438-179">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="82438-180">**Description :** *Camion de réparation*</span><span class="sxs-lookup"><span data-stu-id="82438-180">**Description:** *Repair Truck*</span></span>
    - <span data-ttu-id="82438-181">**Compte client :** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="82438-181">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="82438-182">**Actif :** *VE-102*</span><span class="sxs-lookup"><span data-stu-id="82438-182">**Asset:** *VE-102*</span></span>

        > [!NOTE]
        > <span data-ttu-id="82438-183">La recherche n’affiche que les actifs liés au compte client sélectionné.</span><span class="sxs-lookup"><span data-stu-id="82438-183">The lookup shows only assets that are linked to the selected customer account.</span></span>

    - <span data-ttu-id="82438-184">**Type de tâche de maintenance :** *Réparation*</span><span class="sxs-lookup"><span data-stu-id="82438-184">**Maintenance job type:** *Repair*</span></span>
    - <span data-ttu-id="82438-185">**Commerce :** *Mécanique*</span><span class="sxs-lookup"><span data-stu-id="82438-185">**Trade:** *Mechanic*</span></span>
    - <span data-ttu-id="82438-186">**Niveau de service :** *4*</span><span class="sxs-lookup"><span data-stu-id="82438-186">**Service level:** *4*</span></span>

1. <span data-ttu-id="82438-187">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="82438-187">Select **OK**.</span></span>

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a><span data-ttu-id="82438-188">Étape 8 : Passer en revue l’ordre de travail et commencer à l’utiliser</span><span class="sxs-lookup"><span data-stu-id="82438-188">Step 8: Review the work order and start to work on it</span></span>

<span data-ttu-id="82438-189">Dans cette section, vous allez travailler sur l’ordre de travail que vous avez créé dans la section précédente.</span><span class="sxs-lookup"><span data-stu-id="82438-189">In this section, you will work on the work order that you created in the previous section.</span></span>

1. <span data-ttu-id="82438-190">Suivez ces étapes pour vérifier que le projet parent est le projet *Ordre de travail Pelican Wholesales* :</span><span class="sxs-lookup"><span data-stu-id="82438-190">Follow these steps to verify that the parent project is the *Pelican wholesales Work order* project:</span></span>

    1. <span data-ttu-id="82438-191">Dans la section **Tâches de maintenance des ordres de travail**, sélectionnez une ligne.</span><span class="sxs-lookup"><span data-stu-id="82438-191">In the **Work order maintenance jobs** section, select a line.</span></span>
    1. <span data-ttu-id="82438-192">Sur l’organisateur **Détails de la ligne**, inspectez la valeur **ID de projet**.</span><span class="sxs-lookup"><span data-stu-id="82438-192">On the **Line details** FastTab, inspect the **Project ID** value.</span></span> <span data-ttu-id="82438-193">Il doit s’agir d’un nombre avec trait d’union sous la forme *\<Parent-Project-ID\>-\<Project-ID\>*.</span><span class="sxs-lookup"><span data-stu-id="82438-193">It should be a hyphenated number in the form *\<Parent-Project-ID\>-\<Project-ID\>*.</span></span> <span data-ttu-id="82438-194">Cette valeur est un lien.</span><span class="sxs-lookup"><span data-stu-id="82438-194">This value is a link.</span></span>
    1. <span data-ttu-id="82438-195">Sélectionnez le lien de l’ID de projet pour ouvrir une page dans laquelle vous pouvez afficher le projet parent et les noms de projet.</span><span class="sxs-lookup"><span data-stu-id="82438-195">Select the project ID link to open a page where you can view the parent project and project names.</span></span>

1. <span data-ttu-id="82438-196">Dans le volet Actions, sous l’onglet **Ordre de travail**, dans le groupe **État du cycle de vie**, sélectionnez **Mettre à jour l’état de l’ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="82438-196">On the Action Pane, on the **Work order** tab, in the **Lifecycle state** group, select **Update work order state**.</span></span>
1. <span data-ttu-id="82438-197">Dans la boîte de dialogue **Mettre à jour l’état de l’ordre de travail**, dans la colonne **Sélectionner**, cochez la case de la ligne où le champ **État du cycle de vie** est défini sur *En cours*.</span><span class="sxs-lookup"><span data-stu-id="82438-197">In the **Update work order state** dialog box, in the **Select** column, select the check box for the row where the **Lifecycle state** field is set to *In progress*.</span></span>
1. <span data-ttu-id="82438-198">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="82438-198">Select **OK**.</span></span>
1. <span data-ttu-id="82438-199">Dans la boîte de dialogue **État du cycle de vie : en cours**, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="82438-199">In the **Lifecycle state: InProgress** dialog box, select **OK**.</span></span>

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a><span data-ttu-id="82438-200">Étape 9 : Publier les heures passées sur l’ordre de travail et créer une proposition de facture</span><span class="sxs-lookup"><span data-stu-id="82438-200">Step 9: Post the hours that were spent on the work order and create a new invoice proposal</span></span>

<span data-ttu-id="82438-201">Dans cette section, vous continuerez à travailler sur l’ordre de travail sur lequel vous avez travaillé dans la section précédente.</span><span class="sxs-lookup"><span data-stu-id="82438-201">In this section, you will continue to work on the work order that you worked on in the previous section.</span></span>

1. <span data-ttu-id="82438-202">Dans le volet Actions, sous l’onglet **Ordre de travail**, dans le groupe **Projet**, sélectionnez **Journaux**.</span><span class="sxs-lookup"><span data-stu-id="82438-202">On the Action Pane, on the **Work order** tab, in the **Project** group, select **Journals**.</span></span>

    <span data-ttu-id="82438-203">La page **Journaux des ordres de travail** apparaît.</span><span class="sxs-lookup"><span data-stu-id="82438-203">The **Work order journals** page appears.</span></span> <span data-ttu-id="82438-204">Ici, vous pouvez enregistrer le temps que vous avez passé sur l’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="82438-204">Here, you can register the time that you spent on the work order.</span></span>

1. <span data-ttu-id="82438-205">Dans l’organisateur **Heures**, sélectionnez **Ajouter une ligne**.</span><span class="sxs-lookup"><span data-stu-id="82438-205">On the **Hours** FastTab, select **Add line**.</span></span>
1. <span data-ttu-id="82438-206">Sur la nouvelle ligne, définissez le champ **Heures** sur *4*.</span><span class="sxs-lookup"><span data-stu-id="82438-206">On the new, line, set the **Hours** field to *4*.</span></span>
1. <span data-ttu-id="82438-207">Dans le volet Actions, sélectionnez **Publier les journaux**.</span><span class="sxs-lookup"><span data-stu-id="82438-207">On the Action Pane, select **Post journals**.</span></span>
1. <span data-ttu-id="82438-208">Fermez la page **Journaux des ordres de travail** pour revenir à l’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="82438-208">Close the **Work order journals** page to return to the work order.</span></span>
1. <span data-ttu-id="82438-209">Dans le volet Actions, sous l’onglet **Facturation**, sélectionnez **Nouvelle proposition de facture**.</span><span class="sxs-lookup"><span data-stu-id="82438-209">On the Action Pane, on the **Invoicing** tab, select **New invoice proposal**.</span></span>
1. <span data-ttu-id="82438-210">Dans la boîte de dialogue **Créer une proposition de facture**, dans la section **Transactions de projet**, cochez la case **Sélectionner** pour chaque ligne que vous souhaitez facturer.</span><span class="sxs-lookup"><span data-stu-id="82438-210">In the **Create invoice proposal** dialog box, in the **Project transactions** section, select the **Select** check box for every line  that you want to invoice.</span></span>
1. <span data-ttu-id="82438-211">Sélectionnez **OK** pour fermer la boîte de dialogue et afficher la nouvelle proposition de facture.</span><span class="sxs-lookup"><span data-stu-id="82438-211">Select **OK** to close the dialog box and view the new invoice proposal.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]