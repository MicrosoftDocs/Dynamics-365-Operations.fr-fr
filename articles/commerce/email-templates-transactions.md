---
title: Créer des modèles d'e-mail pour les événements transactionnels
description: Cette rubrique décrit comment créer, charger et configurer des modèles d’e-mail pour les événements transactionnels dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 756e2a64ef4c33c347106968eb6bc79a413c3ff7
ms.sourcegitcommit: 88babb2fffe97e93bbde543633fc492120f2a4fc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2021
ms.locfileid: "5555243"
---
# <a name="create-email-templates-for-transactional-events"></a>Créer des modèles de messages électroniques pour les événements transactionnels

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment créer, charger et configurer des modèles d’e-mail pour les événements transactionnels dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Dynamics 365 Commerce fournit une solution prête à l'emploi pour l'envoi d'e-mails qui alertent les clients sur les événements transactionnels (par exemple, lorsqu'une commande est passée, une commande est prête pour le retrait ou une commande a été expédiée). Cette rubrique décrit les étapes de création, de téléchargement et de configuration des modèles d'e-mail utilisés pour envoyer des e-mails transactionnels.

## <a name="create-an-email-template"></a>Créer un modèle d'e-mail

Avant de pouvoir mapper un événement transactionnel spécifique à un modèle d'e-mail, vous devez créer le modèle.

Pour créer un modèle d'e-mail, procédez comme suit.

1. Dans Commerce Headquarters, accédez à **Retail et Commerce \> Paramétrage Headquarters \> Modèles d’e-mail de l’organisation** ou **Administration d’organisation \> Paramétrage \> Modèles d’e-mail de l’organisation**.
1. Sélectionnez **Nouveau**.
1. Définissez les champs suivants sous **Général** :

    - **ID e-mail** - L'ID e-mail est l'identifiant unique d'un modèle. Il s'agit de la valeur qui s'affiche lorsque vous sélectionnez un modèle à mapper à un événement.
    - **Description de l'email** - Vous pouvez utiliser ce champ facultatif pour fournir une description du modèle. La valeur que vous entrez n'apparaît que dans Commerce headquarters.
    - **Nom de l'expéditeur** - Le nom que vous entrez apparaît dans le champ « De » de la plupart des clients de messagerie.
    - **E-mail de l'expéditeur** - Saisissez l'adresse e-mail à utiliser pour les e-mails envoyés à l'aide de ce modèle.
    - **Code de langue par défaut** - Ce champ spécifie la version localisée de l'e-mail envoyé par défaut, si aucune langue n'est fournie par le canal qui invoque ce modèle.

1. Sous **Contenu du message électronique**, sélectionnez **Nouveau**.
1. Dans le champ **Langue**, entrez la langue du modèle d'e-mail. Vous pourrez ajouter plus de langues et de modèles localisés ultérieurement.
1. Dans le champ **Objet**, entrez l'objet de l'e-mail qui doit apparaître dans le champ objet de l'e-mail.
1. Sélectionnez **Modifier** pour télécharger votre modèle d'e-mail.

## <a name="create-an-email-message-body-by-using-html"></a>Créer un corps de message électronique en HTML

Le corps du message de votre e-mail est composé en HTML. Vous pouvez utiliser n'importe quelle mise en page, style et image de marque pris en charge par le format HTML et les feuilles de style en cascade en ligne (CSS). Vous pouvez également utiliser des images, si vous les hébergez sur un point de terminaison Web accessible au public. Pour ajouter une image, entrez son URL dans l'attribut **src** de la balise **&lt;img&gt;** HTML.

> [!NOTE]
> Les clients de messagerie imposent des restrictions de mise en page et de style qui pourraient nécessiter des ajustements du HTML et du CSS que vous utilisez pour le corps du message. Nous vous recommandons de vous familiariser avec les meilleures pratiques de création de code HTML qui seront prises en charge par les clients de messagerie les plus populaires.

## <a name="add-placeholders-to-the-email-message-body"></a>Ajouter des espaces réservés au corps du message électronique

Votre e-mail peut contenir des espaces réservés qui sont remplacés par des valeurs spécifiques au client et à la transaction lors de la génération de l'e-mail. Les espaces réservés sont toujours entourés de signes de pourcentage (%) et sont insérés directement dans le document HTML.

Voici un exemple :

```html
<p>
    Hello %customername%,<br />
    Order number %salesid%, can be picked up from the <b>%pickupstorename%</b> store.
</p>
```

### <a name="order-placeholders-sales-order-level"></a>Espaces réservés de la commande (au niveau de la commande client)

