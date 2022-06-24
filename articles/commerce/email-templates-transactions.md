---
title: Créer des modèles d’e-mail pour les événements transactionnels
description: Cet article décrit comment créer, charger et configurer des modèles d’e-mail pour les événements transactionnels dans Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9a4d67d901608e210b4060a655ce39f0ea707a52
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910548"
---
# <a name="create-email-templates-for-transactional-events"></a>Créer des modèles d’e-mail pour les événements transactionnels

[!include [banner](includes/banner.md)]


Cet article décrit comment créer, charger et configurer des modèles d’e-mail pour les événements transactionnels dans Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce fournit une solution prête à l’emploi pour l’envoi d’e-mails qui alertent les clients sur des événements transactionnels. Par exemple, des e-mails peuvent être envoyés lorsqu’une commande est passée, est prête à être récupérée ou a été expédiée. Cet article décrit les étapes de création, de téléchargement et de configuration des modèles d’e-mail utilisés pour envoyer des e-mails transactionnels.

## <a name="notification-types"></a>Types de notification

Les notifications peuvent être configurées pour informer les clients par e-mail lorsque des événements spécifiques se produisent dans le cadre de la commande et du cycle de vie du client. Pour configurer les notifications, vous devez mettre en correspondance un modèle d’e-mail avec un type de notification en créant un profil Commerce de notification par e-mail. Pour plus d’informations sur la configuration des profils de notification par e-mail, voir [Configurer un profil de notification par e-mail](email-notification-profiles.md).

Dynamics 365 Commerce prend en charge les types de notification suivants.

### <a name="order-created"></a>Commande créée

Le type de notification *Commande créée* est déclenché lorsqu’une nouvelle commande client est créée dans Commerce Headquarters.

> [!NOTE]
> Le type de notification Commande créée n’est pas déclenché pour les transactions au comptant sans livraison qui se produisent à un terminal de point de vente (PDV). Dans ce cas, un reçu envoyé par e-mail et/ou imprimé est généré à la place. Pour plus d’informations, voir [Envoyer des accusés de réception par e-mail depuis Modern POS (MPOS)](email-receipts.md).

### <a name="order-confirmed"></a>Commande confirmée

Le type de notification *Commande confirmée* est déclenché lorsqu’un document de confirmation de commande est généré pour une commande client dans Commerce Headquarters.

### <a name="picking-completed"></a>Prélèvement terminé

Le type de notification *Prélèvement terminé* est déclenché lorsqu’une liste de prélèvement pour une commande est marquée comme terminée dans Commerce Headquarters.

> [!NOTE]
> Le type de notification Prélèvement terminé n’est pas déclenché lorsqu’un article est marqué comme prélevé sur un terminal de PDV.

### <a name="packing-completed"></a>Emballage terminé

Le type de notification *Emballage terminé* est déclenché lorsqu’un bon de livraison est généré pour une commande dans Commerce Headquarters sur un terminal de PDV.

Le type de notification Emballage terminé prend en charge les espaces réservés d’e-mail supplémentaires suivants pour faciliter la fonctionnalité Commande prête pour l’enlèvement et la fonctionnalité de recherche de commande à partir d’e-mails transactionnels.

| Nom de l’espace réservé    | Objectif |
| ------------------- | ------- |
| `pickupstorename`     | Nom du magasin où la commande est disponible pour enlèvement. |
| `pickupstoreaddress`  | Adresse du magasin où la commande est disponible pour enlèvement. |
| `pickupstoreopenfrom` | Heure d’ouverture du magasin d’enlèvement. |
| `pickupstoreopento` | Heure de fermeture du magasin d’enlèvement. |
| `pickupchannelid`     | ID de canal de magasin du magasin d’enlèvement. |
| `packingslipid`      | ID du bon de livraison de la commande qui sera enlevée. |
| `confirmationid`      | ID de confirmation de commande de la commande qui sera enlevée. (Cet identifiant est parfois appelé ID référence de canal.) |

