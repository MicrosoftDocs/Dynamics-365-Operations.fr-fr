---
title: Cartes-cadeaux numériques e-commerce
description: Cet article décrit le fonctionnement des cartes-cadeaux numériques dans la mise en œuvre du e-commerce de Microsoft Dynamics 365 Commerce. Elle fournit également un aperçu des étapes de configuration importantes.
author: anupamar-ms
ms.date: 05/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.15
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: b31ef231ea56f1c3d2fc199bb0a19bd0c991dc8b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269995"
---
# <a name="e-commerce-digital-gift-cards"></a>Cartes-cadeaux numériques e-commerce

[!include [banner](includes/banner.md)]

Cet article décrit le fonctionnement des cartes-cadeaux numériques dans la mise en œuvre du e-commerce de Microsoft Dynamics 365 Commerce. Elle fournit également un aperçu des étapes de configuration importantes.

Dans Dynamics 365 Commerce, l’achat de cartes-cadeaux numériques suit le même flux que l’achat d’autres produits du système. Aucun module supplémentaire ne doit être configuré. Si plusieurs cartes-cadeaux sont ajoutées au panier, les articles de la carte-cadeau ne sont pas regroupés sur une seule ligne de vente. Ce comportement est requis car chaque ligne de vente est facturée à l’aide d’un numéro de carte-cadeau distinct.

L’achat de cartes-cadeaux numériques est pris en charge dans Dynamics 365 Commerce 10.0.16 et versions ultérieures.

L’illustration suivante montre un exemple de la page de détails du produit (PDP) pour une carte-cadeau numérique sur le site e-commerce Fabrikam.

![Exemple de PDP de carte cadeau numérique sur le site e-commerce Fabrikam.](./media/GiftcardPDP.PNG)

## <a name="turn-on-the-digital-gift-card-feature-in-commerce-headquarters"></a>Activez la fonction de carte-cadeau numérique dans Commerce Headquarters

Pour que le flux d’achat des cartes-cadeaux numériques fonctionne dans Dynamics 365 Commerce, la fonction d’**achat d’une carte-cadeau sur e-commerce** doit être activée dans Commerce Headquarters. Vous trouverez cette fonction dans l’espace de travail **Gestion des fonctionnalités** dans Commerce Headquarters, comme le montre l’illustration suivante.

![Espace de travail de gestion des fonctionnalités dans Commerce Headquarters.](./media/Featureflag.PNG)

## <a name="configure-a-digital-gift-card-in-commerce-headquarters"></a>Configurer une carte-cadeau numérique dans Commerce Headquarters

Les produits des cartes-cadeaux numériques doivent être configurés dans Commerce Headquarters. Le processus est semblable au processus des autres produits. Cependant, les étapes importantes suivantes sont spécifiques à la configuration des cartes-cadeaux pour l’achat. Pour plus d’informations sur la création et la configuration des produits, consultez [Créer un produit dans Commerce](create-new-product-commerce.md).

