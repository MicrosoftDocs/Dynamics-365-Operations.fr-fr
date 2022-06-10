---
title: Validation du pourcentage d’écart de coût standard
description: Cette rubrique fournit des informations sur la configuration des profils de validation pour le coût standard.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: bc4f1bd7c1bf7a8f214f20460b10d371d8f3c790
ms.sourcegitcommit: 1ea145dc606e243c7f51d91a5c0dd9e385bbda4a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "8804608"
---
# <a name="standard-cost-variance-posting"></a>Validation du pourcentage d’écart de coût standard

Lorsque vous utilisez la valorisation standard pour un ou plusieurs produits de votre organisation, vous devez configurer les [conditions préalables au calcul des coûts standard](/supply-chain/cost-management/prerequisites-standard-costs.md). Cette rubrique explique les comptes de validation requis pour l’étape 3 des conditions préalables, "Affecter des comptes généraux aux validations d’article liées aux écarts de coût standard".

Différents types d’écarts peuvent survenir pour les achats et les ordres de fabrication. Pour des exemples d’écarts de production, voir [Sources courantes d’écarts de production](/supply-chain/cost-management/common-sources-of-production-variances.md). Des écarts de prix de bon de commande se produisent lorsque vous utilisez le coût standard pour un article acheté, et il existe une différence entre le coût standard du produit et le montant facturé sur le bon de commande.

## <a name="sample-posting-profile-configuration"></a>Exemple de configuration de profil de publication

Le tableau suivant montre des exemples de types de validation par défaut. Il comprend des exemples de comptes principaux et des descriptions.

- La colonne « Débit/crédit ? » indique si la transaction est généralement un débit ou un crédit. Dans certains cas, une transaction peut afficher soit des débits, soit des crédits.
- La colonne "Compte de compensation" indique que le type de comptabilisation est un compte de compensation. En d’autres termes, le montant qui est enregistré sur ce compte est automatiquement annulé lorsqu’une transaction ultérieure est enregistrée.
- La colonne "P/F" indique le type d’affichage. "P" représente l’affichage physique et "F" représente l’affichage financier.
- La colonne "Suivre" indique si le compte principal du type de validation est généralement le même que le compte principal d’un autre type de validation. Plus précisément, il indique le type de validation généralement utilisé pour la validation.

> [!NOTE]
> Les comptes principaux et les noms des comptes principaux dans le tableau sont des suggestions. Nous vous recommandons de travailler avec votre comptable pour déterminer la meilleure configuration pour les besoins de votre entreprise.

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit ? | Compte de compensation | P/F | Suivre | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-----|--------|-------------|
| Écart de prix d’achat | 510310 | Écart de prix d’achat | Dépenses | Soit | N° | V | Non applicable | Ce compte est utilisé lorsqu’il existe un écart entre le prix d’achat et le coût standard d’un bon de commande. |
| Réévaluation du coût de stock | 510330 | Réévaluation du coût de stock | Dépenses | Soit | N° | V | Non applicable | Ce compte est utilisé lorsqu’une nouvelle version d’évaluation des coûts est activée pour un article de coût standard afin de réévaluer le stock disponible. |
| Écart de modification des coûts | 510320 | Écart de modification des coûts | Dépenses | Soit | N° | V | Non applicable | Ce compte est utilisé lorsqu’il existe une différence de coûts standard entre les sites, ou lorsqu’un article est retourné et qu’il y a un changement entre le coût standard d’origine et le coût standard actuel d’un produit. |
| Écart de taille de lot de production | 510370 | Écart de taille de lot de production | Dépenses | Soit | N° | V | Non applicable | Ce compte est utilisé lorsqu’il existe des différences entre la base de calcul de la nomenclature (BOM) et la quantité réelle pour le calcul du coût de l’ordre de fabrication. |
| Écart de prix de production | 510340 | Écart de prix de production | Dépenses | Soit | N° | V | Non applicable | Ce compte est utilisé lorsqu’il existe des différences de prix entre le coût estimé et le coût réel d’un ordre de fabrication. |
| Écart de quantité de production | 510350 | Écart de quantité de production | Dépenses | Soit | N° | V | Non applicable | Ce compte est utilisé lorsqu’il existe des différences de quantité entre le coût estimé et les coûts réels d’un ordre de fabrication. |
| Écart de substitution de production | 510360 | Écart de substitution de production | Dépenses | Soit | N° | V | Non applicable | Ce compte est utilisé lorsqu’il y a une consommation inattendue sur un ordre de fabrication. |
| Écart d’arrondi | 618160 | Différence d’arrondi | Dépenses | Soit | N° | V | Non applicable | Ce compte est utilisé lorsqu’il existe une différence d’arrondi lorsque les coûts de production sont calculés à partir des coûts standard. |
