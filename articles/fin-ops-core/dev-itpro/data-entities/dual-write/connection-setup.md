---
title: Scénarios pris en charge pour la configuration en double écriture
description: Cette rubrique décrit les scénarios pris en charge pour la configuration en double écriture.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: d7ff514768ee8e4797b591da89e190a855385885
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172852"
---
# <a name="supported-scenarios-for-dual-write-setup"></a>Scénarios pris en charge pour la configuration en double écriture

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Vous pouvez configurer une connexion en double écriture entre un environnement Finance and Operations et un environnement Common Data Service.

+ Un environnement **Finance and Operations** offre la plateforme sous-jacente pour les applications **Finance and Operations** (par exemple, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail et Dynamics 365 Human Resources).
+ Un environnement **Common Data Service** offre à la plateforme sous-jacente les **applications pilotées par modèle dans Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing et Dynamics 365 Project Service Automation).

Le mécanisme de configuration varie en fonction de votre abonnement et de l'environnement.

+ Pour les nouvelles instances des applications Finance and Operations, la configuration d'une connexion en double écriture commence dans Microsoft Dynamics Lifecycle Services (LCS). Si vous avez une licence pour Microsoft Power Platform, vous obtiendrez un nouvel environnement Common Data Service si votre client n'en a pas.
+ Pour les applications Finance and Operations des instances existantes, la configuration d'une connexion en double écriture commence dans l'environnement Finance and Operations.

Les scénarios de configuration suivants sont pris en charge :

+ [Une nouvelle instance d'application Finance and Operations et une nouvelle instance d'application pilotée par modèle](#new-new)
+ [Une nouvelle instance d'application Finance and Operations et une instance d'application pilotée par modèle existante](#new-existing)
+ [Une nouvelle instance d'application Finance and Operations qui a des données de démonstration et une nouvelle instance d'application pilotée par modèle](#new-demo-new)
+ [Une nouvelle instance d'application Finance and Operations qui a des données de démonstration et une instance d'application pilotée par modèle existante](#new-demo-existing)
+ [Une instance d'application Finance and Operations existante et une instance d'application pilotée par modèle existante ou nouvelle](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a>Une nouvelle instance d'application Finance and Operations et une nouvelle instance d'application pilotée par modèle

Pour configurer une connexion en double écriture entre une nouvelle instance d'une application Finance and Operations qui n'a pas de données et une nouvelle instance d'une application pilotée par modèle dans Dynamics 365, suivez les étapes de [Configuration en double écriture de Lifecycle Services](lcs-setup.md). Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :

- Un nouvel environnement Finance and Operations vide est provisionné.
- Une nouvelle instance vide d'une application pilotée par modèle est provisionnée lorsque la solution CRM principale est installée.
- Une connexion en double écriture est établie pour les données de la société DAT.
- Les mappages d'entités sont activés pour la synchronisation en direct.

Les deux environnements sont alors prêts pour la synchronisation des données en direct.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a>Une nouvelle instance d'application Finance and Operations et une instance d'application pilotée par modèle existante

Pour configurer une connexion en double écriture entre une nouvelle instance d'une application Finance and Operations qui n'a pas de données et une instance existante d'une application pilotée par modèle dans Dynamics 365, suivez les étapes de [Configuration en double écriture de Lifecycle Services](lcs-setup.md). Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :

- Un nouvel environnement Finance and Operations vide est provisionné.
- Une connexion en double écriture est établie pour les données de la société DAT.
- Les mappages d'entités sont activés pour la synchronisation en direct.

Les deux environnements sont alors prêts pour la synchronisation des données en direct.

Pour synchroniser les données Common Data Service existantes à l'application Finance and Operations, procédez comme suit.

1. Créez une entreprise dans l'application Finance and Operations.
2. Ajoutez l'entreprise à la configuration de la connexion en double écriture.
3. [Amorcez](bootstrap-company-data.md) les données Common Data Service à l'aide d'un code d'entreprise à trois lettres de l'Organisation internationale de normalisation (ISO).

Étant donné que la double écriture est en mode Synchronisation en direct, la diffusion des données de Common Data Service commence automatiquement vers l'application Finance and Operations.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a>Une nouvelle instance d'application Finance and Operations qui a des données de démonstration et une nouvelle instance d'application pilotée par modèle

Pour configurer une connexion en double écriture entre une nouvelle instance d'une application Finance and Operations contenant des données de démonstration et une nouvelle instance d'une application pilotée par modèle dans Dynamics 365, suivez les étapes dans la section [Une nouvelle instance d'application Finance and Operations et une nouvelle instance d'application pilotée par modèle ](#new-new) précédente dans cette rubrique. Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données de démonstration avec l'application pilotée par modèle, procédez comme suit.

1. Ouvrez l'application Finance and Operations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.
2. Exécutez la fonctionnalité **Synchronisation initiale** pour les entités pour lesquelles vous souhaitez synchroniser les données.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a>Une nouvelle instance d'application Finance and Operations qui a des données de démonstration et une instance d'application pilotée par modèle existante

Pour configurer une connexion en double écriture entre une nouvelle instance d'une application Finance and Operations contenant des données de démonstration et une instance d'une application pilotée par modèle existante dans Dynamics 365, suivez les étapes dans la section [Une nouvelle instance d'application Finance and Operations et une instance d'application pilotée par modèle existante](#new-existing) précédente dans cette rubrique. Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données de démonstration avec l'application pilotée par modèle, procédez comme suit.

1. Ouvrez l'application Finance and Operations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.
2. Exécutez la fonctionnalité **Synchronisation initiale** pour les entités pour lesquelles vous souhaitez synchroniser les données.

Pour synchroniser les données Common Data Service existantes à l'application Finance and Operations, procédez comme suit.

1. Créez une entreprise dans l'application Finance and Operations.
2. Ajoutez l'entreprise à la configuration de la connexion en double écriture.
3. [Amorcez](bootstrap-company-data.md) les données Common Data Service à l'aide du code d'entreprise à trois lettres de l'Organisation internationale de normalisation (ISO).

Étant donné que la double écriture est en mode Synchronisation en direct, la diffusion des données de Common Data Service commence automatiquement vers l'application Finance and Operations.

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a>Une instance d'application Finance and Operations existante et une instance d'application pilotée par modèle existante ou nouvelle

La configuration d'une connexion en double écriture entre une instance existante d'une application Finance and Operations et une instance nouvelle ou existante d'une application pilotée par modèle dans Dynamics 365 se produit dans l'environnement Finance and Operation.

1. Configurez la connexion à partir de l'application Finance and Operations.
2. Pour synchroniser les données Common Data Service existantes avec l'application Finance and Operations, [amorcez](bootstrap-company-data.md) les données Common Data Service à l'aide d'un code d'entreprise ISO à trois lettres.

Étant donné que la double écriture est en mode Synchronisation en direct, la diffusion des données de Common Data Service commence automatiquement vers l'application Finance and Operations.
