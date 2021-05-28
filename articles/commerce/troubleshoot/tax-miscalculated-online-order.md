---
title: Les taxes sur les commandes en ligne ne sont pas correctement calculées
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque les taxes sur les commandes en ligne ne sont pas correctement calculées ou lorsque le groupe de taxe sur la ligne de vente n’est pas correctement défini.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f7cef533d76bdddfbad2e8c5f84f81ef62bccc38
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021101"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a>Les taxes sur les commandes en ligne ne sont pas correctement calculées

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque les taxes sur les commandes en ligne ne sont pas correctement calculées ou lorsque le groupe de taxe sur la ligne de vente n’est pas correctement défini.

## <a name="description"></a>Description

Lorsqu’une commande e-commerce est passée, les taxes ne sont pas correctement calculées ou le groupe de taxe sur la ligne de vente est défini de manière incorrecte.

## <a name="resolution"></a>Résolution

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a>Configurer la taxe pour un magasin de détail dans Commerce Headquarters

Pour configurer la taxe pour un magasin de détail dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Canaux \> Tous les magasins**.
1. Sélectionnez le magasin pour lequel configurer la taxe.
1. Sur le raccourci **Général**, dans la section **Taxe**, configurez les informations de taxe pour le magasin.

> [!NOTE]
> Pour le retrait de produits dans un magasin, le groupe de taxe provient du magasin sélectionné pour le retrait. Pour plus d’informations, voir [Paramétrage d’autres options de taxe pour les magasins](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a>Configurer la taxe pour l’adresse d’un client dans Commerce Headquarters

Pour configurer la taxe pour l’adresse d’un client dans Commerce Headquarters, procédez comme suit.

1. Allez dans **Comptabilité client \> Clients \> Tous les clients**.
1. Sélectionnez le client pour lequel vous voulez configurer la taxe.
1. Sur le raccourci **Adresses**, sélectionnez l’adresse pour laquelle configurer les taxes, sélectionnez **Plus d’options**, puis **Avancé**.
1. Sous le raccourci **Général**, sélectionnez le **Groupe de taxe**.
1. Dans le champ **Taxe**, sélectionnez la valeur appropriée.

> [!NOTE]
> Pour les expéditions impliquant une taxe sur l’adresse du client, l’adresse de livraison de la ligne détermine le groupe de taxe de la ligne. Si le client expédie à une adresse existante pour laquelle un groupe de taxe est déjà configuré, le groupe de taxe existant sera utilisé. Par défaut, les adresses n’ont pas de groupe de taxe lorsqu’elles sont créées.

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a>Configurer les groupes de taxe générale dans Commerce Headquarters

Pour configurer les groupes de taxe générale dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Taxe \> Taxes indirectes \> Taxe \> Groupes de taxe**.
1. Dans le volet de navigation de gauche, sélectionnez le groupe de taxe à configurer.
1. Sur le raccourci **Taxe selon la destination de vente au détail**, configurez les taxes pour le groupe de taxe.

> [!NOTE]
> Pour les expéditions qui n’impliquent pas de taxe sur l’adresse du client, l’adresse de livraison de la ligne et les taxes selon la destination qui sont configurées pour le groupe de taxe déterminent le groupe de taxe. Pour plus d’informations, voir [Configurer les taxes pour les magasins en ligne en fonction de la destination](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer la taxe pour les commandes en ligne](../sales-tax-config.md)