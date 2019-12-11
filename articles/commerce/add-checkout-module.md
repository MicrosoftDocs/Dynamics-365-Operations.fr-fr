---
title: Module Paiement
description: Cette rubrique décrit comment ajouter un module de caisse à une nouvelle page et définir les propriétés requises.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 4b810441fd25d41ee0893b119b4f7d91e7435d21
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697081"
---
# <a name="checkout-module"></a>Module Paiement

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique décrit comment ajouter un module de caisse à une nouvelle page et définir les propriétés requises.

## <a name="overview"></a>Vue d'ensemble

Module de caisse est un conteneur spécial qui héberge tous les modules requis pour créer une commande. Un module de caisse peut inclure les modules qui traitent l'adresse d'expédition, les méthodes d'expédition, les informations de facturation, le récapitulatif de commande, et d'autres informations liées à une commande client. Il présente un flux pas-à-pas qu'un client utilise pour entrer toutes les informations appropriées pour faire un achat.

Un module de caisse affiche des données sur l'ID panier. Cet ID panier est enregistré comme cookie du navigateur. Un ID panier est requis pour afficher les informations dans le module de caisse, tels que les articles dans la commande, le montant total, et des remises.

## <a name="checkout-module-properties"></a>Propriétés du module de paiement

Un module de caisse héberge un ensemble de modules à l'intérieur de celui-ci. Une propriété de largeur vous permet de spécifier si les articles dans le module de caisse doivent s'adapter à la largeur de celui-ci ou remplir écran.

Un module de caisse a plusieurs emplacements, par exemple un emplacement **Informations de caisse**, un emplacement **Synthèse de la commande**, et un emplacement **Passer la commande**. Chaque emplacement prend en charge un ensemble de modules qui figurent dans une disposition spécifique dans la page. Par exemple, l'emplacement **Informations de caisse** contient tous les modules nécessaires pour déclencher un paiement, tels que les modules pour l'adresse d'expédition et le mode de paiement. L'emplacement **Synthèse de la commande** affiche une synthèse de la commande et prend en charge l'action de placement de la commande. L'emplacement **Passer la commande** prend également en charge l'action de placement la commande. Les modules de placement de commande peuvent être définis dans deux emplacements pour optimiser le processus de placement de commandes auprès de différentes plateformes.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>Modules qui peuvent être utilisés dans un module de caisse

