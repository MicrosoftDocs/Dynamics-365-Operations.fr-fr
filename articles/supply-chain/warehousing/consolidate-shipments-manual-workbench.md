---
title: Consolider les expéditions à l’aide de l’atelier de consolidation des expéditions
description: Cette rubrique présente un scénario dans lequel plusieurs commandes sont validées dans l’entrepôt puis consolidées en expéditions ultérieurement à l’aide de l’atelier de consolidation des expéditions.
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSShipConsolidationSetShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 29dd403ce2378beb6f4ba71a0b3c0836eed7566a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838416"
---
# <a name="consolidate-shipments-by-using-the-shipment-consolidation-workbench"></a>Consolider les expéditions à l’aide de l’atelier de consolidation des expéditions

[!include [banner](../includes/banner.md)]

Cette rubrique présente un scénario dans lequel plusieurs commandes sont validées dans l’entrepôt puis consolidées en expéditions ultérieurement à l’aide de l’atelier de consolidation des expéditions.

## <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Le scénario de cette rubrique fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management. Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l’entité juridique sur **USMF** avant de commencer.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Configurer des stratégies de consolidation d’expédition et des filtres de produits

Le scénario décrit ici suppose que vous avez déjà activé la fonctionnalité, effectué les exercices de la rubrique [Configurer les stratégies de consolidation de l’expédition](configure-shipment-consolidation-policies.md) et créé les stratégies et autres enregistrements qui y sont décrits. Assurez-vous de faire ces exercices avant de continuer avec ce scénario.

## <a name="turn-on-the-manual-shipment-consolidation-feature"></a>Activer la fonctionnalité de consolidation manuelle des expéditions

Avant de pouvoir utiliser la fonctionnalité *Consolidation manuelle des expéditions*, vous devez l’activer dans votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Consolidation manuelle des expéditions*

Comme mentionné dans [Configurer les stratégies de consolidation de l’expédition](configure-shipment-consolidation-policies.md), vous devez également activer la fonctionnalité *Consolider les expéditions* avant de pouvoir créer des stratégies. Cependant, vous devriez déjà avoir terminé cette étape.

## <a name="create-the-sales-orders-for-this-scenario"></a>Créez les commandes client pour ce scénario

Commencez par créer une collection de commandes client avec lesquelles vous pouvez travailler. Vous devez travailler avec un entrepôt activé pour les processus d’entrepôt avancés (WMS). À moins qu’un autre entrepôt ne soit explicitement mentionné, ce même entrepôt doit être utilisé pour chacun des ensembles de commandes suivants.

Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client** et créez une collection de commandes client dont les paramètres sont décrits dans les sous-sections suivantes.

### <a name="create-order-set-1"></a>Créer le jeu de commandes 1

#### <a name="sales-orders-1-1-and-1-2"></a>Commandes client 1-1 et 1-2

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Mode de livraison :** *Airwa-Air*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.

#### <a name="sales-order-1-3"></a>Commande client 1-3

1. Créez une commande client possédant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Mode de livraison :** *10*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.
1. Ajoutez une deuxième ligne de commande avec les paramètres suivants :

    - **Numéro d’article :** *A0002* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*
    - **Mode de livraison :** *Airwa-Air*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la deuxième ligne de commande.

### <a name="create-order-set-2"></a>Créer le jeu de commandes 2

#### <a name="sales-orders-2-1-and-2-2"></a>Commandes client 2-1 et 2-2

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-002*
    - **Mode de livraison :** *Airwa-Air*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *M9200* (un article où le filtre **Code 4** est défini sur *Inflammable*)
    - **Quantité :** *1.00*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.
1. Ajoutez une deuxième ligne de commande avec les paramètres suivants :

    - **Numéro d’article :** *M9201* (un article où le filtre **Code 4** est défini sur *Explosif*)
    - **Quantité :** *1.00*
    - **Mode de livraison :** *Airwa-Air*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la deuxième ligne de commande.

### <a name="create-order-set-3"></a>Créer le jeu de commandes 3

#### <a name="sales-orders-3-1-and-3-2"></a>Commandes client 3-1 et 3-2

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Demande client :** *1*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.

#### <a name="sales-orders-3-3-and-3-4"></a>Commandes client 3-3 et 3-4

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Demande client :** *2*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.

### <a name="create-order-set-4"></a>Créer le jeu de commandes 4

#### <a name="sales-orders-4-1-and-4-2"></a>Commandes client 4-1 et 4-2

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-003*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.

