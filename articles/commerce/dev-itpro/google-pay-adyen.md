---
title: Configurer Google Pay avec Adyen
description: Cet article décrit comment configurer Google Pay avec Adyen dans Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 07/05/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: cdf950fc7b3720543d93e108d4e3c3c2ab254e09
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838389"
---
# <a name="configure-google-pay-with-adyen"></a>Configurer Google Pay avec Adyen

[!include [banner](../includes/banner.md)]

Cet article décrit comment configurer Google Pay avec Adyen dans Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce offre une intégration prête à l’emploi pour Google Pay lorsque le service de passerelle de paiement Adyen est utilisé. Google Pay est un mode de paiement par portefeuille numérique qui utilise un compte marchand Google Pay en coordination avec le service de paiement Adyen. Lorsqu’il est configuré, le bouton Google Pay est disponible en tant que mode de paiement sélectionnable lors du paiement de la commande en ligne. Lorsque les utilisateurs sélectionnent **Google Pay** dans un navigateur ou un appareil pris en charge, ils sont invités à effectuer leur paiement directement avec le service Google Pay. Ils sont ensuite renvoyés à la vitrine en ligne pour finaliser la commande.

Lorsque Google Pay est utilisé avec le module de paiement express dans Commerce, les informations de compte de paiement de l’utilisateur sont automatiquement préremplies dans le formulaire de paiement pour aider l’utilisateur à passer plus rapidement le processus de paiement. Commerce inclut un module de paiement express qui permet un comportement de paiement express. Le module de paiement express peut être utilisé dans un fragment qui peut être inclus sur une page de paiement ou de panier. Le connecteur de référence Dynamics 365 Payment Connector pour Google Pay est utilisé en sus du connecteur Dynamics 365 Payment Connector pour Adyen pour activer à la fois les options de paiement express et de paiement standard lorsque PayPal est configuré. Google Pay peut également être configuré avec les terminaux de paiement Adyen et le point de vente (POS) Commerce pour une utilisation en magasin.

## <a name="key-terms"></a>Termes clés

| Terme | Description |
|---|---|
| Google Pay | Également connu sous le nom de « bouton » Google Pay, Google Pay est une offre de paiement par portefeuille prise en charge via le connecteur Adyen. Elle permet l’expérience client et l’intégration prises en charge par le connecteur Dynamics Google Pay Connector. |
| Portefeuille | Un type de paiement qui n’inclut pas les caractéristiques de paiement traditionnelles, telles que la plage de numéros d’identification bancaire (BIN) et la date d’expiration, qui sont utilisées pour différencier les types de cartes de crédit et de débit. |
| Module Paiement express | Un module Dynamics 365 Commerce qui prend en charge un comportement de paiement plus rapide lorsque des méthodes de paiement prises en charge sont utilisées. |

## <a name="prerequisites"></a>Conditions préalables

