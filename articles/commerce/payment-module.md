---
title: Module Paiement
description: Cette rubrique couvre le modules Paiement et explique comment le configurer dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 85b5d8306eb4e9f2a4b9df13d95ab88020c3591e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000663"
---
# <a name="payment-module"></a>Module Paiement

[!include [banner](includes/banner.md)]

Cette rubrique couvre le modules Paiement et explique comment le configurer dans Microsoft Dynamics 365 Commerce.

Le module Paiement permet aux clients de payer leurs commandes en utilisant des cartes de crédit ou de débit. L’intégration du paiement pour ce module est fournie par le connecteur de paiement Dynamics 365 pour Adyen. Pour plus d’informations sur le paramétrage et la configuration du connecteur de paiement, voir [Connecteur de paiement Dynamics 365 pour Adyen](dev-itpro/adyen-connector.md).  

À partir de la version 10.0.14 de Commerce, le module de paiement a également été intégré au connecteur de paiement Dynamics 365 pour PayPal pour permettre aux clients de payer leurs commandes à l'aide de PayPal. Pour plus d’informations sur le paramétrage et la configuration du connecteur de paiement Dynamics 365 pour Paypal, voir [Connecteur de paiement Dynamics 365 pour Paypal](paypal.md). 

## <a name="dynamics-365-payment-connector-for-adyen"></a>Connecteur de paiement Dynamics 365 pour Adyen 

Le module Paiement héberge les informations de paiement qui sont transmises via Adyen dans un cadre HTML en ligne (iFrame). Le module Paiement interagit avec Commerce Scale Unit pour récupérer les informations de paiement Adyen. Dans le cadre de l’interaction Commerce Scale Unit, le module Paiement peut permettre aux informations d’adresse de facturation d’être transmises dans l’iFrame par le biais d'Adyen ou dans un module séparé. Dans le thème Fabrikam, l’adresse de facturation est activée en tant que module séparé. Cette approche permet une plus grande flexibilité de mise en forme, car les lignes d’adresse peuvent être affichées de sorte qu’elles ressemblent aux lignes de l’adresse de livraison.

Le module Paiement permet également aux clients connectés d’enregistrer leurs informations de paiement. Les informations de paiement et l’adresse de facturation sont enregistrées et gérées via le connecteur de paiement Adyen.

Le module Paiement couvre tous les frais de commande qui ne sont pas déjà couverts par des points de fidélité ou une carte cadeau. Si le total d’une commande est entièrement couvert par des points de fidélité ou des crédits de cartes cadeaux, le module Paiement sera masqué, et le client pourra passer la commande sans lui.

Le connecteur de paiement Adyen prend également en charge l’authentification rigoureuse des clients (SCA). Une partie de la révision de la directive (PSD2) sur les services de paiement de l’Union européenne (UE) exige que les acheteurs en ligne soient authentifiés en dehors de leur expérience d’achat en ligne lorsqu’ils utilisent un moyen de paiement électronique. Pendant le flux de paiement, les clients sont redirigés vers leur site bancaire, puis après authentification, ils sont redirigés vers le flux de paiement Commerce. Au cours de cette redirection, les informations qu’un client a entrées dans le flux de paiement (par exemple, l’adresse de livraison, les options de livraison, les informations sur la carte-cadeau et les informations de fidélité) seront conservées. Avant de pouvoir activer la fonctionnalité de paiement Adyen, le connecteur de paiement doit être configuré pour la SCA au siège Commerce. Pour plus d’informations, voir [Authentification forte du client avec Adyen](adyen_redirect.md). Cette fonctionnalité a été activée dans la version 10.0.12 de Commerce.

> [!NOTE]
> Pour le connecteur de paiement Adyen, le module iframe du module de paiement ne peut s’afficher que si vous ajoutez l'URL Adyen à la liste d'autorisation de votre site. Pour effectuer cette étape, ajoutez **\*.adyen.com** aux directives **child-src**, **connect-src**, **img-src**, **script-src**, et **style-src** de la stratégie de sécurité du contenu de votre site. Pour plus d’informations, voir [Gérer la stratégie de sécurité du contenu](manage-csp.md). 

