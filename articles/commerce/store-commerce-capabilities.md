---
title: Fonctionnalités de l’application Store Commerce
description: Cet article décrit les fonctionnalités disponibles dans l’application Store Commerce pour Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2022-09-30
ms.openlocfilehash: d713cc0e9537ae20ffddee6e77779a16e74bd779
ms.sourcegitcommit: eb9a53d5cf10f1ada68757536d6a94b2cb00929d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725635"
---
# <a name="store-commerce-app-capabilities"></a>Fonctionnalités de l’application Store Commerce

[!include [banner](includes/banner.md)]

L’application Store Commerce est l’application de point de vente (PDV) moderne pour Microsoft Dynamics 365 Commerce. Elle permet aux entreprises de traiter les transactions en magasin et de gérer les opérations back-office telles que l’inventaire et le traitement des commandes. L’application permet également aux entreprises de gérer la relation client au travers de la fidélisation et de la gestion des clients. 

Appuyée sur Commerce Scale Unit (CSU), l’application Store Commerce fournit une solution omnicanale complète. Par exemple, un client peut acheter un produit en ligne et le retirer dans un magasin à proximité, poursuivant ainsi son parcours d’achat à travers les canaux sans perdre aucune donnée. 

Cet article fournit une vue d’ensemble des fonctionnalités de l’application Store Commerce.