L’utilisation de Google Pay avec Adyen dans Commerce nécessite un compte Google Merchant. Pour plus d’informations sur la configuration de votre compte Google Merchant, consultez la [documentation Adyen sur Google Pay](https://docs.adyen.com/payment-methods/google-pay/) et la [Liste de contrôle d’intégration](https://developers.google.com/pay/api/web/guides/test-and-deploy/integration-checklist) de Google.

Le mode de paiement Google Pay doit également être intégré à votre compte Adyen. Pour obtenir des instructions sur le lien d’intégration, consultez [Adyen Google Pay](https://www.adyen.com/payment-methods/google-pay).

Vous devez également activer la fonction de portefeuille amélioré dans Dynamics 365 Commerce headquarters. Accédez à **Espaces de travail \> Gestion des fonctionnalités**, recherchez la fonctionnalité **Prise en charge du portefeuille améliorée et améliorations des paiements**, sélectionnez la fonction, puis **Activer**. Une fois la fonction activée, exécutez le calendrier de distribution **1110** pour rendre le changement disponible sur tous les canaux.

## <a name="map-the-google-pay-payment-method"></a>Mapper le mode de paiement Google Pay

Google Pay est un mode de paiement par portefeuille numérique. Pour plus d’informations sur la configuration du mappage des paiements pour Google Pay, consultez [Prise en charge du paiement par portefeuille](../wallets.md).

Pour mapper le mode de paiement Google Pay aux types de paiement par carte pour les canaux de point de vente et en ligne, procédez comme suit.

1. Dans Commerce headquarters, accédez à **Retail et Commerce \> Configuration de canal \> Modes de paiements \> Types de carte**.
1. Sélectionnez **Nouveau** pour ajouter une ligne pour Google Pay.
1. Dans le champ **ID**, saisissez **GooglePay**.
1. Dans le champ **Nom de paiement électronique**, saisissez **Google Pay**.
1. Dans le champ **Type**, entrez **Portefeuille**.
1. Dans le champ **Émetteur**, saisissez **Google**.
1. Dans le volet Actions, sélectionnez **Mise en correspondance des processeurs** pour ouvrir la boîte de dialogue **Méthodes de mappage de paiement de processeur**.
1. Sous **Modes de paiement de processeur non mappés**, vous voyez une liste de modes de paiement de processeur non mappés, chacun étant associé au connecteur approprié. Pour mapper les modes de paiement du processeur Google Pay non mappés aux types de paiement par carte, procédez comme suit pour chaque type de paiement par carte :

    1. Sous **Types de paiement par carte**, sélectionnez un type de paiement par carte.
    1. Dans la colonne **Modes de paiement de processeur non mappés**, sélectionnez les connecteurs **Dynamics 365 Payment Connector pour Adyen** (pour une utilisation au point de vente) et **Dynamics 365 Payment Connector pour Google Pay** (pour une utilisation dans les canaux en ligne).
    1. Sélectionnez **Ajouter**. Les sélections sont ajoutées à la colonne **Modes de paiement de processeur mappés**.

1. Lorsque vous avez terminé de mapper les modes de paiement, sélectionnez **Enregistrer**.
1. Sur la page **Types de cartes**, sélectionnez **Enregistrer**.

## <a name="configure-a-commerce-online-store-for-google-pay"></a>Configurer une boutique en ligne Commerce pour Google Pay

Pour configurer une boutique en ligne Commerce pour utiliser Google Pay, procédez comme suit.

1. Dans Commerce headquarters, accédez à **Retail et Commerce \> Canaux \> Magasins en ligne**.
1. Sélectionnez le canal de la boutique en ligne associée à votre site en sélectionnant sa valeur **ID de canal de vente au détail**.
1. Sur le raccourci **Comptes de paiement**, sous **Connecteur**, confirmez que le connecteur **Dynamics 365 Payment Connector for Adyen** est répertorié. S’il ne figure pas dans la liste, suivez les instructions de [Configurer Dynamics 365 Connector pour Adyen](adyen-connector-setup.md) pour l’ajouter.

    > [!NOTE]
    > Dans la plupart des cas, le connecteur **Dynamics 365 Payment Connector for Adyen** doit être répertorié comme le premier connecteur de votre canal (le premier connecteur est également appelé connecteur principal). Il doit ensuite être suivi des autres connecteurs qui seront utilisés, comme les connecteurs **Dynamics 365 Payment Connector pour PayPal** et **Dynamics 365 Payment Connector pour GooglePay**.

1. Une fois le connecteur **Dynamics 365 Payment Connector pour Adyen** ajouté, sélectionnez **Ajouter** pour ajouter le connecteur **Dynamics 365 Payment Connector pour GooglePay**. Définissez ensuite les propriétés suivantes pour le connecteur.

    | Champ                  | Description | Requis | Définir automatiquement | Exemple de valeur |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Nom de l’assembly          | Nom de l’assembly pour le connecteur Dynamics 365 Payment Connector pour GooglePay. | Oui | Oui | *Nom binaire* |
    | ID compte de service     | L’identifiant unique pour la configuration des propriétés du marchand. Cet identifiant est apposé sur les transactions de paiement et identifie les propriétés du marchand que les processus en aval (comme la facturation) doivent utiliser. | Oui | Oui | *GUID* |
    | ID marchand Google     | Saisissez l’identifiant de marchand Google attribué à votre compte marchand Google. Cette propriété est obligatoire pour les environnements de production, mais facultative pour les environnements de test. Pour plus d’informations, rendez-vous sur <https://pay.google.com/>. | Oui | N° | *Identifiant numérique* |
    | ID compte de marchand    | Entrez un identificateur unique pour le marchand Adyen. Cette valeur est fournie lorsque vous vous inscrivez auprès d’Adyen, comme décrit dans [S’inscrire à Adyen](adyen-connector-setup.md#sign-up-with-adyen). | Oui | N° | *Identificateur du marchand* |
    | Clé d’API de cloud          | Entrez la clé d’API cloud Adyen. Pour obtenir cette clé, suivez les instructions dans [Comment obtenir la clé API](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Oui | N° | "abcdefg" |
    | Environnement de la passerelle    | L’environnement de la passerelle Adyen à mapper. Les valeurs possibles sont **Test** et **Live**. Vous devez définir ce champ sur **Live** uniquement pour les appareils de production et les transactions. | Oui | Oui | « Live » |
    | Devises prises en charge   | Les devises que le connecteur doit traiter. Dans les scénarios de présence de carte, Adyen peut prendre en charge des devises supplémentaires via [Conversion dynamique des devises](https://www.adyen.com/pos-payments/dynamic-currency-conversion) après l’envoi de la demande de transaction au terminal de paiement. Contactez le support Adyen pour obtenir une liste des devises prises en charge. | Oui | Oui | « USD;EUR » |
    | Types de mode de paiement pris en charge | Les types de mode de paiement que le connecteur doit traiter. | Oui | Oui | « Google Pay » |

1. Une fois que vous avez terminé de définir les propriétés du connecteur, exécutez la tâche de planification de la distribution **1070 (Configuration du canal**).


### <a name="use-the-payment-express-module-with-google-pay"></a>Utiliser le module de paiement express avec Google Pay

Le module de paiement express Commerce fonctionne avec les méthodes de paiement compatibles pour offrir aux clients du site la possibilité de payer plus rapidement en préremplissant les informations de leur compte de service de paiement lors du processus de paiement. Le module de paiement express fait référence au bouton du connecteur configuré et renvoie les détails de la commande sélectionnée par l’utilisateur (adresse, informations de contact et mode de paiement) pour pré-remplir le formulaire de paiement.

Lorsque le module de paiement express est utilisé avec Google Pay, si les clients sélectionnent le bouton Google Pay dans la section **Paiement express**, la fenêtre iframe de Google Pay s’ouvre. Les utilisateurs peuvent ensuite se connecter à leur compte Google pour utiliser l’adresse de livraison, l’adresse de facturation, l’adresse e-mail et le mode de paiement Google Pay de son choix pour payer la transaction.

Lorsque les utilisateurs exécutent l’action dans la fenêtre Google Pay, il est redirigé vers la page de paiement du site Commerce, où le formulaire de paiement est pré-rempli avec leurs détails de compte Google Pay. Une fois que les utilisateurs sont revenus sur la page de paiement à partir de la fenêtre Google Pay, ils voient les détails suivants :

- Dans le flux de paiement express, la première option de livraison disponible pour l’adresse de livraison renvoyée sera présélectionnée pour le client.
- Lorsque Google Pay est utilisé, aucune adresse e-mail de contact n’est renvoyée. Les utilisateurs de paiement invités devront entrer une adresse e-mail dans la section contact de la page de paiement. Les utilisateurs connectés verront leurs coordonnées automatiquement renseignées à partir de leur compte client Dynamics (l’adresse e-mail principale qu’ils ont utilisée pour l’authentification).

Les clients ont la possibilité de revoir les commandes et d’en modifier les détails avant de sélectionner **Passer la commande** pour finaliser la commande.

### <a name="configure-google-pay-in-site-builder"></a>Configurer Google Pay dans le créateur de site 

Avant de configurer vos fragments ou vos pages avec Google Pay, vous devez vous assurer que vos politiques de sécurité de contenu pour votre site sont définies dans le générateur de sites Commerce.

Pour vous assurer que vos politiques de sécurité de contenu sont définies dans le générateur de site, procédez comme suit.

1. Dans votre site, accédez à **Paramètres du site \> Extensions**.
1. Sur l’onglet **Stratégie de la sécurité de contenu**, ajoutez une ligne pour `*.google.com` aux directives **child-src**, **connect-src**, **frame-ancestors**, **frame-src**, **img-src**, **script-src** et **style-src**.
1. Lorsque vous avez terminé, sélectionnez **Enregistrer et publier**.

### <a name="configure-the-payment-express-fragment-with-google-pay-in-site-builder"></a>Configurez le fragment de paiement express avec Google Pay dans le générateur de site

Pour configurer le fragment de paiement express avec Google Pay pour la boutique en ligne, procédez comme suit.

1. Dans le générateur de site, accédez à **Fragments**.
1. Cliquez sur **Nouveau**.
1. Dans la boîte de dialogue **Nouveau fragment**, sélectionnez le module **Conteneur**, entrez un nom pour le fragment (par exemple, **Paiement express**), puis sélectionnez **OK**. 
1. Sélectionnez le nouvel emplacement **Conteneur par défaut** du fragment.
1. Dans le volet des propriétés du module sur la droite, définissez les propriétés du module de conteneur :

    - **Titre** : saisissez un titre à afficher pour la section de paiement express de votre site (par exemple, **Paiement express**).
    - **Disposition du conteneur** : sélectionnez **Flux**.
    - **Largeur** - Sélectionnez **Remplir le conteneur**.
    - **Enfants affichés** : sélectionnez **Trois** pour spécifier le nombre d’enfants qui tiendront dans une ligne de la section de paiement express de la page de paiement (par exemple, une zone de texte, paiement express pour PayPal et paiement express pour Google Pay).
    - **Nom de classe CSS** : saisissez **msc-express-payment-container** (obligatoire).

    > [!IMPORTANT]
    > - La valeur **Nom de classe CSS** doit être définie sur **msc-express-payment-container** pour contrôler le comportement du conteneur pendant le paiement. Ce comportement inclut le masquage, la réduction et d’autres actions qui s’appliquent à la section de paiement express pendant le flux de paiement. La classe **msc-express-payment-container** fonctionne avec les opérations par défaut publiées avec le module d’extraction de la bibliothèque de modules.
    > - Des styles supplémentaires peuvent être ajoutés au **nom de classe CSS**. Si vous personnalisez le comportement du module, vérifiez les contrôles de style si vous utilisez le même comportement codé de la bibliothèque de modules dans le module de paiement pour le comportement de paiement express.

1. Dans l’emplacement **Conteneur par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner les modules**, sélectionnez le module **Paiement express**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module **Paiement express**, définissez ou ajustez la valeur **Hauteur de l’élément iFrame** en pixels (**60**).
1. Dans le champ **Types d’appels d’offres pris en charge**, entrez **GooglePay**. La valeur doit correspondre à la chaîne **Types de mode de paiement pris en charge** dans le connecteur qui est configuré pour le canal (comme décrit dans la section [Configurer une boutique en ligne Commerce pour Google Pay](#configure-a-commerce-online-store-for-google-pay) plus haut dans cet article).

    > [!NOTE]
    > Vous pouvez répéter les étapes 6 à 9 pour ajouter des modules **Paiement express** pour d’autres modes de paiement. Alignez la valeur **Types de mode de paiement pris en charge** avec les types de paiement supplémentaires configurés (par exemple, **Paypal**).

1. Facultatif : vous pouvez ajouter un module de bloc de texte au module de conteneur par défaut pour inclure des instructions ou des informations de divulgation. Après avoir ajouté le module, dans le volet des propriétés, entrez le texte souhaité dans le champ **Texte enrichi**. Vous pouvez positionner le texte sur ou sous les modules de paiement express en sélectionnant les points de suspension (**...**) dans l’emplacement de **Bloc de texte**, puis en sélectionnant **Déplacer vers le haut** ou **Déplacer vers le bas**.
1. Sélectionnez **Enregistrer** pour enregistrer vos modifications, puis sélectionnez **Terminer la modification**.
1. Sélectionnez **Publier** pour publier le fragment.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Ajouter le fragment de paiement express à la page de paiement

Pour ajouter le fragment de paiement express à la page de paiement, procédez comme suit.

1. Dans le générateur de site, accédez à **Pages**, puis sélectionnez la page de paiement de votre site.
1. Sélectionnez **Modifier**.
1. Dans l’**Emplacement principal**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module sur la droite, définissez les propriétés du module de conteneur :

    - **Disposition du conteneur** - Sélectionnez **Empilé**.
    - **Largeur** - Sélectionnez **Remplir le conteneur**.
    - **Enfants affichés** : sélectionnez **Trois** pour spécifier le nombre d’enfants qui tiendront dans une ligne de la section de paiement express de la page de paiement (par exemple, une zone de texte, paiement express pour PayPal et paiement express pour Google Pay).

1. Dans l’emplacement du module **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un fragment**.
1. Dans la boîte de dialogue **Sélectionner un fragment**, recherchez et sélectionnez le fragment de paiement express que vous avez créé au préalable, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer** pour enregistrer vos modifications, puis sélectionnez **Terminer la modification**.
1. Sélectionnez **Publier** pour publier la page.

> [!NOTE]
> Si la page de paiement comprend déjà un conteneur contenant le fragment de paiement et que vous souhaitez que le module de paiement express soit rendu au-dessus du conteneur de paiement normal, vous pouvez le positionner au-dessus ou en dessous du paiement existant en sélectionnant les points de suspension (**...**) dans l’**Emplacement principal**, puis en sélectionnant **Déplacer vers le haut** ou **Déplacer vers le bas**.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Ajouter le fragment de paiement express à la page de panier

Pour ajouter le fragment de paiement express à la page de panier, procédez comme suit.

1. Dans le générateur de site, accédez à **Pages**, puis sélectionnez la page de paiement de votre panier.
2. Sélectionnez **Modifier**.
3. Dans la vue en plan, développez l’**Emplacement principal** dans l’arborescence, et recherchez le conteneur qui contient le module **Panier**.
4. Dans le module **Panier**, sélectionnez l’emplacement **Paiement express**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
5. Dans la boîte de dialogue **Sélectionner les modules**, sélectionnez le module **Paiement express**, puis sélectionnez **OK**.
6. Sélectionnez l’emplacement de module **Paiement express**. Ensuite, dans le volet des propriétés à droite, sous **Types d’offres pris en charge**, saisissez **GooglePay**. La valeur doit correspondre à la chaîne **Types de mode de paiement pris en charge** dans le connecteur qui est configuré pour le canal (comme décrit dans la section [Configurer une boutique en ligne Commerce pour Google Pay](#configure-a-commerce-online-store-for-google-pay) plus haut dans cet article).
1. Sélectionnez **Enregistrer** pour enregistrer vos modifications, puis sélectionnez **Terminer la modification**.
1. Sélectionnez **Publier** pour publier la page.

Les utilisateurs peuvent inclure jusqu’à trois modules **Paiement express** (en d’autres termes, trois options de paiement prises en charge disponibles) dans l’emplacement **Paiement express** du panier.

### <a name="set-up-google-pay-as-an-option-in-the-checkout-payment-section"></a>Configurez Google Pay en tant qu’option dans la section de paiement à la caisse

Vous pouvez configurer Google Pay en tant qu’option dans la section de paiement en caisse pour une fonctionnalité de paiement uniquement et non express. Le formulaire de paiement sera rempli par l’utilisateur et la page de paiement Google Pay préparera uniquement le paiement pour le paiement par Google Pay. Aucune information de compte Google ne sera utilisée pour écraser les détails de paiement remplis.

> [!NOTE]
> La procédure suivante suppose que votre site utilise un fragment de paiement configuré avec des informations de retrait, une adresse de livraison, des options de livraison, des informations de contact, des conditions générales facultatives et une section pour les éléments de paiement. Le module de paiement de la bibliothèque de modules par défaut est publié avec un conteneur de section de paiement contenant un bloc de texte, des points de fidélité, une carte-cadeau et des modules de paiement. Pour plus d’informations, voir [Module de paiement](../payment-module.md).

Pour configurer Google Pay en tant qu’option de paiement standard dans la section **Mode de paiement** de la page de paiement, suivez ces étapes.

1. Dans le générateur de site, accédez à **Fragments**, puis sélectionnez le fragment de paiement de votre site.
1. Sélectionnez **Modifier**.
1. Dans l’emplacement **Informations de caisse**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner les modules**, sélectionnez le module **Paiement**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module **Paiement** sur la droite, définissez les propriétés du module de conteneur :

    - **Titre** : saisissez un titre à afficher pour la section de paiement express de votre site (par exemple, **Google Pay**).
    - **Hauteur de l’iFrame** : remplacez la valeur par votre hauteur de conception préférée en pixels (par exemple, **75**). 
    - **Types d’offre pris en charge** : saisissez **GooglePay** pour correspondre à la configuration du connecteur Google Pay dans Commerce headquarters.
    - **Est le paiement principal** : laissez la case décochée. (Cette propriété est généralement activée pour le module de paiement Adyen.)
    - **Remplacement du style de paiement** : cette propriété n’est pas prise en charge pour la configuration de Google Pay.
    - **Utiliser l’identifiant du connecteur** : cette propriété doit être sélectionnée si plusieurs connecteurs de paiement sont utilisés sur la page.

1. Positionnez le module sur ou sous les autres modules de paiement en sélectionnant les points de suspension (**...**) dans l’emplacement de **Paiement**, puis en sélectionnant **Déplacer vers le haut** ou **Déplacer vers le bas**.
1. Sélectionnez **Enregistrer** pour enregistrer vos modifications, puis sélectionnez **Terminer la modification**.
1. Cliquez sur **Publier**.

### <a name="modes-of-delivery"></a>Modes de livraison

Avec le module de paiement express configuré pour utiliser Google Pay, la première option de livraison renvoyée pour l’adresse de livraison sélectionnée pour le compte Google Pay sera présélectionnée. Les utilisateurs ont la possibilité d’ajuster l’adresse de livraison à une option différente s’ils le souhaitent.

L’ordre dans lequel les modes de livraison sont affichés dans le module de paiement express est configuré sur la page **Modes de livraison** du canal dans Commerce headquarters. Dans Commerce headquarters, accédez à **Retail et Commerce \> Canaux \> Magasins en ligne**, et sélectionnez la valeur **ID canal de vente au détail** pour votre magasin. Dans le volet Actions, sous l’onglet **Paramétrage**, sélectionnez **Modes de livraison**. Les modes de livraison qui y sont listés seront affichés dans une même commande dans le module de paiement express. Sélectionnez **Gérer les modes de livraison** dans le volet Actions pour ajouter ou supprimer des modes de livraison pour un canal ou un produit de vente au détail. Pour plus d’informations sur la configuration des modes de livraison, consultez [Configurer les modes de livraison](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Le module de paiement utilise également le module d’options de livraison lorsque les modes de livraison sont rendus lors du paiement. Pour plus d’informations, voir [Module Options de livraison](../delivery-options-module.md).

Les modes de livraison sont affichés au fur et à mesure qu’ils sont ajoutés à la liste **Modes de livraison** dans le magasin en ligne.

## <a name="configure-commerce-pos-for-google-pay"></a>Configurer le PDV Commerce pour Google Pay

La configuration du PDV utilise le paramètre du champ **Service TEF** du profil de matériel pour le connecteur Dynamics 365 Payment Connector pour Adyen. Pour plus d’informations sur la configuration du service de transfert électronique de fonds (TEF) pour le connecteur Dynamics 365 Payment Connector pour Adyen dans Commerce headquarters, voir [Configurer un profil de matériel de PDV Dynamics 365](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile).

Le mappage du processeur pour le connecteur Adyen capture les types de carte de portefeuille que Google Pay utilise sur le terminal de point de vente.

## <a name="additional-resources"></a>Ressources supplémentaires

[FAQ Paiements](payments-retail.md)

[Module Validation](../add-checkout-module.md)

[Module Paiement](../payment-module.md)
