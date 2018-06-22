---
title: "Intégration à Microsoft Dynamics 365 for Field Service"
description: "Cette rubrique fournit une vue d'ensemble de l'intégration à Microsoft Dynamics 365 for Field Service"
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a57e23691a6b4d48c6b8dd6d1f61fc9730365b39
ms.openlocfilehash: 0c1268d2fddcf7b28ecfc3197f21e9d30a5a5855
ms.contentlocale: fr-fr
ms.lasthandoff: 05/31/2018

---


# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a>Intégration à Microsoft Dynamics 365 for Field Service

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Finance and Operations active la synchronisation des processus d'entreprise entre Finance and Operations et Microsoft Dynamics 365 for Field Service. Les scénarios d'intégration sont configurés à l'aide de modèles d'intégrateur de données extensibles et de Common Data Service (CDS) pour activer la synchronisation des processus d'entreprise.

[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)

La première phase de l'intégration entre Field Service et Finance and Operations porte sur l'activation des ordres d'exécution et des accords dans Field Service à facturer en Finance and Operations. Le flux pris en charge commence dans Field Service, où les informations des ordres d'exécution sont synchronisées dans Finance and Operations comme commandes client. Dans Finance and Operations, des commandes client sont facturées pour générer des documents de facture. De plus, les informations des factures d'accord Field Service sont synchronisées sur Finance and Operations. L'intégrateur de données Microsoft Dynamics 365 synchronise les données à l'aide de projets personnalisables. Les modèles standard peuvent être utilisés pour créer des projets d'intégration personnalisés dans lesquels des champs standard et personnalisés supplémentaires, ainsi que des entités, peuvent être mis en correspondance pour ajuster l'intégration et satisfaire aux besoins spécifiques.

La première phase de l'intégration entre Field Service et Finance and Operations active la synchronisation des éléments suivants :

- [Produits de Finance and Operations sur des produits de Field Service incluant des informations sur le type de produit](field-service-product.md)
- [Des ordres d'exécution Field Service sur des commandes client Finance and Operations](field-service-work-order.md)
- [Des factures Field Service en factures financières Finance and Operations](field-service-invoice.md)

Pour afficher un exemple de la synchronisation d'un ordre d'exécution entre Field Service et Finance and Operations, visionnez la courte vidéo YouTube [Synchroniser un ordre d'exécution entre Dynamics 365 for Field Service et Finance and Operations](https://www.youtube.com/watch?v=hAB4TDVMjxU).

[![](https://img.youtube.com/vi/hAB4TDVMjxU/0.jpg)](https://www.youtube.com/watch?v=hAB4TDVMjxU)

## <a name="system-requirements-for-finance-and-operations"></a>Configuration requise pour Finance and Operations
L'intégration Field Service prend en charge les versions suivantes :

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a>Dynamics 365 for Finance and Operations, version 8.0 (avril 2018) ou versions ultérieures

- Dynamics 365 for Finance and Operations version 8.0 (avril 2018) a été publié en avril 2018 et a pour numéro de version de l'application 8.0.30.8020 avec Platform Update 15 (7.0.4841.35234). 

## <a name="system-requirements-for-field-service"></a>Configuration requise pour Field Service
Pour utiliser la solution d'intégration Field Service, vous devez installer les composants suivants :

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a>Microsoft Dynamics 365 for Field Service 9.0 ou versions ultérieures

- Dynamics 365 for Field Service version 1612 (9.0.1.733) (DB 9.0.1.733) en ligne ou ultérieure.
- Solution Prospect en disponibilités pour Dynamics 365, version 1.15.0.1 or ultérieure. La solution est disponible pour le téléchargement depuis [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Solution d'intégration Field Service pour Dynamics 365 version 1.0.0.0 ou ultérieure. La solution est disponible pour le téléchargement depuis [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).

