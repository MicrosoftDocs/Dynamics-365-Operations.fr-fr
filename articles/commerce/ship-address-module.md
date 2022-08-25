---
title: Module Adresse d’expédition
description: Cet article couvre le module Adresse d’expédition et explique comment le configurer dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 48e6909b4dac9722830a83ec3a63a58876768d7e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275003"
---
# <a name="shipping-address-module"></a>Module Adresse d’expédition

[!include [banner](includes/banner.md)]

Cet article décrit le module Adresse d’expédition et explique comment le configurer dans Microsoft Dynamics 365 Commerce.

Le module Adresse d’expédition permet aux clients d’ajouter ou de sélectionner l’adresse d’expédition pour une commande pendant le flux de paiement. Si un client est connecté, toutes les adresses précédemment enregistrées pour ce client sont affichées et le client peut sélectionner parmi celles-ci. Le client peut également ajouter une nouvelle adresse. Le module Adresse de livraison est utilisé pour tous les articles sur une commande qui nécessitent l’expédition.

Les formats d’adresse de livraison peuvent être définis dans le siège Commerce pour chaque pays ou région, et le module d’adresse de livraison applique alors les règles spécifiques au pays ou à la région.

Lorsque les clients saisissent une adresse de livraison pendant le processus de paiement, ils ont la possibilité d’enregistrer l’adresse en tant qu’adresse principale. Cette option n’est affichée que si un client est connecté.

Bien que le module Adresse de livraison ne fournisse pas la validation d’adresse, cette fonctionnalité peut être implémentée à la personnalisation.

L’illustration suivante montre un exemple d’un nouveau module d’adresse de livraison dans une page de caisse.

![Exemple de module Adresse de livraison sur une page de paiement.](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a>Propriétés du module

| Nom de la propriété | Valeurs | Description  |
|---------------|--------|-------------|
| Titre | Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Rubrique optionnelle pour le module Adresse de livraison. |
| Afficher le type d’adresse | **Vrai** ou **Faux** | Si cette propriété facultative est définie sur **True**, un type d’adresse, tel que **Domicile** ou **Professionnelle**, sera affiché. Si aucun type d’adresse n’est spécifié, l’adresse sera automatiquement enregistrée sous **Type**=**Autre**. |
| Activer la suggestion automatique| **Vrai** ou **Faux** | Si cette propriété facultative est définie sur **Vrai**, des suggestions d’adresses automatiques seront fournies. Ces suggestions sont générées par Bing Maps. Pour plus d’informations sur la configuration de l’intégration de Bing Maps pour votre site, voir [Module de sélection de magasin](store-selector.md). Cette fonctionnalité est disponible à partir de la version 10.0.15 de Commerce.|
|Options de suggestion automatique| Nombre| Si les suggestions d’adresses automatiques sont activées, vous pouvez spécifier des options supplémentaires, par exemple le nombre maximal de suggestions à fournir.|

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a>Ajouter un module Adresse de livraison à une page de caisse et définir les propriétés requises

Un module Adresse de livraison ne peut être ajouté qu’à un module de caisse. Pour plus d’informations sur la configuration d’un module Adresse de livraison et son ajout à une page de caisse, voir [Module de caisse](add-checkout-module.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Panier](add-cart-module.md)

[Module Icône de panier](cart-icon-module.md)

[Module Validation](add-checkout-module.md)

[Module Paiement](payment-module.md)

[Module Options de livraison](delivery-options-module.md)

[Module Information sur les prélèvements](pickup-info-module.md)

[Module Détails de la commande](order-confirmation-module.md)

[Module Carte cadeau](add-giftcard.md)

[Module Sélection de magasin](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
