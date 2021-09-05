---
title: Conseils sur la configuration de la double écriture
description: Cette rubrique décrit les scénarios pris en charge pour la configuration en double écriture.
author: RamaKrishnamoorthy
ms.date: 10/12/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6450ef7b0a59df3a8da2c8bed3aa9c0b14a9cc97
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2021
ms.locfileid: "7417055"
---
# <a name="guidance-for-dual-write-setup"></a>Conseils sur la configuration de la double écriture

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Vous pouvez configurer une connexion en double écriture entre un environnement Finance and Operations et un environnement Dataverse.

+ Un environnement **Finance and Operations** offre la plateforme sous-jacente pour les applications **Finance and Operations** (par exemple, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce et Dynamics 365 Human Resources).
+ Un **environnement Dataverse** offre à la plateforme sous-jacente les **applications Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Marketing et Dynamics 365 Project Service Automation).

> [!IMPORTANT]
> Le module Human Resources dans Dynamics 365 Finance prend en charge les connexions en double écriture, mais l’application Dynamics 365 Human Resources, non.

Le mécanisme de configuration varie en fonction de votre abonnement et de l’environnement :

+ Pour les nouvelles instances des applications Finance and Operations, la configuration d’une connexion en double écriture commence dans Microsoft Dynamics Lifecycle Services (LCS). Si vous avez une licence pour Microsoft Power Platform, vous obtiendrez un nouvel environnement Dataverse si votre client n’en a pas.
+ Pour les applications Finance and Operations des instances existantes, la configuration d’une connexion en double écriture commence dans l’environnement Finance and Operations.

Avant de commencer la double écriture sur une entité, vous pouvez exécuter une synchronisation initiale pour gérer les données existantes des deux côtés : des applications Finance and Operations et des applications d’engagement client. Vous pouvez ignorer la synchronisation initiale si vous ne devez pas synchroniser les données entre les deux environnements.

Une synchronisation initiale vous permet de copier les données existantes d’une application vers une autre de manière bidirectionnelle. Il existe plusieurs scénarios de configuration en fonction des environnements dont vous disposez déjà et du type de données qu’ils contiennent.

Les scénarios de configuration suivants sont pris en charge :

+ [Une nouvelle instance d’application Finance and Operations et une nouvelle instance d’application Customer Engagement](#new-new)
+ [Une nouvelle instance d’application Finance and Operations et une instance d’application Customer Engagement existante](#new-existing)
+ [Une nouvelle instance d’application Finance and Operations qui a des données et une nouvelle instance d’application Customer Engagement](#new-data-new)
+ [Une nouvelle instance d’application Finance and Operations qui a des données et une instance d’application Customer Engagement existante](#new-data-existing)
+ [Une instance d’application Finance and Operations existante et une nouvelle instance d’application Customer Engagement](#existing-new)
+ [Une instance d’application Finance and Operations existante et une instance d’application Customer Engagement existante](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>Une nouvelle instance d’application Finance and Operations et une nouvelle instance d’application Customer Engagement

Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations qui n’a pas de données et une nouvelle instance d’une application Customer Engagement, suivez les étapes de [Configuration en double écriture depuis Lifecycle Services](lcs-setup.md). Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :

- Un nouvel environnement Finance and Operations vide est provisionné.
- Une nouvelle instance vide d’une application Customer Engagement est provisionnée lorsque la solution CRM principale est installée.
- Une connexion en double écriture est établie pour les données de la société DAT.
- Les mappages de tables sont activés pour la synchronisation en direct.

Les deux environnements sont alors prêts pour la synchronisation des données en direct.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>Une nouvelle instance d’application Finance and Operations et une instance d’application Customer Engagement existante

Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations qui n’a pas de données et une instance existante d’une application Customer Engagement, suivez les étapes de [Configuration en double écriture depuis Lifecycle Services](lcs-setup.md). Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :

- Un nouvel environnement Finance and Operations vide est provisionné.
- Une connexion en double écriture est établie pour les données de la société DAT.
- Les mappages de tables sont activés pour la synchronisation en direct.

Les deux environnements sont alors prêts pour la synchronisation des données en direct.

Pour synchroniser les données Dataverse existantes à l’application Finance and Operations, procédez comme suit.

1. Créez une entreprise dans l’application Finance and Operations.
2. Ajoutez l’entreprise à la configuration de la connexion en double écriture.
3. [Amorcez](bootstrap-company-data.md) les données Dataverse à l’aide d’un code d’entreprise à trois lettres de l’Organisation internationale de normalisation (ISO).
4. Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.

Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example) plus loin dans cette rubrique.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>Une nouvelle instance d’application Finance and Operations qui a des données et une nouvelle instance d’application Customer Engagement

Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations contenant des données et une nouvelle instance d’une application Customer Engagement, suivez les étapes dans la section [Une nouvelle instance d’application Finance and Operations et une nouvelle instance d’application Customer Engagement](#new-new) plus haut dans cette rubrique. Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données avec l’application Customer Engagement, procédez comme suit.

1. Ouvrez l’application Finance and Operations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.
2. Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.

Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example).

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>Une nouvelle instance d’application Finance and Operations qui a des données et une instance d’application Customer Engagement existante

Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations contenant des données et une instance existante d’une application Customer Engagement, suivez les étapes dans la section [Une nouvelle instance d’application Finance and Operations et une instance d’application Customer Engagement existante](#new-existing) plus haut dans cette rubrique. Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données avec l’application Customer Engagement, procédez comme suit.

1. Ouvrez l’application Finance and Operations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.
2. Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.

Pour synchroniser les données Dataverse existantes à l’application Finance and Operations, procédez comme suit.

1. Créez une entreprise dans l’application Finance and Operations.
2. Ajoutez l’entreprise à la configuration de la connexion en double écriture.
3. [Amorcez](bootstrap-company-data.md) les données Dataverse à l’aide du code d’entreprise à trois lettres de l’Organisation internationale de normalisation (ISO).
4. Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.

Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>Une instance d’application Finance and Operations existante et une nouvelle instance d’application Customer Engagement

La configuration d’une connexion en double écriture entre une instance existante d’une application Finance and Operations et une nouvelle instance d’une application Customer Engagement se produit dans l’environnement Finance and Operation.

1. [Configurez la connexion à partir de l’application Finance and Operations](enable-dual-write.md).
2. Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.

Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>Une instance d’application Finance and Operations existante et une instance d’application Customer Engagement existante

La configuration d’une connexion en double écriture entre une instance existante d’une application Finance and Operations et une instance existante d’une application d’engagement client se produit dans l’environnement Finance and Operation.

1. [Configurez la connexion à partir de l’application Finance and Operations](enable-dual-write.md).
2. Pour synchroniser les données Dataverse existantes avec l’application Finance and Operations, [amorcez](bootstrap-company-data.md) les données Dataverse à l’aide d’un code d’entreprise ISO à trois lettres.
3. Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.

Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example).

## <a name="example"></a>Exemple

Pour un exemple, voir [Activation de la carte des tables Clients V3 – Contacts](enable-entity-map.md#enable-table-map)

Pour une approche alternative basée sur les volumes de données dans chaque entité qui doivent exécuter une synchronisation initiale, voir [Considérations relatives à la synchronisation initiale](initial-sync-guidance.md).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]