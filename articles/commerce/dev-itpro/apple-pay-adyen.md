---
title: Configurez Apple Pay avec Adyen dans Dynamics 365 Commerce
description: Cet article décrit comment configurer Apple Pay avec Adyen dans Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: 896847cee696e221b2114f7f28a0b56e73fc911b
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838227"
---
# <a name="set-up-apple-pay-with-adyen-in-dynamics-365-commerce"></a>Configurez Apple Pay avec Adyen dans Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Cet article décrit comment configurer Apple Pay avec Adyen dans Microsoft Dynamics 365 Commerce.

## <a name="key-terms"></a>Termes clés

| Terme | Description |
|---|---|
| Apple Pay | Également connu sous le nom de « bouton » Apple Pay, Apple Pay est une offre de paiement par portefeuille prise en charge par le connecteur Adyen. Elle permet l’expérience client et l’intégration prises en charge par le connecteur Microsoft Dynamics 365 Apple Pay. |
| Portefeuille | Un type de paiement qui n’inclut pas les caractéristiques de paiement traditionnelles, telles que la plage Numéro d’identification bancaire (BIN) et la date d’expiration, qui sont utilisées pour différencier les types de cartes de crédit et de débit. |

Dynamics 365 Commerce offre une intégration prête à l’emploi pour Apple Pay lorsque le service de passerelle de paiement Adyen est utilisé. Apple Pay est un mode de paiement par portefeuille numérique qui utilise un compte marchand Apple Pay en coordination avec le service de paiement Adyen. Lorsqu’il est configuré, le bouton Apple Pay est une mode de paiement sélectionnable qui fait partie de la page de paiement de la commande d’une boutique en ligne. Le bouton Apple Pay est présenté comme une option de paiement uniquement pour les périphériques Apple Pay pris en charge. Lorsque les utilisateurs sélectionnent **Apple Pay** dans un navigateur ou sur un périphérique pris en charge, ils sont dirigés vers le service Apple Pay pour terminer leur paiement directement. Ils sont ensuite renvoyés vers la vitrine en ligne pour finaliser la commande.

La référence de connecteur Dynamics 365 Payment Connector pour Apple Pay est utilisée en sus du connecteur Dynamics 365 Payment Connector pour Adyen pour activer Apple Pay et les paiements par carte de crédit sur le site. Apple Pay peut également être configuré pour être utilisé dans les boutiques équipées de terminaux de paiement Adyen qui utilisent le connecteur Dynamics 365 Payment Connector pour Adyen avec le point de vente (PDV) Commerce. Dans ce cas, le connecteur Dynamics 365 Payment Connector pour Adyen gère l’exploitation du périphérique de paiement Apple par le terminal.

## <a name="prerequisites"></a>Conditions préalables