## <a name="platform"></a>Plateforme

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Omnicanal | Dynamics 365 Commerce fournit une solution omnicanale complète qui unifie le back-office, le magasin, le centre d’appels et les expériences numériques. | [Vue d’ensemble](index.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/dynamics-365-commerce-overview-november-2-2020) |
| Commerce administré à distance | Commerce Scale Unit héberge le moteur de commerce sans affichage. Le moteur de commerce sans affichage constitue le point central pour toute la logique métier du commerce et alimente une solution omnicanale complète. | <p>[Vue d’ensemble de l’architecture](commerce-architecture.md)</p><p>[Architecture sans affichage](dev-itpro/retail-server-architecture.md)</p> | [Entretien sur la technologie](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-commerce-architecture-overview-december-4-2020) |
| Commerce Headquarters | Commerce headquarters fournit des fonctionnalités de back-office qui permettent la configuration des produits, des employés, des processus métier, de la tarification et d’autres fonctionnalités nécessaires à l’entreprise. | [Vue d’ensemble de l’architecture](commerce-architecture.md) | |
| Point de vente (PDV) | L’application Store Commerce est l’expérience de point de vente pour Dynamics 365 Commerce. Elle délivre des fonctionnalités de point de vente complètes et riches qui aident les vendeurs, les caissiers et les responsables à fournir un service client de qualité supérieure. En outre, elle fournit plusieurs options de déploiement aux détaillants, contribue à améliorer les performances et offre une meilleure gestion du cycle de vie des applications (ALM). | [Application Store Commerce](dev-itpro/store-commerce.md) | <p>[Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/modernize-the-dynamics-365-commerce-in-store-technology-using-the-new-store-commerce-app-march-30-2022)</p><p>[Vidéo](https://youtu.be/7B332XH_zfs)</p><p>[Migration de MPOS vers Store Commerce](dev-itpro/pos-extension/migrate-mpos-store-commerce.md)</p> |
| Déploiement cloud | Plusieurs instances Commerce Scale Unit peuvent être déployées pour la répartition de la charge et la proximité géographique. | [Déploiement Cloud](../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md) | |
| Déploiement local | À l’aide d’un déploiement de données métier local, les clients de Commerce peuvent mieux posséder et gérer leur un environnement Dynamics 365. | [Déploiement local](../fin-ops-core/dev-itpro/deployment/deploy-retail-onprem.md) | |

## <a name="device-management"></a>Gestion des périphériques

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Plusieurs facteurs de forme | L’application Store Commerce est prise en charge sur plusieurs facteurs de forme d’appareils, tels que les PC, les tablettes et les appareils mobiles. L’interface utilisateur (UI) réactive permet de redimensionner automatiquement la mise en page et de l’adapter à la taille de l’écran. | [Configurations visuelles](pos-screen-layouts.md) | |
| Multiplateforme | L’application Store Commerce est prise en charge sur les plateformes Web, Windows, iOS et Android. | [Plateformes](dev-itpro/hybridapp.md) | |
| Stratégie de marque | Le concepteur d’écran vous permet de personnaliser les dispositions d’écran pour répondre aux besoins de votre entreprise. De plus, vous pouvez créer des thèmes, des mises en page, des couleurs et des images en fonction des rôles des employés, puis les partager avec les utilisateurs pour obtenir cohérence de marque et facilité d’utilisation. | [Configurations visuelles](pos-screen-layouts.md) | [Vidéo](https://www.youtube.com/watch?v=ldqCw2wf5fY) |
| Topologie | Différentes topologies en magasin sont prises en charge, en fonction de la disponibilité du réseau. | <p>[Topologie](dev-itpro/retail-modern-pos-architecture.md)</p><p>[Infographie](dev-itpro/retail-in-store-topology.md)</p> | |
| Gestion de plusieurs périphériques | Il est possible de gérer facilement de nombreux appareils dans différents magasins depuis Commerce headquarters. | [Activation](set-up-activation-accounts-validate-devices-hq.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/commerce-mass-deployment-with-sccm-system-center-configuration-manager-october-6-2022) |

## <a name="employee-management"></a>Gestion des employés

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Connexion | Chaque employé du magasin peut avoir une connexion dédiée. Les types de connexion incluent le nom d’utilisateur, le code-barres, le lecteur de bande magnétique (MSR), la biométrie et Azure Active Directory (Azure AD). | <p>[Azure AD](aad-pos-logon.md)</p><p>[Connexion étendue](extended-logon.md)</p> | |
| Autorisations | Différents niveaux d’autorisations sont pris en charge pour les employés, tels que l’autorisation de créer des commandes et l’autorisation de modifier des commandes. | [Autorisations](tasks/create-pos-permission-groups.md) | |
| Gestion des horaires et de la présence | La présence peut être gérée à l’aide de la fonction Time Clock (Horloge de pointage). Les données de présence peuvent être traitées au niveau de la paie à l’aide de l’application Dynamics 365 Human Resources. | [Gestion des horaires](retail-time-attendance.md) | |
| Commission sur les ventes | Les ventes peuvent être suivies par le commercial pour calculer des commissions ou d’autres primes. | [Commission](pos-sales-groups-track-commissions.md) | |

## <a name="merchandising"></a>Promotion des ventes

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Gestion des assortiments | Les responsables du merchandising peuvent assortir les produits afin qu’ils soient disponibles à la vente dans un canal spécifique et pendant une période spécifique. | [Assortiments](assortments.md) | |
| Catalogues | Les responsables du merchandising peuvent gérer des catalogues pour identifier les produits que vous souhaitez proposer avec des prix spécifiques au catalogue. | [Catalogues](/dynamicsax-2012/appuser-itpro/about-retail-product-catalogs) | |
| Gestion des produits et des catégories | Dans Commerce headquarters, les responsables du merchandising peuvent créer des produits qui ont des variantes, des attributs, une unité de mesure, etc. Ils peuvent également définir une hiérarchie des catégories pour organiser les produits. | [Produit](retail-hierarchies.md) | |
| Offres groupées | Les responsables du merchandising peuvent regrouper les produits afin qu’ils soient vendus sous forme de lot ou de kit. | [Kits](/dynamicsax-2012/appuser-itpro/about-setting-up-retail-product-kits) | |
| Codes info | Utilisez les codes info pour demander au caissier d’entrer des informations au cours de diverses actions au PDV, tels que les ventes d’article, les retours d’article, ou la sélection de clients. | [Codes info](/dynamicsax-2012/appuser-itpro/about-info-codes-retail) | |
| Articles associés | Utilisez les articles associés pour réaliser une vente incitative de produits lorsqu’un article est ajouté à la transaction. | [Articles associés](/dynamicsax-2012/appuser-itpro/set-up-products-for-cross-selling-and-up-selling) | |
| Garanties | Les garanties prolongées peuvent être vendues avec les produits. | [Garantie](extended-warranty.md) | |
| Impression d’étiquettes | Il est possible de générer des étiquettes contenant des informations sur le produit telles que le numéro de lot, le numéro de série et la date d’expiration. | [Impression d’étiquettes](/dynamicsax-2012/appuser-itpro/create-and-print-labels-overview) | |

## <a name="assisted-selling"></a>Vente assistée

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Parcours de produit | Parcourir les produits par catégorie. | [Hiérarchie de produit](retail-hierarchies.md) | |
| Recherche de produits | Recherchez des produits par nom et affinez les recherches en utilisant des attributs de produit tels que la marque, le prix et le matériau. Cette fonctionnalité est optimisée par Azure Cognitive Search. | [Recherche dans le cloud](cloud-powered-search-overview.md) | |
| Page Détails de produit | Les pages détaillées sur les produits peuvent inclure des images, une description, des attributs de produit et des produits recommandés. Les recommandations sont alimentées par le service Recommandations. | | |
| Comparaison de produits | Comparez plusieurs produits et aidez les clients à en choisir un et à l’ajouter à une transaction. | | |
| Allée sans fin | Consultez facilement le stock d’autres magasins et créez des commandes. | [Recherche de stock](pos-inventory-lookup-operation.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Recommandations | Effectuez des ventes incitatives et des ventes croisées à l’aide du service Recommandations. Ce service utilise une technologie brevetée pour suggérer des recommandations basées sur les tendances d’achat et des caractéristiques telles que les nouveautés, les looks similaires et les meilleures ventes. Ces recommandations sont disponibles sur les pages de détails des produits, la page **Détails du client** et la page **Transactions**. | [Recommandations](product-recommendations.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-recommendations-march-2-2021) |

## <a name="customer-relationship"></a>Relation client

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Gestion des clients | Créez, modifier et gérez les comptes client. Les comptes clients peuvent être gérés en mode asynchrone pour éviter le traitement en temps réel. | [Gestion](customer-mgmt-stores.md) | |
| Attributs du client | La structure des attributs client permet de capturer des données supplémentaires liées au client en fonction des besoins de l’entreprise. | [Attributs](dev-itpro/customer-attributes.md) | |
| Page Détails du client | Une riche page de détails sur le client offre une vue omnicanale des interactions du client sur tous les canaux. Ces interactions incluent les achats, les listes de souhaits et les points de fidélité. | | |
| Recherche de clients dans le cloud | Recherchez des clients par nom, numéro de téléphone, adresse e-mail, carte de fidélité, adresse, etc. | [Recherche dans le cloud](pos-search-improvements.md#customer-search) | |
| Fidélité et récompenses | Les clients peuvent rejoindre des programmes de fidélité et gagner et échanger des points de fidélité sur tous les canaux. | [Fidélité](set-up-customer-loyalty-program.md) | |
| Gestion des clients | Gérez les clients clés à l’aide d’un registre client et suivez les activités et les notes sur le profil du client. L’intégration de Dynamics 365 Customer Insights permet aux employés du magasin d’obtenir des indices sur la prochaine meilleure action pour chaque client. | [Gestion des clients](clienteling-overview.md#activities-and-notes) | |

## <a name="pricing-and-discounts"></a>Tarification et remises

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Accords commerciaux | Les responsables de la tarification peuvent utiliser des accords commerciaux pour définir des prix spéciaux basés sur des offres à long terme pour des clients spécifiques. | [Tarification](price-management.md)| [Vidéo](https://www.youtube.com/watch?v=r2VD8IxHesM) |
| Contrats de vente | Les responsables de la tarification peuvent utiliser des accords commerciaux pour définir des prix contractuels dans les scénarios de commerce interentreprises (B2B). | [Tarification](price-management.md) | |
| Ajustements de prix | Les responsables de la tarification peuvent utiliser la fonction d’ajustement de prix pour créer, suivre et gérer les réductions de prix pour leurs produits au fil du temps. | [Ajustements de prix](price-adjustments-discounts.md) | |
| Remises | Les responsables de la tarification peuvent configurer plusieurs types de remises pour exécuter une variété de promotions. Ces remises comprennent les remises simples, les remises sur quantité, les remises de seuil, les remises sur les assortiments, les remises basées sur le mode de paiement et les remises sur l’expédition. | [Remises](retail-discounts-overview.md) | |
| Coupons | Les responsables de la tarification peuvent configurer des codes de coupon ou des codes-barres, les lier à des remises et les distribuer aux clients. Les vendeurs peuvent ajouter des coupons aux transactions de vente ou les supprimer. | [Coupons](coupons.md) | |
| Groupes de prix | Les responsables de la tarification peuvent utiliser la fonctionnalité de groupe de prix pour définir des prix contextuels basés sur des canaux, des catalogues, des affiliations ou des programmes de fidélité. | [Tarification](price-management.md) | |
| Promotions disponibles | Les vendeurs peuvent facilement rechercher les promotions disponibles pour les produits du magasin, les produits qui ont été ajoutés à une transaction, etc. | [Fonctions de tarification](pos-pricing-functions.md) | |
| Vérifications de prix | Les vendeurs peuvent consulter rapidement les prix de vente actifs des produits dans le magasin. | [Fonctions de tarification](pos-pricing-functions.md) | |
| Remplacements de prix | Les vendeurs qui disposent des autorisations requises peuvent remplacer les prix configurés par le système ou calculés. | [Fonctions de tarification](pos-pricing-functions.md) | |
| Remises manuelles | Les vendeurs qui disposent des autorisations requises peuvent appliquer des remises manuelles aux transactions de vente ou aux lignes de vente. | [Fonctions de tarification](pos-pricing-functions.md) | |

## <a name="electronic-payments"></a>Paiements électroniques

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Crédit et débit | L’application Store Commerce prend en charge les principaux paiements par carte de crédit via la passerelle de paiement Adyen et l’exécution des commandes via PayPal. Le kit de développement logiciel Paiements permet des connexions de passerelle externe prises en charge par les intégrations de fournisseurs de logiciels indépendants (ISV). | <p>[Adyen](dev-itpro/adyen-connector.md?tabs=10-0-23)</p><p>[PayPal](paypal.md)</p><p>[Paiements](payment-methods.md)</p> | <p>[Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-configuration-february-9-2021)</p><p>[Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-overview-processing-february-4-2021)</p> |
| Prise en charge du portefeuille numérique | L’application Store Commerce prend en charge les paiements via des méthodes de portefeuille numérique qui n’utilisent pas les plages de numéros d’identification bancaire (BIN) comme le font les cartes de crédit traditionnelles. Les méthodes de paiement peuvent être associées à des paiements par portefeuille numérique tels qu’Adyen. | [Portefeuille](wallets.md) | |
| Prise en charge des cartes cadeaux | Carte cadeau Dynamics 365 avec Numéro d’identification bancaire, Solutions de valeur stockée (SVS) et cartes-cadeaux Givex. Les cartes cadeaux peuvent être achetées et échangées lors d’une commande. | [Cartes cadeaux](dev-itpro/gift-card.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/d365-commerce-internal-gift-cards-november-16-2021) |
| Protection contre la fraude | Dynamics 365 Fraud Protection vous aide à prévenir les activités frauduleuses et à identifier les endroits où la fraude pourrait passer inaperçue. | [Fraud Protection](dev-itpro/dfp.md) | [Vidéo](https://www.youtube.com/watch?v=j_1nEiq3LfM) |

## <a name="taxes-and-charges"></a>Taxes et frais

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Taxes | L’application Store Commerce prend en charge de nombreux types de taxes indirectes, tels que la taxe, la taxe sur la valeur ajoutée (VAT), la Taxe sur les Produits et Services (GST), les frais basés sur l’unité et la retenue à la source. | [Taxes](/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json) | |
| Frais | Les frais peuvent être configurés au niveau de la ligne, au niveau de l’en-tête, en tant que frais automatiques, par canal, etc. | [Frais](omni-auto-charges.md) | |

## <a name="order-processing-and-fulfillment"></a>Traitement et exécution de commande

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Création de commande | Une commande peut être créée pour être expédiée ou récupérée dans un magasin à proximité. Il est possible d’indiquer des créneaux horaires pour le retrait. | [Vue d’ensemble](customer-orders-overview.md) | |
| Modification de commande | Une commande peut être modifiée, retournée, annulée, etc. | <p>[Annuler](customer-orders-overview.md#cancel-a-customer-order)</p><p>[Retours](pos-returns.md)</p> | |
| Recherche | Recherchez et filtrez les commandes à l’aide d’informations spécifiques à la commande. | [Recherche](enhancedorderrecall.md) | |
| Attributs de commande | La structure des attributs de commande permet de capturer des informations supplémentaires liées à la commande en fonction des besoins de l’entreprise. | [Attributs](dev-itpro/order-attributes.md) | |
| Livraison directe | Les articles peuvent être marqués pour la livraison directe par un fournisseur à une adresse client. La livraison directe est également connue sous le nom de parachutage. | [Livraison directe](/dynamics365/supply-chain/sales-marketing/tasks/ship-orders-direct-deliveries) | |
| Devis | Les employés du magasin peuvent créer des devis pour les clients et peuvent spécifier un prix spécial, des remises manuelles et une date de validité du devis. | [Devis](/dynamics365/supply-chain/sales-marketing/tasks/create-edit-sales-quotations) | |
| Exécution | Les magasins peuvent prélever, emballer et expédier les commandes. Un bon de livraison peut être ajouté aux colis prêts à être expédiés. | [Exécution](order-fulfillment-overview.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-supporting-buy-online-pickup-in-store-curbside-with-dynamics-365-commerce-pos-february-3-2021) |
| Gestion des commandes distribuées | L’application Store Commerce prend en charge l’optimisation intelligente de l’exécution des commandes, où des stratégies commerciales peuvent être configurées en fonction de la nature de l’entreprise, du type de client, de l’origine d’une commande et du mode de livraison d’une commande. | [DOM](dom.md) | |

## <a name="inventory-management"></a>Gestion des stocks

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Réassort magasin | Rationalisez la distribution des stocks disponibles d’un centre de distribution vers plusieurs magasins ou entrepôts. | [Réassort magasin](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Cross-docking | Rationalisez la distribution des stocks sur les bons de commande entrants vers plusieurs magasins ou entrepôts. | [Cross-docking](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Stock entrant | Recevez le stock d’un fournisseur via un bon de commande ou d’un autre entrepôt via un ordre de transfert. Créez un bon de commande entrant ou une demande d’ordre de transfert. | [Entrant(e)](pos-inbound-inventory-operation.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Stock sortant | Expédiez le stock vers un autre entrepôt via un ordre de transfert et créez une demande d’ordre de transfert sortant. | [Sortant(e)](pos-outbound-inventory-operation.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Recherche de stock | Vérifiez le stock disponible des produits dans les magasins et les entrepôts, et vérifiez le stock disponible à la promesse (ATP) à des dates futures. | [Recherche de stock](pos-inventory-lookup-operation.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Ajustement de stock | Ajustez le stock entrant ou sortant d’un entrepôt de magasin pour répondre aux besoins spécifiques de l’entreprise sans utiliser de vente, de réception ou de recomptage. | [Ajustement de stock](work-with-store-inventory.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Inventaires | Dénombrez le stock physique et ajustez le stock de comptabilité du système en conséquence. | [Comptage](work-with-store-inventory.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Mouvement de stock | Déplacez du stock entre les emplacements d’un magasin. | [Mouvement](work-with-store-inventory.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |

## <a name="financials"></a>Finances

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Gestion des disponibilités | L’application Store Commerce prend en charge la gestion des espèces et d’autres modes de paiement spécifiés dans le magasin. De plus, le rapprochement des équipes dans le magasin peut être activé pour les fonctionnalités avancées de gestion de trésorerie. | [Monétaire](cash-mgmt.md) | |
| Tableaux d’analyse et rapprochement | Les transactions en espèces et transactionnelles pour un magasin sont enregistrées dans Commerce headquarters via les processus de validation des relevés. | [Relevés](retail-statements.md) | |
| Transactions de revenus et de dépenses | Traitez les transactions de fonds de caisse dans le magasin et enregistrez les revenus qui ne proviennent pas des voies traditionnelles, tels que l’argent perdu et trouvé, la part des recettes d’une cafétéria dans le hall et les services de nettoyage des tapis. | [Relevés](retail-statements.md) | |
| Paiement des factures | Saisissez les paiements par rapport aux factures. | [Facture](payinvoice.md) | |

## <a name="employee-productivity"></a>Productivité des employés

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Gestion des tâches | Créez des listes de tâches et des tâches, et attribuez-les aux magasins et aux employés. Suivez le statut des tâches dans les magasins. L’intégration parfaite avec Microsoft Teams est assurée. | <p>[Gestion des tâches](task-mgmt-overview.md)</p><p>[Microsoft Teams](commerce-teams-integration.md)</p> | [Vidéo](https://www.youtube.com/watch?v=ES1whB4C2lU) |

## <a name="hardware-and-peripherals"></a>Matériel et périphériques

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Connecter des périphériques | Connectez des périphériques tels que des imprimantes, des tiroirs-caisses, des scanners et des appareils de paiement à un terminal de PDV. | [Périphériques](retail-peripherals-overview.md) ||
| Partager des périphériques | Les imprimantes de reçus, les tiroirs-caisses et les appareils de paiement peuvent être partagés entre plusieurs terminaux en les connectant à une station matérielle partagée. | <p>[Station matérielle](retail-peripherals-overview.md) ||
| Simulateur de PDV et de périphérique | Le simulateur de périphérique prend en charge le test de scénarios qui nécessitent des périphériques de PDV physiques. Il comprend également un simulateur de PDV qui permet de tester la compatibilité des périphériques physiques avec sans devoir déployer le client du PDV. | [Simulateur](dev-itpro/retail-peripheral-simulator.md) | |

## <a name="receipts"></a>Accusés de réception

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Impression des tickets de caisse | Les reçus de différents types, tels que les tickets de caisse, les reçus de carte de crédit, les reçus de cadeau et les factures, peuvent être imprimés par défaut ou après confirmation du caissier à la caisse. Ils peuvent également être réimprimés à partir du journal. | [Impression](receipt-templates-printing.md) | |
| Réceptions d’e-mail | Les reçus peuvent être envoyés par e-mail à partir du point de vente une fois le paiement effectué. | [Adresse e-mail](email-receipts.md) | |
| Conception des reçus | Les reçus de magasin peuvent être personnalisés afin de présenter des données et des mises en page adaptées au détaillant et au type de transaction. Les reçus peuvent également être étendus afin d’afficher les données personnalisées requises par le détaillant. | [Conception](receipt-templates-printing.md) | |

## <a name="offline-support"></a>Prise en charge hors connexion

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Hors connexion transparente | Le mode hors connexion transparente vous permet de continuer à effectuer des transactions même lorsque la connectivité Internet est limitée ou indisponible. L’exclusion de données vous aide à réduire la taille des bases de données hors connexion et à optimiser les performances. | [Hors connexion](pos-operations.md) | |
| Basculement basé sur les performances | Passez en mode hors connexion lorsqu’une dégradation des performances est détectée. | [Hors connexion](dev-itpro/implementation-considerations-offline.md) | [Vidéo](https://youtu.be/sQU-2pgHToI) |
| Tableau de bord hors connexion | Le tableau de bord **Statut hors connexion** affiche le statut hors connexion, les erreurs et les détails des données pour chaque appareil. Par conséquent, il est facile de gérer le statut de nombreux appareils. | [Hors connexion](dev-itpro/implementation-considerations-offline.md) | [Vidéo](https://youtu.be/sQU-2pgHToI)|

## <a name="extensibility"></a>Extensibilité

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Commerce Headquarters | Les solutions Commerce headquarters peuvent être personnalisées en ajoutant ou en modifiant des processus métier. Commerce headquarters prend en charge l’utilisation de métadonnées et d’un modèle d’extension basé sur du code pour ajouter des fonctionnalités personnalisées. Il peut être facilement intégré dans des solutions externes. | [Vue d’ensemble](dev-itpro/extend-customer-cdx-package.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-unlock-the-power-of-dynamics-365-commerce-commerce-extensibility-overview-february-23-2021) |
| Commerce sans affichage | Le cadre d’API Omnicanal extensible peut être utilisé pour personnaliser et ajouter une logique métier. Les API dotées de gestionnaires de requêtes et de schémas d’extension pré-déclenchement et post-déclenchement. | [CSU](dev-itpro/retail-server-customer-consumer-api.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| Kit de développement logiciel Commerce | Le kit de développement logiciel Commerce inclut le code, des exemples de code, des modèles et les outils nécessaires pour étendre ou personnaliser les fonctionnalités de Dynamics 365 Commerce. Le kit de développement logiciel est publié dans différents référentiels dans GitHub, en fonction des composants d’extension. | [Kit de développement logiciel (SDK)](dev-itpro/retail-sdk/sdk-github.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| Point de vente | L’application Store Commerce peut être étendue indépendamment à l’aide de la fonction d’extension de PDV du kit de développement logiciel Commerce. La structure prend en charge la personnalisation de l’expérience utilisateur (UX), des workflows et de la logique métier. | [PDV](dev-itpro/pos-extension/pos-extension-overview.md) | [Entretien sur la technologie](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |

## <a name="reporting"></a>Déclaration

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Etats des ventes | Des rapports de ventes par membre du personnel, caisse enregistreuse, type de paiement, retours, produit, etc. sont disponibles pour les gérants de magasin. Les responsables peuvent consulter ces rapports et les utiliser pour allouer des commissions et identifier les tendances des produits. | | |

## <a name="diagnostics"></a>Diagnostics

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Operational Insights | Les mesures de fiabilité et de performance de l’intégrité du service organisé par le magasin sont disponibles dans l’abonnement Application Insights. Des fonctionnalités de surveillance et d’alertes avancées sont disponibles. | | |
| Contrôle d’intégrité | La disponibilité des périphériques connectés à un point de vente peut être vérifiée en exécutant l’opération de contrôle d’intégrité. Les problèmes de périphériques individuels peuvent ensuite être résolus et vérifiés. | [Contrôle d’intégrité](pos-healthcheck.md) | [Vidéo](https://www.youtube.com/watch?v=RfPDNmnqYvY) |

## <a name="globalization"></a>Mondialisation

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Prise en charge multi-marchés | Les fonctionnalités spécifiques au marché telles que l’intégration fiscale, la taxe sur les biens et services, la facturation avancée et les acomptes de paiement sont prises en charge immédiatement. Cette fonctionnalité couvre plusieurs marchés en Europe, en Amérique du Nord et en Amérique du Sud, en Russie, en Asie, en Arabie Saoudite, etc. | [Mondialisation](localizations/fiscal-integration-for-retail-channel.md) | |

## <a name="compliance"></a>Conformité

| Capacité | Description | Documentation | Contenu supplémentaire |
|---|---|---|---|
| Normes Microsoft | L’application Store Commerce respecte les normes Microsoft en matière de sécurité, de confidentialité, d’accessibilité, le Règlement général sur la protection des données (RGPD), la délimitation des données de l’Union européenne (UE), etc. | | |