Pour plus d’informations sur les fonctionnalités d’enregistrement des clients et de recherche de commandes, voir [Configurer la géodétection et la redirection](geo-detection-redirection.md) et [Activer la recherche de commande pour les paiements sans inscription](order-lookup-guest.md).

### <a name="order-ready-for-pickup"></a>Commande prête pour l’enlèvement

Le type de notification *Commande prête pour l’enlèvement* est déclenché lorsqu’une commande est marquée comme emballée et que le mode de livraison est défini sur **Prélèvement client** sur une ou plusieurs lignes de commande.

> [!NOTE]
> Le type de notification Commande prête pour l’enlèvement a été remplacé par le type de notification Emballage terminé. Ce type de notification est personnalisé par mode de livraison.

### <a name="order-shipped"></a>Commande expédiée

Le type de notification *Commande expédiée* est déclenché lorsqu’une commande dont le mode de livraison est Enlèvement hors magasin est facturée.

> [!NOTE]
> Le type de notification Commande expédiée a été remplacé par le type de notification Commande facturée. Ce type de notification est personnalisé par mode de livraison.

### <a name="order-invoiced"></a>Commande facturée

Le type de notification *Commande facturée* est déclenché lorsqu’une commande client est facturée dans un PDV ou dans Commerce Headquarters.

### <a name="issue-gift-card"></a>Émettre une carte cadeau

Le type de notification *Émettre une carte cadeau* est déclenché lorsqu’une commande client contenant un produit de type carte-cadeau est facturée.

> [!NOTE]
> L’e-mail de notification Émettre une carte cadeau est envoyé au destinataire de la carte-cadeau. Le destinataire de la carte cadeau est précisé dans Commerce Headquarters, sur une ligne de commande client individuelle dans l’onglet **Emballage** sous **Détails de la ligne**. Il peut être spécifié manuellement ou par programmation.

Le type de notification Émettre une carte cadeau prend en charge les espaces réservés supplémentaires suivants.

| Nom de l’espace réservé      | Objectif |
| --------------------- | ------- |
| `giftcardnumber`        | Le numéro de la carte cadeau, pour les produits du type de la carte cadeau. |
| `availablebalance` | Le solde restant sur la carte-cadeau. |
| `giftcardmessage`       | Le message de la carte cadeau, pour les produits du type de la carte cadeau. |
| `giftcardpin`         | Le code PIN de la carte cadeau, pour les produits du type de la carte cadeau. (Cet espace réservé est spécifique aux cartes cadeaux externes.) |
| `giftcardexpiration`    | La date d’expiration de la carte cadeau, pour les produits du type de la carte cadeau. (Cet espace réservé est spécifique aux cartes cadeaux externes.) |
| `giftcardrecipientname` | Le nom du destinataire de la carte cadeau, pour les produits du type de la carte cadeau. |
| `giftcardbuyername`     | Le nom de l’acheteur de la carte cadeau, pour les produits du type de la carte cadeau. |

Pour plus d’informations sur les cartes-cadeaux, voir [Cartes-cadeaux numériques e-commerce](digital-gift-cards.md) et [Prendre en charge des cartes cadeaux externes](dev-itpro/gift-card.md).

### <a name="order-cancellation"></a>Annulation de commande

Le type de notification *Annulation de commande* est déclenché lorsqu’une commande client est annulée dans Commerce Headquarters.

### <a name="customer-created"></a>Client créé

Le type de notification *Client créé* est déclenché lorsqu’une nouvelle entité client est créée dans Commerce Headquarters.

### <a name="b2b-prospect-approved"></a>Prospect B2B approuvé

Le type de notification *Prospect B2B approuvé* est déclenché lorsque la demande d’intégration d’un prospect est approuvée dans Commerce Headquarters. Pour plus d’informations sur l’approbation ou le rejet des prospects B2B, voir [Configurer l’utilisateur administrateur pour un nouveau partenaire commercial](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner). 

