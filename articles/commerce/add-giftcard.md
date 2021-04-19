---
title: Module de carte cadeau
description: Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a4e4e06ab7032d68fcd36a8e80bc714ebaaac821
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797669"
---
# <a name="gift-card-module"></a>Module Carte cadeau

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Les modules de cartes cadeaux peuvent être utilisé dans les modules de paiement pour accepter des cartes cadeaux, moyen de paiement courant utilisé dans les transactions d’e-commerce. Le module de carte cadeau prend en charge les cartes cadeaux Dynamics 365, SVS et Givex. Les cartes cadeaux SVS et Givex sont échangées via le fournisseur de paiement Adyen. Pour plus d’informations sur la prise en charge des cartes cadeaux externes telles que SVS et Givex, voir [Prise en charge des cartes cadeaux externes](./dev-itpro/gift-card.md).

> [!NOTE]
> La prise en charge du remboursement des cartes cadeaux SVS et Givex pendant le processus de paiement est disponible dans la version 10.0.11 de Dynamics 365 Commerce. 

Deux modules de cartes-cadeaux sont disponibles :

- **Carte cadeau** – Ce module peut être utilisé sur une page de paiement pour utiliser une carte-cadeau comme offre. 
- **Vérification du solde de la carte-cadeau** – Ce module peut être utilisé sur n’importe quelle page pour vérifier le solde d’une carte cadeau. Ce module est disponible dans Commerce version 10.0.14 et ultérieure.

> [!NOTE]
> La prise en charge du module de vérification du solde de la carte cadeau est disponible dans la version 10.0.14 de Dynamics 365 Commerce.

L’image suivante montre un exemple de module de carte cadeau dans une page de caisse.

![Exemple d’un module de carte cadeau](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Propriétés du module

- **Afficher des champs supplémentaires** - Cette propriété définit quels champs doivent être affichés pour les cartes cadeaux en plus du numéro de carte-cadeau, qui est toujours affiché par défaut. Par exemple, certaines cartes cadeaux prennent en charge l’affichage d’un numéro d’identification personnel (PIN) et d’autres prennent en charge l’affichage d’un code PIN et d’une date d’expiration. Alternativement, cette propriété peut être définie sur « Aucune », ce qui n’affichera que le numéro de la carte cadeau et aucun champ supplémentaire.

Valeurs prises en charge :
-   PIN
-   Date d’expiration
-   Code PIN et date d’expiration 
-   None

## <a name="site-settings-for-gift-card-modules"></a>Paramètres du site pour les modules de cartes cadeaux

Dans le générateur de site Commerce, sous **Paramètres du site \> Extensions**, il y a un paramètre de module de carte cadeau appelé **Type de carte cadeau pris en charge**. Ce paramètre prend en charge trois valeurs :
- **Carte cadeau Dynamics 365** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365. Ce paramètre n’est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.
- **Cartes cadeaux SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Givex et SVS. Ce paramètre est pris en charge pour les utilisateurs connectés et anonymes sur le site de commerce électronique.
- **Cartes cadeaux Dynamics 365, SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365, Givex et SVS. Ce paramètre n’est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.

> [!IMPORTANT]
> Ces paramètres sont disponibles dans la version 10.0.11 de Dynamics 365 Commerce et ne sont requis que si vous avez besoin d’assistance pour les cartes cadeaux SVS ou Givex. Si vous effectuez une mise à jour à partir d’une ancienne version de Dynamics 365 Commerce, vous devez mettre à jour manuellement le fichier appsettings.json. Pour obtenir des instructions de mise à jour du fichier appsettings.json, consultez [Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file). 

## <a name="add-a-gift-card-module-to-a-page"></a>Ajouter un module de carte cadeau à une page

Pour obtenir des instructions sur la façon d’ajouter un module de carte cadeau à une page de paiement et de définir les propriétés requises, voir [Module de paiement ](add-checkout-module.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Panier](add-cart-module.md)

[Module Icône de panier](cart-icon-module.md)

[Module Validation](add-checkout-module.md)

[Module Paiement](payment-module.md)

[Module Adresse d’expédition](ship-address-module.md)

[Module Options de livraison](delivery-options-module.md)

[Module d’information sur le retrait](pickup-info-module.md)

[Module Détails de la commande](order-confirmation-module.md)

[Prendre en charge des cartes cadeaux externes](./dev-itpro/gift-card.md)

[Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]