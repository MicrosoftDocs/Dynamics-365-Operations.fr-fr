---
title: Définir et tenir à jour les canaux de vente au détail
description: Cette rubrique fournit une vue d'ensemble du processus de paramétrage des magasins traditionnels, qui sont appelés des magasins de vente au détail dans Dynamics 365 Retail. Il inclut des informations sur les tâches que vous devez effectuer avant et après avoir paramétré un magasin de vente au détail.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 45d0386d215da15103a417502debb245c91f6309
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934606"
---
# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="28968-104">Définir et tenir à jour les canaux de vente au détail</span><span class="sxs-lookup"><span data-stu-id="28968-104">Define and maintain retail channels</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="28968-105">Cette rubrique fournit une vue d'ensemble du processus de paramétrage des magasins traditionnels, qui sont appelés des magasins de vente au détail dans Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="28968-105">This topic provides an overview of the process for setting up brick-and-mortar stores, which are referred to as retail stores in Dynamics 365 Retail.</span></span> <span data-ttu-id="28968-106">Il inclut des informations sur les tâches que vous devez effectuer avant et après avoir paramétré un magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="28968-106">It includes information about the tasks that you must complete both before and after you set up a retail store.</span></span>

<span data-ttu-id="28968-107">Retail prend en charge plusieurs canaux de vente au détail, tels que les magasins en ligne, les centres d'appels et les magasins traditionnels.</span><span class="sxs-lookup"><span data-stu-id="28968-107">Retail supports multiple retail channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="28968-108">Les magasins physiques sont également appelés magasins de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="28968-108">A brick-and-mortar store is called a retail store.</span></span> <span data-ttu-id="28968-109">Chaque magasin de vente au détail peut proposer son propre mode de paiement, ses propres groupes de prix, ses propres caisses enregistreuses de PDV, ses propres comptes de revenus et de dépenses et son propre personnel.</span><span class="sxs-lookup"><span data-stu-id="28968-109">Each retail store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="28968-110">Vous devez définir tous ces éléments pour un magasin de vente au détail avant de le créer.</span><span class="sxs-lookup"><span data-stu-id="28968-110">You must set up all these elements for a retail store before you create it.</span></span> <span data-ttu-id="28968-111">Une fois le magasin de vente au détail créé, vous affectez les produits dont vous souhaitez la présence dans ce magasin.</span><span class="sxs-lookup"><span data-stu-id="28968-111">After you create the retail store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="28968-112">Vous affectez également des employés, des caisses enregistreuses et des clients au magasin.</span><span class="sxs-lookup"><span data-stu-id="28968-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="28968-113">Enfin, vous ajoutez le nouveau magasin à une hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="28968-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-retail-stores"></a><span data-ttu-id="28968-114">Paramétrage des magasins de vente au détail</span><span class="sxs-lookup"><span data-stu-id="28968-114">Setting up retail stores</span></span>

<span data-ttu-id="28968-115">Avant de paramétrer un magasin de vente au détail dans Retail, vous devez exécuter certaines tâches préalables.</span><span class="sxs-lookup"><span data-stu-id="28968-115">Before you can set up a retail store in Retail, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="28968-116">Vous pouvez ensuite créer le magasin de vente au détail et ajouter des informations.</span><span class="sxs-lookup"><span data-stu-id="28968-116">You can then create the retail store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="28968-117">Logiciels requis</span><span class="sxs-lookup"><span data-stu-id="28968-117">Prerequisites</span></span>

<span data-ttu-id="28968-118">Vous devez exécuter certaines tâches préalables avant de paramétrer un magasin de vente au détail :</span><span class="sxs-lookup"><span data-stu-id="28968-118">You must complete the following tasks before you can set up a retail store:</span></span>

