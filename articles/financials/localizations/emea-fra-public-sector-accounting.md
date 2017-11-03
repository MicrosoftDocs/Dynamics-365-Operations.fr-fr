---
title: "Comptabilité du secteur public en France"
description: "Cet article décrit la comptabilité du secteur public en France."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 19621
ms.assetid: f6bfb9dd-c3a7-48d3-b31d-23e6f27c1323
ms.search.region: France
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5a29c1a9911c95acd2f8d13d7ba779a72dec456f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="public-sector-accounting-in-france"></a>Comptabilité du secteur public en France

[!include[banner](../includes/banner.md)]


Cet article décrit la comptabilité du secteur public en France.

<a name="prerequisites"></a>Conditions préalables
-------------

Les fonctionnalités dédiées au secteur public français sont disponibles lorsque les conditions suivantes sont remplies :

-   La clé de configuration **Secteur public** et la sous-clé **Réglementation française** sont sélectionnées.
-   L'option **Utiliser les règles comptables du secteur public français** est sélectionnée sur la page **Paramètres de budgétisation**.
-   Le code pays/région par défaut est France.

Les étapes de paramétrage supplémentaires pour les fonctionnalités spécifiques sont traitées dans l'article correspondant à chaque fonctionnalité.

## <a name="french-public-sector-topics"></a>Rubriques relatives au secteur public français
-   [Mandats de paiement](emea-fra-mandats-de-paiement.md) Le directeur utilise le mandat de paiement pour informer le comptable que l'organisation doit payer un montant spécifique à une autre entité et pour autoriser le comptable à payer ledit montant.
-   [Mises en attente du paiement d'une facture fournisseur](emea-fra-vendor-invoice-payment-holds-public-sector.md) Les processus standard liés aux mises en attente du paiement de factures fournisseur ont été étendus pour les entités françaises du secteur public.
-   [Titres de recette](emea-fra-titres-de-recette-public-sector.md) Le directeur utilise le titre de recette pour informer le comptable que l'organisation est autorisée à recouvrer un montant spécifique auprès d'une autre entité et autoriser le comptable à recouvrer ledit montant.
-   [Engagements](emea-fra-commitments-public-sector.md) Les engagements permettent de réserver des montants budgétés afin qu'une organisation puisse explicitement effectuer le suivi des réservations budgétaires à des fins de gestion et de déclaration tout au long du cycle des dépenses.
-   [Approvisionnements](emea-fra-procurement-sourcing-public-sector.md)
    -   Les fonctionnalités standard associés aux contrats d'achat ont été étendues pour les entités françaises du secteur public.  Par exemple, vous pouvez créer des tranches et des lots, contrôler l'accès du département, gérer les certifications de fournisseur, et paramétrer les fournisseurs principaux, les fournisseurs secondaires, et les sous-traitants. Ces capacités vous permettent de répondre aux besoins du Code des marchés publics.
    -   Pour vous conformer aux réglementations du secteur public en France, il se peut que vous deviez déterminer des seuils de dépenses pour les achats dans les catégories d'approvisionnement définies par la Clé de Contrôle Marché. Une règle de stratégie **Seuils de dépense par catégorie** utilisée avec vos stratégies d'achat vous permet d'utiliser les attributs de la date d'effet, les montants des dépenses prévues, ainsi que les montants des seuils afin de prendre en charge les pratiques d'approvisionnement requises et de garantir l'utilisation efficace et effective des fonds publics.





