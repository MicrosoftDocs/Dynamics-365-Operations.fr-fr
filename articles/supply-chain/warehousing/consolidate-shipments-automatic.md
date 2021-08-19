---
title: Consolider les expéditions lancées dans l’entrepôt à l’aide du lancement automatique de commandes client
description: Cette rubrique présente un scénario dans lequel plusieurs commandes sont lancées dans l’entrepôt dans la même procédure périodique de lancement dans l’entrepôt automatisée.
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: dba864cd11ab9ae7a4ca4c2e2094cbdd066d9ba9a42ddd7d53eebf72955ec191
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716442"
---
# <a name="consolidate-shipments-released-to-the-warehouse-using-automatic-release-of-sales-orders"></a>Consolider les expéditions lancées dans l’entrepôt à l’aide du lancement automatique de commandes client

[!include [banner](../includes/banner.md)]

Cette rubrique présente un scénario dans lequel plusieurs commandes sont lancées dans l’entrepôt dans la même procédure périodique de lancement dans l’entrepôt automatisée. Les commandes seront automatiquement regroupées en expéditions, en fonction de règles définies comme stratégies de consolidation.

Au cours du scénario, vous allez créer des ensembles de commandes client et lancer chaque ensemble dans l’entrepôt. Vous passerez ensuite en revue les envois créés ou mis à jour pendant la consolidation des expéditions, en fonction des stratégies configurées.

## <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Le scénario de cette rubrique fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management. Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l’entité juridique sur **USMF** avant de commencer.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Configurer des stratégies de consolidation d’expédition et des filtres de produits

Le scénario décrit ici suppose que vous avez déjà activé la fonctionnalité, effectué les exercices de la rubrique [Configurer les stratégies de consolidation de l’expédition](configure-shipment-consolidation-policies.md) et créé les stratégies et autres enregistrements qui y sont décrits. Assurez-vous de faire ces exercices avant de continuer avec ce scénario.

## <a name="create-the-sales-orders-for-this-scenario"></a>Créez les commandes client pour ce scénario

Commencez par créer une collection de commandes client avec lesquelles vous pouvez travailler. Vous devez travailler avec un entrepôt activé pour les processus d’entrepôt avancés (WMS). À moins qu’un autre entrepôt ne soit explicitement mentionné, ce même entrepôt doit être utilisé pour chacun des ensembles de commandes suivants.

Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client** et créez une collection de commandes client dont les paramètres sont décrits dans les sous-sections suivantes.

### <a name="create-order-set-1"></a>Créer le jeu de commandes 1

#### <a name="sales-order-1-1"></a>Commande client 1-1

1. Créez une commande client possédant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Mode de livraison :** *Airwa-Air*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

#### <a name="sales-order-1-2"></a>Commande client 1-2

1. Créez une commande client possédant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Mode de livraison :** *Airwa-Air*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

#### <a name="sales-order-1-3"></a>Commande client 1-3

1. Créez une commande client possédant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Mode de livraison :** *10*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

1. Ajoutez une deuxième ligne de commande avec les paramètres suivants :

    - **Numéro d’article :** *A0002* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*
    - **Mode de livraison :** *Airwa-Air*

### <a name="create-order-set-2"></a>Créer le jeu de commandes 2

#### <a name="sales-orders-2-1-and-2-2"></a>Commandes client 2-1 et 2-2

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-002*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *M9200* (un article où le filtre **Code 4** est défini sur *Inflammable*)
    - **Quantité :** *1.00*

1. Ajoutez une deuxième ligne de commande avec les paramètres suivants :

    - **Numéro d’article :** *M9201* (un article où le filtre **Code 4** est défini sur *Explosif*)
    - **Quantité :** *1.00*
    - **Mode de livraison :** *Airwa-Air*

### <a name="create-order-set-3"></a>Créer le jeu de commandes 3

#### <a name="sales-order-3-1"></a>Commande client 3-1

1. Créez une commande client possédant les paramètres suivants :

    - **Compte client :** *US-002*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *M9200* (un article où le filtre **Code 4** est défini sur *Inflammable*)
    - **Quantité :** *1.00*

