---
title: Génération d'états de canal en ligne
description: Cette rubrique décrit la procédure de génération d’états pour votre canal en ligne dans Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3ec93bd8ef8dea6ca979dee1819a9c9abcc38a2e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251479"
---
# <a name="generate-online-channel-reports"></a>Génération d’états de canal en ligne


[!include [banner](includes/banner.md)]

Cette rubrique décrit la procédure de génération d’états pour votre canal en ligne dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Vous pouvez générer et afficher plusieurs états dans Commerce pour voir comment votre canal en ligne fonctionnement.

## <a name="channel-summary-report"></a>État de synthèse du canal

Le rapport **Synthèse de canal** affiche une synthèse des transactions suivantes pour le canal sélectionné :

- Transactions de vente
- Transactions de paiement
- Transactions de taxe
- Transactions avec remise

Pour générer un rapport de **Synthèse de canal**, procédez comme suit.

1. Aller à **Retail et Commerce \> Recherches et états \> États des ventes \> État récapitulatif de canal**.
1. Entrez une date dans le champ **Date de début**.
1. Entrez une date dans le champ **Date de fin**.
1. Dans le champ **Canal**, sélectionnez le canal en ligne.
1. Cliquez sur **OK**.
 
## <a name="channel-sales-by-year-report"></a>État des ventes de canal par année 

Le rapport **Ventes du canal par an** affiche une comparaison des ventes année après année pour un magasin spécifique. Vous sélectionnez l'année par rapport à laquelle comparer les ventes, et l'état compare les ventes de l'année sélectionnée avec celle de l'année précédente.

Pour générer un rapport de **Ventes du canal par an**, procédez comme suit.

1. Aller à **Retail et Commerce \> Recherches et états \> États des ventes \> État des ventes de canal par année**.
1. Dans le champ **De l'année civile**, entrez une année.
1. Dans le champ **À l'année civile**, entrez une année.
1. Dans le champ **Canal**, sélectionnez le canal en ligne.
1. Cliquez sur **OK**.

## <a name="channel-sales-by-hour-report"></a>État des ventes de canal par heure

Le rapport **Ventes du canalisez par heure** affiche les mesures de ventes par heure pour un canal ou une unité opérationnelle sélectionnée.

Pour générer un rapport de **Ventes du canal par heure**, procédez comme suit.

1. Aller à **Retail et Commerce \> Recherches et états \> États des ventes \> État des ventes de canal par heure**.
1. Entrez une date dans le champ **Date de début**.
1. Entrez une date dans le champ **Date de fin**.
1. Dans le champ **Canal**, sélectionnez le canal en ligne.
1. Cliquez sur **OK**.

## <a name="top-customers-report"></a>État des principaux clients

Le rapport **Principaux clients** afficher des mesures des ventes des *N* clients principaux pour un canal ou une unité opérationnelle sélectionnée. La valeur *N* est un nombre de 10 à 100 basé sur une mesure agrégée sélectionnée par l'utilisateur.

Pour générer un rapport de **Principaux clients**, procédez comme suit.

1. Aller à **Retail et Commerce \> Recherches et états \> États des ventes \> État des principaux clients**.
1. Entrez une date dans le champ **Date de début**.
1. Entrez une date dans le champ **Date de fin**.
1. Dans le champ **Canal**, sélectionnez le canal en ligne.
1. Cliquez sur **OK**.

## <a name="top-discounts-report"></a>État Principales remises

Le rapport **Principales remises** afficher des mesures des ventes des *N* remises principales pour un canal ou une unité opérationnelle sélectionnée. La valeur *N* est un nombre de 10 à 100 basé sur une mesure agrégée sélectionnée par l'utilisateur.

Pour générer un rapport de **Principales remises**, procédez comme suit.

1. Aller à **Retail et Commerce \> Recherches et états \> États des ventes \> État Principales remises**.
1. Entrez une date dans le champ **Date de début**.
1. Entrez une date dans le champ **Date de fin**.
1. Dans le champ **Canal**, sélectionnez le canal en ligne.
1. Cliquez sur **OK**.

## <a name="top-products-report"></a>État Principaux produits

Le rapport **Principaux produits** afficher des mesures des ventes des *N* produits principaux pour un canal ou une unité opérationnelle sélectionnée. La valeur *N* est un nombre de 10 à 100 basé sur une mesure agrégée sélectionnée par l'utilisateur.

Pour générer un rapport de **Principaux produits**, procédez comme suit.

1. Aller à **Retail et Commerce \> Recherches et états \> États des ventes \> État Principaux produits**.
1. Entrez une date dans le champ **Date de début**.
1. Entrez une date dans le champ **Date de fin**.
1. Dans le champ **Canal**, sélectionnez le canal en ligne.
1. Cliquez sur **OK**.

## <a name="category-sales-report"></a>État des ventes par catégorie

Le rapport **Ventes par catégorie** affiche les mesures des ventes au cours d'une période sélectionnée pour chaque nœud d'une hiérarchie de catégories pour un canal ou une unité opérationnelle sélectionnée.

Pour générer un rapport de **Ventes par catégorie**, procédez comme suit.

1. Accédez à **Retail et Commerce \> Recherches et états \> États des ventes \> État des ventes par catégorie**.
1. Entrez une date dans le champ **Date de début**.
1. Entrez une date dans le champ **Date de fin**.
1. Dans le champ **Canal**, sélectionnez le canal en ligne.
1. Cliquez sur **OK**.

## <a name="organization-sales-report"></a>État des ventes d'organisation

Le rapport **Ventes de l'organisation** affiche les performances de vos magasins de vente par unité d'organisation. Cet état inclut la quantité et le montant vendus par magasin, et la marge bénéficiaire de chaque magasin. L'unité d'organisation est basée sur la hiérarchie par défaut de génération d'états.

Pour générer un rapport **Ventes par catégorie**, procédez comme suit.

1. Accédez à **Retail et Commerce \> Recherches et états \> États des ventes \> État des ventes d'organisation**.
1. Entrez une date dans le champ **Date de début**.
1. Entrez une date dans le champ **Date de fin**.
1. Cliquez sur **OK**.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Page d'accueil de Commerce](../retail/index.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]