L’illustration suivante montre un exemple de modules de carte-cadeau, de points de fidélité et de paiement Adyen sur une page de caisse.

![Exemple de modules de carte cadeau, de points de fidélité et de paiement Adyen sur une page de caisse](./media/ecommerce-payments.PNG)

## <a name="dynamics-365-payment-connector-for-paypal"></a>Connecteur de paiement Dynamics 365 pour Paypal

À partir de la version 10.0.14 de Commerce, le module de paiement est également intégré au connecteur de paiement Dynamics 365 pour PayPal. Pour plus d’informations sur le paramétrage et la configuration de ce connecteur de paiement, voir [Connecteur de paiement Dynamics 365 pour Paypal](paypal.md).
 
Sur la page de paiement, vous pouvez configurer à la fois les connecteurs Adyen et Paypal. Le module de paiement a été amélioré avec des propriétés supplémentaires pour aider à identifier le connecteur avec lequel il doit fonctionner. Pour plus de détails, consultez les propriétés **Types d'appels d'offres pris en charge** et **Est le paiement principal** du module dans le tableau suivant.
  
Lorsque le module de paiement est configuré pour utiliser le connecteur de paiement Paypal, un bouton Paypal apparaît sur la page de paiement. Lorsqu'il est appelé par le client, le module de paiement rend un iFrame contenant des informations Paypal. Le client peut se connecter et fournir ses informations Paypal dans cette iFrame pour terminer sa transaction. Lorsqu'un client choisit de payer avec Paypal, le solde de la commande sera débité via Paypal.

Le connecteur de paiement Paypal ne nécessite pas de module d'adresse de facturation car toutes les informations relatives à la facturation sont gérées par Paypal dans son iFrame. Cependant, les modules d'adresse de livraison et d'options de livraison sont obligatoires.

L'illustration suivante montre un exemple de deux modules de paiement sur une page de paiement, l'un configuré avec le connecteur de paiement Adyen et l'autre avec le connecteur de paiement Paypal.
![Exemple de modules de paiement Adyen et Paypal sur une page de caisse](./media/ecommerce-paypal.png)

