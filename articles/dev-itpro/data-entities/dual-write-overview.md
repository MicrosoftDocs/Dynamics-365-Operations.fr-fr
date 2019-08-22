---
title: Intégration de données en temps réel entre Finance and Operations et Common Data Service
description: Cette rubrique offre une vue d'ensemble de l'intégration entre Microsoft Dynamics 365 for Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: aa614c8e6a79a3f7a4f8f2f99f1f1bd1a67ac921
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797226"
---
# <a name="near-real-time-data-integration-between-finance-and-operations-and-common-data-service"></a>Intégration de données en temps réel entre Finance and Operations et Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Dans le monde numérique actuel, les écosystèmes commerciaux utilisent la suite Microsoft Dynamics 365 dans son ensemble. Comme les données des personnes, des clients, des opérations et de l'Internet des objets (IoT) arrivent dans une seule source, il existe une possibilité de boucles de rétroaction numérique. Pour obtenir cette expérience, l'intégration entre Dynamics 365 for Finance and Operations et les applications Dynamics 365 for Customer Engagement est vital. Les applications Customer Engagement reposent sur Common Data Service. L'intégration entre les données de Finance and Operations avec Common Data Service permet aux applications Customer Engagement de communiquer avec cohérence et de manière fluide avec Finance and Operations.

Finance and Operations et Common Data Service fournissent la synchronisation des données en temps quasi-réel entre Finance and Operations et les applications Customer Engagement via une infrastructure en double écriture. La couverture est large et couvre 28 zones de Finance and Operations. L'objectif est de fournir une expérience utilisateur « Dynamics 365 Unique » avec des flux de données transparents qui connectent les processus d'entreprise entre applications.

![Diagramme de vue d'ensemble de l'architecture](media/dual-write-overview.jpg)

Les propositions de valeur suivantes sont disponibles pour les clients :

+ [Hiérarchie d'organisation dans Common Data Service](dual-write-organization.md)
+ [Concept de société dans Common Data Service](dual-write-company.md)
+ [Données principales client intégrées](dual-write-customer.md)
+ [Données principales fournisseur intégrées](dual-write-vendor.md)
+ Produit générique unifié

## <a name="system-requirements"></a>Configuration requise

Les flux de données en temps quasi-réel synchrones nécessitent les versions suivantes :

+ Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (juiellet 2019) avec Platform update 28, ou version ultérieure
+ Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) ou version ultérieure

## <a name="setup-instructions"></a>Définir des instructions

Procédez comme suit pour paramétrer l'intégration entre Finance and Operations et Common Data Service.
    
1. Pour le paramétrage du système en double écriture, voir le [guide pas à pas](https://aka.ms/dualwrite-docs) dans l'annonce de la version préliminaire de la double écriture.
2. Téléchargez et installez la solution à partir de [Finance and Operations, Common Data Service et intégration Customer Engagement](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) du groupe Yammer. Le module contient cinq solutions :

    + Dynamics365Company
    + CurrencyExchangeRates
    + Dynamics365FinanceAndOperationsCommon
    + Dynamics365FinanceCommon
    + Dynamics365SupplyChainCommon

3. Suivez l'ordre d'exécution de la [synchronisation des données de référence initiales](dual-write-initial.md).
4. Si vous rencontrez des problèmes de synchronisation en double écriture, voir [Guide de résolution des problèmes d'intégration des données](dual-write-troubleshooting.md).

> [!IMPORTANT]
> Vous ne pouvez pas exécuter la double écriture et [Prospect en disponibilités](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) côte à côte. Si vous exécutez la solution Prospect en disponibilités, vous devez la désinstaller. Vous devez également désactiver les modèles de double écriture client et fournisseur qui font partie de la solution Prospect en disponibilités.
