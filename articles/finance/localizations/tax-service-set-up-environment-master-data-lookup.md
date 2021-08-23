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
ms.openlocfilehash: c4435dbfdb808a75b41a77d3c15d1c9fd29b266f353b1fbe18955ff985ab38bd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718177"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Configurer un environnement pour la recherche de données principales

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer votre environnement pour utiliser la fonctionnalité de recherche de données principales pour le calcul des taxes.

1. Configurez l’intégration de Power Platform dans Lifecycle Services (LCS). Pour plus d’informations, voir la rubrique [Intégration de Microsoft Power Platform - Vue d’ensemble des compléments](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
2. Configurez Dynamics 365 Finance et Microsoft Dataverse. Pour plus d’informations, consultez [Obtenir la solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) et [Authentification et autorisation](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
3. Vous devez paramétrer les entités suivantes : Pour plus d’informations, consultez [Activation des entités virtuelles](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).
      - CompanyInfoEntity
      - CurrencyEntity
      - CustCustomerV3Entity
      - DeliveryTermsEntity
      - EcoResProductCategoryEntity
      - EcoResReleasedProductV2Entity
      - LogisticsAddressCityEntity
      - LogisticsAddressCountryRegionTranslationEntity
      - LogisticsAddressStateEntity
      - PurchProcurementChargeCDSEntity
      - SalesChargeCDSEntity
      - TaxGroupEntity
      - TaxItemGroupHeadingEntity
      - VendVendorV2Entity
4. Configurez Dynamics 365 Regulatory Configuration Service (RCS). 
5. Créez une demande de service pour que Microsoft active la distribution de version d’évaluation des fonctionnalités suivantes :

      - ERCdsFeature
      - TaxServiceCDSFeature

6. Accédez à l’espace de travail **Gestion des fonctionnalités**, puis activez les fonctionnalités suivantes :

      - (Version préliminaire) Prise en charge des sources de données de la gestion des états électroniques Dataverse
      - (Version préliminaire) Prise en charge des sources de données Dataverse du service fiscal
      - (Version préliminaire) Fonctionnalités de globalisation

5. connectez-vous à RCS à l’aide d’un compte d’administrateur de locataire.
6. Accédez à **Gestion des états électroniques** > **Applications connectées**. 
7. Sélectionnez **Nouveau** pour ajouter un enregistrement et entrez les informations de champ suivantes. 

   - Dans le champ **Nom**, entrez un nom.
   - Dans le champ **Type**, sélectionnez **Dataverse**.
   - Dans le champ **Application**, entrez votre URL Dataverse.
   - Dans le champ **Locataire**, entrez votre locataire.
   - Dans le champ **URL personnalisée**, entrez votre URL Dataverse et ajoutez-y « /api/data/v9.1 » à la fin.

8. Sélectionnez **Vérifier la connexion** et terminez le processus de connexion. 

   [![Bouton Vérifier la connexion.](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

9. Accédez à **Gestion des états électroniques** > **Configurations de taxe** et importez des configurations de taxe à partir de [Configurations de taxe](https://go.microsoft.com/fwlink/?linkid=2158352).

   [![Page Configurations de taxe, arborescence du modèle de données de taxe.](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

10. Accédez à la **Mise en correspondance du modèle de document de taxe**, ou à la **Mise en correspondance du modèle Dataverse** si vous utilisez une configuration Microsoft et, dans le champ **Application connectée**, sélectionnez l’enregistrement que vous avez créé à l’étape 7.
11. Définissez **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.

   [![Page Mise en correspondance de modèle.](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