Les espaces réservés suivants récupèrent et affichent les données définies au niveau de la commande client (par opposition au niveau de la ligne de vente).

| Nom de l'espace réservé     | Valeur de l'espace réservé                                            |
| -------------------- | ------------------------------------------------------------ |
| customername         | Le nom du client ayant passé la commande.               |
| salesid              | L'ID ventes de la commande.                                   |
| deliveryaddress      | L'adresse de livraison des commandes expédiées.                     |
| customeraddress      | L'adresse du client.                                 |
| customeremailaddress | L’adresse e-mail que le client a saisie lors du paiement.     |
| deliverydate         | La date de livraison.                                           |
| shipdate             | La date d'expédition.                                               |
| modeofdelivery       | Le mode de livraison de la commande.                              |
| frais              | Le total des frais pour la commande.                             |
| taxe                  | Le montant total de la taxe pour la commande.                                 |
| total                | Le montant total de la commande.                              |
| ordernetamount       | Le montant total de la commande, moins le montant total de la taxe.         |
| Remise             | La remise totale pour la commande.                            |
| storename            | Le nom du magasin où la commande a été passée.            |
| storeaddress         | L'adresse du magasin ayant passé la commande.              |
| storeopenfrom        | L'heure d'ouverture du magasin ayant passé la commande.         |
| storeopento          | L'heure de fermeture du magasin ayant passé la commande.         |
| pickupstorename      | Le nom du magasin où la commande sera récupérée.     |
| pickupstoreaddress   | L'adresse du magasin où la commande sera récupérée.  |
| pickupopenstorefrom  | L'heure d'ouverture du magasin où la commande sera récupérée. |
| pickupopenstoreto    | L'heure de fermeture du magasin où la commande sera récupérée. |

### <a name="order-line-placeholders-sales-line-level"></a>Espaces réservés de la ligne de commande (au niveau de la ligne de vente)

Les espaces réservés suivants récupèrent et affichent des données pour des produits (lignes) individuels dans la commande client.

| Nom de l'espace réservé               | Valeur de l'espace réservé |
|--------------------------------|-------------------|
| productid                      | L'ID produit de la ligne. |
| lineproductname                | Nom du produit. |
| lineproductdescription         | La description du produit. |
| linequantity                   | Le nombre d'unités commandées pour la ligne, plus l'unité de mesure (par exemple, **ea** ou **paire**). |
| lineunit                       | L'unité de mesure de la ligne. |
| linequantity_withoutunit       | Le nombre d'unités commandées pour la ligne, sans l'unité de mesure. |
| linequantitypicked             | Quand l'événement **PickOrder** est utilisé, le nombre d'unités qui ont été récupérées. Autrement, **0** (zéro). |
| linequantitypicked_withoutunit | Quand l'événement **PickOrder** est utilisé, le nombre d'unités qui ont été sélectionnées, sans l'unité de mesure. Autrement, **0** (zéro). |
| linequantitypacked             | Quand les événements **PackOrder** et **Commande prête pour l'enlèvement** sont utilisés, le nombre d'unités qui ont été emballées. Autrement, **0** (zéro). |
| linequantitypacked_withoutuom  | Quand les événements **PackOrder** et **Commande prête pour l'enlèvement** sont utilisés, le nombre d'unités qui ont été emballées, sans l'unité de mesure. Autrement, **0** (zéro). |
| linequantityshipped            | Toujours **0**, sauf lorsque des événements spécifiques sont utilisés, comme décrit dans la ligne suivante. |
| linequantityshipped_withoutuom | Quand l'événement **ShipOrder** est utilisé, le nombre d'unités qui ont été sélectionnées, sans l'unité de mesure. Autrement, **0** (zéro). |
| lineprice                      | Le prix d'une seule unité. |
| linenetamount                  | Le prix de la ligne une fois que le nombre d'unités et la remise sont appliqués. |
| linediscount                   | La remise pour une unité individuelle. |
| lineshipdate                   | La date d'expédition de la ligne. |
| linedeliverydate               | La date de livraison de la ligne. |
| linedeliverymode               | Le mode de livraison de la ligne. |
| linedeliveryaddress            | L'adresse de livraison de la ligne. |
| giftcardnumber                 | Le numéro de la carte cadeau, pour les produits du type de la carte cadeau. |
| giftcardbalance                | Le solde de la carte cadeau, pour les produits du type de la carte cadeau. |
| giftcardmessage                | Le message de la carte cadeau, pour les produits du type de la carte cadeau. |
| giftcardpin                    | Le code PIN de la carte cadeau, pour les produits du type de la carte cadeau. (Cet espace réservé est spécifique aux cartes cadeaux externes.) |
| giftcardexpiration             | La date d'expiration de la carte cadeau, pour les produits du type de la carte cadeau. (Cet espace réservé est spécifique aux cartes cadeaux externes.) |
| giftcardrecipientname          | Le nom du destinataire de la carte cadeau, pour les produits du type de la carte cadeau. |
| giftcardbuyername              | Le nom de l'acheteur de la carte cadeau, pour les produits du type de la carte cadeau. |

