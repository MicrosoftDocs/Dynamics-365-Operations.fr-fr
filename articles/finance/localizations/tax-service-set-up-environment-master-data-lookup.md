---
title: Configurer un environnement pour la recherche de données principales
description: Cette rubrique explique comment configurer votre environnement pour utiliser la fonctionnalité de recherche de données principales pour le calcul des taxes.
author: kai-cloud
ms.date: 10/26/2021
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
ms.openlocfilehash: 901f8bcb0220355866952b68e92bc2dd906bb430
ms.sourcegitcommit: 2113678369f47944f8725ca656f461fa159f87f6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2021
ms.locfileid: "7700402"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Configurer un environnement pour la recherche de données principales

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer votre environnement pour utiliser la fonctionnalité de recherche de données principales pour le calcul des taxes.

1. Configurer l'intégration de Microsoft Power Platform dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations, voir la rubrique [Intégration de Microsoft Power Platform - Vue d’ensemble des compléments](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Une fois cette étape terminée, le nom d'un environnement Microsoft Power Platform apparaîtra dans la section **Intégration Power Platform**.
2. Accédez au [centre d'administration Microsoft Power Platform](https://admin.powerplatform.microsoft.com/environments), puis sélectionnez le nom de l'environnement. L'URL d'environnement est fourni.
3. Configurez Dynamics 365 Finance et Dataverse. Pour plus d’informations, consultez [Obtenir la solution d'entité virtuelle](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution) et [Authentification et autorisation](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
4. Vous devez paramétrer les entités suivantes : Pour plus d’informations, consultez [Activer des entités virtuelles Microsoft Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

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

5. Configurez Regulatory Configuration Service (RCS). Ouvrez l’espace de travail **Gestion des fonctionnalités**, puis activez les fonctionnalités suivantes :

    - Prise en charge des sources de données de la gestion des états électroniques Dataverse
    - Prise en charge des sources de données Dataverse du service fiscal
    - Fonctionnalités de globalisation

6. connectez-vous à RCS à l’aide d’un compte d’administrateur de locataire.
7. Accédez à **Gestion des états électroniques** > **Applications connectées**. 
8. Sélectionnez **Nouveau** pour ajouter un enregistrement et entrez les informations de champ suivantes. 

    - Dans le champ **Nom**, entrez un nom.
    - Dans le champ **Type**, sélectionnez **Dataverse**.
    - Dans le champ **Application**, entrez votre URL Dataverse.
    - Dans le champ **Locataire**, entrez votre locataire.
    - Dans le champ **URL personnalisée**, entrez votre URL Dataverse et ajoutez-y « /api/data/v9.1 » à la fin.

9. Sélectionnez **Vérifier la connexion** et terminez le processus de connexion. 

    [![Bouton Vérifier la connexion.](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

10. Accédez à **Gestion des états électroniques** > **Configurations de taxe** et importez des configurations de taxe à partir de [Configurations de taxe](https://go.microsoft.com/fwlink/?linkid=2158352).

    [![Page Configurations de taxe, arborescence du modèle de données de taxe.](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

11. Accédez à la **Mise en correspondance du modèle de document de taxe**, ou à la **Mise en correspondance du modèle Dataverse** si vous utilisez une configuration Microsoft et, dans le champ **Application connectée**, sélectionnez l’enregistrement que vous avez créé à l’étape 7.
12. Définissez **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.

    [![Page Mise en correspondance de modèle.](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