Le type de notification Prospect B2B approuvé prend en charge les espaces réservés supplémentaires suivants.

| Nom de l’espace réservé | Objectif                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`       | Prénom du prospect B2B tel qu’il est saisi dans l’application. |
| `lastname`         | Nom du prospect B2B tel qu’il est saisi dans l’application. |
| `company`          | Nom de la société du candidat tel qu’il est saisi dans l’application. |
| `email`            | Adresse e-mail du prospect tel qu’elle est saisie dans l’application.   |
| `zipcode`          | Code postal de l’adresse principale du prospect. |
| `comments`         | Commentaire que le prospect a saisi dans l’application. |
| `storename`        | Nom du canal où le prospect a été créé. |
| `storeurl`         | Vide par défaut. Une extension personnalisée doit être créée pour utiliser cet espace réservé. |

### <a name="b2b-prospect-rejected"></a>Prospect B2B rejeté

Le type de notification *Prospect B2B rejeté* est déclenché lorsque la demande d’intégration d’un prospect est rejetée dans Commerce Headquarters. Pour plus d’informations sur l’approbation ou le rejet des prospects B2B, voir [Configurer l’utilisateur administrateur pour un nouveau partenaire commercial](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner). 

Le type de notification Prospect B2B rejeté prend en charge les espaces réservés supplémentaires suivants.

| Nom de l’espace réservé | Objectif                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`        | Prénom du prospect B2B tel qu’il est saisi dans l’application. |
| `lastname`         | Nom du prospect B2B tel qu’il est saisi dans l’application. |
| `company`          | Nom de la société du candidat tel qu’il est saisi dans l’application. |

## <a name="create-an-email-template"></a>Créer un modèle d’e-mail

Avant de pouvoir mapper un événement transactionnel spécifique à un modèle d’e-mail, vous devez créer le modèle.

Pour créer un modèle d’e-mail, procédez comme suit.

1. Dans Commerce Headquarters, accédez à **Retail et Commerce \> Paramétrage Headquarters \> Modèles d’e-mail de l’organisation** ou **Administration d’organisation \> Paramétrage \> Modèles d’e-mail de l’organisation**.
1. Sélectionnez **Nouveau**.
1. Définissez les champs suivants sous **Général** :

    - **ID e-mail** – L’ID e-mail est l’identifiant unique d’un modèle. C’est la valeur qui s’affiche lorsque vous sélectionnez un modèle à mettre en correspondance avec un événement.
    - **Description de l’email** - Vous pouvez utiliser ce champ facultatif pour fournir une description du modèle. La valeur que vous entrez n’apparaît que dans Commerce headquarters.
    - **Nom de l’expéditeur** - Le nom que vous entrez apparaît dans le champ « De » de la plupart des clients de messagerie.
    - **E-mail de l’expéditeur** - Saisissez l’adresse e-mail à utiliser pour les e-mails envoyés à l’aide de ce modèle.
    - **Code de langue par défaut** - Ce champ spécifie la version localisée de l’e-mail envoyé par défaut, si le canal qui invoque ce modèle ne spécifie pas de langue.

1. Sous **Contenu du message électronique**, sélectionnez **Nouveau**.
1. Dans le champ **Langue**, entrez la langue du modèle d’e-mail. Vous pourrez ajouter plus de langues et de modèles localisés ultérieurement.
1. Dans le champ **Objet**, entrez l’objet de l’e-mail qui doit apparaître dans le champ objet de l’e-mail.
1. Sélectionnez **Modifier** pour télécharger votre modèle d’e-mail.

## <a name="create-an-email-message-body-by-using-html"></a>Créer un corps de message électronique en HTML

