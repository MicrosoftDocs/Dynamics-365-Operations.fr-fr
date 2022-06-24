---
title: Conseils sur la configuration de la double écriture
description: Cet article décrit les scénarios pris en charge pour la configuration en double écriture.
author: RamaKrishnamoorthy
ms.date: 10/12/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: a0d1b4e1f093874a8fd37cf7aadb331cd1e7adc4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873147"
---
# <a name="guidance-for-dual-write-setup"></a>Conseils sur la configuration de la double écriture

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]



Vous pouvez configurer une connexion en double écriture entre un environnement de finances et d’opérations et un environnement Dataverse.

+ Un **environnement de finances et d’opérations** offre la plateforme sous-jacente pour les **applications de finances et d’opérations** (par exemple, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce et Dynamics 365 Human Resources).
+ Un **environnement Dataverse** offre à la plateforme sous-jacente les **applications Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Marketing et Dynamics 365 Project Service Automation).

> [!IMPORTANT]
> Le module Human Resources dans Dynamics 365 Finance prend en charge les connexions en double écriture, mais ce n’est pas le cas avec l’application Dynamics 365 Human Resources.

Le mécanisme de configuration varie en fonction de votre abonnement et de l’environnement :

+ Pour les nouvelles instances des applications Finances et Opérations, la configuration d’une connexion en double écriture commence dans Microsoft Dynamics Lifecycle Services (LCS). Si vous avez une licence pour Microsoft Power Platform, vous obtiendrez un nouvel environnement Dataverse si votre client n’en a pas.
+ Pour les instances existantes des applications Finances et Opérations, la configuration d’une connexion en double écriture commence dans l’environnement de finances et d’opérations.

Avant de commencer la double écriture sur une entité, vous pouvez exécuter une synchronisation initiale pour gérer les données existantes des deux côtés : des applications Finances et Opérations et des applications d’engagement client. Vous pouvez ignorer la synchronisation initiale si vous ne devez pas synchroniser les données entre les deux environnements.

Une synchronisation initiale vous permet de copier les données existantes d’une application vers une autre de manière bidirectionnelle. Il existe plusieurs scénarios de configuration en fonction des environnements dont vous disposez déjà et du type de données qu’ils contiennent.

Les scénarios de configuration suivants sont pris en charge :