L'illustration suivante montre un exemple de l'iFrame Paypal appelée à l'aide du bouton Paypal. 
![Exemple d'iFrame Paypal sur une page de paiement](./media/ecommerce-paypal-iframe.png)

## <a name="payment-module-properties"></a>Propriétés du module Paiement

| Nom de la propriété | Valeurs | Description |
|---------------|--------|-------------|
| Titre | Texte d’en-tête | Rubrique optionnelle pour le module Paiement. |
| Hauteur de l’iFrame | Pixels | Hauteur de l’iFrame, en pixels. La hauteur peut être ajustée au besoin. |
| Afficher l’adresse de facturation | **Vrai** ou **Faux** | Si cette propriété est définie sur **True**, l’adresse de facturation sera transmise par Adyen dans le module Paiement iFrame. S’il est réglé sur **False**, l’adresse de facturation ne sera pas transmise par Adyen, et un utilisateur Commerce devra configurer un module pour afficher l’adresse de facturation sur la page de caisse. Pour le connecteur de paiement Paypal, ce champ n'a aucun impact, car l'adresse de facturation est entièrement gérée dans Paypal. |
| Remplacement du style de paiement | Code de feuilles de style en cascade (CSS) | Le module Paiement étant hébergé dans un iFrame, la capacité de style est limitée. Vous pouvez obtenir un style en utilisant cette propriété. Pour remplacer les styles de site, vous devez coller le code CSS comme valeur de cette propriété. Les remplacements et les styles CSS du générateur de site ne s’appliquent pas à ce module. |
|Types d’offre pris en charge| Chaîne| Si plusieurs connecteurs de paiement sont configurés, vous devez fournir la chaîne de type de paiement pris en charge telle que définie dans la configuration du connecteur de paiement du siège de Commerce (voir l'image suivante). S'il est vide, il utilise par défaut le connecteur de paiement Adyen. Ajouté dans la version 10.0.14 de Commerce.|
|Est le paiement principal|  **Vrai** ou **Faux** | Si **Vrai**, tous les messages d'erreur seront générés à partir du connecteur de paiement principal sur la page de paiement. Si les connecteurs de paiement Adyen et Paypal sont configurés, définissez Adyen sur **Vrai**, qui a été ajouté dans la version 10.0.14 de Commerce.|

L'illustration suivante montre un exemple de valeur **Types d'offres pris en charge** définie sur "Paypal" dans la configuration du connecteur de paiement au siège de Commerce.
![Exemple de types d'appels d'offres pris en charge au siège du Commerce](./media/ecommerce-paymenttendertypes.png)

## <a name="billing-address"></a>Adresse de facturation

Un module d'adresse de facturation peut être utilisé sur la page de paiement si les lignes d'adresse de facturation du connecteur de paiement Adyen ne correspondent pas suffisamment à l'apparence du reste du site. 

Pour utiliser un module d'adresse de facturation sur la page de paiement lorsque le module de paiement est intégré au connecteur de paiement Adyen, définissez la propriété **Afficher l'adresse de facturation** sur **Faux** afin qu'un module d'adresse de facturation dédié puisse être utilisé à la place de l'adresse de facturation Adyen par défaut. Dans ce cas, l'auteur du site doit inclure un module d'adresse de facturation sur la page de paiement. Le connecteur de paiement Adyen permet également d'utiliser l'adresse de livraison comme adresse de facturation afin de minimiser le nombre d'étapes pour l'utilisateur du site.

Similaire aux modules de paiement, une propriété **Types d'appels d'offres pris en charge** a été ajoutée au module d'adresse de facturation dans Commerce version 10.0.14. La valeur de cette propriété doit être identique à la valeur fournie dans le module de paiement pour s'assurer qu'ils fonctionnent ensemble. Pour le connecteur de paiement Adyen, le module de paiement et le module d'adresse de facturation doivent laisser cette valeur vide (état par défaut). Pour le connecteur Paypal, un module d'adresse de facturation dédié n'est pas nécessaire. Pour les autres types de connecteurs de paiement, la chaîne doit être fournie telle que configurée dans le siège de Commerce.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Ajouter un module Paiement à une page de caisse et définir les propriétés requises

Un module Paiement ne peut être ajouté qu’à un module de caisse. Pour plus d’informations sur la configuration d’un module Paiement pour une page de caisse, voir [Module de caisse](add-checkout-module.md).

Si les deux connecteurs de paiement Adyen et Paypal sont nécessaires, ajoutez les deux modules à la section de paiement. Assurez-vous que la valeur de la propriété **Types d'appels d'offres pris en charge** est configurée pour Paypal et laissez ce champ vide pour Adyen. Définissez également la propriété **Paiement principal** sur **Vrai** pour Adyen.

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Panier](add-cart-module.md)

[Module Icône de panier](cart-icon-module.md)

[Module Validation](add-checkout-module.md)

[Module Adresse d’expédition](ship-address-module.md)

[Module Options de livraison](delivery-options-module.md)

[Module d'information sur le retrait](pickup-info-module.md)

[Module Détails de la commande](order-confirmation-module.md)

[Module Carte cadeau](add-giftcard.md)

[Connecteur de paiement Dynamics 365 pour Adyen](dev-itpro/adyen-connector.md)

[Connecteur de paiement Dynamics 365 pour Paypal](paypal.md)

[Authentification rigoureuse des clients à l’aide d’Adyen](adyen_redirect.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]