1. Ajoutez une deuxième ligne de commande avec les paramètres suivants :

    - **Numéro d’article :** *M9201* (un article où le filtre **Code 4** est défini sur *Explosif*)
    - **Quantité :** *1.00*
    - **Mode de livraison :** *Airwa-Air*

> [!NOTE]
> Cette commande est identique aux deux commandes que vous avez créées pour le jeu de commandes 2. Cependant, elle est répertoriée comme son propre ensemble de commandes, car vous la publierez séparément plus tard dans ce scénario.

### <a name="create-order-set-4"></a>Créer le jeu de commandes 4

#### <a name="sales-order-4-1"></a>Commande client 4-1

1. Créez une commande client possédant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Bon de commande client :** *1*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

### <a name="create-order-set-5"></a>Créer le jeu de commandes 5

#### <a name="sales-orders-5-1-and-5-2"></a>Commandes client 5-1 et 5-2

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Demande client :** *2*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

#### <a name="sales-order-5-3"></a>Commande client 5-3

1. Créez une commande client possédant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Bon de commande client :** *1*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

### <a name="create-order-set-6"></a>Créer le jeu de commandes 6

#### <a name="sales-orders-6-1-and-6-2"></a>Commandes client 6-1 et 6-2

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-003*
    - **Demande client :** *2*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

#### <a name="sales-orders-6-3-and-6-4"></a>Commandes client 6-3 et 6-4

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-004*
    - **Demande client :** *1*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

#### <a name="sales-orders-6-5-and-6-6"></a>Commandes client 6-5 et 6-6

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-007*
    - **Site :** *6*
    - **Entrepôt :** *61*
    - **Regroupement :** *ShipCons*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

#### <a name="sales-orders-6-7-and-6-8"></a>Commandes client 6-7 et 6-8

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-007*
    - **Site :** *6*
    - **Entrepôt :** *61*
    - **Regroupement :** Laissez ce champ vide.

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)
    - **Quantité :** *1.00*

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a>Lancement automatique des commandes client dans l’entrepôt