- **Adresse d'expédition** – Ce module permet à un client ajouter ou de sélectionner l'adresse d'expédition pour une commande. Si le client est connecté, toutes les adresses précédemment enregistrées pour ce client sont affichées. Le client peut ensuite sélectionner parmi ces adresses. Le client peut également ajouter une nouvelle adresse. L'adresse de livraison est utilisée pour tous les articles de la commande qui nécessitent l'expédition. Elle ne peut pas être personnalisée pour des articles de lignes individuelles. Les formats d'adresse d'expédition sont définis pour chaque pays ou région, et des règles spécifiques au pays/à la région sont appliqués par ce module. Bien que ce module ne fournisse pas la validation d'adresse, celle-ci peut être implémentée à la personnalisation. Si la commande inclut uniquement des articles qui sont prélevés en magasin, ce module est automatiquement masqué.
- **Options de livraison** – Ce module permet à un client sélectionner une option de livraison pour une commande. Les options de livraison sont basées sur l'adresse d'expédition. Si l'adresse d'expédition est modifiée, les options de livraison doivent être extraites de nouveau. Si la commande inclut uniquement des articles qui sont prélevés en magasin, ce module est automatiquement masqué.
- **Conteneur de section de caisse** – Ce module est un conteneur dans lequel vous pouvez mettre plusieurs modules pour créer une section dans le flux de caisse. Par exemple, vous pouvez mettre tous les modules liés au paiement à l'intérieur de ce conteneur pour les faire apparaître comme une section. Ce module n'affecte que la disposition du flux.
- **Carte cadeau** – Ce module permet à un client de payer une commande à l'aide d'une carte cadeau. Il prend en charge que les cartes cadeaux Microsoft Dynamics 365 Commerce. Une ou plusieurs cartes cadeaux peuvent être appliquées à une commande. Si le solde de la carte cadeau ne couvre pas le montant du panier, la carte cadeau peut être combinée avec un autre mode de paiement. Les cartes cadeaux ne peuvent être utilisées que si le client est connecté.
- **Points de fidélité** – Ce module permet à un client payer une commande à l'aide de ses points de fidélité. Il fournit une synthèse des points disponibles et points arrivant à expiration, et permet au client de sélectionner un nombre de point à échanger. Si le client n'est pas connecté ou s'il n'est pas un membre du programme de fidélité, ou si le montant total dans le panier est de 0 (zéro), ce module est automatiquement masqué.
- **Carte de crédit** – Ce module permet à un client de payer une commande à l'aide d'une carte de crédit. Si le montant total dans le panier est couvert par les points de fidélité ou une carte cadeau, ou s'il s'élève à 0 (zéro), ce module est automatiquement masqué. L'intégration de la carte de crédit est fournie par le connecteur de paiement Adyen. Pour plus d'informations sur l'utilisation de ce connecteur, voir [Connecteur de paiement Adyen](https://).
- **Adresse de facturation** – Ce module permet à un client de fournir des informations de facturation. Ces information sont traitées, de même que les informations de la carte de crédit, par Adyen. Ce module inclut une option qui permet aux clients d'utiliser leur adresse de facturation comme adresse d'expédition.
- **Informations de contact** – Ce module permet à un client d'ajouter ou de modifier des informations de contact (adresse e-mail) pour une commande.
- **Passer la commande** – Ce module permet à un client de passer une commande.
- **Bloc riche de contenu** – Ce module contient tous les messages pilotés par le système de gestion de contenu (CMS). Par exemple, il peut contenir un message indiquant : « Pour tout problème avec votre commande, contact-vous au 1-800-FABRIKAM ». 
- **Synthèse de la commande** – Ce module affiche l'analyse des coûts d'une commande.
- **Articles de ligne de commande** – Ce module affiche une synthèse des articles qui seront inclus dans une commande.

## <a name="retail-server-interaction"></a>Interaction du serveur de vente au détail

La plupart des informations de paiement, telles que l'adresse d'expédition et le mode d'expédition, sont enregistrées dans le panier et traitées dans le cadre de la commande. La seule exception est les informations de carte de crédit. Ces informations sont traitées directement à l'aide du connecteur de paiement Adyen. Le paiement est autorisé mais n'est pas facturé.

## <a name="add-a-checkout-module-to-a-new-page-and-set-the-required-properties"></a>Ajouter un module de caisse à une nouvelle page et définir les propriétés requises

Pour ajouter un module de caisse à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Fragment \> Nouveau fragment**, puis nommez le nouveau fragment **Fragment de caisse**.
1. Ajoutez un module de caisse au fragment.
1. Ajoutez un en-tête au module de caisse.
1. À l'emplacement **Informations de caisse**, ajoutez les modules d'adresse d'expédition, d'options de livraison, de conteneur de section de caisse, et d'informations sur le contact. Il devrait désormais exister quatre sections à l'emplacement **Informations de caisse**.
1. Dans le module de conteneur de section de caisse, ajoutez les modules de carte cadeau, de points de fidélité, et de carte de crédit. Ainsi, vous vous assurez que tous les modes de paiement s'affichent dans la section.
1. À l'emplacement **Synthèse de la commande**, ajoutez les modules de synthèse de commande, d'emplacement de commande, et de bloc riche de contenu.
1. Dans le module de bloc riche de contenu, ajoutez le texte suivant : **Si vous avez des questions sur votre commande, contactez le 1-800-FABRIKAM.**
1. À l'emplacement **Passer la commande**, ajoutez un module Passer la commande.
1. Sélectionnez **Enregistrer**. Certains modules ne s'affichent pas dans l'aperçu, car ils n'ont pas de contexte de panier.
1. Archivez le fragment, et publiez-le.
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
