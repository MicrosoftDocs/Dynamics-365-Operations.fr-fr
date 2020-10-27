---
title: Consolider les expéditions manuellement à l'aide de la page Consolider les expéditions
description: Cette rubrique présente un scénario dans lequel plusieurs commandes sont validées dans l'entrepôt puis consolidées ultérieurement à l'aide de la page Consolider les expéditions.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: ac60bef797d8e0bbe0d20f1585d5c3c0163f8788
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986790"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a>Consolider les expéditions manuellement à l'aide de la page Consolider les expéditions

[!include [banner](../includes/banner.md)]

Cette rubrique présente un scénario dans lequel plusieurs commandes sont validées dans l'entrepôt puis consolidées ultérieurement à l'aide de la page **Consolider les expéditions**.

## <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Le scénario de cette rubrique fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management. Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l'entité juridique sur **USMF** avant de commencer.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Configurer des stratégies de consolidation d'expédition et des filtres de produits

Le scénario décrit ici suppose que vous avez déjà activé la fonctionnalité, effectué les exercices de la rubrique [Configurer les stratégies de consolidation de l'expédition](configure-shipment-consolidation-policies.md) et créé les stratégies et autres enregistrements qui y sont décrits. Assurez-vous de faire ces exercices avant de continuer avec ce scénario.

## <a name="create-the-sales-orders-for-this-scenario"></a>Créez les commandes client pour ce scénario

Commencez par créer une collection de commandes client avec lesquelles vous pouvez travailler. Vous devez travailler avec un entrepôt activé pour les processus d'entrepôt avancés (WMS). À moins qu'un autre entrepôt ne soit explicitement mentionné, ce même entrepôt doit être utilisé pour chacun des ensembles de commandes suivants.

Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client** et créez une collection de commandes client dont les paramètres sont décrits dans les sous-sections suivantes.

### <a name="create-sales-orders-1-and-2"></a>Créer les commandes client 1 et 2

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-007*
    - **Regroupement :** *ShipCons*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d'article :** *A0001* (un article auquel aucun filtre**Code 4** n'est affecté)
    - **Quantité :** *1.00*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.

### <a name="create-sales-orders-3-and-4"></a>Créer les commandes client 3 et 4

1. Créez deux commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-007*
    - **Regroupement :** Laissez ce champ vide.

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d'article :** *A0001* (un article auquel aucun filtre**Code 4** n'est affecté)
    - **Quantité :** *1.00*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.

## <a name="release-the-orders-to-the-warehouse"></a>Lancer les commandes dans l'entrepôt

Suivez ces étapes pour valider chaque commande client que vous avez créée pour ce scénario dans l'entrepôt.

1. Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client**.
1. Recherchez et sélectionnez la commande client à lancer.
1. Dans le volet Actions, sous l'onglet **Entrepôt**, sélectionnez **Actions \> Lancer dans l'entrepôt** pour lancer la commande client sélectionnée.
1. Répétez cette procédure pour chaque autre commande client que vous avez créée pour ce scénario.

## <a name="consolidate-shipments"></a>Consolider les expéditions

1. Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.
1. Recherchez et sélectionnez un envoi créé lors de la validation de la commande client 1 dans l'entrepôt. (Le champ **Stratégie de consolidation d'expédition** doit être défini sur *Regroupement de commandes*.)
1. Dans le volet Actions, sous l'onglet **Expéditions**, sélectionnez **Expéditions \> Consolider les expéditions**.
1. Vérifiez les expéditions qui sont suggérées pour la consolidation. Une seule expédition ayant la même stratégie doit être suggérée pour la consolidation.
1. Fermez la page **Consolidation des expéditions**.
1. Recherchez et sélectionnez un envoi créé lors de la validation de la commande client 3 dans l'entrepôt. (Le champ **Stratégie de consolidation d'expédition** doit être défini sur *Par défaut*.)
1. Dans le volet Actions, sous l'onglet **Expéditions**, sélectionnez **Expéditions \> Consolider les expéditions**.
1. Vérifiez qu'aucune expédition n'est suggérée pour la consolidation.
1. Sélectionnez **Afficher les filtres**.
1. Dans le volet **Filtres**, supprimez le filtre **Numéro de commande**, puis sélectionnez **Appliquer**.
1. Vérifiez les expéditions qui sont suggérées pour la consolidation. Une seule expédition ayant la même stratégie doit être suggérée pour la consolidation.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Stratégies de consolidation de l'expédition](about-shipment-consolidation-policies.md)
- [Configurer les stratégies de consolidation de l'expédition](configure-shipment-consolidation-policies.md)