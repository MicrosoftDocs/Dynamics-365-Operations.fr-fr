---
title: Module Paiement
description: Cette rubrique décrit comment ajouter un module de caisse à une nouvelle page et définir les propriétés requises.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3805c0faabc8afc3decffb924b7f25332ff1ab16
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025388"
---
# <a name="checkout-module"></a>Module Paiement


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment ajouter un module de caisse à une nouvelle page et définir les propriétés requises.

## <a name="overview"></a>Vue d'ensemble

Module de validation est un conteneur spécial qui héberge tous les modules requis pour créer une commande. Il présente un flux pas-à-pas qu'un client utilise pour entrer toutes les informations appropriées pour faire un achat. Il capture l'adresse d'expédition, la méthode d'expédition et les informations de facturation. Il fournit également un résumé de commande et d'autres informations liées à une commande client.

Un module de caisse affiche des données sur l'ID panier. Cet ID panier est enregistré comme cookie du navigateur. Un ID panier est requis pour afficher les informations dans le module de caisse, tels que les articles dans la commande, le montant total, et des remises.

## <a name="checkout-module-properties"></a>Propriétés du module de paiement

Un module de paiement affiche un résumé de la commande et fournit la fonctionnalité pour passer une commande. Pour rassembler toutes les informations client requises avant de passer une commande, des modules supplémentaires doivent être ajoutés au module de validation. Par conséquent, les détaillants ont la possibilité d'ajouter des modules personnalisés au flux de validation ou d'exclure des modules en fonction de leurs besoins.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>Modules qui peuvent être utilisés dans un module de caisse

- **Adresse d'expédition** – Ce module permet à un client ajouter ou de sélectionner l'adresse d'expédition pour une commande. Si le client est connecté, toutes les adresses précédemment enregistrées pour ce client sont affichées. Le client peut ensuite sélectionner parmi ces adresses. Le client peut également ajouter une nouvelle adresse. L'adresse de livraison est utilisée pour tous les articles de la commande qui nécessitent l'expédition. Elle ne peut pas être personnalisée pour des articles de lignes individuelles. Les formats d'adresse d'expédition sont définis pour chaque pays ou région, et des règles spécifiques au pays/à la région sont appliqués par ce module. Bien que ce module ne fournisse pas la validation d'adresse, celle-ci peut être implémentée à la personnalisation. Si la commande inclut uniquement des articles qui sont prélevés en magasin, ce module est automatiquement masqué.
- **Options de livraison** – Ce module permet à un client sélectionner une option de livraison pour une commande. Les options de livraison sont basées sur l'adresse d'expédition. Si l'adresse d'expédition est modifiée, les options de livraison doivent être extraites de nouveau. Si la commande inclut uniquement des articles qui sont prélevés en magasin, ce module est automatiquement masqué.
- **Conteneur de section de caisse** – Ce module est un conteneur dans lequel vous pouvez mettre plusieurs modules pour créer une section dans le flux de caisse. Par exemple, vous pouvez mettre tous les modules liés au paiement à l'intérieur de ce conteneur pour les faire apparaître comme une section. Ce module n'affecte que la disposition du flux.
- **Carte cadeau** – Ce module permet à un client de payer une commande à l'aide d'une carte cadeau. Il prend en charge que les cartes cadeaux Microsoft Dynamics 365 Commerce. Une ou plusieurs cartes cadeaux peuvent être appliquées à une commande. Si le solde de la carte cadeau ne couvre pas le montant du panier, la carte cadeau peut être combinée avec un autre mode de paiement. Les cartes cadeaux ne peuvent être utilisées que si le client est connecté.
- **Points de fidélité** – Ce module permet à un client payer une commande à l'aide de ses points de fidélité. Il fournit une synthèse des points disponibles et points arrivant à expiration, et permet au client de sélectionner un nombre de point à échanger. Si le client n'est pas connecté ou s'il n'est pas un membre du programme de fidélité, ou si le montant total dans le panier est de 0 (zéro), ce module est automatiquement masqué.
- **Paiement** – Ce module permet à un client de payer une commande à l'aide d'une carte de crédit. Si le montant total dans le panier est couvert par les points de fidélité ou une carte cadeau, ou s'il s'élève à 0 (zéro), ce module est automatiquement masqué. L'intégration de la carte de crédit est fournie par le connecteur de paiement Adyen pour ce module. Pour plus d'informations sur l'utilisation de ce connecteur, voir [Connecteur de paiement Dynamics 365 pour Adyen](dev-itpro/adyen-connector.md).
- **Adresse de facturation** – Ce module permet à un client de fournir des informations de facturation. Ces information sont traitées, de même que les informations de la carte de crédit, par Adyen. Ce module inclut une option qui permet aux clients d'utiliser leur adresse de facturation comme adresse d'expédition.
- **Informations de contact** – Ce module permet à un client d'ajouter ou de modifier des informations de contact (adresse e-mail) pour une commande.
- **Bloc de texte** – Ce module contient tous les messages pilotés par le système de gestion de contenu (CMS). Par exemple, il peut contenir un message indiquant : « Pour tout problème avec votre commande, contactez le 1-800-Fabrikam ». 

## <a name="commerce-scale-unit-interaction"></a>Interaction avec l'unité d'échelle commerciale

La plupart des informations de paiement, telles que l'adresse d'expédition et le mode d'expédition, sont enregistrées dans le panier et traitées dans le cadre de la commande. La seule exception est les informations de carte de crédit. Ces informations sont traitées directement à l'aide du connecteur de paiement Adyen. Le paiement est autorisé mais n'est pas facturé.

## <a name="add-a-checkout-module-to-a-new-page-and-set-the-required-properties"></a>Ajouter un module de caisse à une nouvelle page et définir les propriétés requises

Pour ajouter un module de caisse à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Fragment \> Nouveau fragment**, puis nommez le nouveau fragment **Fragment de caisse**.
1. Ajoutez un module de caisse au fragment.
1. Ajoutez un en-tête au module de caisse.
1. Ajoutez les modules d'adresse d'expédition, d'options de livraison, de conteneur de section de validation et d'informations sur le contact. 
1. Dans le module de conteneur de section de validation, ajoutez les modules de carte cadeau, de points de fidélité et de paiement. Ainsi, vous vous assurez que tous les modes de paiement s'affichent dans la section.
1. Enregistrez et affichez un aperçu du fragment. Certains modules qui n'ont pas de contexte de panier peuvent ne pas s'afficher dans l'aperçu.
1. Terminez la modification du fragment et publiez-le.
1. Créez un modèle qui utilise le nouveau fragment de caisse.
1. Créez une page de caisse qui utilise le nouveau modèle.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Container](add-container-module.md)

[Module Zone d'achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Module Confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
