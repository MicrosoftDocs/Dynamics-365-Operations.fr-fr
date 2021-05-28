---
title: Configurer un environnement pour la recherche de données principales
description: Cette rubrique explique comment configurer votre environnement pour utiliser la fonctionnalité de recherche de données principales pour le calcul des taxes.
author: kai-cloud
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e4aa941c57e8c31793d6db8ae87140cd1bb1a82b
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021342"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="fb7fb-103">Configurer un environnement pour la recherche de données principales</span><span class="sxs-lookup"><span data-stu-id="fb7fb-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb7fb-104">Cette rubrique explique comment configurer votre environnement pour utiliser la fonctionnalité de recherche de données principales pour le calcul des taxes.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="fb7fb-105">Configurez l'intégration de Power Platform dans Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="fb7fb-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="fb7fb-106">Pour plus d’informations, voir la rubrique [Intégration de Microsoft Power Platform - Vue d'ensemble des compléments](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fb7fb-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="fb7fb-107">Configurez Dynamics 365 Finance et Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="fb7fb-108">Pour plus d'informations, consultez [Obtenir la solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) et [Authentification et autorisation](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="fb7fb-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="fb7fb-109">Vous devez paramétrer les entités suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb7fb-109">Set up the following entities.</span></span> <span data-ttu-id="fb7fb-110">Pour plus d’informations, consultez [Activation des entités virtuelles](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="fb7fb-110">For more information, see [Enabling virtual entities](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span></span>
      - <span data-ttu-id="fb7fb-111">CompanyInfoEntity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-111">CompanyInfoEntity</span></span>
      - <span data-ttu-id="fb7fb-112">CurrencyEntity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-112">CurrencyEntity</span></span>
      - <span data-ttu-id="fb7fb-113">CustCustomerV3Entity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-113">CustCustomerV3Entity</span></span>
      - <span data-ttu-id="fb7fb-114">DeliveryTermsEntity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-114">DeliveryTermsEntity</span></span>
      - <span data-ttu-id="fb7fb-115">EcoResProductCategoryEntity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-115">EcoResProductCategoryEntity</span></span>
      - <span data-ttu-id="fb7fb-116">EcoResReleasedProductV2Entity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-116">EcoResReleasedProductV2Entity</span></span>
      - <span data-ttu-id="fb7fb-117">LogisticsAddressCityEntity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-117">LogisticsAddressCityEntity</span></span>
      - <span data-ttu-id="fb7fb-118">LogisticsAddressCountryRegionTranslationEntity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-118">LogisticsAddressCountryRegionTranslationEntity</span></span>
      - <span data-ttu-id="fb7fb-119">LogisticsAddressStateEntity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-119">LogisticsAddressStateEntity</span></span>
      - <span data-ttu-id="fb7fb-120">PurchProcurementChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-120">PurchProcurementChargeCDSEntity</span></span>
      - <span data-ttu-id="fb7fb-121">SalesChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-121">SalesChargeCDSEntity</span></span>
      - <span data-ttu-id="fb7fb-122">TaxGroupEntity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-122">TaxGroupEntity</span></span>
      - <span data-ttu-id="fb7fb-123">TaxItemGroupHeadingEntity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-123">TaxItemGroupHeadingEntity</span></span>
      - <span data-ttu-id="fb7fb-124">VendVendorV2Entity</span><span class="sxs-lookup"><span data-stu-id="fb7fb-124">VendVendorV2Entity</span></span>
4. <span data-ttu-id="fb7fb-125">Configurez Dynamics 365 Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="fb7fb-125">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="fb7fb-126">Créez une demande de service pour que Microsoft active la distribution de version d’évaluation des fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb7fb-126">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="fb7fb-127">ERCdsFeature</span><span class="sxs-lookup"><span data-stu-id="fb7fb-127">ERCdsFeature</span></span>
      - <span data-ttu-id="fb7fb-128">TaxServiceCDSFeature</span><span class="sxs-lookup"><span data-stu-id="fb7fb-128">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="fb7fb-129">Accédez à l’espace de travail **Gestion des fonctionnalités**, puis activez les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb7fb-129">Go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="fb7fb-130">(Version préliminaire) Prise en charge des sources de données de la gestion des états électroniques Dataverse</span><span class="sxs-lookup"><span data-stu-id="fb7fb-130">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="fb7fb-131">(Version préliminaire) Prise en charge des sources de données Dataverse du service fiscal</span><span class="sxs-lookup"><span data-stu-id="fb7fb-131">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="fb7fb-132">(Version préliminaire) Fonctionnalités de globalisation</span><span class="sxs-lookup"><span data-stu-id="fb7fb-132">(Preview) Globalization features</span></span>

5. <span data-ttu-id="fb7fb-133">connectez-vous à RCS à l'aide d'un compte d'administrateur de locataire.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-133">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="fb7fb-134">Accédez à **Gestion des états électroniques** > **Applications connectées**.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-134">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="fb7fb-135">Sélectionnez **Nouveau** pour ajouter un enregistrement et entrez les informations de champ suivantes.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-135">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="fb7fb-136">Dans le champ **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-136">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="fb7fb-137">Dans le champ **Type**, sélectionnez **Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-137">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="fb7fb-138">Dans le champ **Application**, entrez votre URL Dataverse.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-138">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="fb7fb-139">Dans le champ **Locataire**, entrez votre locataire.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-139">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="fb7fb-140">Dans le champ **URL personnalisée**, entrez votre URL Dataverse et ajoutez-y « /api/data/v9.1 » à la fin.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-140">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="fb7fb-141">Sélectionnez **Vérifier la connexion** et terminez le processus de connexion.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-141">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="fb7fb-142">[![Bouton Vérifier la connexion](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="fb7fb-142">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="fb7fb-143">Accédez à **Gestion des états électroniques** > **Configurations de taxe** et importez des configurations de taxe à partir de [Configurations de taxe](https://go.microsoft.com/fwlink/?linkid=2158352).</span><span class="sxs-lookup"><span data-stu-id="fb7fb-143">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="fb7fb-144">[![Page Configurations de taxe, arborescence du modèle de données de taxe](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="fb7fb-144">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="fb7fb-145">Accédez à la **Mise en correspondance du modèle de document de taxe**, ou à la **Mise en correspondance du modèle Dataverse** si vous utilisez une configuration Microsoft et, dans le champ **Application connectée**, sélectionnez l'enregistrement que vous avez créé à l'étape 7.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-145">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="fb7fb-146">Définissez **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="fb7fb-146">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="fb7fb-147">[![Page Mise en correspondance de modèle](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="fb7fb-147">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
