---
title: Vue d’ensemble de la double écriture
description: Cet article offre une présentation générale de la double écriture, qui est une infrastructure prête à l’emploi qui fournit une interaction en temps quasi réel entre les applications d’engagement client et les applications de finances et d’opérations.
author: RamaKrishnamoorthy
ms.date: 02/06/2020
ms.topic: overview
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 943607a3ef28db11b7bc7805257914117e6ae38c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289636"
---
# <a name="dual-write-overview"></a>Vue d’ensemble de la double écriture

[!include [banner](../../includes/banner.md)]





## <a name="what-is-dual-write"></a>Qu’est-ce que la double écriture ?

La double écriture est une infrastructure prête à l’emploi qui fournit une interaction en temps quasi réel entre les applications d’engagement client et les applications de finances et d’opérations. Lorsque les données sur les clients, les produits, les personnes et les opérations vont au-delà des limites de l’application, tous les départements d’une organisation sont habilités.

La double écriture offre une intégration bidirectionnelle étroitement couplée entre les applications de finances et d’opérations et Dataverse. Toute modification de données dans les applications de finances et d’opérations provoque des écritures dans Dataverse et toute modification de données dans Dataverse provoque des écritures dans les applications de finances et d’opérations. Ce flux de données automatisé offre une expérience utilisateur intégrée dans les différentes applications.

![Relation de données entre les applications.](media/dual-write-overview.jpg)

La double écriture a deux aspects : un aspect *infrastructure* et un aspect *application*.

### <a name="infrastructure"></a>Infrastructure

L’infrastructure de double écriture est extensible et fiable et comprend les fonctionnalités clés suivantes :

+ Flux de données synchrone et bidirectionnel entre les applications
+ Synchronisation avec les modes lecture, pause et rattrapage pour prendre en charge le système pendant les modes en ligne et hors connexion/asynchrone.
+ Possibilité de synchroniser les données initiales entre les applications
+ Vue combinée des journaux d’activité et d’erreur pour les administrateurs de données
+ Possibilité de configurer des alertes et des seuils personnalisés et de s’abonner aux notifications
+ Interface utilisateur intuitive pour le filtrage et les transformations
+ Possibilité de définir et d’afficher les dépendances et les relations entre les tables
+ Extensibilité pour les tables et les mappages standard et personnalisés
+ Gestion fiable du cycle de vie des applications
+ Expérience de configuration initiale pour les nouveaux clients

### <a name="application"></a>Application

La double écriture crée un mappage entre les concepts des applications de finances et d’opérations et les concepts des applications d’engagement client. Cette intégration prend en charge les scénarios suivants :

+ Données principales client intégrées
+ Accès aux cartes de fidélité et aux points de récompense des clients
+ Expérience de gestion des produits uniformisée
+ Prise en charge de la hiérarchie d’organisation
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


## <a name="top-reasons-to-use-dual-write"></a>Principales raisons d’utiliser la double écriture

La double écriture assure l’intégration des données entre les applications Microsoft Dynamics 365. Cette infrastructure robuste relie des environnements et permet à différentes applications métier de fonctionner ensemble. Voici les principales raisons pour lesquelles vous devez utiliser la double écriture :

+ La double écriture offre une intégration étroitement couplée, en temps quasi réel et bidirectionnelle entre les applications Finances et Opérations et les applications d’engagement client. Cette intégration fait de Microsoft Dynamics 365 un emplacement central pour toutes vos solutions d’entreprise. Les clients qui utilisent Dynamics 365 Finance et Dynamics 365 Supply Chain Management, mais qui utilisent des solutions autres que Microsoft pour la gestion de la relation client, se tournent vers Dynamics 365 pour sa prise en charge de la double écriture.
+ Les données des clients, des produits, des opérations, des projets et de l’Internet des objets (IoT) sont automatiquement envoyées à Dataverse via la double écriture. Cette connexion est utile pour les entreprises intéressées par les extensions Power Platform.
+ L’infrastructure de double écriture suit le principe no-code/low-code. Un effort d’ingénierie minimal est nécessaire pour étendre les mappages entre tables standard et pour inclure des mappages personnalisés.
+ La double écriture prend en charge à la fois le mode en ligne et le mode hors connexion. Microsoft est la seule société qui offre une prise en charge des modes en ligne et hors connexion.

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>Que signifie la double écriture pour les développeurs et les architectes d’applications Customer Engagement ?

La double écriture automatise le flux de données entre les applications de finances et d’opérations et les applications d’engagement client. La double écriture se compose de deux solutions AppSource installées sur Dataverse. Les solutions étendent le schéma de table, les plug-ins et les workflows sur Dataverse afin qu’ils puissent évoluer à la taille de l’ERP. Pour une mise en œuvre réussie, les développeurs et les architectes d’applications d’engagement client doivent comprendre ces changements et collaborer avec leurs homologues sur les applications de finances et d’opérations.

Pour créer la parité avec les applications de finances et d’opérations, la double écriture apporte des changements cruciaux dans le schéma Dataverse. Si vous comprenez le plan, vous pouvez éviter certaines retouches de conception et de développement à l’avenir.

+ Lorsque le package AppSource de double écriture est installé, Dataverse dispose de nouveaux concepts, tels que la société et la partie. Ces concepts aident les applications basées sur Dataverse, y compris Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service et Dynamics 365 Field Service, pour interagir de manière transparente avec les applications de finances et d’opérations.

+ Les activités et les notes sont unifiées et étendues pour prendre en charge à la fois les C1 (utilisateurs du système) et les C2 (clients du système).

+ Pour éviter la perte de données lors de la transmission de devises entre les applications de finances et d’opérations et Dataverse, vous pourrez augmenter le nombre de décimales dans le type de données de devise des applications d’engagement client. La fonctionnalité traduit automatiquement les lignes existants dans le nouvel état étendu au niveau de la couche de métadonnées. Au cours de ce processus, la valeur monétaire est convertie en données décimales plutôt qu’en données monétaires et la valeur monétaire prend en charge 10 décimales. Cette fonctionnalité est une adhésion, et les organisations qui n’ont pas besoin de plus de 4 décimales de précision n’ont pas besoin de l’activer. Pour plus d’informations, voir [Migration de type de données de devise pour la double écriture](currrency-decimal-places.md).

+ [Prise d’effet de date](../../dev-tools/date-effectivity.md) sera ajouté à Dataverse. Elle prendra en charge les données passées, présentes et futures sur la même table.

+ Les [conversions d’unités](../../../../supply-chain/pim/tasks/manage-unit-measure.md) de produit sont prises en charge pour les produits, les devis, les commandes et les factures.

Pour plus d’informations sur les modifications à venir, voir [Nouveautés ou modifications dans la double écriture](whats-new-dual-write.md).



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