Le corps du message de votre e-mail est composé en HTML. Vous pouvez utiliser n’importe quelle mise en page, style et image de marque pris en charge par le format HTML et les feuilles de style en cascade en ligne (CSS). Vous pouvez également utiliser des images, si vous les hébergez sur un point de terminaison Web accessible au public. Pour ajouter une image, entrez son URL dans l’attribut **src** de la balise **&lt;img&gt;** HTML.

> [!NOTE]
> Les clients de messagerie imposent des restrictions de mise en page et de style qui pourraient nécessiter des ajustements du HTML et du CSS que vous utilisez pour le corps du message. Nous vous recommandons de vous familiariser avec les meilleures pratiques de création de code HTML que les clients de messagerie les plus populaires prendront en charge.

## <a name="add-placeholders-to-the-email-message-body"></a>Ajouter des espaces réservés au corps du message électronique

Votre e-mail peut contenir des espaces réservés qui sont remplacés par des valeurs spécifiques au client et à la transaction lors de la génération de l’e-mail. Les espaces réservés sont toujours entourés de signes de pourcentage (%) et sont insérés directement dans le document HTML.

Voici un exemple :

```html
<p>
    Hello %customername%,<br />
    Order number %salesid%, can be picked up from the <b>%pickupstorename%</b> store.
</p>
```

### <a name="order-placeholders-sales-order-level"></a>Espaces réservés de la commande (au niveau de la commande client)

Les espaces réservés suivants récupèrent et affichent les données définies au niveau de la commande client (par opposition au niveau de la ligne de vente).

| Nom de l’espace réservé     | Objectif                                                      |
| -------------------- | ------------------------------------------------------------ |
| `customername`         | Le nom du client ayant passé la commande.               |
| `customeraddress`      | L’adresse du client.                                 |
| `customeremailaddress` | L’adresse e-mail que le client a saisie lors du paiement.     |
| `salesid`              | L’ID ventes de la commande.                                   |
| `orderconfirmationid`  | L’ID intercanal qui a été généré lors de la création de la commande.   |
| `channelid`            | L’ID du canal de vente au détail ou en ligne par lequel la commande a été passée. |
| `deliveryname`         | Le nom spécifié pour l’adresse de livraison.         |
| `deliveryaddress`      | L’adresse de livraison des commandes expédiées.                     |
| `deliverydate`         | La date de livraison.                                           |
| `shipdate`             | La date d’expédition.                                               |
| `modeofdelivery`       | Le mode de livraison de la commande.                              |
| `ordernetamount`       | Le montant total de la commande, moins le montant total de la taxe.         |
| `discount`            | La remise totale pour la commande.                            |
| `charges`              | Le total des frais pour la commande.                             |
| `tax`                  | Le montant total de la taxe pour la commande.                                 |
| `total`                | Le montant total de la commande.                              |
| `storename`            | Le nom du magasin où la commande a été passée.            |
| `storeaddress`         | L’adresse du magasin ayant passé la commande.              |
| `storeopenfrom`        | L’heure d’ouverture du magasin ayant passé la commande.         |
| `storeopento`          | L’heure de fermeture du magasin ayant passé la commande.         |
| `pickupstorename`      | Le nom du magasin où la commande sera récupérée.\*   |
| `pickupstoreaddress`   | L’adresse du magasin où la commande sera récupérée.\* |
| `pickupopenstorefrom`  | L’heure d’ouverture du magasin où la commande sera récupérée.\* |
| `pickupopenstoreto`    | L’heure de fermeture du magasin où la commande sera récupérée.\* |
| `pickupchannelid`     | L’ID de canal du magasin qui est spécifié pour un mode de livraison en retrait.\* |
| `packingslipid`        | L’ID du bon de livraison qui a été généré lorsque les lignes d’une commande ont été emballées.\* |

\* Ces espaces réservés renvoient des données uniquement lorsqu’ils sont utilisés pour le type de notification **Commande prête pour l’enlèvement**. 

### <a name="order-line-placeholders-sales-line-level"></a>Espaces réservés de la ligne de commande (au niveau de la ligne de vente)

