---
title: Afficher les remises dans le PDV
description: Cette rubrique explique comment Microsoft Dynamics 365 Commerce aide les vendeurs à se renseigner sur les promotions et comment les utiliser dans le cadre des mouvements de vente croisée et de vente incitative.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 05/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-Commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail, Commerce
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-02-28
ms.dyn365.ops.version: Application update 10.0.10
ms.openlocfilehash: 0ffa7ca6294c7b523ec743f1cb9bc4aef8ef46a8
ms.sourcegitcommit: 4d5bcda288341572076364559125c86e2ec05273
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2020
ms.locfileid: "3334706"
---
# <a name="show-discounts-in-pos"></a>Afficher les remises dans le PDV

[!include [banner](includes/banner.md)]

Les promotions jouent un rôle important dans la motivation des clients qui doivent prendre des décisions d'achat. Par exemple, les vacances peuvent générer le plus grand nombre de ventes pour les détaillants, car l'ensemble du marché de détail est inondé de promotions et de remises attrayantes. Si les collaborateurs du magasin connaissent et comprennent quelles sont les promotions disponibles, ils peuvent facilement profiter de ces promotions pour effectuer des ventes croisées et vendre des articles de gamme supérieure. Cette rubrique explique comment Microsoft Dynamics 365 Commerce aide les vendeurs à se renseigner sur les promotions et comment les utiliser dans le cadre des mouvements de vente croisée et de vente incitative.

## <a name="learn-about-store-discounts"></a>En savoir plus sur les remises en magasin

Commerce comprend une opération intitulée « Afficher toutes les remises ». Cette opération affiche toutes les remises actuellement en cours dans un magasin. L'opération « Afficher toutes les remises » peut être associée à un bouton du point de vente (PDV), et ce bouton peut être ajouté à la page **Bienvenue** ou **Transaction**. L'illustration suivante présente un exemple de la page **Toutes les remises** qui est ouverte.

![Page Toutes les remises](./media/View_all_discounts.png "Page Toutes les remises")

Pour afficher les remises, le système recherche toutes les remises correspondant à une ou plusieurs des conditions suivantes :

- Le groupe de prix de la remise correspond au groupe de prix du magasin.
- Le groupe de prix de la remise est associé à un programme d'affiliation ou de fidélité.
- Le groupe de prix de la remise est associé à un catalogue lui-même associé au magasin.

La page **Toutes les remises** affiche uniquement quelques remises basées sur les coupons, car les détaillants créent généralement des milliers de coupons et des remises correspondantes pour des clients uniques, et cette page n'est pas destinée à afficher les remises spécifiques aux clients. Les remises basées sur les coupons ne sont affichées que si l'option **Appliquer sans code coupon** est activée dans chaque en-tête de coupon. Dans ce cas, les caissiers peuvent appliquer le coupon sans avoir à saisir ou à scanner un code coupon ou un code à barres.

Si l'option **Appliquer sans code coupon** est activée, divers scénarios deviennent disponibles. Par exemple, les caissiers peuvent accorder des remises supplémentaires aux clients à des fins d'apaisement ou en raison de défauts de produit. Les codes coupon ou les codes à barres imprimés ne doivent pas être distribués aux caissiers. Au lieu de cela, les caissiers peuvent sélectionner le bouton **Appliquer le coupon**. Le coupon est ensuite automatiquement appliqué à la transaction. S'il existe plusieurs coupons pour un en-tête de coupon, le système sélectionne automatiquement le premier coupon actif de la transaction.

Sur la page **Toutes les remises**, les vendeurs peuvent également rechercher des remises par mot clé. La recherche par mot clé a lieu dans les champs contenant le nom et la description de la remise. Les vendeurs peuvent également filtrer les remises selon que la remise nécessite un code coupon ou non.

## <a name="cross-sell-and-upsell-by-using-discounts"></a>Vente croisée et vente incitative à l'aide de remises

Les remises multilignes, telles que les remises sur quantité, les remises mix-and-match et les remises seuil, sont un excellent moyen de motiver les clients à acheter plus de produits pour obtenir des remises plus importantes. Par conséquent, elles contribuent également à augmenter la taille du panier d'un client et les revenus du détaillant. Ces remises peuvent être publiées sur les sites Web de commerce électronique, sur les médias sociaux et sur des bannières dans le magasin.

Cependant, même lorsque toutes ces méthodes publicitaires sont utilisées, les clients peuvent rater l'occasion de profiter des promotions. Pour permettre aux vendeurs de savoir quelles promotions sont applicables à une ligne sélectionnée, ou même à l'ensemble du panier, les détaillants peuvent ajouter le bouton de l'opération « Afficher toutes les remises disponibles » à la grille de boutons dans la page **Transaction**. De cette façon, un vendeur peut sélectionner une ligne de transaction, puis le bouton pour afficher toutes les remises disponibles pour la ligne sélectionnée. Le vendeur peut également sélectionner un autre onglet pour afficher les remises qui s'appliquent à l'ensemble de la transaction.

La page **Toutes les remises** présente uniquement les remises qui n'entrent en concurrence avec aucune des remises appliquées. Ce comportement permet de garantir que, si un vendeur informe un client d'une remise et si le client exécute l'action requise (par exemple, il achète un article supplémentaire pour bénéficier d'une remise de 10 %), la remise est appliquée à la transaction. Les remises basées sur les coupons ne sont affichées que si l'option **Appliquer sans code coupon** est activée.

Dans un scénario simple où toutes les remises ont la même priorité, le mode de simultanéité de la remise est défini sur **Composé** et le contrôle de simultanéité de la remise est défini sur **Meilleur prix et composé dans la priorité, ne jamais composer dans plusieurs priorités**, la page **Toutes les remises** affiche toutes les remises disponibles pour un produit, car toutes les remises sont composées et ne sont pas en concurrence les unes avec les autres.

Les illustrations suivantes montrent la logique qui détermine les remises à afficher dans les scénarios avancés, comme un scénario où le mode de remise simultanée est défini sur **Meilleur prix** ou **Exclusif** et deux priorités ou plus sont utilisées. Dans ces scénarios, les remises affichées sont davantage affectées selon que le contrôle de simultanéité de la remise est défini sur **Meilleur prix et composé dans la priorité, ne jamais composer dans plusieurs priorités** ou **Meilleur prix uniquement dans la priorité, toujours composer dans plusieurs priorités**.

L'illustration suivante montre la logique utilisée lorsque le contrôle de simultanéité de la remise est défini sur **Meilleur prix et composé dans la priorité, ne jamais composer dans plusieurs priorités**.

![Logique pour Meilleur prix et composé dans la priorité, ne jamais composer dans plusieurs priorités](./media/Model_1.png "Logique pour Meilleur prix et composé dans la priorité, ne jamais composer dans plusieurs priorités.").

L'illustration suivante montre la logique utilisée lorsque le contrôle de simultanéité de la remise est défini sur **Meilleur prix uniquement dans la priorité, toujours composer dans plusieurs priorités**.

![Logique pour Meilleur prix uniquement dans la priorité, toujours composer dans plusieurs priorités](./media/Model_2.png "Logique pour Meilleur prix uniquement dans la priorité, toujours composer dans plusieurs priorités").
