---
title: Module de carte cadeau
description: Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 70047376cec44523cc9cfe4df792bde23c776d8c
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261567"
---
# <a name="gift-card-module"></a>Module de carte cadeau

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Les cartes cadeaux sont un mode de paiement courant et le module de cartes cadeaux peut être utilisé dans un module de paiement pour accepter des cartes cadeaux. Le module de carte cadeau prend en charge les cartes cadeaux Dynamics 365, SVS et Givex. Les cartes cadeaux SVS et Givex sont échangées via le fournisseur de paiement Adyen.

Pour plus d'informations sur la prise en charge des cartes cadeaux externes telles que SVS et Givex, consultez [Prise en charge des cartes cadeaux externes](./dev-itpro/gift-card.md)

## <a name="module-properties"></a>Propriétés du module

- **Afficher des champs supplémentaires** - Cette propriété définit quels champs doivent être affichés pour les cartes cadeaux en plus du numéro de carte-cadeau, qui est toujours affiché par défaut. Par exemple, certaines cartes cadeaux prennent en charge l'affichage d'un numéro d'identification personnel (PIN) et d'autres prennent en charge l'affichage d'un code PIN et d'une date d'expiration. Alternativement, cette propriété peut être définie sur « Aucune », ce qui n'affichera que le numéro de la carte cadeau et aucun champ supplémentaire.

Valeurs prises en charge :
-   PIN
-   Date d'expiration
-   Code PIN et date d'expiration 
-   None

## <a name="site-settings-for-gift-card-modules"></a>Paramètres du site pour les modules de cartes cadeaux

Dans le générateur de site Commerce, sous **Paramètres du site \> Extensions**, il y a un paramètre de module de carte cadeau appelé **Type de carte cadeau pris en charge**. Ce paramètre prend en charge trois valeurs :
- **Carte cadeau Dynamics 365** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365. Ce paramètre n'est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.
- **Cartes cadeaux SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Givex et SVS. Ce paramètre est pris en charge pour les utilisateurs connectés et anonymes sur le site de commerce électronique.
- **Cartes cadeaux Dynamics 365, SVS et Givex** - Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365, Givex et SVS. Ce paramètre n'est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.

## <a name="add-a-gift-card-module-to-a-page"></a>Ajouter un module de carte cadeau à une page

Pour obtenir des instructions sur la façon d'ajouter un module de carte cadeau à une page de paiement et de définir les propriétés requises, voir [Module de paiement ](add-checkout-module.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module de validation](add-checkout-module.md)

[Prendre en charge des cartes cadeaux externes](./dev-itpro/gift-card.md)