Les espaces réservés suivants récupèrent et affichent des données pour des produits (lignes) individuels dans la commande client.

| Nom de l’espace réservé               | Objectif |
|--------------------------------|-------------------|
| `productid`                      | <p>L’ID du produit. Cet ID prend en compte les variantes.</p><p><strong>Remarque :</strong> Cet espace réservé a été remplacé par `lineproductrecid`.</p> |
| `lineproductrecid`               | L’ID du produit. Cet ID prend en compte les variantes. Il identifie de manière unique un article au niveau de la variante. |
| `lineitemid`                     | L’ID de niveau produit du produit. (Cet ID ne prend en compte les variantes.) |
| `lineproductvariantid`           | L’ID de la variante de produit. |
| `lineproductname`                | Nom du produit. |
| `lineproductdescription`         | La description du produit. |
| `linequantity`                   | Le nombre d’unités commandées pour la ligne, plus l’unité de mesure (par exemple, **ea** ou **paire**). |
| `lineunit`                       | L’unité de mesure de la ligne. |
| `linequantity_withoutunit`       | Le nombre d’unités commandées pour la ligne, sans l’unité de mesure. |
| `linequantitypicked`             | Quand l’événement **PickOrder** est utilisé, le nombre d’unités qui ont été récupérées. Autrement, **0** (zéro). |
| `linequantitypicked_withoutunit` | Quand l’événement **PickOrder** est utilisé, le nombre d’unités qui ont été sélectionnées, sans l’unité de mesure. Autrement, **0** (zéro). |
| `linequantitypacked`             | Quand les événements **PackOrder** et **Commande prête pour l’enlèvement** sont utilisés, le nombre d’unités qui ont été emballées. Autrement, **0** (zéro). |
| `linequantitypacked_withoutuom`  | Quand les événements **PackOrder** et **Commande prête pour l’enlèvement** sont utilisés, le nombre d’unités qui ont été emballées, sans l’unité de mesure. Autrement, **0** (zéro). |
| `linequantityshipped`            | Toujours **0**, sauf lorsque des événements spécifiques sont utilisés, comme décrit dans la ligne suivante. |
| `linequantityshipped_withoutuom` | Quand l’événement **ShipOrder** est utilisé, le nombre d’unités qui ont été sélectionnées, sans l’unité de mesure. Autrement, **0** (zéro). |
| `lineprice`                      | Le prix d’une seule unité. |
| `linenetamount`                  | Le prix de la ligne une fois que le nombre d’unités et la remise sont appliqués. |
| `linediscount`                   | La remise pour une unité individuelle. |
| `lineshipdate`                   | La date d’expédition de la ligne. |
| `linedeliverydate`               | La date de livraison de la ligne. |
| `linedeliverymode`               | Le mode de livraison de la ligne. |
| `linedeliveryaddress`            | L’adresse de livraison de la ligne. |
| `linepickupdate`                 | La date de retrait que le client a spécifiée, pour les commandes qui utilisent un mode de livraison en retrait. |
| `linepickuptimeslot`             | La plage de retrait que le client a spécifiée, pour les commandes qui utilisent un mode de livraison en retrait. |
| `giftcardnumber`                 | Le numéro de la carte cadeau, pour les produits du type de la carte cadeau. |
| `giftcardbalance`                | Le solde de la carte cadeau, pour les produits du type de la carte cadeau. |
| `giftcardmessage`                | Le message de la carte cadeau, pour les produits du type de la carte cadeau. |
| `giftcardpin`                    | Code PIN de la carte cadeau, pour les produits du type de la carte cadeau. (Cet espace réservé est spécifique aux cartes cadeaux externes.) |
| `giftcardexpiration`             | La date d’expiration de la carte cadeau, pour les produits du type de la carte cadeau. (Cet espace réservé est spécifique aux cartes cadeaux externes.) |
| `giftcardrecipientname`          | Le nom du destinataire de la carte cadeau, pour les produits du type de la carte cadeau. |
| `giftcardbuyername`              | Le nom de l’acheteur de la carte cadeau, pour les produits du type de la carte cadeau. |

