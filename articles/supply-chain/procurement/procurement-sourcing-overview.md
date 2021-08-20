---
title: Présentation des approvisionnements
description: Cet article fournit une vue d’ensemble de la fonctionnalité disponible dans le module Approvisionnement.
author: kamaybac
ms.date: 05/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogListPage, CatVendorCatalogListPage, PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "58021"
- intro-internal
ms.assetid: eea24e23-a803-4de0-a218-6485757cde1b
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4ed0ffa7b1e0b48008d4192d9d9a471158dc430d2013740074a6563168ed7194
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775625"
---
# <a name="procurement-and-sourcing-overview"></a>Présentation des approvisionnements

[!include [banner](../includes/banner.md)]

Cet article fournit une vue d’ensemble de la fonctionnalité disponible dans le module Approvisionnement.

Le module Approvisionnements couvre toutes les étapes : identification d’un besoin de produit et de services, approvisionnement du produit, réception, facturation et traitement du paiement des fournisseurs. Les processus d’approvisionnement peuvent être configurés en fonction des besoins spécifiques en définissant des stratégies et des workflows d’achat.

## <a name="identifying-a-need-for-product-and-services"></a>Identification d’un besoin de produit et services

Le besoin de produits ou de services peut venir de *demandes*, par exemple, lorsqu’un employé a besoin d’un produit. Des *catalogues de produits* peuvent être paramétrés pour guider la sélection sur des produits disponibles, ou des demandes peuvent être effectuées pour les produits qui ne sont pas encore à disposition dans un catalogue, ce qui permet au département des achats de prendre en considération la manière dont le produit peut être fourni.  

Des *Plafonds de dépenses* peuvent être utilisés pour limiter le montant de la demande, puis le *workflow d’achat* ajoute l’option de demande d’approbation avant que la commande soit passée. Il est également possible de spécifier la répartition des fonds budgétaires, le cas échéant.  

Le département d’approvisionnement identifie les fournisseurs pour les biens et services nécessaires, et cela peut impliquer qu’une *demande de devis* soit envoyée à plusieurs fournisseurs potentiels. Il est possible de partager les spécifications du produit demandé que les fournisseurs potentiels peuvent afficher pour voir s’ils peuvent fournir un produit conforme. Les fournisseurs retournent leurs offres qui sont alors examinées par le département d’approvisionnement afin de sélectionner le fournisseur auprès duquel se fournir.  

Les commandes fournisseur incluent une option pour envoyer au fournisseur une *demande de renseignements sur les achats* au lieu d’un processus plus complet de demande de devis. La demande de renseignements sur les achats peut être utilisée pour établir des conditions comme les prix, les remises, ainsi que la date de livraison de la commande. Si les fournisseurs sont paramétrés pour utiliser le portail **Fournisseur**, la fonctionnalité de demande de renseignements sur les achats est désactivée. À la place la commande est partagée dans le portail **Fournisseur** et lorsqu’une *demande de confirmation* est envoyée, le fournisseur peut directement confirmer la commande.  

Des *Catalogues fournisseur* peuvent être utilisés pour collecter des informations sur l’assortiment de produits que les fournisseurs peuvent fournir. Les fournisseurs peuvent publier leur propre catalogue, ce qui simplifie la mise à jour du catalogue. Il est possible d’associer une *liste des fournisseurs agréés* à un produit, ce qui permet de guider la sélection du fournisseur lorsque de nouvelles commandes fournisseur sont ouvertes, et d’empêcher l’utilisation de fournisseurs non souhaités.

## <a name="procurement"></a>Approvisionnement

Les *commandes fournisseur* peuvent être créées de différentes manières, notamment :

- Comme résultat de la planification qui a identifié une demande nécessitant un achat. Ce processus génère des commandes fournisseur prévisionnelles, et lorsque celles-ci sont lancées, les commandes fournisseur sont générées.
- Via le traitement des demandes d’achat qui entraîne un approvisionnement.
- Via le traitement des contrats d’achat, où les commandes fournisseur sont créées en tant que commandes lancées à partir de contrats. Cela est utilisée couramment lorsque des contrats d’achat servent à représenter des commandes globales.
- Manuellement, lorsque la commande fournisseur créée n’est pas basée sur un autre document.

Les commandes fournisseur configurées avec des *workflows d’approbation d’achat* requièrent une approbation pour être enregistrées comme approuvées, ce qui est obligatoire pour que la commande soit traitée plus avant.

Les commandes fournisseur sont *confirmées* pour représenter qu’un accord a été établi avec le fournisseur. La commande fournisseur progressera ensuite progressivement via différents états jusqu’à ce qu’elle soit finalement facturée ou annulée.  

Lorsque vous créez une commande fournisseur, de nombreux champs sont prérenseignés avec des valeurs par défaut provenant des informations sur le fournisseur enregistrées dans la page **Fournisseurs**. Cela signifie qu’il existe un nombre limité de champs que vous devez renseigner sur la commande fournisseur, bien que vous puissiez choisir de remplacer les valeurs par défaut.

### <a name="prices-and-discounts"></a>Prix et remises

