---
title: Vue d'ensemble de la double écriture
description: Cette rubrique donne une vue d'ensemble de la double écriture. La double écriture est une infrastructure qui fournit une interaction en temps quasi réel entre les applications pilotées par modèle de Microsoft Dynamics 365 et les applications Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
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
ms.openlocfilehash: 64626ebdd7fbad3d47a4b4c6bbc45bf3bc0c8277
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172782"
---
# <a name="dual-write-overview"></a>Vue d'ensemble de la double écriture

[!include [banner](../../includes/banner.md)]



## <a name="what-is-dual-write"></a>Qu'est-ce que la double écriture ?

La double écriture est une infrastructure prête à l'emploi qui fournit une interaction en temps quasi réel entre les applications pilotées par modèle de Microsoft Dynamics 365 et les applications Finance and Operations. Lorsque les données sur les clients, les produits, les personnes et les opérations vont au-delà des limites de l'application, tous les départements d'une organisation sont habilités.

La double écriture offre une intégration bidirectionnelle étroitement couplée entre les applications Finance and Operations et Common Data Service. Toute modification de données dans les applications Finance and Operations provoque des écritures dans Common Data Service et toute modification de données dans Common Data Service provoque des écritures dans les applications Finance and Operations. Ce flux de données automatisé offre une expérience utilisateur intégrée dans les différentes applications.

![Relation de données entre les applications](media/dual-write-overview.jpg)

La double écriture a deux aspects : un aspect *infrastructure* et un aspect *application*.

### <a name="infrastructure"></a>Infrastructure

L'infrastructure de double écriture est extensible et fiable et comprend les fonctionnalités clés suivantes :

+ Flux de données synchrone et bidirectionnel entre les applications
+ Synchronisation avec les modes lecture, pause et rattrapage pour prendre en charge le système pendant les modes en ligne et hors connexion/asynchrone.
+ Possibilité de synchroniser les données initiales entre les applications
+ Vue consolidée des journaux d'activité et d'erreur pour les administrateurs de données
+ Possibilité de configurer des alertes et des seuils personnalisés et de s'abonner aux notifications
+ Interface utilisateur intuitive pour le filtrage et les transformations
+ Possibilité de définir et d'afficher les dépendances et les relations entre les entités
+ Extensibilité pour les entités et les mappages standard et personnalisés
+ Gestion fiable du cycle de vie des applications
+ Expérience de configuration initiale pour les nouveaux clients

### <a name="application"></a>Application

La double écriture crée un mappage entre les concepts des applications Finance and Operations et les concepts des applications pilotées par modèle de Dynamics 365. Cette intégration prend en charge les scénarios suivants :

+ Données principales client intégrées
+ Accès aux cartes de fidélité et aux points de récompense des clients
+ Expérience de gestion des produits uniformisée
+ Prise en charge de la hiérarchie d'organisation
+ Données principales fournisseur intégrées
+ Accès aux données de référence financières et fiscales
+ Expérience du moteur de tarification à la demande
+ Expérience Prospect en disponibilités intégrée
+ Possibilité de servir à la fois les actifs internes et les actifs client via des agents sur le terrain
+ Expérience Approvisionnement au paiement intégrée
+ Activités et notes intégrées pour les données et les documents du client
+ Possibilité de rechercher la disponibilité et les détails du stock disponible
+ Expérience Projet en disponibilités
+ Possibilité de gérer plusieurs adresses et rôles via le concept de partie
+ Gestion à source unique pour les utilisateurs
+ Canaux intégrés pour la vente au détail et le marketing
+ Visibilité sur les promotions et les remises
+ Fonctions de demande de service
+ Opérations de service simplifiées

## <a name="top-reasons-to-use-dual-write"></a>Principales raisons d'utiliser la double écriture

La double écriture assure l'intégration des données entre les applications Microsoft Dynamics 365. Cette infrastructure robuste relie des environnements et permet à différentes applications métier de fonctionner ensemble. Voici les principales raisons pour lesquelles vous devez utiliser la double écriture :

+ La double écriture offre une intégration étroitement couplée, en temps quasi réel et bidirectionnelle entre les applications Finance and Operations et les applications pilotées par modèle de Dynamics 365. Cette intégration fait de Microsoft Dynamics 365 un emplacement central pour toutes vos solutions d'entreprise. Les clients qui utilisent Dynamics 365 Finance et Dynamics 365 Supply Chain Management, mais qui utilisent des solutions autres que Microsoft pour la gestion de la relation client, se tournent vers Dynamics 365 pour sa prise en charge de la double écriture.
+ Les données des clients, des produits, des opérations, des projets et de l'Internet des objets (IoT) sont automatiquement envoyées à Common Data Service via la double écriture. Cette connexion est très utile pour les entreprises intéressées par les extensions Microsoft Power Platform.
+ L'infrastructure de double écriture suit le principe no-code/low-code. Un effort d'ingénierie minimal est nécessaire pour étendre les mappages entre tables standard et pour inclure des mappages personnalisés.
+ La double écriture prend en charge à la fois le mode en ligne et le mode hors connexion. Microsoft est la seule société qui offre une prise en charge des modes en ligne et hors connexion.

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a>Que signifie la double écriture pour les utilisateurs et les architectes des produits CRM ?

La double écriture automatise le flux de données entre les applications Finance and Operations et Common Data Service. Dans les versions futures, les concepts des applications pilotées par modèle de Dynamics 365 (par exemple, client, contact, devis et commande) seront mis à l'échelle sur les clients milieu de gamme et haut de gamme.

Dans la première version, l'automatisation est gérée en grande partie par des solutions à double écriture. Dans les versions futures, ces solutions feront partie de Common Data Service. En comprenant les modifications à venir dans Common Data Service, vous pouvez vous épargner des efforts à long terme. Voici quelques-une des modifications importantes :

+ Common Data Service aura de nouveaux concepts, comme la société et la partie. Ces concepts affecteront toutes les applications reposant sur Common Data Service, comme Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service et Dynamics 365 Field Service.
+ Les activités et les notes sont unifiées et étendues pour prendre en charge à la fois les C1 (utilisateurs du système) et les C2 (clients du système).
+ Voici quelques-unes des modifications à venir dans Common Data Service :

    - Le type de données Décimal remplacera le type de données Devise.
    - Les dates de validité prendront en charge les données passées, présentes et futures au même emplacement.
    - Il y aura une plus grande prise en charge des devises et des taux de change, et l'API **Taux de change** sera révisée.
    - Les conversions d'unités seront prises en charge.

Pour plus d'informations sur les modifications à venir, voir [Données dans Common Data Service - phase 1 et 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/finance-operations-crossapp-capabilities/data-common-data-service-phase-1).