### <a name="format-of-order-line-placeholders-in-the-email-message-body"></a>Format des espaces réservés de ligne de commande dans le corps du message électronique

Lorsque vous créez le code HTML pour les lignes de commande individuelles dans le corps du message électronique, entourez le bloc extensible de code HTML et les espaces réservés pour les lignes avec les espaces réservés suivants. Notez que les espaces réservés se trouvent à l’intérieur des balises de commentaire HTML.

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

Les tickets de caisse peuvent être envoyés par e-mail aux clients qui effectuent des achats dans un point de vente au détail (PDV). En général, les étapes de création du modèle de ticket de caisse envoyé par e-mail sont les mêmes que celles de création de modèles pour d’autres événements transactionnels. Cependant, les modifications suivantes sont requises :

- L’espace réservé **%message%** est utilisé pour insérer le texte du ticket de caisse dans l’e-mail. Pour vous assurer que le corps du ticket de caisse s’affiche correctement, entourez l’espace réservé **%message%** avec des balises **&lt;pre&gt;** et **&lt;/pre&gt;** HTML.
- L’espace réservé **%receiptid%** peut être utilisé pour afficher un code QR ou un code barres représentant l’ID du ticket de caisse. (Les codes QR et les codes barres sont générés de manière dynamique et diffusés par un service tiers.) Pour plus d’informations sur la façon d’afficher un code QR ou un code barres dans un ticket de caisse envoyé par e-mail, voir [Ajouter un code QR ou un code barres aux e-mails transactionnels et de ticket de caisse](add-qr-code-barcode-email.md).

## <a name="upload-the-email-html"></a>Télécharger l’e-mail au format HTML

Après avoir créé et testé le code HTML de votre corps de message, il doit être téléchargé vers Commerce headquarters. Actuellement, le courrier électronique au format HTML ne peut pas être exporté. Par conséquent, vous devez conserver la copie principale de votre code HTML en dehors de Commerce headquarters.

Pour télécharger un modèle d’e-mail nouveau ou modifié au format HTML, procédez comme suit.

1. Dans Commerce Headquarters, accédez à **Retail et Commerce \> Configuration du siège \> Modèles d’e-mail d’organisation**.
1. Sélectionnez la ligne de la langue pour laquelle vous souhaitez ajouter ou remplacer du HTML. Vous pouvez également sélectionner **Nouveau** pour créer une ligne pour une nouvelle langue.
1. Sélectionnez **Modifier**.
1. Dans la boîte de dialogue qui apparaît, sélectionnez **Parcourir**. Accédez au document HTML que vous souhaitez télécharger, sélectionnez-le, puis sélectionnez **Ouvrir**.
1. Sélectionnez **Charger**.
1. Une fois que votre e-mail au format HTML apparaît dans la fenêtre d’aperçu, cliquez sur **OK**.
1. Assurez-vous que la case à cocher **A un corps** est cochée pour la ligne.

Si vous avez déjà configuré Commerce Headquarters pour envoyer des e-mails, votre nouvel e-mail ou celui mis à jour sera envoyé à tous les clients qui effectuent une transaction qui appelle l’événement mappé au modèle.

Pour plus d’informations sur la configuration des e-mails dans Dynamics 365 Commerce, voir [Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md).

## <a name="additional-resources"></a>Ressources supplémentaires 

[Configurer un profil de notification par e-mail](email-notification-profiles.md)

[Configurer et envoyer un e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md)

[Paramétrage des envois de tickets de caisse par e-mail](/dynamicsax-2012/appuser-itpro/set-up-email-receipts)

[Envoyer des tickets de caisse par e-mail depuis Modern POS](email-receipts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
