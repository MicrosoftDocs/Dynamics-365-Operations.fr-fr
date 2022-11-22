---
title: Vue d’ensemble du complément Inventory Visibility
description: Cet article explique ce qu’est la visibilité des stocks et décrit ses fonctionnalités.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: overview
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: dd790bcaada0c1a05e46b4edacaa31fc4e15be92
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762805"
---
# <a name="inventory-visibility-add-in-overview"></a>Vue d’ensemble du complément de visibilité des stocks

[!include [banner](../includes/banner.md)]

Le complément Inventory Visibility (également appelé *Service Inventory Visibility*) fournit un microservice indépendant et hautement évolutif qui permet la validation en temps réel des changements de stock disponible et le suivi de la visibilité sur toutes vos sources de données et tous vos canaux. Il fournit une plateforme qui vous permet de gérer votre stock global à l’aide de fonctionnalités qui incluent (mais ne sont pas limitées à) la liste suivante :

- Suivez de manière centralisée le dernier état des stocks (tel que disponible, commandé, acheté, en transit, retourné et mis en quarantaine) au travers de tous vos sources de données, entrepôts et emplacements en connectant votre Supply Chain Management ou d’autres sources de données logistiques tierces (telles que les systèmes de gestion, les systèmes tiers de planification des ressources d’entreprise \[ERP\], des systèmes de point de vente \[PDV\] et des systèmes de gestion d’entrepôt) au service Inventory Visibility.
- Interrogez la disponibilité et les ruptures de stock disponibles et obtenez des réponses immédiates en appelant directement le service Inventory Visibility.
- Évitez la survente, en particulier lorsque votre demande provient de différents canaux, en effectuant des réservations souples en temps réel dans le service Inventory Visibility.
- Gérez mieux les commandes promises et les attentes des clients en fournissant des dates précises actuelles ou à venir prochainement, de sorte que la fonction de disponibilité à la vente (DAV) omnicanale puisse calculer les dates prévues d’exécution des commandes.

## <a name="extensibility"></a>Extensibilité

Le service Inventory Visibility est hautement extensible, car l’entrée et la sortie des données ne sont pas limitées aux applications Microsoft. Les systèmes externes peuvent accéder au service via des interfaces de programmation d’application (API) RESTful. Outre l’utilisation des mappages prêts à l’emploi fournis pour la source de données et les dimensions de Supply Chain Management, vous pouvez intégrer la Inventory Visibility à plusieurs systèmes tiers en configurant des sources de données supplémentaires, des mesures d’état des stocks (appelées *mesures physiques* dans le service Inventory Visibility) et les dimensions de stock via l’application de configuration. De cette manière, vous pouvez interroger et modifier de manière flexible vos multiples sources de données et vos dimensions de stock prédéfinies.

De plus, étant donné que la Inventory Visibility repose sur Microsoft Dataverse, ses données peuvent être utilisées pour intégrer Power Apps. Vous pouvez également utiliser Power BI pour créer des tableaux de bord personnalisés qui répondent aux besoins de votre entreprise.

## <a name="scalability"></a>Évolutivité

Le service Inventory Visibility peut être étendu ou réduit en fonction de votre volume de données. L’expérience d’évolutivité est généralement transparente et est menée par l’équipe de la plateforme Microsoft, sur la base de la détection et de l’évaluation automatiques de votre volume de données de transaction.

L’illustration suivante présente une vue d’ensemble de l’architecture d’Inventory Visibility.

[<img src="media/inventory-visibility-architecture.png" alt="Inventory Visibility architecture." title="Architecture d’Inventory Visibility" width="720" />](media/inventory-visibility-architecture.png)

## <a name="feature-highlights"></a>Principales fonctionnalités

### <a name="get-a-global-view-of-real-time-inventory"></a>Obtenir une vue globale des stocks en temps réel