### <a name="format-of-order-line-placeholders-in-the-email-message-body"></a>Format des espaces réservés de ligne de commande dans le corps du message électronique

Lorsque vous créez le code HTML pour les lignes de commande individuelles dans le corps du message électronique, entourez le bloc extensible de code HTML et les espaces réservés pour les lignes avec les espaces réservés suivants qui sont placés à l'intérieur des balises de commentaire HTML.

```html
<!--%tablebegin.salesline%-->

(Insert the repeating block of HTML and placeholders for individual lines here.)

<!--%tableend.salesline%-->
```

Voici un exemple :

```HTML
<table>
    <tr>
        <td>Product name</td>
        <td>Quantity</td>
        <td>Price</td>
    </tr>
    <!--%tablebegin.salesline%-->
    <tr>
        <td>%lineproductname%</td>
        <td>%linequantity_withoutunit%</td>
        <td>%lineprice%</td>
    </tr>
    <!--%tableend.salesline%-->
</table>
```

## <a name="create-a-template-for-emailed-receipts"></a>Créer un modèle pour les tickets de caisse envoyés par e-mail

Les tickets de caisse peuvent être envoyés par e-mail aux clients qui effectuent des achats dans un point de vente au détail (PDV). En général, les étapes de création du modèle de ticket de caisse envoyé par e-mail sont les mêmes que celles de création de modèles pour d'autres événements transactionnels. Cependant, les modifications suivantes sont requises :

- Le texte du ticket de caisse est inséré dans l’e-mail en utilisant l’espace réservé **%message%**. Pour vous assurer que le corps du ticket de caisse s’affiche correctement, entourez l’espace réservé **%message%** avec des balises **&lt;pre&gt;** et **&lt;/pre&gt;** HTML.
- L’espace réservé **%receiptid%** peut être utilisé pour afficher un code QR ou un code barres représentant l’ID du ticket de caisse. (Les codes QR et les codes barres sont générés de manière dynamique et diffusés par un service tiers.) Pour plus d’informations sur la façon d’afficher un code QR ou un code barres dans un ticket de caisse envoyé par e-mail, voir [Ajouter un code QR ou un code barres aux e-mails transactionnels et de ticket de caisse](add-qr-code-barcode-email.md).

## <a name="upload-the-email-html"></a>Télécharger l'e-mail au format HTML

Après avoir créé et testé le code HTML de votre corps de message, il doit être téléchargé vers Commerce headquarters. Actuellement, le courrier électronique au format HTML ne peut pas être exporté. Par conséquent, vous devez conserver la copie principale de votre code HTML en dehors de Commerce headquarters.

Pour télécharger un modèle d'e-mail nouveau ou modifié au format HTML, procédez comme suit.

1. Dans Commerce Headquarters, accédez à **Retail et Commerce \> Configuration du siège \> Modèles d'e-mail d'organisation**.
1. Sélectionnez la ligne de la langue pour laquelle vous souhaitez ajouter ou remplacer du HTML. Vous pouvez également sélectionner **Nouveau** pour créer une ligne pour une nouvelle langue.
1. Sélectionnez **Modifier**.
1. Dans la boîte de dialogue qui apparaît, sélectionnez **Parcourir**. Accédez au document HTML que vous souhaitez télécharger, sélectionnez-le, puis sélectionnez **Ouvrir**.
1. Sélectionnez **Charger**.
1. Une fois que votre e-mail au format HTML apparaît dans la fenêtre d'aperçu, cliquez sur **OK**.
1. Assurez-vous que la case à cocher **A un corps** est cochée pour la ligne.

Si vous avez déjà configuré Commerce Headquarters pour envoyer des e-mails, votre nouvel e-mail ou celui mis à jour sera envoyé à tous les clients qui effectuent une transaction qui appelle l'événement mappé au modèle.

Pour plus d'informations sur la configuration des e-mails dans Dynamics 365 Commerce, voir [Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md).

## <a name="additional-resources"></a>Ressources supplémentaires 

[Configurer un profil de notification par e-mail](email-notification-profiles.md)

[Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md)

[Paramétrage des envois de tickets de caisse par e-mail](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-email-receipts)

[Envoyer des tickets de caisse par e-mail depuis Modern POS](email-receipts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
