---
title: Paramétrer des coupons pour les ventes au détail
description: Cette rubrique fournit une vue d’ensemble des coupons et décrit leur paramétrage.
author: scott-tucker
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailCoupon, RetailParameters, RetailSharedParameters
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: scotttuc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 9d8b9977d733c87566249bcb9658b80c4350c17d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792023"
---
# <a name="set-up-coupons-for-retail-sales"></a>Paramétrer des coupons pour les ventes au détail

[!include [banner](includes/banner.md)]

## <a name="overview-of-coupons"></a>Vue d’ensemble des coupons

Les coupons sont des codes et des codes-barres utilisés pour ajouter des remises aux transactions. Chaque coupon peut avoir plusieurs codes, et chaque code peut avoir ses propres dates d’effet.

Chaque coupon est associé à une remise. Les groupes de prix associés à la remise définissent les clients qui peuvent utiliser un coupon ou les canaux dans lesquels un coupon est valide.

Les coupons sont essentiellement une validation supplémentaire en plus des remises. Le coupon fournit les codes de coupon et les codes-barres requis, ainsi que les plages de dates pour ces codes. Le coupon fournit également les limites d’utilisation facultatives et les propriétés requises par le client. La remise définit l’ensemble des produits pour lesquels le coupon est valide. Les groupes de prix de la remise définissent l’ensemble des clients, canaux ou catalogues pour lesquels le coupon est valide.

Pour créer un coupon, vous devez créer la remise et le coupon séparément. Vous les liez ensuite en sélectionnant la remise sur la page de coupon dans Commerce.

> [!NOTE]
> Après avoir lié un coupon à une remise, plusieurs champs de la page de la remise dans Commerce passent en lecture seule car ils sont gérés par les paramètres du coupon. Ces champs comprennent les champs associés au statut et aux plages de date standard.

### <a name="limited-use-coupons"></a>Coupons à utilisation limitée

Les coupons peuvent être configurés comme des coupons à utilisation limitée. La limite d’utilisation peut être définie par client ou par canal, ou comme une limite globale. Cette limite est appliquée lorsque le code ou le code-barres est saisi ou numérisé dans POS ou lors de la saisie de la commande client.

La limite est appliquée par code de coupon sur un coupon. Par exemple, un coupon à utilisation unique qui a deux codes de coupon peut être utilisé deux fois : une fois pour chaque code de coupon. Chaque code sur un coupon peut être défini indépendamment sur Actif.

Les coupons peuvent être utilisés sur n’importe quel canal de vente. Cependant, pour les commandes auprès des centres d’appels, les coupons à usage limité ne peuvent être utilisés que pour les commandes de centre d’appels où le paramètre **Achèvement de commande** est activé sur le centre d’appels. S’il n’est pas activé, seuls les coupons sans restriction d’utilisation peuvent être utilisés dans les commandes auprès des centres d’appels.

> [!NOTE]
> Une fois qu’un code de coupon a atteint sa limite d’utilisation, le système n’effectue *pas* automatiquement la modification du statut du code de coupons à « Utilisé ». Cependant, ce code de coupon a atteint sa limite d’utilisation et ne peut pas être utilisé. Si le statut du code d’un coupon est défini manuellement sur tout sauf **Actif**, ce code de coupon ne peut être utilisé dans aucun canal.  

## <a name="managing-coupons"></a>Gestion des coupons

Vous devez créer la remise et le coupon séparément. Vous les liez ensuite en sélectionnant la remise sur la page de coupon. Après avoir lié un coupon à une remise, plusieurs champs de la remise passent en lecture seule, car ils sont gérés par les paramètres du coupon. Ces champs comprennent les champs associés au statut et aux plages de date standard.

Les coupons sont dorénavant une validation supplémentaire en plus des remises. Le coupon fournit les codes de coupon et les codes-barres, ainsi que les plages de dates, les limites d’utilisation et les propriétés requises par le client. La remise définit l’ensemble des produits pour lesquels le coupon est valide. Les groupes de prix de la remise définissent l’ensemble des clients, canaux ou catalogues pour lesquels le coupon est valide.

## <a name="system-setup-for-coupons"></a>Paramétrage du système pour les coupons

Avant de paramétrer un coupon, vous devez paramétrer le code-barres du coupon et deux souches de numéros de coupon.

1. Dans la page **Caractères de masque**, créez un caractère de masque pour le code de coupon. Vous pouvez sélectionner n’importe quel caractère inutilisé.
2. Dans la page **Paramétrage du masque de code-barres**, créez un masque de code-barres. Définissez le champ **Type** sur **Coupon**.
3. Dans la page **Paramétrage des codes-barres**, créez un code-barres qui utilise le masque de code-barres que vous venez de créer.
4. Dans la page **Souches de numéros**, créez deux souches de numéros. Une souche est pour l’ID du code de coupon, et l’autre souche est pour le numéro de coupon. L’ID du code de coupon est l’identificateur unique de chaque code de coupon d’un coupon. Le numéro de coupon est l’identificateur unique d’un coupon. Chaque coupon peut avoir plusieurs codes et codes-barres qui déclenchent le coupon.

    > [!NOTE]
    > Pour les deux souches de numéros, vous devez définir le champ **Portée** sur **Société**. Dans la plupart des cas, vous devez générer automatiquement les deux souches de numéros.

5. Dans la page **Paramètres de commerce**, sous l’onglet **Codes-barres**, sélectionnez le code-barres créé précédemment.
6. Dans la page **Paramètres partagés du commerce**, sous l’onglet **Souches de numéros**, sélectionnez les souches de numéros créées pour le numéro de coupon et l’ID du code de coupon.
7. Vous pouvez maintenant ouvrir la page **Coupons** et créer des coupons.

## <a name="the-effect-of-partial-updates-on-coupons"></a>Effet des mises à jour partielles des coupons

La fonctionnalité de coupon comprend plusieurs fonctions distinctes. Commerce Headquarters (HQ) et le canal peuvent être partiellement mis à jour dans différents composants. Par conséquent, il est important de comprendre comment les mises à jour partielles affectent la fonctionnalité de coupon dans son ensemble.

- **Le siège est partiellement mis à jour, mais l’unité d’échelle commerciale et le PDV ne sont pas mis à jour.** Lors d’une mise à jour du siège, les pages de coupon et de remise sont mises à jour, et le moteur de prix de commerce est également mis à jour. Si un seul de ces deux composants est mis à jour, certaines pages dans Commerce ne correspondent pas aux données de calcul du prix. Par conséquent, des erreurs de remise inattendues peuvent se produire pendant les calculs de la remise.
- **Le siège est mis à jour, mais l’unité d’échelle commerciale et le PDV ne sont pas mis à jour (N-1).** Tous les magasins ne pouvant pas être mis à jour simultanément, nous vous conseillons de mettre à jour le siège avant de mettre à jour les magasins. Dans le scénario N-1, la nouvelle fonctionnalité associée aux coupons n’est pas disponible dans les magasins qui n’ont pas encore été mis à jour. Par exemple, la fonctionnalité de coupon introduit des lignes d’« exclusion ». Si vous utilisez des lignes d’exclusion sur une remise, elles ne s’appliquent pas dans un magasin qui exécute une version antérieure.
- **Le siège n’est pas mis à jour, mais l’unité d’échelle commerciale et le PDV sont mis à jour (N+1).** Le moteur de prix mis à jour dans l’unité d’échelle commerciale pouvant gérer les codes de remise hérités lors du calcul des prix, la mise à jour ne devrait avoir aucun impact fonctionnel dans ce scénario.


[!INCLUDE[footer-include](../includes/footer-banner.md)]