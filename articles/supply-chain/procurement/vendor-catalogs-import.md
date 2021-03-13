---
title: Importer les catalogues fournisseur
description: Cette rubrique décrit le processus pour importer les données du catalogue fournisseur.
author: RichardLuan
manager: tfehr
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests, CatVendorCatalogDetails, CatVendorCatalogReleaseApprovedProducts, CatVendorCMRDetails, CatVendorCatalogProductPerCompanyStatus, CatVendorMaintenanceEventLog, CatVendorCatalogReviewTool, CatVendorCatalogFileUpload, CatVendorCatalogMaintenanceRequest, CatVendorCatalogFileInLegalEntity, CatVendorCatalogSchema, CatVendorCatalogFilePreviewPane, CatVendorCatalogImportParameter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: riluan
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 6a6fc2b4fe4245a1fe5b5a7eaafe8cc7fd337ab9
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020752"
---
# <a name="import-vendor-catalogs"></a><span data-ttu-id="44299-103">Importer les catalogues fournisseur</span><span class="sxs-lookup"><span data-stu-id="44299-103">Import vendor catalogs</span></span>

[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a><span data-ttu-id="44299-104">Importation des catalogues fournisseur</span><span class="sxs-lookup"><span data-stu-id="44299-104">Vendor catalogs import</span></span>

<span data-ttu-id="44299-105">Dans Dynamics 365 Supply Chain Management, les acheteurs peuvent créer et mettre à jour des catalogues que les employés de la société peuvent utiliser lorsqu'ils commandent des articles et des services pour un usage interne.</span><span class="sxs-lookup"><span data-stu-id="44299-105">In Dynamics 365 Supply Chain Management, purchasing professionals can create and maintain catalogs for company employees to use when they order items and services for internal use.</span></span> <span data-ttu-id="44299-106">Pour créer un catalogue d'approvisionnement, vous pouvez ajouter les articles et les services que vous voulez rendre disponibles pour les employés, soit en important les données du catalogue de produits, soit en ajoutant les données de catalogue de produits dans le produit générique manuellement.</span><span class="sxs-lookup"><span data-stu-id="44299-106">To create a procurement catalog, you can add the items and services that you want to make available to employees, either by importing the product catalog data or by manually adding the product catalog data to the product master.</span></span> 

<span data-ttu-id="44299-107">Vous pouvez charger les données de catalogue envoyées par un fournisseur depuis le client Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="44299-107">You can upload catalog data submitted by a vendor from the Microsoft Dynamics 365 client.</span></span>

<span data-ttu-id="44299-108">Les données du produit envoyées par un fournisseur sous forme de fichier DMC (demande de mise à jour de catalogue) doivent être au format XML.</span><span class="sxs-lookup"><span data-stu-id="44299-108">The product data that a vendor submits to you, in the form of a catalog maintenance request (CMR) file, must be in XML file format.</span></span> <span data-ttu-id="44299-109">Le fichier DMC doit contenir les détails des produits que le fournisseur propose à votre société.</span><span class="sxs-lookup"><span data-stu-id="44299-109">The CMR file should contain the details for the products that the vendor supplies to your company.</span></span>

## <a name="import-vendor-catalog-data"></a><span data-ttu-id="44299-110">Importer les données de catalogue fournisseur</span><span class="sxs-lookup"><span data-stu-id="44299-110">Import vendor catalog data</span></span>

<span data-ttu-id="44299-111">Pour importer les données d'un catalogue fournisseur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="44299-111">To import vendor catalog data, you must complete the following tasks:</span></span>

1. <span data-ttu-id="44299-112">Paramétrez un projet dans l'espace de travail Gestion des données dans lequel vous avez défini les règles de mise en correspondance des données.</span><span class="sxs-lookup"><span data-stu-id="44299-112">Set up a project in the Data management workspace where you have defined your data mapping rules.</span></span> <span data-ttu-id="44299-113">Sélectionnez **Gestion des données** puis **Définir les rôles des projets de données**.</span><span class="sxs-lookup"><span data-stu-id="44299-113">Select **Data management** and then select **Set up roles for data projects**.</span></span>

2. <span data-ttu-id="44299-114">Paramétrez une hiérarchie des catégories d'approvisionnement, puis affectez vos fournisseurs aux catégories d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="44299-114">Set up a procurement category hierarchy, and assign your vendors to procurement categories.</span></span> <span data-ttu-id="44299-115">Si vous utilisez des codes marchandise, ajoutez-les aux catégories d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="44299-115">If you use commodity codes, add the commodity codes to the procurement categories.</span></span> <span data-ttu-id="44299-116">Pour plus d'informations sur le paramétrage d'une hiérarchie des catégories d'approvisionnement, voir [Paramétrer une hiérarchie des catégories d'approvisionnement](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="44299-116">For information about setting up a procurement category hierarchy, see [Set up a procurement category hierarchy](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span></span>

3. <span data-ttu-id="44299-117">Configurez le fournisseur pour l'importation du catalogue.</span><span class="sxs-lookup"><span data-stu-id="44299-117">Configure the vendor for catalog import.</span></span> <span data-ttu-id="44299-118">Sélectionnez un fournisseur, puis **Approvisionnement** > **Paramétrage** > **Configurer le fournisseur pour l'importation de catalogues**.</span><span class="sxs-lookup"><span data-stu-id="44299-118">Select a vendor, and then select **Procurement** > **Set up** > **Configure vendor for catalog import**.</span></span>

4. <span data-ttu-id="44299-119">Configurez le workflow pour l'importation du catalogue.</span><span class="sxs-lookup"><span data-stu-id="44299-119">Configure workflow for catalog import.</span></span> <span data-ttu-id="44299-120">Créez un modèle de fichier DMC et partagez-le avec votre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="44299-120">Create a CMR file template and share this with your vendor.</span></span>

5. <span data-ttu-id="44299-121">Sélectionnez **Approvisionnements** \> **Commun** \> **Catalogues** \> **Catalogues fournisseur** pour créer un catalogue fournisseur.</span><span class="sxs-lookup"><span data-stu-id="44299-121">Select **Procurement and sourcing** \> **Common** \> **Catalogs** \> **Vendor catalogs** to create a vendor catalog.</span></span> <span data-ttu-id="44299-122">Les fichiers DMC envoyés par le fournisseur sont regroupés dans ce catalogue.</span><span class="sxs-lookup"><span data-stu-id="44299-122">The catalog maintenance request (CMR) files that you receive from your vendor are grouped in this catalog.</span></span> 

6. <span data-ttu-id="44299-123">Téléchargez le fichier DMC.</span><span class="sxs-lookup"><span data-stu-id="44299-123">Upload the CMR file.</span></span>

7. <span data-ttu-id="44299-124">Révisez, approuvez ou rejetez les produits du catalogue fournisseur.</span><span class="sxs-lookup"><span data-stu-id="44299-124">Review, approve, or reject the products in the vendor catalog.</span></span> <span data-ttu-id="44299-125">Les produits sont automatiquement mis en correspondance avec les catégories d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="44299-125">The products are automatically mapped to the procurement categories.</span></span> 

<span data-ttu-id="44299-126">Les produits approuvés sont ajoutés au produit générique et sont lancés dans les entités juridiques sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="44299-126">Approved products are added to the product master and are released to the selected legal entities.</span></span> <span data-ttu-id="44299-127">Seuls les produits approuvés peuvent être ajoutés au catalogue d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="44299-127">Only approved products can be added to the procurement catalog.</span></span>

## <a name="generate-a-catalog-import-file-template"></a><span data-ttu-id="44299-128">Génération d'un modèle de fichier d'importation de catalogue</span><span class="sxs-lookup"><span data-stu-id="44299-128">Generate a catalog import file template</span></span>

<span data-ttu-id="44299-129">Le modèle de fichier d'importation de catalogue est un fichier XSD que vous pouvez utiliser pour créer un fichier DMC pour les produits d'un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="44299-129">The catalog import file template is an XSD file that you use to create a CMR file for a vendor's products.</span></span> <span data-ttu-id="44299-130">Le fichier DMC que vous créez permet de créer, de remplacer ou de modifier un catalogue.</span><span class="sxs-lookup"><span data-stu-id="44299-130">You can use the CMR file to create a new catalog, replace an existing catalog, or modify an existing catalog.</span></span>

1. <span data-ttu-id="44299-131">Sélectionnez **Approvisionnements** \> **Catalogues** \> **Catalogues fournisseur** et double-cliquez sur le catalogue à utiliser.</span><span class="sxs-lookup"><span data-stu-id="44299-131">Select **Procurement and sourcing** \> **Catalogs** \> **Vendor  catalogs** and double-click the catalog that you want  to work with.</span></span>

2. <span data-ttu-id="44299-132">Téléchargez un modèle d'importation de catalogue actif (fichier XSD).</span><span class="sxs-lookup"><span data-stu-id="44299-132">Download a current catalog import template (XSD file).</span></span> <span data-ttu-id="44299-133">Sur la page **Mettre à jour le catalogue**, dans le **Volet Actions**, sous l'onglet **Catalogues**, dans le groupe **Informations associées**, cliquez sur **Générer un modèle de catalogue** et sélectionnez **Catégorie d'approvisionnement**.</span><span class="sxs-lookup"><span data-stu-id="44299-133">On the **Update catalog** page, on the **Action Pane**, on the **Catalogs** tab, in the **Related information** group, click **Generate catalog template** and select **Procurement category**.</span></span>

    - <span data-ttu-id="44299-134">Avec l'option **Catégorie d'approvisionnement**, vous pouvez générer un modèle de catalogue incluant les catégories d'approvisionnement dans lesquelles le fournisseur est autorisé à livrer des produits.</span><span class="sxs-lookup"><span data-stu-id="44299-134">With the **Procurement category** option you can generate a catalog template that includes the procurement categories in which the vendor is authorized to provide products.</span></span>

3. <span data-ttu-id="44299-135">Dans la boîte de dialogue **Enregistrer sous**, sélectionnez l'emplacement de stockage du modèle de fichier de catalogue et enregistrez le fichier.</span><span class="sxs-lookup"><span data-stu-id="44299-135">In the **Save as** dialog box, select the location where you want to store the catalog file template and save the file.</span></span>

<span data-ttu-id="44299-136">Pour plus d'informations et pour obtenir des exemples, consultez ce billet de blog : [Catalogues fournisseur dans Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span><span class="sxs-lookup"><span data-stu-id="44299-136">For more information and for examples, refer to this blog post: [Vendor catalogs in Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span></span>
