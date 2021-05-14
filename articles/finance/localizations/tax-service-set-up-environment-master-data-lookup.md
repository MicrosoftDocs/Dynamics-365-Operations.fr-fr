---
title: Configurer un environnement pour la recherche de données principales
description: Cette rubrique explique comment configurer votre environnement pour utiliser la fonctionnalité de recherche de données principales pour le calcul des taxes.
author: kai-cloud
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 9f9b385df1db60b27698d90281c43fabb574af49
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924152"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="ded94-103">Configurer un environnement pour la recherche de données principales</span><span class="sxs-lookup"><span data-stu-id="ded94-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ded94-104">Cette rubrique explique comment configurer votre environnement pour utiliser la fonctionnalité de recherche de données principales pour le calcul des taxes.</span><span class="sxs-lookup"><span data-stu-id="ded94-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="ded94-105">Configurez l'intégration de Power Platform dans Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="ded94-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="ded94-106">Pour plus d’informations, voir la rubrique [Intégration de Microsoft Power Platform - Vue d'ensemble des compléments](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ded94-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="ded94-107">Configurez Dynamics 365 Finance et Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="ded94-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="ded94-108">Pour plus d'informations, consultez [Obtenir la solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) et [Authentification et autorisation](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="ded94-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="ded94-109">Vous devez paramétrer les entités suivantes :</span><span class="sxs-lookup"><span data-stu-id="ded94-109">Set up the following entities.</span></span> <span data-ttu-id="ded94-110">Pour plus d’informations, consultez [Activation des entités virtuelles](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="ded94-110">For more information, see [Enabling virtual entities](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span></span>
      - <span data-ttu-id="ded94-111">CompanyInfoEntity</span><span class="sxs-lookup"><span data-stu-id="ded94-111">CompanyInfoEntity</span></span>
      - <span data-ttu-id="ded94-112">CurrencyEntity</span><span class="sxs-lookup"><span data-stu-id="ded94-112">CurrencyEntity</span></span>
      - <span data-ttu-id="ded94-113">CustCustomerV3Entity</span><span class="sxs-lookup"><span data-stu-id="ded94-113">CustCustomerV3Entity</span></span>
      - <span data-ttu-id="ded94-114">DeliveryTermsEntity</span><span class="sxs-lookup"><span data-stu-id="ded94-114">DeliveryTermsEntity</span></span>
      - <span data-ttu-id="ded94-115">EcoResProductCategoryEntity</span><span class="sxs-lookup"><span data-stu-id="ded94-115">EcoResProductCategoryEntity</span></span>
      - <span data-ttu-id="ded94-116">EcoResReleasedProductV2Entity</span><span class="sxs-lookup"><span data-stu-id="ded94-116">EcoResReleasedProductV2Entity</span></span>
      - <span data-ttu-id="ded94-117">LogisticsAddressCityEntity</span><span class="sxs-lookup"><span data-stu-id="ded94-117">LogisticsAddressCityEntity</span></span>
      - <span data-ttu-id="ded94-118">LogisticsAddressCountryRegionTranslationEntity</span><span class="sxs-lookup"><span data-stu-id="ded94-118">LogisticsAddressCountryRegionTranslationEntity</span></span>
      - <span data-ttu-id="ded94-119">LogisticsAddressStateEntity</span><span class="sxs-lookup"><span data-stu-id="ded94-119">LogisticsAddressStateEntity</span></span>
      - <span data-ttu-id="ded94-120">PurchProcurementChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="ded94-120">PurchProcurementChargeCDSEntity</span></span>
      - <span data-ttu-id="ded94-121">SalesChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="ded94-121">SalesChargeCDSEntity</span></span>
      - <span data-ttu-id="ded94-122">TaxGroupEntity</span><span class="sxs-lookup"><span data-stu-id="ded94-122">TaxGroupEntity</span></span>
      - <span data-ttu-id="ded94-123">TaxItemGroupHeadingEntity</span><span class="sxs-lookup"><span data-stu-id="ded94-123">TaxItemGroupHeadingEntity</span></span>
      - <span data-ttu-id="ded94-124">VendVendorV2Entity</span><span class="sxs-lookup"><span data-stu-id="ded94-124">VendVendorV2Entity</span></span>
4. <span data-ttu-id="ded94-125">Configurez Dynamics 365 Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="ded94-125">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="ded94-126">Créez une demande de service pour que Microsoft active la distribution de version d’évaluation des fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="ded94-126">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="ded94-127">ERCdsFeature</span><span class="sxs-lookup"><span data-stu-id="ded94-127">ERCdsFeature</span></span>
      - <span data-ttu-id="ded94-128">TaxServiceCDSFeature</span><span class="sxs-lookup"><span data-stu-id="ded94-128">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="ded94-129">Accédez à l’espace de travail **Gestion des fonctionnalités**, puis activez les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="ded94-129">Go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="ded94-130">(Version préliminaire) Prise en charge des sources de données de la gestion des états électroniques Dataverse</span><span class="sxs-lookup"><span data-stu-id="ded94-130">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="ded94-131">(Version préliminaire) Prise en charge des sources de données Dataverse du service fiscal</span><span class="sxs-lookup"><span data-stu-id="ded94-131">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="ded94-132">(Version préliminaire) Fonctionnalités de globalisation</span><span class="sxs-lookup"><span data-stu-id="ded94-132">(Preview) Globalization features</span></span>

5. <span data-ttu-id="ded94-133">connectez-vous à RCS à l'aide d'un compte d'administrateur de locataire.</span><span class="sxs-lookup"><span data-stu-id="ded94-133">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="ded94-134">Accédez à **Gestion des états électroniques** > **Applications connectées**.</span><span class="sxs-lookup"><span data-stu-id="ded94-134">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="ded94-135">Sélectionnez **Nouveau** pour ajouter un enregistrement et entrez les informations de champ suivantes.</span><span class="sxs-lookup"><span data-stu-id="ded94-135">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="ded94-136">Dans le champ **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="ded94-136">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="ded94-137">Dans le champ **Type**, sélectionnez **Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="ded94-137">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="ded94-138">Dans le champ **Application**, entrez votre URL Dataverse.</span><span class="sxs-lookup"><span data-stu-id="ded94-138">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="ded94-139">Dans le champ **Locataire**, entrez votre locataire.</span><span class="sxs-lookup"><span data-stu-id="ded94-139">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="ded94-140">Dans le champ **URL personnalisée**, entrez votre URL Dataverse et ajoutez-y « /api/data/v9.1 » à la fin.</span><span class="sxs-lookup"><span data-stu-id="ded94-140">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="ded94-141">Sélectionnez **Vérifier la connexion** et terminez le processus de connexion.</span><span class="sxs-lookup"><span data-stu-id="ded94-141">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="ded94-142">[![Bouton Vérifier la connexion](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="ded94-142">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="ded94-143">Accédez à **Gestion des états électroniques** > **Configurations de taxe** et importez des configurations de taxe à partir de [Configurations de taxe](https://go.microsoft.com/fwlink/?linkid=2158352).</span><span class="sxs-lookup"><span data-stu-id="ded94-143">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="ded94-144">[![Page Configurations de taxe, arborescence du modèle de données de taxe](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="ded94-144">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="ded94-145">Accédez à la **Mise en correspondance du modèle de document de taxe**, ou à la **Mise en correspondance du modèle Dataverse** si vous utilisez une configuration Microsoft et, dans le champ **Application connectée**, sélectionnez l'enregistrement que vous avez créé à l'étape 7.</span><span class="sxs-lookup"><span data-stu-id="ded94-145">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="ded94-146">Définissez **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="ded94-146">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="ded94-147">[![Page Mise en correspondance de modèle](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="ded94-147">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