Prix et remises comprend des informations sur les prix, les remises, ainsi que les conditions de remise offertes. Les prix et remises peuvent être représentés sous forme d’*accords commerciaux*. Les accords commerciaux représentent les listes des prix du fournisseur avec les prix ou les remises, avec un ensemble spécifique de dates pendant lesquelles l’accord est valide. Les prix et les remises peuvent être négociées et représentés par des *contrats d’achat* stipulant des conditions comme l’engagement d’acheter certains volumes ou montants en devises comme prérequis des conditions négociées. Des *Accords de remise* peuvent être créés avec des fournisseurs dans lesquels l’approvisionnement de produits ou de groupes de produits spécifiques peut déclencher une remise du fournisseur en fonction du montant ou du volume d’achat.

### <a name="delivery-options"></a>Options de livraison

Il existe différentes options du processus de livraison associé à une commande fournisseur. Les produits commandés peuvent être répartis en programmes de *livraison*, dans lesquels des parties de la quantité commandée peuvent être planifiées pour la livraison à des dates différentes. La livraison peut également inclure la *livraison directe* initialisée à partir d’une commande client, qui automatise la génération du bon de livraison sur la commande client en même temps que l’enregistrement de l’accusé de réception de marchandises dans la commande fournisseur. Les commandes fournisseur peuvent également faire partie d’une chaîne de *commandes intersociétés*, également appelées commandes fournisseur intersociétés, dans lesquelles les produits sont commandés à partir d’une commande client intersociétés correspondante. Dans ce cas, certaines étapes sont automatiques entre les deux commandes intersociétés associées.

### <a name="supplementary-items"></a>Articles supplémentaires

Les produits peuvent être paramétrés pour inclure des *articles supplémentaires*. Il s’agit de proposer des produits liés au produit commandé. Les produits supplémentaires peuvent être obligatoires ou facultatifs. Dans certains cas, les articles supplémentaires peuvent être ajoutés en tant que produits gratuits qui accompagnent l’achat d’autres produits.

### <a name="purchase-order-charges"></a>Frais de commande fournisseur

Des frais peuvent être associés à la commande fournisseur. Cela peut se produire automatiquement via la définition des frais automatiques ou en ajoutant les frais manuellement. Les frais peuvent être associés à la commande au niveau de l’en-tête ou de la ligne de commande. La comptabilité des frais peut être paramétrée de différentes manières. Par exemple, vous pouvez paramétrer des frais à comptabiliser comme coût de produit. Si vous effectuez cela, les frais doivent être affectés au niveau de la ligne de commande avant que la commande ne puisse être confirmée. Il existe une option qui peut vous aider à répartir les frais entre l’en-tête de commande et les lignes.

## <a name="product-receipt-and-invoicing"></a>Accusé de réception de marchandises et facture

Les commandes fournisseur incluant des produits physiques requièrent généralement qu’un *enregistrement d’arrivée* soit effectué dans un entrepôt, et qu’ensuite un *accusé de réception de marchandises* soit enregistré pour la commande. Les commandes fournisseur avec des produits qui honorent des demandes peuvent être configurées de sorte que l’employé qui a demandé les produits doive également fournir une *confirmation de réception*.  

Certaines commandes fournisseur incluent des produits qui sont des services ou d’autres produits non physiques pour lesquels la réception dans un entrepôt n’est pas nécessaire. Les produits peuvent être créés en tant que services ou des *catégories d’approvisionnement* peuvent être utilisées directement sur la commande fournisseur pour de telles commandes. Avec ces commandes, la prise en compte de l’accusé de réception de marchandises est parfois ignorée et la commande est facturée directement, autrement, l’enregistrement de l’accusé de réception de marchandises est effectué sur la commande fournisseur sans enregistrement d’arrivée précédent.  

L’accusé de réception de marchandises peut provoquer la consommation automatique à des fins spécifiques. Cela inclut la consommation implicite avec la livraison directe, la consommation pour un projet ou la comptabilisation du produit en tant qu’immobilisation.  

Lorsque des *factures fournisseur* arrivent de la part du fournisseur, elles peuvent d’abord être enregistrées dans le *registre des factures* indépendamment de la commande fournisseur, puis être ultérieurement approuvées comme enregistrement correspondant à la commande fournisseur. Enregistrer la facture fournisseur avec la commande fournisseur inclut la mise en correspondance de l’accusé de réception de marchandises avec la facture.  

Des *répartitions comptables* peuvent être spécifiées dans la commande fournisseur pour décrire comment elle doit être traitée dans la comptabilité et peuvent également définir la manière dont la répartition des fonds budgétaires est obtenue lorsque celle-ci est incluse dans votre configuration.  

Les commandes fournisseur facturées enregistreront le passif dans le compte fournisseur dans la comptabilité fournisseur, à partir de laquelle le *paiement du fournisseur* peut être traité.

## <a name="vendor-performance"></a>Performances du fournisseur

Les performances et la révision de l’achat sont prises en charge par des *états d’approvisionnement et de comptabilité fournisseur* qui comprennent une analyse des dépenses et une analyse des performances des fournisseurs.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]