#### <a name="sales-orders-4-3-and-4-4"></a>Commandes client 4-3 et 4-4

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-004*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.

#### <a name="sales-orders-4-5-and-4-6"></a>Commandes client 4-5 et 4-6

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-007*
    - **Site :** *6*
    - **Entrepôt :** *61*
    - **Regroupement :** *ShipCons*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.

#### <a name="sales-orders-4-7-and-4-8"></a>Commandes client 4-7 et 4-8

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-007*
    - **Site :** *6*
    - **Entrepôt :** *61*
    - **Regroupement :** Laissez ce champ vide.

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.

## <a name="release-the-orders-to-the-warehouse"></a>Lancer les commandes dans l’entrepôt

Suivez ces étapes pour valider chaque commande client que vous avez créée pour ce scénario dans l’entrepôt.

1. Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client**.
1. Recherchez et sélectionnez la commande client à lancer.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Actions \> Lancer dans l’entrepôt** pour lancer la commande client sélectionnée.
1. Répétez cette procédure pour chaque autre commande client que vous avez créée pour ce scénario.

## <a name="consolidate-the-shipments-by-using-the-shipment-consolidation-workbench"></a>Consolider les expéditions à l’aide de l’atelier de consolidation des expéditions

1. Allez dans **Gestion des entrepôts \> Lancement dans l’entrepôt \> Atelier de consolidation des expéditions**.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requête, sur l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne ayant les paramètres suivants sur la grille :

    - **Table :** *Commandes client*
    - **Champ :** *Commande client*
    - **Critères :** Saisissez une liste séparée par des virgules des numéros de commande client pour chaque jeu de commandes que vous avez créé pour ce scénario.

1. Sélectionnez **OK** pour enregistrer votre requête et fermer la boîte de dialogue.
1. Sélectionnez **Consolider les expéditions** dans le volet Actions.
1. Sélectionnez toutes les expéditions, puis sélectionnez **Consolider** sur le volet Actions.

## <a name="verify-the-shipments"></a>Vérifier les expéditions

La procédure suivante vous permet de vérifier les expéditions qui ont été créées ou mises à jour suite à la consolidation des expéditions. Utilisez-la pour passer en revue chaque jeu de commandes que vous avez créé pour ce scénario, puis passez en revue les sous-sections qui suivent pour vous assurer que vous avez obtenu les résultats attendus.

1. Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.
1. Recherchez et sélectionnez l’expédition requise.
1. Si une stratégie de consolidation a été utilisée lors de la création ou de la mise à jour de l’expédition, elle doit apparaître dans le champ **Stratégie de consolidation d’expédition**.

### <a name="related-shipments-for-order-set-1"></a>Expéditions connexes pour le jeu de commandes 1

Deux expéditions sont normalement créées :

- La première expédition contient trois lignes et a été créée à l’aide de la stratégie de consolidation des expéditions *CustomerMode*.
- Le deuxième envoi, qui n’utilise pas le moyen de transport *Avion*, a été créé en utilisant la stratégie de consolidation des expéditions *CustomerOrderNo*.

### <a name="related-shipments-for-order-set-2"></a>Expéditions connexes pour le jeu de commandes 2

Trois expéditions sont normalement créées :

- La première expédition contient les articles *Inflammables*.
- Chacune des deux autres expéditions contient une ligne avec l’article *Explosif*.

### <a name="related-shipments-for-order-set-3"></a>Expéditions connexes pour le jeu de commandes 3

Deux expéditions sont normalement créées :

- La première expédition contient des lignes de commande provenant de la commande client où le champ **Demande client** est défini sur *1*.
- La deuxième expédition contient des lignes de commande provenant de la commande client où le champ **Demande client** est défini sur *2*.

### <a name="related-shipments-for-order-set-4"></a>Expéditions connexes pour le jeu de commandes 4

Quatre expéditions sont normalement créées :

- Les lignes des deux commandes pour le client *US-003* ont été regroupées en une seule expédition à l’aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.
- Les lignes des deux commandes pour le client *US-004* ont été regroupées en une seule expédition à l’aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.
- Les lignes des commandes client 4-5 et 4-6 pour le client *US-007* ont été regroupées en une seule expédition à l’aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.
- Les lignes des commandes client 4-7 et 4-8 pour le client *US-007* ont été regroupées en une seule expédition à l’aide de la stratégie de consolidation des expéditions *CrossOrder*.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Stratégies de consolidation de l’expédition](about-shipment-consolidation-policies.md)
- [Configurer les stratégies de consolidation de l’expédition](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]