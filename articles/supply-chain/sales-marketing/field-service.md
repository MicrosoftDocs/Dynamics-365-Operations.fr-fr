---
title: Vue d'ensemble de l'intégration à Microsoft Dynamics 365 Field Service
description: Cette rubrique offre une vue d'ensemble de l'intégration à Microsoft Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 041044cf6b5a5de2091a4b61d98b7d07445e43ef
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209120"
---
# <a name="integration-with-microsoft-dynamics-365-field-service-overview"></a>Vue d'ensemble de l'intégration à Microsoft Dynamics 365 Field Service

[!include[banner](../includes/banner.md)]

Supply Chain Management permet la synchronisation des processus d'entreprise entre Dynamics 365 Supply Chain Management et Dynamics 365 Field Service. Les scénarios d'intégration sont configurés à l'aide de modèles d'intégrateur de données extensibles et de Common Data Service pour activer la synchronisation des processus d'entreprise.
Les modèles standard peuvent être utilisés pour créer des projets d'intégration personnalisés, dans lesquels des champs standard et personnalisés supplémentaires, ainsi que des entités, peuvent être mis en correspondance pour ajuster l'intégration et satisfaire aux besoins professionnels spécifiques. 

L'intégration avec Field Service se base sur la fonctionnalité existante de Prospect en disponibilités.

![Synchronisation des processus d'entreprise entre Supply Chain Management et Field Service](./media/field-service-integration.png)

La première phase de l'intégration entre Field Service et Supply Chain Management porte sur l'activation des ordres de travail et des accords dans Field Service à facturer dans Supply Chain Management. Le flux pris en charge commence dans Field Service, où les informations des ordres de travail sont synchronisées avec Supply Chain Management comme commandes client. Dans Supply Chain Management, les commandes client sont facturées pour générer des documents de facture. De plus, les informations des factures d'accord Field Service sont synchronisées sur Supply Chain Management. L'intégrateur de données Microsoft Dynamics 365 synchronise les données à l'aide de projets personnalisables. Les modèles standard peuvent être utilisés pour créer des projets d'intégration personnalisés dans lesquels des champs standard et personnalisés supplémentaires, ainsi que des entités, peuvent être mis en correspondance pour ajuster l'intégration et satisfaire aux besoins spécifiques.

La première phase de l'intégration entre Field Service et Supply Chain Management active la synchronisation des éléments suivants :

- [Synchroniser directement les produits provenant du module Supply Chain Management sur les produits dans Field Service](field-service-product.md)
- [Synchroniser des bons de travail de Field Service sur des commandes client de Supply Chain Management](field-service-work-order.md)
- [Synchroniser des factures d'accord de Field Service sur des factures financières dans Supply Chain Management](field-service-invoice.md)

Pour afficher un exemple de la synchronisation d'un ordre de travail entre Field Service et Supply Chain Management, visionnez la courte vidéo YouTube [Procédure de synchronisation d'un ordre de travail avec l'intégration de Microsoft Dynamics 365](https://www.youtube.com/watch?v=46ylO7raZAo).

## <a name="integration-with-field-service-including-inventory-and-project-information"></a>Intégration à Field Service, notamment les informations de stock et de projet

La fonctionnalité supplémentaire de cette deuxième phase est axée sur la possibilité offerte aux techniciens de terrain d'avoir un aperçu des informations sur le stock dans Supply Chain Management, ce qui leur permet de mettre à jour les niveaux de stock et d'effectuer des transferts de matériel. En outre, les sociétés installant ou entretenant des marchandises vendues bénéficieront d'un meilleur contrôle et d'une plus grande visibilité sur le processus de vente et de service complet avec l'intégration des projets.

### <a name="functionality-includes-integration-of"></a>La fonctionnalité inclut l'intégration de :
- Informations sur l'entrepôt
- Informations sur le stock disponible
- Transferts de stock
- Ajustements du stock
- Projets Supply Chain Management connectés aux ordres de travail Dynamics 365 Field Service
- Les ordres de travail Dynamics 365 Field Service avec un lien vers les projets Supply Chain Management appliquent ce numéro de projet à la commande client pour permettre la facturation depuis le projet. 

![Synchronisation des processus d'entreprise entre Supply Chain Management et Field Service](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-supply-chain-management-enables-synchronization-with-the-following-templates"></a>La seconde phase de l'intégration entre Field Service et Supply Chain Management active la synchronisation avec les modèles suivants :
- Entrepôts (Supply Chain Management vers Field Service) - Entrepôts de Supply Chain Management vers Field Service [requête avancée] 
- Stock de produit (Supply Chain Management vers Field Service) - Informations au niveau du stock de Supply Chain Management vers Field Service [requête avancée] 
- Ajustement du stock (Field Service vers Supply Chain Management) - Ajustements de stock de Field Service vers Supply Chain Management [requête avancée] 
- Transferts de stock (Field Service vers Supply Chain Management) - Transferts de stock de Field Service vers Supply Chain Management [requête avancée] 
- Projets (Supply Chain Management vers Field Service) - Liste de projets de Supply Chain Management vers Field Service 
- Ordres de travail avec le projet (Field Service vers Supply Chain Management) - Ordres de travail dans Field Service vers les commandes client  dans Supply Chain Management, avec la prise en charge de projet [Requête avancée] 
- Produits Field Service avec unité de stock (Supply Chain Management vers Sales) - « Produits lancés vendables » Supply Chain Management vers « Produits » Sales pour Field Service, y compris l'unité de stock 

## <a name="system-requirements"></a>Configuration requise

### <a name="system-requirements-for-supply-chain-management"></a>Configuration système pour Supply Chain Management
L'intégration Field Service prend en charge les versions suivantes :

- Dynamics 365 for Finance and Operations version 8.1.2 (décembre 2018) a été publiée en décembre 2018 et a pour numéro de version de l'application 8.1.195 avec Platform Update 22 (7.0.5095). 

### <a name="system-requirements-for-field-service"></a>Configuration requise pour Field Service
Pour utiliser la solution d'intégration Field Service, vous devez installer les composants suivants :

- Field Service (version 8.2.0.286) ou version ultérieure sur Dynamics 365 9.1.x - Publiée en novembre 2018
- Solution Prospect en disponibilités pour Dynamics 365, version 1.15.0.1 or ultérieure. La solution est disponible pour le téléchargement depuis [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Solution « Intégration Field Service, projet et stock » pour Dynamics 365 version 2.0.0.0 ou ultérieure. La solution est disponible pour le téléchargement depuis [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2).
