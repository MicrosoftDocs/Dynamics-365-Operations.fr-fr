---
title: "Définir des coupons pour les ventes au détail"
description: "Cette rubrique fournit une vue d'ensemble des coupons de vente au détail et décrit leur paramétrage."
author: scott-tucker
manager: AnnBe
ms.date: 05/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailCoupon, RetailParameters, RetailSharedParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.search.region: Global
ms.search.industry: retail
ms.author: scotttuc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: bd3596b6c78c5959ca289c73bcc5785eb770be39
ms.contentlocale: fr-fr
ms.lasthandoff: 01/04/2019

---

# <a name="set-up-coupons-for-retail-sales"></a>Définir des coupons pour les ventes au détail

[!include [banner](includes/banner.md)]

## <a name="overview-of-coupons"></a>Vue d'ensemble des coupons

Les coupons sont des codes et des codes-barres utilisés pour ajouter des remises de vente au détail aux transactions. Chaque coupon peut avoir plusieurs codes, et chaque code peut avoir ses propres dates d'effet.

Chaque coupon est associé à une remise de vente au détail. Les groupes de prix associés à la remise définissent les clients qui peuvent utiliser un coupon ou les canaux dans lesquels un coupon est valide.

Les coupons sont essentiellement une validation supplémentaire en plus des remises de vente au détail. Le coupon fournit les codes de coupon et les codes-barres requis, ainsi que les plages de dates pour ces codes. Le coupon fournit également les limites d'utilisation facultatives et les propriétés requises par le client. La remise définit l'ensemble des produits pour lesquels le coupon est valide. Les groupes de prix de la remise définissent l'ensemble des clients, canaux ou catalogues pour lesquels le coupon est valide.

Pour créer un coupon, vous devez créer la remise et le coupon séparément. Vous les liez ensuite en sélectionnant la remise sur la page de coupon dans Microsoft Dynamics 365 for Retail.

> [!NOTE]
> Une fois qu'un coupon est lié à une remise, plusieurs champs de la page de remise dans Microsoft Dynamics 365 for Retail passent en lecture seule, car ils sont gérés par les paramètres du coupon. Ces champs comprennent les champs associés au statut et aux plages de date standard.

### <a name="limited-use-coupons"></a>Coupons à utilisation limitée

Les coupons peuvent être configurés comme des coupons à utilisation limitée. La limite d'utilisation peut être définie par client ou par canal, ou comme une limite globale. Cette limite est appliquée lorsque le code ou le code-barres est saisi ou numérisé dans POS ou lors de la saisie de la commande client.

La limite est appliquée par code de coupon sur un coupon. Par exemple, un coupon à utilisation unique qui a deux codes de coupon peut être utilisé deux fois : une fois pour chaque code de coupon. Chaque code sur un coupon peut être défini indépendamment sur Actif.

> [!NOTE]
> Une fois qu'un code de coupons a atteint sa limite d'utilisation, le système n'effectue *pas* automatiquement la modification du statut du code de coupons à « Utilisé ». Toutefois, le système n'autorise pas davantage l'utilisation d'un code de coupon qui a atteint sa limite d'utilisation. Si le statut du code d'un coupon est défini manuellement sur tout sauf « Actif », ce code de coupon ne peut pas être utilisé dans aucun canal.

## <a name="managing-coupons"></a>Gestion des coupons

Vous devez créer la remise et le coupon séparément. Vous les liez ensuite en sélectionnant la remise sur la page de coupon. Après avoir lié un coupon à une remise, plusieurs champs de la remise passent en lecture seule, car ils sont gérés par les paramètres du coupon. Ces champs comprennent les champs associés au statut et aux plages de date standard.

Les coupons sont essentiellement une validation supplémentaire en plus des remises de vente au détail. Le coupon fournit les codes de coupon et les codes-barres, ainsi que les plages de dates, les limites d'utilisation et les propriétés requises par le client. La remise définit l'ensemble des produits pour lesquels le coupon est valide. Les groupes de prix de la remise définissent l'ensemble des clients, canaux ou catalogues pour lesquels le coupon est valide.

## <a name="system-setup-for-coupons"></a>Paramétrage du système pour les coupons

Avant de paramétrer un coupon, vous devez paramétrer le code-barres du coupon et deux souches de numéros de coupon.

1. Dans la page **Caractères de masque**, créez un caractère de masque pour le code de coupon. Vous pouvez sélectionner n'importe quel caractère inutilisé.
2. Dans la page **Paramétrage du masque de code-barres**, créez un masque de code-barres. Définissez le champ **Type** sur **Coupon**.
3. Dans la page **Paramétrage des codes-barres**, créez un code-barres qui utilise le masque de code-barres que vous venez de créer.
4. Dans la page **Souches de numéros**, créez deux souches de numéros. Une souche est pour l'ID du code de coupon, et l'autre souche est pour le numéro de coupon. L'ID du code de coupon est l'identificateur unique de chaque code de coupon d'un coupon. Le numéro de coupon est l'identificateur unique d'un coupon. Chaque coupon peut avoir plusieurs codes et codes-barres qui déclenchent le coupon.

    > [!NOTE]
    > Pour les deux souches de numéros, vous devez définir le champ **Portée** sur **Société**. Dans la plupart des cas, vous devez générer automatiquement les deux souches de numéros.

5. Dans la page **Paramètres Retail**, sous l'onglet **Codes-barres**, sélectionnez le code-barres créé précédemment.
6. Dans la page **Paramètres partagés Retail**, sous l'onglet **Souches de numéros**, sélectionnez les souches de numéros que vous avez créées pour le numéro de coupon et l'ID du code de coupon.
7. Vous pouvez maintenant ouvrir la page **Coupons** et créer des coupons.

## <a name="the-effect-of-partial-updates-on-coupons"></a>Effet des mises à jour partielles des coupons

La fonctionnalité de coupon comprend plusieurs fonctions distinctes dans Dynamics 365 for Retail. Microsoft Dynamics 365 for Retail Headquarters (HQ) et le canal peuvent être partiellement mis à jour dans différents composants. Par conséquent, il est important de comprendre comment les mises à jour partielles affectent la fonctionnalité de coupon dans son ensemble.

- **Le siège est partiellement mis à jour, mais le serveur Retail et POS ne sont pas mis à jour.** Lors d'une mise à jour du siège, les pages de coupon et de remise sont mises à jour, et le moteur de prix de vente au détail est également mis à jour. Si un seul de ces deux composants est mis à jour, certaines pages dans Retail ne correspondront pas aux données de calcul du prix. Par conséquent, des erreurs de remise inattendues peuvent se produire pendant les calculs de la remise.
- **Le siège est mis à jour, mais le serveur Retail et POS ne sont pas mis à jour (N-1).** Comme tous les magasins de vente au détail ne peuvent pas être mis à jour simultanément, nous vous recommandons de mettre à jour le siège avant de mettre à jour les magasins de vente au détail. Dans le scénario N-1, la nouvelle fonctionnalité associée aux coupons n'est pas disponible dans les magasins qui n'ont pas encore été mis à jour. Par exemple, la fonctionnalité de coupon introduit des lignes d'« exclusion ». Si vous utilisez des lignes d'exclusion sur une remise, elles ne sont pas appliquées dans un magasin de vente au détail qui exécute une version antérieure.
- **Le siège n'est pas mis à jour, mais le serveur Retail et POS sont mis à jour (N+1).** Comme le moteur de prix mis à jour dans Retail peut gérer les codes de remise hérités lors des calculs de prix, la mise à jour ne devrait avoir aucun impact fonctionnel dans ce scénario.