- Lorsque vous configurez des produits de cartes-cadeaux numériques dans la boîte de dialogue **Nouveau produit**, définissez le champ **Type de produit** sur **Service**. (Pour ouvrir la boîte de dialogue, accédez à **Commerce et vente au détail \> Produits et catégories \> Produits par catégorie**, et sélectionnez **Nouveau**.) La disponibilité en stock pour les produits de type **Service** n’est pas vérifiée avant qu’une commande soit passée. Pour plus d’informations, voir [Créer un nouveau produit](create-new-product-commerce.md#create-a-new-product).
- Sur la page **Paramètres commerciaux**, sur l’onglet **Validation**, le champ **Produit de la carte cadeau** doit être défini sur **Carte-cadeau numérique**, comme indiqué dans l’illustration suivante. Si le produit est une carte-cadeau externe, consultez [Prendre en charge des cartes cadeaux externes](./dev-itpro/gift-card.md) pour plus d’informations.

    ![Champ Produit de la carte cadeau dans Commerce Headquarters.](./media/PostGiftcard.png)

- Si une carte-cadeau doit prendre en charge plusieurs montants prédéfinis (par exemple, 25 $, 50 $ et 100 $), la dimension **Taille** doit être utilisée pour définir ces montants prédéfinis. Chaque montant prédéfini sera une variante de produit. Pour plus d’informations, voir [Dimensions de produit](../supply-chain/pim/product-dimensions.md?toc=%2fdynamics365%2fretail%2ftoc.json).
- Si les clients doivent pouvoir spécifier un montant personnalisé pour une carte-cadeau en plus des montants prédéfinis, commencez par configurer une variante qui autorise un montant personnalisé. L’attribut **Taille** prend en charge les variantes de montant personnalisées. Ensuite, ouvrez le produit à partir de la page **Produits lancés dans la catégorie**, puis sur le raccourci **Commerce**, définissez le champ **Entrer un prix** sur **Obligation d’entrer un nouveau prix**, comme indiqué dans l’exemple suivant. Ce paramètre garantit que les clients peuvent entrer un prix lorsqu’ils parcourent le produit sur une PDP.

    ![Champ Entrer un prix dans Commerce Headquarters.](./media/KeyInPrice.png)
    
    L’exemple suivant montre une liste de variantes de produits de cartes-cadeaux numériques dans Commerce Headquarters, y compris deux variantes de prix personnalisées.
    ![Variantes de produit de carte-cadeau numérique avec exemple de variante de prix personnalisé](./media/DigitalGiftCards_ProductVariantsWithCustom.png)

- Le mode de livraison d’une carte-cadeau numérique doit être défini sur **Électronique**. Sur la page **Modes de livraison** (**Commerce et vente au détail \> Paramétrage du canal \> Modes de livraison**), sélectionnez le mode de livraison **Électronique** dans le volet de liste, puis ajoutez le produit de la carte-cadeau numérique à la grille du raccourci **Produits**, comme indiqué dans l’illustration suivante. Pour plus d’informations, voir [Paramétrer des modes de livraison](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

    ![Produits de cartes-cadeaux numériques sur la page Mode de livraison dans Commerce Headquarters.](./media/ElectronicMode.PNG)
    
- Assurez-vous qu’un profil de fonctionnalité en ligne a été créé et est associé à votre magasin en ligne dans Commerce Headquarters. Dans le profil de fonctionnalité, définissez l’option **Produits agrégés** sur **Oui**. Ce paramètre garantit que tous les articles, à l’exception des cartes-cadeaux, sont regroupés. Pour plus d’informations, voir [Créer un profil de fonctionnalité en ligne](online-functionality-profile.md).
- Pour vous assurer que les clients reçoivent un e-mail après la facturation d’une carte-cadeau, créez un nouveau type de notification par e-mail sur la page **Profils de notification par e-mail** et définissez le champ **Type de notification par e-mail** sur **Émettre une carte-cadeau**. Pour plus d’informations, voir [Configurer un profil de notification par e-mail](email-notification-profiles.md).

## <a name="add-product-images-to-the-commerce-site-builder-media-library"></a>Ajouter des images de produits à la médiathèque du générateur de site Commerce

Vous devez ajouter des images de produits pour les produits de cartes-cadeaux numériques à la médiathèque du générateur de site Commerce. Assurez-vous que les noms de fichiers des fichiers d’image de la carte-cadeau respectent les conventions de dénomination de votre site pour les images de produit. Pour plus d’informations, voir [Charger des images](dam-upload-images.md).

## <a name="configure-a-custom-amount-for-a-digital-gift-card-in-commerce-site-builder"></a>Configurer un montant personnalisé pour une carte-cadeau numérique dans le générateur de site Commerce

Si une carte-cadeau numérique est configurée pour autoriser un montant personnalisé, ce comportement doit également être activé dans le [module de zone d’achat](add-buy-box.md) qui est utilisé sur les PDP de votre site. Le module de zone d’achat prend en charge la configuration du module pour permettre des montants personnalisés. Vous pouvez également définir les montants minimum et maximum autorisés pour les montants personnalisés.

Pour configurer un montant personnalisé pour une carte-cadeau numérique dans le générateur de site Commerce, procédez comme suit :

1. Accédez au module de zone d’achat utilisé sur les PDP de votre site. Ce module de zone d’achat peut être implémenté dans un fragment, dans un modèle ou sur une page.
1. Sélectionnez **Modifier**.
1. Dans le volet des propriétés sur la droite, activez la case à cocher **Autoriser un prix personnalisé**.
1. Facultatif : pour définir les montants minimum et maximum des montants personnalisés, saisissez les montants sous **Prix minimum** et **Prix maximum**.
1. Sélectionnez **Terminer la modification**, puis **Publier**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Zone d’achat](add-buy-box.md)

[Module Validation](add-checkout-module.md)

[Module Panier](add-cart-module.md)

[Créer un produit dans Commerce](create-new-product-commerce.md)

[Paramétrer des modes de livraison](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Dimensions de produit](../supply-chain/pim/product-dimensions.md?toc=%2fdynamics365%2fretail%2ftoc.json)

[Configurer un profil de notification par e-mail](email-notification-profiles.md)

[Créer un profil de fonctionnalité en ligne](online-functionality-profile.md)

[Prendre en charge des cartes cadeaux externes](./dev-itpro/gift-card.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