La Inventory Visibility garantit que vous avez accès aux quantités de stocks les plus récentes à tout moment, sur tous vos canaux, emplacements et entrepôts. Vous tirez le meilleur parti de son utilisation en soutien de vos activités opérationnelles quotidiennes chaque fois que vous devez obtenir des enregistrements de stock. L’inventaire physique disponible, les quantités vendues et les quantités achetées sont toutes disponibles prêtes à l’emploi. Vous pouvez également configurer d’autres mesures d’inventaire physique (telles que les données sur les articles retournés, mis en quarantaine et validés) selon vos besoins, pour obtenir ces informations en temps réel. La Inventory Visibility peut traiter efficacement des millions de messages de changement des stocks. Ces données peuvent être agrégées et reflétées immédiatement dans les dernières quantités de stock du service, par seconde ou par minute, selon l’intervalle auquel les données sont validées. Pour plus d’informations, voir [API publiques de la Inventory Visibility](inventory-visibility-api.md).

### <a name="central-inventory-adjustment"></a>Ajustement central des stocks

Inventory Visibility permet aux systèmes externes d’appeler son API pour valider des changements dans les stocks. Les changements sont immédiatement visibles dans Inventory Visibility. Par conséquent, les stocks disponibles sont instantanément déduits.

### <a name="soft-reservation-to-avoid-overselling-across-all-order-channels"></a>Réservation provisoire pour éviter la survente sur tous les canaux de commande

Une *réservation provisoire* vous permet d’affecter ou de marquer des quantités spécifiques pour répondre à une commande ou à une demande. Une réservation provisoire n’affecte pas l’inventaire physique, mais elle se déduit de la quantité de stock *disponible à la réservation* et fournit une quantité mise à jour pour l’exécution des commandes futures. Cette fonctionnalité sera utile si des demandes de vente ou des commandes arrivent dans votre entreprise à partir d’un ou plusieurs canaux ou sources de données qui se trouvent en dehors de votre système de planification des ressources d’entreprise (ERP) du système d’enregistrement.

Si vous n’utilisez pas les réservations provisoires dans le service Inventory Visibility, vous devez attendre que la commande soit synchronisée avec et traitée par votre système ERP pour obtenir une mise à jour de la quantité de stocks physiques. Ce processus a généralement une latence énorme. Cependant, les réservations provisoires prennent effet immédiatement chaque fois qu’une demande de vente ou une commande est générée dans vos canaux de vente. Par conséquent, elles aident à prévenir les situations de survente en garantissant que vos commandes omnicanales n’interféreront pas les unes avec les autres lorsqu’elles atteindront finalement le système ERP. Les réservations provisoires garantissent également que vous pouvez exécuter toutes les commandes que vous avez promises. Par conséquent, elles vous aident à répondre aux attentes des clients et à les fidéliser. Pour plus d’informations, voir [Réservation dans la visibilité des stocks](inventory-visibility-reservations.md).

### <a name="immediate-response-of-atp-quantity-and-dates"></a>Réponse immédiate des dates et de la quantité DAV

La visibilité de votre stock projeté dans un avenir proche (tenant compte des informations d’offre, de demande et de stock disponible projeté) est importante, car elle aide votre entreprise à atteindre les objectifs suivants :

- Réduire les niveaux de stock pour réduire les coûts de gestion des stocks.
- Faciliter le traitement des commandes internes, afin que les commerciaux puissent calculer les dates d’expédition et de livraison, en fonction de la disponibilité des produits commandés.
- Assurer la transparence quant au moment où les clients peuvent s’attendre à ce qu’un article en rupture de stock devienne disponible, en indiquant la prochaine date de disponibilité.

La fonctionnalité DAV est facile à adopter dans votre processus quotidien de traitement des commandes. Plus important encore, comme les autres offres de la Inventory Visibility, la fonctionnalité DAV est *globale et en temps réel*. Par conséquent, vous pouvez configurer plusieurs formules de calcul de la DAV pour avoir des requêtes de disponibilité complète des stocks qui couvrent tous vos canaux commerciaux et sources de données. Pour plus d’informations, voir [Plannings de changement du stock disponible et disponibilité à la vente de la Inventory Visibility](inventory-visibility-available-to-promise.md).

### <a name="preallocate-your-stock-to-important-channels-or-customers-with-inventory-allocation"></a>Préaffectez votre stock à des canaux ou à des clients importants avec la répartition des stocks

La fonctionnalité de répartition Inventory Visibility permet de protéger et de réserver votre stock disponible pour les canaux, groupes de clients ou emplacements importants. Une fois le stock affecté, la consommation des stocks est limitée au pool affecté et les quantités restantes dans le pool sont déduites en temps quasi réel pour refléter la quantité encore disponible. Pour plus d’informations, voir [Répartition de stock pour Inventory Visibility](inventory-visibility-allocation.md).