1. <span data-ttu-id="28968-119">configurez votre structure d'organisation et paramétrez des hiérarchies d'organisation pour les assortiments de vente au détail, le réapprovisionnement et la génération d'états.</span><span class="sxs-lookup"><span data-stu-id="28968-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2. <span data-ttu-id="28968-120">paramétrez un entrepôt qui représente le magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="28968-120">Set up a warehouse that represents the retail store.</span></span>
3. <span data-ttu-id="28968-121">Paramétrez des souches de numéros pour les magasins de vente au détail, les relevés bancaires, et documents de relevé.</span><span class="sxs-lookup"><span data-stu-id="28968-121">Set up number sequences for retail stores, store statements, and statement vouchers.</span></span>
4. <span data-ttu-id="28968-122">configurez les paramètres de Retail.</span><span class="sxs-lookup"><span data-stu-id="28968-122">Configure parameters for Retail.</span></span>
5. <span data-ttu-id="28968-123">Paramétrez les modes de paiement acceptés par le magasin.</span><span class="sxs-lookup"><span data-stu-id="28968-123">Set up the methods of payment that the store accepts.</span></span>
6. <span data-ttu-id="28968-124">Pour traiter les transactions de carte de crédit sur les caisses enregistreuses de point de vente (PDV) au détail, vous pouvez également paramétrer des services de paiement.</span><span class="sxs-lookup"><span data-stu-id="28968-124">To process credit card transactions at retail POS registers, you can also set up payment services.</span></span>
7. <span data-ttu-id="28968-125">Paramétrez les groupes de taxes.</span><span class="sxs-lookup"><span data-stu-id="28968-125">Set up sales tax groups.</span></span>
8. <span data-ttu-id="28968-126">Paramétrez les produits vendus au détail.</span><span class="sxs-lookup"><span data-stu-id="28968-126">Set up retail products.</span></span> <span data-ttu-id="28968-127">Dans le cadre de cette tâche, vous paramétrez également des hiérarchies des produits vendus au détail, des variantes de produit et des assortiments de produits.</span><span class="sxs-lookup"><span data-stu-id="28968-127">As part of this task, you also set up retail product hierarchies, product variants, and product assortments.</span></span>
9. <span data-ttu-id="28968-128">Configurez les groupes de prix de produits.</span><span class="sxs-lookup"><span data-stu-id="28968-128">Set up product price groups.</span></span>
10. <span data-ttu-id="28968-129">Définissez la tarification des produits vendus au détail.</span><span class="sxs-lookup"><span data-stu-id="28968-129">Set up retail product pricing.</span></span> <span data-ttu-id="28968-130">Dans le cadre de cette tâche, vous paramétrez également des ajustements de prix, des remises et des périodes de remise.</span><span class="sxs-lookup"><span data-stu-id="28968-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="28968-131">Paramétrez les membres du personnel.</span><span class="sxs-lookup"><span data-stu-id="28968-131">Set up staff members.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28968-132">Vous devez également attribuer des autorisations appropriées aux collaborateurs pour qu'ils puissent se connecter et effectuer des tâches pour le système Retail POS.</span><span class="sxs-lookup"><span data-stu-id="28968-132">You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the Retail POS system.</span></span>

12. <span data-ttu-id="28968-133">Configurez les profils Retail POS à affecter au magasin.</span><span class="sxs-lookup"><span data-stu-id="28968-133">Configure the Retail POS profiles to assign to the store.</span></span> <span data-ttu-id="28968-134">Cette tâche inclut plusieurs autres tâches, comme le paramétrage des registres, le paramétrage des profils hors ligne, et le paramétrage des formats de réception et les profils.</span><span class="sxs-lookup"><span data-stu-id="28968-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="28968-135">Examinez toutes les tâches incluses dans les conditions préalables et n'effectuez que celles qui vous concernent.</span><span class="sxs-lookup"><span data-stu-id="28968-135">Review all the tasks that are included in the prerequisite, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-retail-store"></a><span data-ttu-id="28968-136">Paramétrage d'un magasin de vente au détail</span><span class="sxs-lookup"><span data-stu-id="28968-136">Set up a retail store</span></span>

<span data-ttu-id="28968-137">Après avoir réalisé les tâches nécessaires, effectuez ces tâches pour paramétrer les détails du magasin de vente au détail :</span><span class="sxs-lookup"><span data-stu-id="28968-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the retail store:</span></span>

