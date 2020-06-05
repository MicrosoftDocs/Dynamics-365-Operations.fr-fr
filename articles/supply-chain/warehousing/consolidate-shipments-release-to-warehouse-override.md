---
title: Consolider les expéditions lorsque la stratégie de consolidation de l'expédition est remplacée à partir de la page Lancement dans l'entrepôt
description: Cette rubrique présente un scénario dans lequel une ou plusieurs lignes de vente doivent être validées manuellement dans l'entrepôt à partir de la page Lancement dans l'entrepôt et la stratégie de consolidation des expéditions définie par le système doit être remplacée avant la libération.
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
ms.author: v-olbara
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 23379b76367336157edad1bf2e534bf0f10799cb
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383772"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden-from-the-release-to-warehouse-page"></a>Consolider les expéditions lorsque la stratégie de consolidation de l'expédition est remplacée à partir de la page Lancement dans l'entrepôt

[!include [banner](../includes/banner.md)]

Cette rubrique présente un scénario dans lequel une ou plusieurs lignes de vente doivent être validées manuellement dans l'entrepôt à partir de la page **Lancement dans l'entrepôt** et la stratégie de consolidation des expéditions définie par le système doit être remplacée avant la libération. Un remplacement de la stratégie de consolidation des expéditions peut être nécessaire si, par exemple, une commande qui n'est généralement pas consolidée avec des expéditions en cours doit être consolidée avec des expéditions en cours.

Au cours du scénario, vous allez créer un ensemble de commandes client, puis remplacer la stratégie de consolidation des expéditions par défaut avant de lancer les commandes dans l'entrepôt.

## <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Le scénario de cette rubrique fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management. Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l'entité juridique sur **USMF** avant de commencer.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Configurer des stratégies de consolidation d'expédition et des filtres de produits

Le scénario décrit ici suppose que vous avez déjà activé la fonctionnalité, effectué les exercices de la rubrique [Configurer les stratégies de consolidation de l'expédition](configure-shipment-consolidation-policies.md) et créé les stratégies et autres enregistrements qui y sont décrits. Assurez-vous de faire ces exercices avant de continuer avec ce scénario.

## <a name="create-the-sales-orders-for-this-scenario"></a>Créez les commandes client pour ce scénario

1. Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client** et créez trois commandes client identiques ayant les paramètres suivants :

    - **Compte client :** *US-002*

1. Ajoutez une ligne de commande possédant les paramètres suivants :

    - **Numéro d'article :** *A0001* (un article auquel aucun filtre**Code 4** n'est affecté)
    - **Quantité :** *1.00*

1. Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a>Validez les commandes client depuis la page Lancement dans l'entrepôt

Suivez ces étapes pour remplacer la stratégie de consolidation des expéditions lors du lancement dans l'entrepôt.

1. Allez dans **Gestion des entrepôts \> Lancement dans l'entrepôt \> Lancement dans l'entrepôt**.
1. Dans le volet supérieur, sélectionnez la première commande client que vous avez créée pour ce scénario.
1. Sélectionnez **Ajouter** pour ajouter la ligne dans le cadre du lancement dans l'entrepôt. Notez que la stratégie de consolidation d'expédition *Par défaut* est appliquée dans le volet inférieur.
1. Dans le volet inférieur, sélectionnez **Sélectionner une nouvelle stratégie de consolidation des expéditions**.
1. Sélectionnez une stratégie qui permet la consolidation avec d'autres expéditions en cours de la même stratégie. Par exemple, sélectionnez la stratégie *CustomerOrderNo*.
1. Sélectionnez **Lancement dans l'entrepôt**.
1. Sélectionnez la deuxième et la troisième commande client que vous avez créée pour ce scénario.
1. Sélectionner **Ajouter** pour ajouter les lignes dans le cadre du lancement dans l'entrepôt. Notez que la stratégie *Par défaut* est appliquée dans le volet inférieur.
1. Sélectionnez la deuxième ligne, puis, dans le champ **Sélectionner une nouvelle stratégie de consolidation des expéditions**, sélectionnez la stratégie *CustomerOrderNo*.
1. Sélectionnez **Lancement dans l'entrepôt** pour les deux lignes.

## <a name="verify-the-shipments"></a>Vérifier les expéditions

Deux expéditions sont normalement créées :

- La première expédition contient deux lignes et a été créée à l'aide de la stratégie de consolidation des expéditions *CustomerOrderNo*.
- La deuxième expédition contient une ligne et a été créée à l'aide de la stratégie de consolidation des expéditions *Par défaut*.

Suivez ces étapes pour examiner les expéditions qui ont été créées.

1. Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.
1. Recherchez et sélectionnez l'expédition requise.
1. Dans le champ **Stratégie de consolidation d'expédition**, consultez la stratégie de consolidation utilisée lors de la création de l'expédition.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Stratégies de consolidation de l'expédition](about-shipment-consolidation-policies.md)
- [Configurer les stratégies de consolidation de l'expédition](configure-shipment-consolidation-policies.md)
