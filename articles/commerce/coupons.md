---
title: Coupons
description: Cet article fournit une vue d’ensemble des fonctionnalités associées aux coupons dans Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-30
ms.openlocfilehash: 20427a04a552ddec013daa6576ec64ab7046e95f
ms.sourcegitcommit: 87e75aa6af2c3280316d7d73eafa14a52353a5e4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/21/2022
ms.locfileid: "9709757"
---
# <a name="coupons"></a>Coupons

[!include [banner](../includes/banner.md)]

Cet article fournit une vue d’ensemble des fonctionnalités associées aux coupons dans Microsoft Dynamics 365 Commerce.

Les coupons sont des codes et des codes-barres utilisés pour ajouter des remises aux transactions. Les détaillants distribuent des coupons aux clients potentiels ou existants pour améliorer la reconnaissance de leur marque, stimuler la conversion, fidéliser leur clientèle, augmenter les ventes et éventuellement stimuler les revenus. Les coupons sont devenus l’un des outils de marketing les plus populaires et constituent une nouvelle norme dans les ventes en ligne.

Dans Dynamics 365 Commerce, les coupons sont liés aux remises et sont considérés comme une validation supplémentaire en plus des remises. Chaque coupon est lié à une remise, et la remise liée définit l’ensemble de produits pour lesquels le coupon est valable.

Les groupes de prix associés à une remise définissent les conditions éligibles pour lesquelles un coupon peut être utilisé. Ces conditions incluent les groupes de clients et les canaux de vente. Les coupons fournissent également les propriétés **Limite d’utilisation** et **Client requis** qui peuvent être utilisées pour configurer des restrictions d’utilisation facultatives.

Chaque coupon peut avoir plusieurs codes de coupon et codes barres de coupon, et chaque code peut avoir ses propres dates d’effet et statut. Si le statut d’un code est défini sur **Inactif**, le code ne peut être utilisé dans aucune chaîne.

## <a name="set-up-a-coupon"></a>Configurer un coupon

Avant de paramétrer un coupon, vous devez paramétrer le code-barres du coupon et deux souches de numéros de coupon.

Pour paramétrer un coupon dans Commerce headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Gestion des stocks \> Codes-barres et étiquettes \> Caractères de masque**.
1. Sélectionnez **Ajouter** pour créer un caractère de masque du type de **Code de coupon**. Dans le champ **Caractère**, vous pouvez sélectionner n’importe quel caractère inutilisé.
1. Accédez à **Retail et Commerce \> Gestion des stocks \> Codes-barres et étiquettes \> Configuration du masque de code barres**.
1. Sélectionnez **Nouveau** pour créer un masque de code barres du type **Coupon**.
1. Accédez à **Retail et Commerce \> Gestion des stocks \> Codes-barres et étiquettes \> Configuration du code barres**.
1. Sélectionnez **Nouveau**, pour créer un code-barres qui utilise le masque de code-barres que vous venez de créer.
1. Accédez à **Administration d’organisation \> Séquences de nombres**.
1. Créez deux souches de N° :

    1. Une souche pour la référence **Numéro de coupon**. Cette séquence définit l’identifiant unique du coupon.
    1. Une souche pour la référence **ID du code coupon**. Cette séquence définit l’identificateur unique de chaque code de coupon d’un coupon.

    Pour les deux souches de numéros, vous devez définir le champ **Portée** sur **Société**. Dans la plupart des cas, vous devez générer automatiquement les deux souches de numéros.

1. Accédez à **Paramètres Commerce \> Prix et remises \> Coupons**.
1. Définissez le champ **Masque de code barres de coupon** sur le code barres que vous avez créé précédemment.
1. Accédez à **Paramètres Commerce \> Souches de numéros**.
1. Sélectionnez les souches de numéros que vous avez créées précédemment pour les références **Numéro de coupon** et **Identifiant du code coupon**.

Pour configurer un coupon, vous devez créer la remise et le coupon séparément, puis les lier en sélectionnant la remise dans le champ **Remise** de la configuration du coupon. Une fois qu’un coupon est lié à une réduction, les champs **Statut**, **Date effective** et **Date d’expiration** de la remise liée sont en lecture seule, car les valeurs sont déterminées par le statut et la période de validité du coupon. Lorsque le statut d’un coupon est défini sur **Actif**, le statut de la remise liée est automatiquement mis à jour pour **Activé**. De la même façon, lorsque le statut d’un coupon est défini sur **Inactif**, le statut de la remise liée est automatiquement mis à jour pour **Désactivé**.

## <a name="use-a-coupon"></a>Utiliser un coupon

Pour ajouter un coupon à une transaction de vente en point de vente (PDV) Commerce, vous pouvez utiliser le code coupon ou le code barres du coupon. Pour utiliser un code promo, sélectionnez l’action **Ajouter un code de coupon**, puis entrez le code. Pour utiliser un code à barres du coupon, scannez le code-barres avec un dispositif de scan ou saisissez le code-barres à l’aide du clavier numérique sur l’écran **Transaction**.

Les détaillants souhaitent parfois que les caissiers puissent accorder des remises fixes aux clients pour des raisons d’apaisement ou à cause de défauts de produits, mais ils ne veulent pas imprimer des codes de coupon et les distribuer aux caissiers. Dans ce cas, vous pouvez définir l’option **Appliquer sans code coupon** pour le coupon sur **Oui**. Les caissiers du PDV peuvent alors utiliser la fonction **Appliquer le coupon** dans l’action **Voir les remises disponibles** pour ajouter un coupon à une transaction sans entrer manuellement le code. S’il existe plusieurs codes coupons pour un en-tête de coupon, le système sélectionne automatiquement le premier coupon actif et l’applique à la transaction.

Pour ajouter un coupon à une commande client du centre d’appels, un utilisateur du centre d’appels doit sélectionner **Coupons** sur l’onglet **Gérer** du volet Actions sur la page de la commande client.

Pour ajouter un coupon à une commande e-commerce, l’acheteur peut saisir le code du coupon dans le champ **code promo** dans le panier.

Après l’ajout d’un coupon à une commande client, le moteur de tarification déclenche immédiatement un recalcul pour l’ensemble de la commande, que le calcul différé soit activé ou non.

> [!NOTE]
> Dans Commerce version 10.0.30 et versions antérieures, une fois que les utilisateurs du centre d’appels ont ajouté un coupon à une commande client du centre d’appels, ils doivent sélectionner **Recalculer** dans le groupe **Calculer** sur l’onglet **Vendre** du volet Actions pour appliquer la remise associée à ce coupon.

## <a name="coupon-usage-limit"></a>Limite d’utilisation du coupon

Les coupons peuvent être configurés pour un usage limité. La limite d’utilisation peut être définie par client ou par canal, ou comme une limite globale. La limite est appliquée par code de coupon sur un coupon. Par exemple, un coupon à utilisation unique qui a deux codes de coupon peut être utilisé deux fois : une fois pour chaque code de coupon.

Les coupons peuvent être utilisés sur tous les canaux de vente. Cependant, pour le centre d’appels, les coupons à usage limité ne peuvent être appliqués que lorsque le paramètre **Activer l’achèvement de la commande** pour le canal du centre d’appels est activé. Si le paramètre **Activer l’achèvement de la commande** est désactivé, seuls les coupons à usage non limité peuvent être appliqués.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
