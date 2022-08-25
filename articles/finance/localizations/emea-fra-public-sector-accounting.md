---
title: Comptabilité du secteur public en France
description: Cet article décrit la comptabilité du secteur public en France.
author: brpotter
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: France
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 19621
ms.assetid: f6bfb9dd-c3a7-48d3-b31d-23e6f27c1323
ms.search.industry: Public sector
ms.openlocfilehash: 7b84c523ded7a823f8e90e9e90d1e6a785b5d469
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282416"
---
# <a name="public-sector-accounting-in-france"></a>Comptabilité du secteur public en France

[!include [banner](../includes/banner.md)]

Cet article décrit la comptabilité du secteur public en France.

## <a name="prerequisites"></a>Conditions préalables

Les fonctionnalités dédiées au secteur public français sont disponibles lorsque les conditions suivantes sont remplies :

-   La clé de configuration **Secteur public** et la sous-clé **Réglementation française** sont sélectionnées.
-   L’option **Utiliser les règles comptables du secteur public français** est sélectionnée sur la page **Paramètres de budgétisation**.
-   Le code pays/région par défaut est France.

Les étapes de paramétrage supplémentaires pour les fonctionnalités spécifiques sont traitées dans l’article correspondant à chaque fonctionnalité.

## <a name="french-public-sector-topics"></a>Rubriques relatives au secteur public français
-   [Mandat de paiement](emea-fra-mandats-de-paiement.md) : le directeur utilise le mandat de paiement pour aviser et autoriser le comptable à verser un montant déterminé à une autre entité.
-   [Mises en attente du paiement d’une facture fournisseur](emea-fra-vendor-invoice-payment-holds-public-sector.md) : Les processus standard liés à la mise en attente du paiement de factures fournisseur ont été étendus pour les entités françaises du secteur public.
-   [Titres de recette](emea-fra-titres-de-recette-public-sector.md) : le directeur utilise le titre de recette pour aviser et autoriser le comptable à collecter un montant déterminé d’une autre entité.
-   [Engagements](emea-fra-commitments-public-sector.md) : Les engagements sont utilisés pour réserver des montants budgétisés. Cela permet à une organisation de suivre explicitement des réservations budgétaires à des fins de gestion et de déclaration tout au long du cycle des dépenses.
-   [Approvisionnements](emea-fra-procurement-sourcing-public-sector.md) :
    -   Les fonctionnalités standard associés aux contrats d’achat ont été étendues pour les entités françaises du secteur public. Par exemple, vous pouvez créer des tranches et des lots, contrôler l’accès du département, gérer les certifications de fournisseur, et paramétrer les fournisseurs principaux, les fournisseurs secondaires, et les sous-traitants. Ces capacités vous permettent de répondre aux besoins du Code des marchés publics.
    -   Pour vous conformer aux réglementations du secteur public en France, déterminez des seuils de dépenses pour les achats dans les catégories d’approvisionnement définies par la Clé de Contrôle Marché. Une règle de stratégie **Seuils de dépense par catégorie** utilisée avec vos stratégies d’achat vous permet d’utiliser les attributs de la date d’effet, les montants des dépenses prévues, ainsi que les montants des seuils afin de prendre en charge les pratiques d’approvisionnement requises. La règle de stratégie garantit également l’utilisation efficiente et efficace des fonds publics.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