### <a name="compatibility-with-wms-items"></a>Compatibilité avec les articles WMS

Microsoft vise à fournir une intégration prête à l’emploi avec les processus de gestion des entrepôts, afin que les clients de la WMS puissent également profiter des avantages du service de visibilité des stocks. Selon la version de la 1e vague de lancement 2022 (version préliminaire publique en mars), le service d’inventaire prend en charge les requêtes de disponibilité des stocks WMS et DAV. La fonctionnalité de répartition et de réservation provisoire sera prise en charge pour les clients WMS dans la prochaine vague. Pour plus d’informations, voir [Prise en charge de la Inventory Visibility pour les articles WMS](inventory-visibility-whs-support.md).

L’illustration suivante présente un résumé de haut niveau des fonctionnalités existantes et de la façon dont elles peuvent être positionnées dans le flux de données.

[<img src="media/inventory-visibility-feature-overview.png" alt="Inventory Visibility feature overview." title="Vue d’ensemble des fonctionnalités Inventory Visibility" width="720" />](media/inventory-visibility-feature-overview.png)

## <a name="licensing"></a>Gestionnaire de licences

Le service Inventory Visibility est disponible dans les versions suivantes :

- **Complément Inventory Visibility pour Microsoft Dynamics 365 Supply Chain Management** : pour les entreprises disposant d’une licence Supply Chain Management valide, Inventory Visibility est disponible sans frais supplémentaires. Inventory Visibility étant un complément basé sur Microsoft Power Platform, il dépend de la capacité de stockage et des limites de l’API de Microsoft Power Platform. Votre licence Supply Chain Management doit inclure le stockage par défaut et la capacité de l’API. Si vous avez besoin de plus de capacité de stockage et de l’API, achetez une licence professionnelle. Pour plus de détails sur la répartition de l’API par défaut et la licence professionnelle, voir [Demander des limites et des répartitions](/power-platform/admin/api-request-limits-allocations) et [Présentation des licences pour Microsoft Power Platform](/power-platform/admin/pricing-billing-skus). Avec les répartitions du stockage et de l’API par défaut, vous pouvez commencer à utiliser le complément Inventory Visibility dès aujourd’hui. Pour plus de détails sur l’installation, voir [Installer et configurer la Inventory Visibility](inventory-visibility-setup.md). Si votre utilisation estimée de l’API et du stockage dépasse la répartition standard, contactez votre représentant commercial et demandez-lui de contacter l’équipe de la plateforme pour une exception.
- **Service Inventory Visibility en tant que composant d’IOM** – Cette version est destinée aux clients de Intelligent Order Management (IOM) ou aux entreprises qui n’utilisent pas Supply Chain Management comme système ERP. La licence est incluse dans le bundle Intelligent Order Management. Pour plus d’informations, voir [Présentation de Intelligent Order Management](/dynamics365/intelligent-order-management/overview).

## <a name="inventory-visibility-terminology"></a>Terminologie d’Inventory Visibility

Il est important de bien comprendre les concepts et les termes suivants lorsque vous utilisez le complément Inventory Visibility :

- **Source de données** : elle représente le système d’où proviennent vos données.
- **Dimensions** : elles identifient les caractéristiques du produit. Il peut s’agir de dimensions de stockage (comme le site ou l’entrepôt) ou de dimensions de produit (comme la couleur, la taille ou le style).
- **Mesures physiques** : quantités qui mesurent différents statuts de stocks, à savoir Disponible, Acheté, En commande ou Vendu.
- **Mesures calculées** : mesures quantitatives calculées à partir d’un ensemble de mesures physiques. Par exemple, la mesure calculée *Total disponible* est calculée de la manière suivante : *Disponible* +  *Acheté* – *En commande* – *Vendu*.
- **Partition** : elle définit une hiérarchie pour la distribution des données reçues par Inventory Visibility. Actuellement, la partition par défaut est le site et l’emplacement.
- **Hiérarchie d’index** : elle définit davantage le mode d’interrogation des stocks et d’obtention de résultats plus granulaires.

Pour plus d’informations sur ces termes et concepts, voir [Configurer Inventory Visibility](inventory-visibility-configuration.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