+ [Une nouvelle instance d’application de finances et d’opérations et une nouvelle instance d’application Customer Engagement](#new-new)
+ [Une nouvelle instance d’application de finances et d’opérations et une instance existante d’application Customer Engagement](#new-existing)
+ [Une nouvelle instance d’application de finances et d’opérations qui a des données et une nouvelle instance d’application Customer Engagement](#new-data-new)
+ [Une nouvelle instance d’application de finances et d’opérations qui a des données et une instance existante d’application Customer Engagement](#new-data-existing)
+ [Une instance existante d’application de finances et d’opérations et une nouvelle instance d’application Customer Engagement](#existing-new)
+ [Une instance existante d’application de finances et d’opérations et une instance existante d’application Customer Engagement](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>Une nouvelle instance d’application de finances et d’opérations et une nouvelle instance d’application Customer Engagement

Pour configurer une connexion en double écriture entre une nouvelle instance d’une application de finances et d’opérations qui n’a pas de données et une nouvelle instance d’une application Customer Engagement, suivez les étapes de [Configuration en double écriture depuis Lifecycle Services](lcs-setup.md). Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :

- Un nouvel environnement de finances et d’opérations vide est mis en service.
- Une nouvelle instance vide d’une application Customer Engagement est provisionnée lorsque la solution CRM principale est installée.
- Une connexion en double écriture est établie pour les données de la société DAT.
- Les mappages de tables sont activés pour la synchronisation en direct.

Les deux environnements sont alors prêts pour la synchronisation des données en direct.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>Une nouvelle instance d’applications de finances et d’opérations et une instance existante d’application Customer Engagement

Pour configurer une connexion en double écriture entre une nouvelle instance d’une application de finances et d’opérations qui n’a pas de données et une instance existante d’une application Customer Engagement, suivez les étapes de [Configuration en double écriture depuis Lifecycle Services](lcs-setup.md). Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :

- Un nouvel environnement de finances et d’opérations vide est mis en service.
- Une connexion en double écriture est établie pour les données de la société DAT.
- Les mappages de tables sont activés pour la synchronisation en direct.

Les deux environnements sont alors prêts pour la synchronisation des données en direct.

Pour synchroniser les données Dataverse existantes à l’application de finances et d’opérations, procédez comme suit.

1. Créez une société dans l’application de finances et d’opérations.
2. Ajoutez l’entreprise à la configuration de la connexion en double écriture.
3. [Amorcez](bootstrap-company-data.md) les données Dataverse à l’aide d’un code d’entreprise à trois lettres de l’Organisation internationale de normalisation (ISO).
4. Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.

Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example) plus loin dans cet article.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>Une nouvelle instance d’application de finances et d’opérations qui a des données et une nouvelle instance d’application Customer Engagement

Pour configurer une connexion en double écriture entre une nouvelle instance d’une application de finances et d’opérations contenant des données et une nouvelle instance d’une application Customer Engagement, suivez les étapes dans la section [Une nouvelle instance d’application de finances et d’opérations et une nouvelle instance d’application Customer Engagement](#new-new) plus haut dans cet article. Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données avec l’application Customer Engagement, procédez comme suit.

1. Ouvrez l’application de finances et d’opérations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.
2. Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.

Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example).

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>Une nouvelle instance d’application de finances et d’opérations qui a des données et une instance existante d’application Customer Engagement

Pour configurer une connexion en double écriture entre une nouvelle instance d’une application de finances et d’opérations contenant des données et une instance existante d’une application Customer Engagement, suivez les étapes dans la section [Une nouvelle instance d’application de finances et d’opérations et une instance existante d’application Customer Engagement](#new-existing) plus haut dans cet article. Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données avec l’application Customer Engagement, procédez comme suit.

1. Ouvrez l’application de finances et d’opérations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.
2. Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.

Pour synchroniser les données Dataverse existantes à l’application de finances et d’opérations, procédez comme suit.

1. Créez une société dans l’application de finances et d’opérations.
2. Ajoutez l’entreprise à la configuration de la connexion en double écriture.
3. [Amorcez](bootstrap-company-data.md) les données Dataverse à l’aide du code d’entreprise à trois lettres de l’Organisation internationale de normalisation (ISO).
4. Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.

Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>Une instance existante d’application de finances et d’opérations et une nouvelle instance d’application Customer Engagement

La configuration d’une connexion en double écriture entre une instance existante d’une application de finances et d’opérations et une nouvelle instance d’une application Customer Engagement se produit dans l’environnement de finances et d’opérations.

1. [Configurer la connexion depuis l’application de finances et d’opérations](enable-dual-write.md).
2. Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.

Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>Une instance existante d’application de finances et d’opérations et une instance existante d’application Customer Engagement

La configuration d’une connexion en double écriture entre une instance existante d’une application de finances et d’opérations et une instance existante d’une application Customer Engagement se produit dans l’environnement de finances et d’opérations.

1. [Configurer la connexion depuis l’application de finances et d’opérations](enable-dual-write.md).
2. Pour synchroniser les données Dataverse existantes avec l’application , [amorcez](bootstrap-company-data.md) les données Dataverse à l’aide d’un code d’entreprise ISO à trois lettres.
3. Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.

Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example).

## <a name="example"></a>Exemple

Pour un exemple, voir [Activation de la carte des tables Clients V3 – Contacts](enable-entity-map.md#enable-table-map)

Pour une approche alternative basée sur les volumes de données dans chaque entité qui doivent exécuter une synchronisation initiale, voir [Considérations relatives à la synchronisation initiale](initial-sync-guidance.md).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]