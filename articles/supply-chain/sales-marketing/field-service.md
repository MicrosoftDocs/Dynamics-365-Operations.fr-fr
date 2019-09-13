---
title: Vue d'ensemble de l'intégration à Microsoft Dynamics 365 for Field Service
description: Cette rubrique offre une vue d'ensemble de l'intégration à Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 22abe83f06b7fc57c73fb82ccafc4b426667e7c6
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865192"
---
# <a name="integration-with-microsoft-dynamics-365-for-field-service-overview"></a>Vue d'ensemble de l'intégration à Microsoft Dynamics 365 for Field Service

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Finance and Operations active la synchronisation des processus d'entreprise entre Finance and Operations et Microsoft Dynamics 365 for Field Service. Les scénarios d'intégration sont configurés à l'aide de modèles d'intégrateur de données extensibles et de Common Data Service (CDS) pour activer la synchronisation des processus d'entreprise.
Les modèles standard peuvent être utilisés pour créer des projets d'intégration personnalisés, dans lesquels des champs standard et personnalisés supplémentaires, ainsi que des entités, peuvent être mis en correspondance pour ajuster l'intégration et satisfaire aux besoins professionnels spécifiques. 

L'intégration avec Field Service se base sur la fonctionnalité existante de Prospect en disponibilités.

![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/field-service-integration.png)

La première phase de l'intégration entre Field Service et Finance and Operations porte sur l'activation des ordres d'exécution et des accords dans Field Service à facturer en Finance and Operations. Le flux pris en charge commence dans Field Service, où les informations des ordres d'exécution sont synchronisées dans Finance and Operations comme commandes client. Dans Finance and Operations, des commandes client sont facturées pour générer des documents de facture. De plus, les informations des factures d'accord Field Service sont synchronisées sur Finance and Operations. L'intégrateur de données Microsoft Dynamics 365 synchronise les données à l'aide de projets personnalisables. Les modèles standard peuvent être utilisés pour créer des projets d'intégration personnalisés dans lesquels des champs standard et personnalisés supplémentaires, ainsi que des entités, peuvent être mis en correspondance pour ajuster l'intégration et satisfaire aux besoins spécifiques.

La première phase de l'intégration entre Field Service et Finance and Operations active la synchronisation des éléments suivants :

- [Produits de Finance and Operations sur des produits de Field Service incluant des informations sur le type de produit](field-service-product.md)
- [Des ordres d'exécution Field Service sur des commandes client Finance and Operations](field-service-work-order.md)
- [Des factures Field Service en factures financières Finance and Operations](field-service-invoice.md)

Pour afficher un exemple de la synchronisation d'un ordre d'exécution entre Field Service et Finance and Operations, visionnez la courte vidéo YouTube [Procédure de synchronisation d'un ordre d'exécution avec l'intégration de Microsoft Dynamics 365](https://www.youtube.com/watch?v=46ylO7raZAo).

## <a name="integration-with-microsoft-dynamics-365-for-field-service-including-inventory-and-project-information"></a>Intégration à Microsoft Dynamics 365 for Field Service, notamment les informations de stock et de projet

La fonctionnalité supplémentaire de cette deuxième phase est axée sur la possibilité offerte aux techniciens de terrain d'avoir un aperçu des informations sur le stock dans Finance and Operations, ce qui leur permet de mettre à jour les niveaux de stock et d'effectuer des transferts de matériel. En outre, les sociétés installant ou entretenant des marchandises vendues bénéficieront d'un meilleur contrôle et d'une plus grande visibilité sur le processus de vente et de service complet avec l'intégration des projets.

### <a name="functionality-includes-integration-of"></a>La fonctionnalité inclut l'intégration de :
- Informations sur l'entrepôt
- Informations sur le stock disponible
- Transferts de stock
- Ajustements du stock
- Projets Dynamics 365 for Finance and Operations connectés aux ordres d'exécution Dynamics 365 for Field Service
- Les ordres d'exécution Dynamics 365 for Field Service avec un lien vers les projets Dynamics 365 for Finance and Operations appliquent ce numéro de projet à la commande client Dynamics 365 for Finance and Operations pour permettre la facturation depuis le projet. 

![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-finance-and-operations-enables-synchronization-with-the-following-templates"></a>La seconde phase de l'intégration entre Field Service et Finance and Operations active la synchronisation avec les modèles suivants :
- Entrepôts (Finance and Operations vers Field Service) - Entrepôts de Finance and Operations vers Field Service [Requête avancée] 
- Produit de stock (Finance and Operations vers Field Service) - Informations sur le niveau de stock de Finance and Operations vers Field Service [Requête avancée] 
- Ajustement de stock (Field Service vers Finance and Operations) - Ajustements de stock de Field Service vers Finance and Operations [Requête avancée] 
- Transferts de stock (Field Service vers Finance and Operations) - Transferts de stock de Field Service vers Finance and Operations [Requête avancée] 
- Projets (Finance and Operations vers Field Service) - Liste des projets de Finance and Operations vers Field Service 
- Ordres d'exécution avec le projet (Field Service vers Finance and Operations) - Ordres d'exécution dans Field Service vers les commandes client dans Finance and Operations, avec la prise en charge de projet [Requête avancée] 
- Produits Field Service avec unité de stock (Finance and Operations vers Sales) - « Produits lancés vendables » Finance and Operations vers « Produits » Sales pour Field Service, y compris l'unité de stock 

## <a name="system-requirements"></a>Configuration requise

### <a name="system-requirements-for-finance-and-operations"></a>Configuration requise pour Finance and Operations
L'intégration Field Service prend en charge les versions suivantes :

- Dynamics 365 for Finance and Operations version 8.1.2 (décembre 2018) a été publié en décembre 2018 et a pour numéro de version de l'application 8.1.195 avec Platform Update 22 (7.0.5095). 

### <a name="system-requirements-for-field-service"></a>Configuration requise pour Field Service
Pour utiliser la solution d'intégration Field Service, vous devez installer les composants suivants :

- Field Service for Dynamics 365 (version 8.2.0.286) ou version ultérieure sur Dynamics 365 9.1.x - Publié en novembre 2018
- Solution Prospect en disponibilités pour Dynamics 365, version 1.15.0.1 or ultérieure. La solution est disponible pour le téléchargement depuis [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Solution « Intégration Field Service, projet et stock » pour Dynamics 365 version 2.0.0.0 ou ultérieure. La solution est disponible pour le téléchargement depuis [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2).
