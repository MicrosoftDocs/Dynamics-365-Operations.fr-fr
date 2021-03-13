---
title: Configurer la taxe pour les commandes en ligne
description: Cette rubrique fournit une vue d'ensemble de la sélection du groupe de taxes pour différents types de commande en ligne dans Dynamics 365 Commerce.
author: gvrmohanreddy
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 56621bb9658b71551c7312aa47812903914bc888
ms.sourcegitcommit: da17648c296b22d517eadb2f71c7803672e5648d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2021
ms.locfileid: "5031787"
---
# <a name="configure-sales-tax-for-online-orders"></a>Configurer la taxe pour les commandes en ligne

[!include [banner](includes/banner.md)]

Cette rubrique fournit une vue d'ensemble de la sélection du groupe de taxes pour différents types de commande en ligne. 

Votre canal d'e-commerce peut souhaiter prendre en charge des options telles que la livraison ou le retrait des commandes en ligne. L'applicabilité de la taxe est basée sur l'option sélectionnée par vos utilisateurs en ligne. Lorsqu'un client du site choisit d'acheter un article en ligne et le fait expédier à une adresse, la taxe est déterminée en fonction du paramètre de groupe de taxes de l'adresse de livraison du client. Lorsqu'un client choisit de récupérer un article acheté dans un magasin, la taxe est déterminée en fonction du paramètre de groupe de taxes du magasin de retrait. 

## <a name="orders-shipped-to-a-customer-address"></a>Commandes expédiées à une adresse client 

En général, les taxes pour les commandes en ligne expédiées aux adresses des clients sont définies par la destination. Chaque groupe de taxes a une configuration de taxe basée sur la destination de vente au détail dans laquelle votre entreprise peut définir des détails de destination tels que le département/la région, l'état, le pays et la ville sous une forme hiérarchique. Lorsqu'une commande en ligne est passée, le moteur de taxe Commerce utilise l'adresse de livraison de chaque élément de ligne de la commande et recherche les groupes de taxes avec les critères de taxe correspondant à la destination. Par exemple, pour une commande en ligne avec une adresse de livraison d'élément de campagne à San Francisco, Californie, le moteur de taxe trouvera le groupe de taxes et le code de taxe pour la Californie, puis calculera la taxe pour chaque élément de ligne en conséquence.  

## <a name="customer-based-tax-groups"></a>Groupes de taxes basés sur le client

Au siège de Commerce, il existe deux emplacements où les groupes de taxes clients sont configurés :

- **Profil du client**
- **Adresse d'expédition du client**

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a>Si le profil d'un client a un groupe de taxes configuré

Un enregistrement de profil d'un client au siège peut avoir un groupe de taxes configuré, mais pour les commandes en ligne, le groupe de taxes configuré dans le profil d'un client ne sera pas utilisé par le moteur de taxe. 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a>Si l'adresse de livraison d'un client a un groupe de taxes configuré

Si l'enregistrement d'adresse de livraison d'un client a un groupe de taxes configuré et qu'une commande en ligne (ou un article) est expédiée à l'adresse de livraison du client, le groupe de taxes configuré dans l'enregistrement d'adresse du client sera utilisé par le moteur de taxes pour les calculs de taxe.

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a>Configurer un groupe de taxes pour un enregistrement d'adresse de livraison d'un client

Pour configurer un groupe de taxes pour l'enregistrement d'adresse de livraison d'un client au siège de Commerce, procédez comme suit.

1. Aller à **Tous les clients**, puis sélectionnez le client souhaité. 
1. Sur le raccourci **Adresses**, sélectionnez l'adresse souhaitée, puis sélectionnez **Plus d'options \> Avancée**. 
1. Sous l'onglet **Général** sur la page **Gérer les adresses**, définissez la valeur de la taxe selon vos besoins.

> [!NOTE]
> Le groupe de taxes est défini à l'aide de l'adresse de livraison de la ligne de commande et les taxes basées sur la destination sont configurées au niveau du groupe de taxes lui-même. Pour plus d'informations, voir [Configurer les taxes pour les magasins en ligne en fonction de la destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

## <a name="order-pickup-in-store"></a>Retrait de commande en magasin

Pour les lignes de commande avec retrait en magasin ou retrait à un point-relais spécifié, le groupe de taxes du magasin de retrait sélectionné sera appliqué. Pour plus d'informations sur la configuration du groupe de taxes pour un magasin donné, voir [Définir d'autres options fiscales pour les magasins](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

> [!NOTE]
> Lorsqu'une ligne de commande est retirée dans un magasin, les paramètres de taxe d'adresse d'un client (s'ils sont configurés) seront ignorés par le moteur de taxe et la configuration de taxe du magasin de retrait sera appliquée. 

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des taxes](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[Modes de calcul des taxes dans le champ Origine](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[Affectation et remplacement des taxes](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[Options de calcul montant entier et intervalle pour les codes taxe](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[Calcul de l’exonération fiscale](tax-exempt-price-inclusive.md) 