L’utilisation d’Apple Pay avec Adyen dans Commerce nécessite un compte marchand Apple. Pour plus d’informations sur la configuration d’Apple Pay dans votre espace client de test, voir [Intégration du composant Apple Pay](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#set-up-apple-pay). Pour plus d’informations sur ce qu’il faut faire lorsque vous êtes prêt à la mise en service dans votre environnement de production, voir [Mise en service](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).

Le mode de paiement Apple Pay doit également être intégré à votre compte Adyen. Adyen peut vous aider à configurer le mode de paiement et peut également vous aider à vous assurer que les domaines pour lesquels vous utiliserez le certificat sont attribués pour être utilisés avec le certificat.

Pour activer la fonctionnalité de portefeuille amélioré dans Commerce Headquarters, accédez à **Espaces de travail \> Gestion des fonctionnalités** et recherchez la fonctionnalité **Prise en charge du portefeuille améliorée et améliorations des paiements**. Sélectionnez la fonctionnalité, puis sélectionnez **Activer**. Une fois la fonction activée, exécutez le calendrier de distribution **1110** pour rendre le changement disponible sur tous les canaux.

## <a name="map-the-apple-pay-payment-method"></a>Mapper le mode de paiement Apple Pay

Apple Pay est un mode de paiement par portefeuille numérique. Pour plus d’informations sur la configuration du mappage des paiements pour Apple Pay, voir [Support de paiement par portefeuille](../wallets.md).

Pour mapper le mode de paiement Apple Pay dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Modes de payement \> Types de cartes**.
1. Sélectionnez **Nouveau** pour ajouter une ligne pour Apple Pay, puis définissez les valeurs suivantes :

    - **ID :** ApplePay
    - **Nom du paiement électronique** : Apple Pay
    - **Type :** portefeuille
    - **Émetteur :** Apple

1. Sélectionnez **Mise en correspondance des processeurs** pour ouvrir la boîte de dialogue **Méthodes de mappage de paiement de processeur**. La colonne **Modes de paiement de processeur non mappés** répertorie les modes de paiement pris en charge pour chaque connecteur disponible (Adyen, PayPal et Apple).
1. Mappez les modes de paiement prise en charge que vous voulez à la fois pour le connecteur **Dynamics 365 Payment Connector pour Adyen** (pour une utilisation au PDV) et pour le connecteur **Dynamics 365 Payment Connector pour Apple Pay** (pour le canal en ligne).
1. Pour chaque ligne de mappage, dans la colonne **Modes de paiement de processeur non mappés**, sélectionnez la ligne à prendre en charge, puis sélectionnez **Ajouter** pour déplacer les sélections vers la colonne **Modes de paiement de processeur mappés**.
1. Cliquez sur **OK**, puis, dans la page **Types de cartes**, cliquez sur **Enregistrer**.

## <a name="set-up-the-apple-pay-certificate-for-your-site"></a>Configurer le certificat Apple Pay pour votre site

Pour chaque site, vous devez télécharger le fichier d’association de domaine (également appelé certificat Apple Pay) comme décrit dans la [Documentation Adyen Apple Pay](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live). Vous pouvez utiliser le générateur de site Commerce pour charger le fichier d’association de domaine dans la bibliothèque multimédia de votre site.

Pour configurer le certificat Apple Pay dans le générateur de site, procédez comme suit :

1. Téléchargez le certificat (fichier d’association de domaine) depuis [Adyen](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).
1. Ajoutez l’extension .txt au fichier d’association de domaine.
1. Dans le générateur de site, [chargez](../upload-serve-static-files.md) le fichier d’association de domaine dans la bibliothèque multimédia de votre site.
1. Accédez à **URL**.
1. Sélectionnez **Nouveau \> Nouvelle URL**.
1. Dans la boîte de dialogue **Nouvelle URL**, sélectionnez **Actif de bibliothèque multimédia**.
1. Dans le champ **Chemin d’accès de l’URL**, entrez le chemin d’accès de l’URL (s’il n’apparaît pas). Après l’URL de base du domaine, entrez la chaîne Apple requise suivante : `<domain>/.well-known/apple-developer-merchantid-domain-association.txt`.
1. Cliquez sur **Suivant**. La bibliothèque multimédia affiche tous les actifs multimédia chargés de type **document** (txt).
1. Sélectionnez le fichier d’association de domaine qui doit servir pour les requêtes à l’URL que vous avez définie précédemment.
1. Cliquez sur **Créer**.

À ce stade, l’URL créée est dans un état de brouillon. Publiez l’URL pour terminer le processus. Le fichier vers lequel pointe l’URL ne sera pas renvoyé tant que vous n’aurez pas publié l’URL.

## <a name="configure-a-commerce-online-store-for-apple-pay"></a>Configurer une boutique en ligne Commerce pour Apple Pay

Pour configurer une boutique en ligne Commerce pour Apple Pay, procédez comme suit.

1. Dans Commerce headquarters, accédez à **Retail et Commerce \> Canaux \> Magasins en ligne**.
1. Sélectionnez la valeur **ID de canal de vente au détail** du canal de la boutique en ligne de votre site.
1. Sur le raccourci **Comptes de paiement**, ajoutez le connecteur **Dynamics 365 Payment Connector pour Adyen**, s’il n’est pas déjà configuré, en suivant les instructions suivantes dans [Configurer le connecteur Dynamics 365 Payement Connector pour Adyen](adyen-connector-setup.md).
1. Une fois le connecteur Adyen configuré, sélectionnez **Ajouter** pour ajouter le connecteur **Dynamics 365 Payment Connector pour Apple Pay**.
1. Entrez des valeurs pour les propriétés de marchand du connecteur.

    | Propriété               | Description | Requis | Définir automatiquement | Exemple de valeur |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Nom de l’assembly          | Nom de l’assembly pour le connecteur Dynamics 365 Payment Connector pour Apple Pay. | Oui | Oui | Nom binaire |
    | ID compte de service     | Identificateur unique de la configuration des propriétés du marchand. Cet identifiant est apposé sur les transactions de paiement et identifie les propriétés du marchand que les processus en aval (comme la facturation) doivent utiliser. | Oui | Oui | Guid |
    | ID compte marchand    | Entrez un identificateur unique pour le marchand Adyen. Cette valeur est fournie lorsque vous vous inscrivez auprès d’Adyen, comme décrit dans [S’inscrire à Adyen](adyen-connector-setup.md#sign-up-with-adyen). | Oui | N° | MerchantIdentifier |
    | Clé d’API de cloud          | Entrez la clé d’API cloud Adyen. Obtenez cette clé en suivant les instructions suivantes dans [Comment obtenir la clé API](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Oui | N° | abcdefg |
    | Environnement de la passerelle    | Entrez l’environnement de la passerelle Adyen à mapper. Les valeurs possibles sont **Test** et **Live**. Vous devez définir ce champ sur **Live** uniquement pour les appareils de production et les transactions. | Oui | Oui | Actif |
    | Devises prises en charge   | Entrez les devises que le connecteur doit traiter. Dans les scénarios de présence de carte, Adyen peut prendre en charge des devises supplémentaires par la [conversion dynamique des devises](https://www.adyen.com/pos-payments/dynamic-currency-conversion) après l’envoi de la demande de transaction au terminal de paiement. Contactez le support Adyen pour obtenir la liste des devises prises en charge. | Oui | Oui | USD;EUR |
    | Types de mode de paiement pris en charge | Entrez les types de mode de paiement que le connecteur doit traiter. | Oui | Oui | ApplePay |

1. Une fois les informations du marchand entrées, exécutez la tâche du programme de distribution de configuration du canal **1070**.


### <a name="configure-content-security-policies-in-site-builder"></a>Configurer les stratégies de sécurité du contenu dans le générateur de site

Avant de configurer vos fragments ou vos pages pour qu’ils utilisent Apple Pay, assurez-vous que vos stratégies de sécurité du contenu (CSP) sont configurées dans le générateur de sites Commerce pour votre site.

Pour configurer les stratégies de sécurité du contenu dans le générateur de site, procédez comme suit.

1. Accédez à **Paramètres du site \> Extensions**.
1. Dans l’onglet **Stratégie de sécurité du contenu**, sélectionnez **Ajouter** pour ajouter une ligne qui contient `https://applepay.cdn-apple.com/jsapi/v1/apple-pay-sdk.js` au niveau des sections **child-src**, **connect-src**, **frame-src**, **img-src**, **script-src** et **style-src**.
1. Une fois terminé, sélectionnez **Enregistrer et publier** pour valider les modifications.

### <a name="set-up-apple-pay-as-a-checkout-payment-option"></a>Configurer Apple Pay comme option de paiement à la caisse

Pour configurer Apple Pay comme option de paiement à la caisse sur la page de paiement (non express) de votre site, procédez comme suit.

1. Dans le générateur de site, accédez à **Fragments** et sélectionnez le fragment de paiement de votre site.
1. Sélectionnez **Modifier**.
1. Dans l’emplacement **Conteneur de section de validation**, sélectionnez les points de suspension (**…**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Apple Pay**, puis cliquez sur **OK**.
1. Cliquez sur **Enregistrer**.
1. Sélectionnez **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.

Les paramètres du module **Apple Pay** sont intégrés au module et se connectent au connecteur Dynamics 365 Payment Connector pour Apple Pay configuré pour le canal en ligne dans Commerce Headquarters.

### <a name="apple-pay-payment-behavior"></a>Comportement du paiement Apple Pay

Le bouton de paiement **Apple Pay** s’affiche uniquement sur les périphériques Apple Pay pris en charge (iPhones, iPads et navigateurs Safari prenant en charge Apple Pay). Si un utilisateur n’utilise pas l’un de ces périphériques, le bouton de paiement **Apple Pay** est masqué.

Lorsqu’un utilisateur sélectionne le bouton de paiement **Apple Pay**, une boîte de dialogue **Apple Pay** s’affiche. Elle permet à l’utilisateur de s’authentifier auprès de son périphérique Apple Pay ou de son navigateur. La boîte de dialogue **Apple Pay** affiche une synthèse du montant de la commande et du mode de paiement que l’utilisateur a configuré sur son Apple Wallet. Il peut consulter ces détails, puis cliquer sur **Payer** pour confirmer le paiement. Une fois le paiement effectué, l’utilisateur est dirigé vers la page de site **Commande terminée** qui affiche un résumé de commande détaillé pour la transaction terminée.

## <a name="configure-commerce-pos-for-apple-pay"></a>Configurer le PDV Commerce pour Apple Pay

La configuration du PDV utilise la configuration du champ **Service TEF** du profil de matériel pour le connecteur Dynamics 365 Payment Connector pour Adyen. Dans Commerce Headquarters, configurez le service TEF pour le connecteur Dynamics 365 Payment Connector pour Adyen comme décrit dans [Configurer un profil de matériel de PDV Dynamics 365](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile).

Vérifiez que vous ajoutez **ApplePay** à la liste des types de mode de paiement dans le champ **Types de mode de paiement pris en charge**. Utilisez des points-virgules (;) pour séparer les types de mode de paiement dans la liste.

Le mappage du processeur pour le connecteur Adyen va capturer les types de carte de portefeuille utilisés par Apple Pay sur le terminal de PDV.

## <a name="additional-resources"></a>Ressources supplémentaires

[FAQ Paiements](payments-retail.md)

[Module Validation](../add-checkout-module.md)

[Module Paiement](../payment-module.md)
