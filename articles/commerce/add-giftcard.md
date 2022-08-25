---
title: Module Carte cadeau
description: Cet article couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 93e2a6608b6d3190df7df1d8f85fd9d7e1c18692
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280556"
---
# <a name="gift-card-module"></a>Module Carte cadeau

[!include [banner](includes/banner.md)]

Cet article couvre les modules de carte cadeau et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Les modules de cartes cadeaux peuvent être utilisé dans les modules de paiement pour accepter des cartes cadeaux, moyen de paiement courant utilisé dans les transactions d’e-commerce. Le module de carte cadeau prend en charge les cartes cadeaux Dynamics 365, SVS et Givex. Les cartes cadeaux SVS et Givex sont échangées via le fournisseur de paiement Adyen. Pour plus d’informations sur la prise en charge des cartes cadeaux externes telles que SVS et Givex, voir [Prise en charge des cartes cadeaux externes](./dev-itpro/gift-card.md).

> [!NOTE]
> La prise en charge du remboursement des cartes cadeaux SVS et Givex pendant le processus de paiement est disponible dans la version 10.0.11 de Dynamics 365 Commerce. 

Deux modules de cartes-cadeaux sont disponibles :

- **Carte cadeau** – Ce module peut être utilisé sur une page de paiement pour utiliser une carte-cadeau comme offre. 
- **Vérification du solde de la carte-cadeau** – Ce module peut être utilisé sur n’importe quelle page pour vérifier le solde d’une carte cadeau. Ce module est disponible dans Commerce version 10.0.14 et ultérieure.

> [!NOTE]
> La prise en charge du module de vérification du solde de la carte cadeau est disponible dans la version 10.0.14 de Dynamics 365 Commerce.

L’image suivante montre un exemple de module de carte cadeau dans une page de caisse.

![Exemple d’un module de carte cadeau.](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Propriétés du module

- **Afficher des champs supplémentaires** – Cette propriété définit quels champs doivent être affichés pour les cartes cadeaux en plus du numéro de carte-cadeau, qui est toujours affiché par défaut. Par exemple, certaines cartes cadeaux prennent en charge l’affichage d’un numéro d’identification personnel (PIN) et d’autres prennent en charge l’affichage d’un code PIN et d’une date d’expiration. Alternativement, cette propriété peut être définie sur « Aucune », ce qui n’affichera que le numéro de la carte cadeau et aucun champ supplémentaire.

    Les valeurs suivantes sont prises en charge :

    - Code PIN
    - Date d’expiration
    - Code PIN et date d’expiration 
    - None

- **Activer pour les utilisateurs invités** : lorsque cette propriété est activée, les utilisateurs invités peuvent accepter ou vérifier les soldes des cartes-cadeaux. Cette propriété nécessite que l’accès anonyme (invité) pour les cartes-cadeaux soit activé dans Commerce Headquarters. Pour plus d’informations, consultez [Activer les paiements par carte-cadeau pour la caisse invités](#enable-gift-card-payments-for-guest-checkout).

> [!IMPORTANT]
> La propriété **Activer pour les utilisateurs invités** est disponible à partir de Commerce version 10.0.21. Elle nécessite l’installation du package de bibliothèque du module Commerce version 9.31.

## <a name="site-settings-for-gift-card-modules"></a>Paramètres du site pour les modules de cartes cadeaux

Dans le générateur de site Commerce, sous **Paramètres du site \> Extensions**, il y a un paramètre de module de carte cadeau appelé **Type de carte cadeau pris en charge**. Ce paramètre prend en charge trois valeurs :
- **Carte cadeau Dynamics 365** – Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365. Ce paramètre n’est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.
- **Cartes cadeaux SVS et Givex** – Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Givex et SVS. Ce paramètre est pris en charge pour les utilisateurs connectés et anonymes sur le site de commerce électronique.
- **Cartes cadeaux Dynamics 365, SVS et Givex** – Lorsque ce paramètre est appliqué, le module de carte cadeau permet uniquement le rachat de cartes cadeaux Dynamics 365, Givex et SVS. Ce paramètre n’est pris en charge que pour les utilisateurs connectés sur le site de commerce électronique.

> [!IMPORTANT]
> Ces paramètres sont disponibles dans la version 10.0.11 de Dynamics 365 Commerce et ne sont requis que si vous avez besoin d’assistance pour les cartes cadeaux SVS ou Givex. Si vous effectuez une mise à jour à partir d’une ancienne version de Dynamics 365 Commerce, vous devez mettre à jour manuellement le fichier appsettings.json. Pour obtenir des instructions de mise à jour du fichier appsettings.json, consultez [Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file). 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a>Étendre les cartes-cadeaux internes aux vitrines de commerce électronique

Par défaut, les cartes-cadeaux internes ne sont pas optimisées pour les vitrines de commerce électronique. Par conséquent, avant d’autoriser l’utilisation de cartes-cadeaux internes pour le paiement, vous devez les configurer avec des extensions qui les rendent plus sécurisées. Voici les zones de cartes-cadeaux que vous devez étendre avant d’autoriser l’utilisation de cartes-cadeaux internes en production :

- **Numéro de la carte-cadeau** – Les séquences de numéros sont utilisées pour générer des numéros de carte-cadeau pour les cartes-cadeaux internes. Étant donné que les séquences de numéros peuvent être facilement prédites, vous devez étendre la génération des numéros de carte-cadeau afin que des chaînes aléatoires sécurisées par cryptographie soient utilisées pour les numéros émis.
- **GetBalance** – L’API **GetBalance** est utilisé pour rechercher les soldes des cartes-cadeaux. Par défaut, il s’agit d’une API publique. Si un code PIN n’est pas requis pour rechercher les soldes des cartes-cadeaux, il existe un risque que des attaques par force brute utilisent l’API **GetBalance** pour pirater les numéros de cartes-cadeaux qui ont des soldes. En mettant en œuvre à la fois un code PIN pour les cartes-cadeaux internes et la limitation de l’API, vous pouvez atténuer ce risque.
- **PIN** – Par défaut, les cartes-cadeaux internes ne prennent pas en charge les codes PIN. Vous devez étendre les cartes-cadeaux internes afin qu’un code PIN soit nécessaire pour rechercher les soldes. Cette fonctionnalité peut également être utilisée pour verrouiller les cartes-cadeaux après plusieurs tentatives incorrectes de saisie du code PIN.

## <a name="enable-gift-card-payments-for-guest-checkout"></a>Activer les paiements par carte-cadeau pour la caisse d’invité

Par défaut, les paiements par carte-cadeau ne sont pas activés pour la caisse d’invité (anonyme). Pour les activer, procédez comme suit.

1. Dans Commerce Headquarters, accédez à **Retail et Commerce \> Configuration de canal \>  Configuration de PDV \> PDV \> Opérations PDV**.
1. Sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) l’en-tête de la grille, puis sélectionnez **Insérer des colonnes**.
1. Dans la boîte de dialogue **Insérer des colonnes**, sélectionnez la case à cocher **AllowAnonymousAccess**.
1. Sélectionnez **Mettre à jour**.
1. Pour les opérations **520** (Solde de carte-cadeau) et **214**, définissez la valeur **AllowAnonymousAccess** sur **1**.
1. Sélectionnez **Enregistrer**.
1. Exécutez la la tâche du planificateur **1090** pour synchroniser les modifications avec la base de données des canaux. 

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