Pour chaque ensemble de commandes client que vous avez créé précédemment, vous devez exécuter une procédure de lancement automatique dans l’entrepôt. Dans chaque cas, vous allez exécuter la [procédure basique de lancement en entrepôt](#release-procedure) qui est fournie ici.

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a>Procédure basique de lancement en entrepôt

Pour chaque ensemble de commandes client que vous avez créé précédemment, vous exécuterez les trois procédures décrites dans les sous-sections suivantes.

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a>Mettre à jour le modèle de vague qui sera utilisé lors du lancement

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.
1. Définissez le champ **Type de modèle de vague** sur *Expédition*.
1. Recherchez et sélectionnez le modèle de vague associé à l’entrepôt que vous avez utilisé dans les jeux de commandes que vous avez créés pour ce scénario. Par exemple, si vous avez utilisé l’entrepôt *24*, sélectionnez le modèle de vague **Expédition par défaut 24**. Si vous avez utilisé l’entrepôt *61*, sélectionnez le modèle de vague **Expédition 61**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Définissez l’option **Traiter la vague à la sortie dans l’entrepôt** sur *Non*.

#### <a name="release-to-the-warehouse"></a>Lancer dans l’entrepôt

1. Allez dans **Gestion des entrepôts \> Lancement dans l’entrepôt \> Lancement automatique des commandes client**.
1. Définissez le champ **Quantité à débloquer** sur *Tout*.
1. Dans le raccourci **Enregistrements à inclure**, sélectionnez **Filtre** pour ouvrir la boîte de dialogue de requête.
1. Dans l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne ayant les paramètres suivants sur la grille :

    - **Table :** *Commandes client*
    - **Table dérivée :** *Commande client*
    - **Champ :** *Commande client*
    - **Critères :** Saisissez une liste séparée par des virgules des numéros de commande client du jeu de commandes souhaité.

1. Cliquez sur **OK** pour enregistrer votre requête.
1. Cliquez sur **OK** pour démarrer la procédure *Lancement automatique dans l’entrepôt*.

#### <a name="review-the-shipment-that-is-created-or-updated"></a>Vérifier l’expédition créée ou mise à jour

1. Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.
1. Recherchez et sélectionnez l’expédition requise.
1. Si une stratégie de consolidation a été utilisée lors de la création ou de la mise à jour de l’expédition, elle doit apparaître dans le champ **Stratégie de consolidation d’expédition**.

### <a name="release-sales-orders-from-order-set-1"></a>Lancer les commandes client du jeu de commandes 1

Suivez la [procédure basique de lancement en entrepôt](#release-procedure) pour libérer les commandes client du jeu de commandes 1.

Lorsque vous avez terminé, vous devriez voir que deux expéditions ont été créées :

- La première expédition contient trois lignes et a été créée à l’aide de la stratégie de consolidation des expéditions *CustomerMode*.
- Le deuxième envoi, qui n’utilise pas le moyen de transport *Avion*, a été créé en utilisant la stratégie de consolidation des expéditions *CustomerOrderNo*.

### <a name="release-sales-orders-from-order-set-2"></a>Lancer les commandes client du jeu de commandes 2

Suivez la [procédure basique de lancement en entrepôt](#release-procedure) pour lancer les commandes client du jeu de commandes 2.

Lorsque vous avez terminé, vous devriez voir que trois expéditions ont été créées :

- La première expédition contient les articles *Inflammables*.
- Chacune des deux autres expéditions contient une ligne avec l’article *Explosif*.

### <a name="release-sales-orders-from-order-set-3"></a>Lancer les commandes client du jeu de commandes 3

Suivez la [procédure basique de lancement en entrepôt](#release-procedure) pour lancer les commandes client du jeu de commandes 3.

Une fois que vous avez terminé, vous devriez voir que les actions suivantes se sont produites :

- Une expédition existante (celle créée lors du lancement du jeu de commandes 2 dans l’entrepôt) a été mise à jour. Une ligne avec l’article *Inflammable* a été ajoutée.
- Une nouvelle expédition a été créée et contient l’article *Explosif*.

### <a name="release-sales-orders-from-order-set-4"></a>Lancer les commandes client du jeu de commandes 4

Suivez la [procédure basique de lancement en entrepôt](#release-procedure) pour lancer les commandes client du jeu de commandes 4.

Lorsque vous avez terminé, vous devriez voir qu’une seule expédition existante (où le champ **Demande client** est défini sur *1*) a été mise à jour. Une nouvelle ligne y a été ajoutée.

### <a name="release-sales-orders-from-order-set-5"></a>Lancer les commandes client du jeu de commandes 5

Suivez la [procédure basique de lancement en entrepôt](#release-procedure) pour lancer les commandes client du jeu de commandes 5.

Une fois que vous avez terminé, vous devriez voir que les actions suivantes se sont produites :

- Une expédition existante (où le champ **Demande client** est défini sur *1*) a été mise à jour. Une ligne de la commande client 5-3 (où le champ **Demande client** est défini sur *1*) y a été ajoutée.
- Une nouvelle expédition a été créée, où les lignes des commandes client 5-1 et 5-2 sont regroupées en une seule expédition.

### <a name="release-sales-orders-from-order-set-6"></a>Lancer les commandes client du jeu de commandes 6

Suivez la [procédure basique de lancement en entrepôt](#release-procedure) pour lancer les commandes client du jeu de commandes 6.

Lorsque vous avez terminé, vous devriez voir que quatre expéditions ont été créées :

- Les lignes des deux commandes pour le client *US-003* ont été regroupées en une seule expédition à l’aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.
- Les lignes des deux commandes pour le client *US-004* ont été regroupées en une seule expédition à l’aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.
- Les lignes des commandes client 6-5 et 6-6 pour le client *US-007* ont été regroupées en une seule expédition à l’aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.
- Les lignes des commandes client 6-7 et 6-8 pour le client *US-007* ont été regroupées en une seule expédition à l’aide de la stratégie de consolidation des expéditions *CrossOrder*.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Stratégies de consolidation de l’expédition](about-shipment-consolidation-policies.md)
- [Configurer les stratégies de consolidation de l’expédition](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]