1. <span data-ttu-id="28968-138">Créez un magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="28968-138">Create a retail store.</span></span>
2. <span data-ttu-id="28968-139">Affectez un groupe de taxe au magasin.</span><span class="sxs-lookup"><span data-stu-id="28968-139">Assign a sales tax group to the store.</span></span>
3. <span data-ttu-id="28968-140">Affectez les modes de paiement acceptés au magasin.</span><span class="sxs-lookup"><span data-stu-id="28968-140">Assign the accepted payment methods to the store.</span></span>
4. <span data-ttu-id="28968-141">Ajoutez des détails aux descriptions des produits que vous proposez dans vos magasins de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="28968-141">Add details to the product descriptions for products that you offer in your retail stores.</span></span> <span data-ttu-id="28968-142">Par exemple, vous pouvez ajouter du texte enrichi et des images.</span><span class="sxs-lookup"><span data-stu-id="28968-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="28968-143">Ces détails des produits apparaissent dans divers contextes, par exemple dans la caisse enregistreuse du PDV ou sur les étiquettes imprimées.</span><span class="sxs-lookup"><span data-stu-id="28968-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5. <span data-ttu-id="28968-144">Ajoutez le magasin à la hiérarchie d'organisation par défaut affectée à un objectif **Assortiment de vente au détail**, **Réassort de la vente au détail**, ou **Génération d'états sur les ventes au détail**.</span><span class="sxs-lookup"><span data-stu-id="28968-144">Add the store to the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-retail-store"></a><span data-ttu-id="28968-145">Après le paramétrage d'un magasin de vente au détail</span><span class="sxs-lookup"><span data-stu-id="28968-145">After you set up a retail store</span></span>

<span data-ttu-id="28968-146">Une fois les détails du magasin de vente au détail, entreprenez ces tâches pour envoyer les données du nouveau magasin de vente au détail à Retail POS :</span><span class="sxs-lookup"><span data-stu-id="28968-146">After you enter the details for the retail store, complete these tasks to send the new retail store data to Retail POS:</span></span>

1. <span data-ttu-id="28968-147">Configurez les caisses enregistreuses des points de vente (PDV) pour le magasin.</span><span class="sxs-lookup"><span data-stu-id="28968-147">Configure the POS registers for the store.</span></span>
2. <span data-ttu-id="28968-148">Affectez des assortiments de produits au magasin.</span><span class="sxs-lookup"><span data-stu-id="28968-148">Assign product assortments to the store.</span></span>
3. <span data-ttu-id="28968-149">Traitez les assortiments pour générer la liste des produits inclus dans l'assortiment et pour rendre les produits disponibles dans le magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="28968-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store.</span></span>
4. <span data-ttu-id="28968-150">Envoyez les données telles que les souches de numéros, les profils matériel et les mises en page d'écran de PDV aux caisses enregistreuses .</span><span class="sxs-lookup"><span data-stu-id="28968-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.</span></span>
5. <span data-ttu-id="28968-151">Publiez le magasin de vente au détail pour envoyer les données du magasin à Retail POS.</span><span class="sxs-lookup"><span data-stu-id="28968-151">Publish the retail store to send store data to Retail POS.</span></span>
6. <span data-ttu-id="28968-152">Exécutez les tâches pour envoyer les données à Retail POS.</span><span class="sxs-lookup"><span data-stu-id="28968-152">Run the jobs to send the store data to Retail POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="28968-153">Hiérarchies de l'organisation</span><span class="sxs-lookup"><span data-stu-id="28968-153">Organization hierarchies</span></span>

<span data-ttu-id="28968-154">Retail utilise des hiérarchies d'organisation pour structurer les canaux de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="28968-154">Retail uses organization hierarchies to structure retail channels.</span></span> <span data-ttu-id="28968-155">Les hiérarchies d'organisation représentent les relations entre les organisations qui composent votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="28968-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="28968-156">Lorsque vous paramétrez des magasins, vous pouvez les ajouter à une hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="28968-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="28968-157">Les magasins partagent ensuite les données utilisées pour les assortiments, le réapprovisionnement et la génération d'états.</span><span class="sxs-lookup"><span data-stu-id="28968-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>

> [!NOTE]
> <span data-ttu-id="28968-158">Pour utiliser la fonctionnalité de ventes au détail, la clé de configuration de **Expédition multiple** doit être activé.</span><span class="sxs-lookup"><span data-stu-id="28968-158">To use Retail sales functionality, the configuration key for **Multiple ship-to** must be enabled.</span></span> <span data-ttu-id="28968-159">Cette clé de configuration se trouve dans les clés **Configuration Commerce** sous **Administration du système**\> **Configurer** \> **Configuration de licence**.</span><span class="sxs-lookup"><span data-stu-id="28968-159">This configuration key can be found in the **Trade configuration** keys under **System Administration**\> **Setup** \> **License Configuration**.</span></span> <span data-ttu-id="28968-160">Cela est nécessaire en raison de la fonctionnalité de ventes au détail qui effectue diverses validations en fonction de l'adresse de livraison configurée au niveau de la ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="28968-160">This is required due to Retail functionality that performs various validations based on the delivery address configured at the sales order line level.</span></span>
