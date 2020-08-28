---
title: Module Paiement
description: Cette rubrique couvre le modules Paiement et explique comment le configurer dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
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
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: f4f6baa3c4a42a2994cab772c98d373996e2648b
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661203"
---
# <a name="payment-module"></a>Module Paiement

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique couvre le modules Paiement et explique comment le configurer dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Le module Paiement permet aux clients de payer leurs commandes en utilisant des cartes de crédit ou de débit. L’intégration du paiement pour ce module est fournie par le connecteur de paiement Dynamics 365 pour Adyen. Pour plus d’informations sur le paramétrage et la configuration du connecteur de paiement, voir [Connecteur de paiement Dynamics 365 pour Adyen](dev-itpro/adyen-connector.md).

Le module Paiement héberge les informations de paiement qui sont transmises via Adyen dans un cadre HTML en ligne (iFrame). Le module Paiement interagit avec Commerce Scale Unit pour récupérer les informations de paiement Adyen. Dans le cadre de l’interaction Commerce Scale Unit, le module Paiement peut permettre aux informations d’adresse de facturation d’être transmises dans l’iFrame ou dans un module séparé. Dans le thème Fabrikam, l’adresse de facturation est affichée dans un module séparé. Cette approche permet une plus grande flexibilité de mise en forme, car les lignes d’adresse peuvent être affichées de sorte qu’elles ressemblent aux lignes de l’adresse de livraison.

Le module Paiement permet également aux clients connectés d’enregistrer leurs informations de paiement. Les informations de paiement et l’adresse de facturation sont enregistrées et gérées via le connecteur de paiement Adyen.

Le module Paiement couvre tous les frais de commande qui ne sont pas déjà couverts par des points de fidélité ou une carte cadeau. Si le total d’une commande est entièrement couvert par des points de fidélité ou des crédits de cartes cadeaux, le module Paiement sera masqué, et le client pourra passer la commande sans lui.

Le connecteur de paiement Adyen prend également en charge l’authentification rigoureuse des clients (SCA). Une partie de la directive 2.0 (PSD2.0) sur les services de paiement de l’Union européenne (UE) exige que les acheteurs en ligne soient authentifiés en dehors de leur expérience d’achat en ligne lorsqu’ils utilisent un moyen de paiement électronique. Lors du processus de paiement, les clients sont redirigés vers leur site bancaire. Ensuite, après authentification, ils sont redirigés vers le flux de paiement Commerce. Au cours de cette redirection, les informations qu’un client a entrées dans le flux de paiement (par exemple, l’adresse de livraison, les options de livraison, les informations sur la carte-cadeau et les informations de fidélité) seront conservées. Avant de pouvoir activer cette fonctionnalité, le connecteur de paiement doit être configuré pour la SCA au siège Commerce. Pour plus d’informations, voir [Authentification forte du client avec Adyen](adyen_redirect.md).

L’illustration suivante montre un exemple de modules de carte-cadeau, de points de fidélité et de paiement sur une page de caisse.

![Exemple de modules de carte-cadeau, de points de fidélité et de paiement sur une page de caisse](./media/ecommerce-payments.PNG)

## <a name="payment-module-properties"></a>Propriétés du module Paiement

| Nom de la propriété | Valeurs | Description  |
|---------------|--------|-------------|
| Titre | Texte d’en-tête | Rubrique optionnelle pour le module Paiement. |
| Hauteur de l’iFrame | Pixels | Hauteur de l’iFrame, en pixels. La hauteur peut être ajustée au besoin. |
| Afficher l’adresse de facturation | **Vrai** ou **Faux** | Si cette propriété est définie sur **True**, l’adresse de facturation sera transmise par Adyen dans le module Paiement iFrame. S’il est réglé sur **False**, l’adresse de facturation ne sera pas transmise par Adyen, et un utilisateur Commerce devra configurer un module pour afficher l’adresse de facturation sur la page de caisse. |
| Remplacement du style de paiement | Code de feuilles de style en cascade (CSS) | Le module Paiement étant hébergé dans un iFrame, la capacité de style est limitée. Vous pouvez obtenir un style en utilisant cette propriété. Pour remplacer les styles de site, vous devez coller le code CSS comme valeur de cette propriété. Les remplacements et les styles CSS du générateur de site ne s’appliquent pas à ce module. |

## <a name="billing-address"></a>Adresse de facturation

Le module Paiement permet aux clients de fournir une adresse de facturation pour leurs informations de paiement. Cela leur permet également d’utiliser leur adresse de livraison comme adresse de facturation, pour faciliter et accélérer le processus de paiement. Si la propriété **Afficher l’adresse de facturation** est définie sur **False**, le module Paiement doit être configuré sur la page de paiement.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Ajouter un module Paiement à une page de caisse et définir les propriétés requises

Un module Paiement ne peut être ajouté qu’à un module de caisse. Pour plus d’informations sur la configuration d’un module Paiement pour une page de caisse, voir [Module de caisse](add-checkout-module.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Panier](add-cart-module.md)

[Module Icône de panier](cart-icon-module.md)

[Module Validation](add-checkout-module.md)

[Module Adresse d’expédition](ship-address-module.md)

[Module Options de livraison](delivery-options-module.md)

[Module Détails de la commande](order-confirmation-module.md)

[Module Carte cadeau](add-giftcard.md)

[Connecteur de paiement Dynamics 365 pour Adyen](dev-itpro/adyen-connector.md)

[Authentification rigoureuse des clients à l’aide d’Adyen](adyen_redirect.md)
