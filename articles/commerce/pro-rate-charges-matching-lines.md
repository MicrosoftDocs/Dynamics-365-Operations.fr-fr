---
title: Calculer au prorata les frais d’en-tête par rapport aux lignes de vente correspondantes
description: Cet article décrit les capacités supplémentaires pour calculer et appliquer des frais automatiques aux commandes du canal de commerce en utilisant la fonctionnalité de frais automatiques avancés.
author: hhaines
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 6b41aa7b012b161626a98fc4aa2d37134552a57a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886930"
---
# <a name="prorate-header-charges-to-matching-sales-lines"></a>Calculer au prorata les frais d’en-tête par rapport aux lignes de vente correspondantes


[!include [banner](includes/banner.md)]

Cet article décrit la fonctionnalité visant à regrouper les frais automatiques au niveau de l’en-tête et à les calculer au prorata par rapport aux lignes de commerce. Cette fonctionnalité est disponible pour les transactions créées au point de vente (PDV) dans la version 10.0.1 de Retail et les ventes créées dans un centre d’appels dans la version 10.0.2 de Retail.

Cette fonctionnalité n’est disponible que si la fonctionnalité [Frais automatiques avancés](/dynamics365/unified-operations/retail/omni-auto-charges) est activée à l’aide de l’option sur la page **Paramètres de commerce**. En outre, le mode de calcul amélioré pour les frais automatiques peut s’appliquer uniquement aux commandes client créées par les canaux de commerce (le PDV, un centre d’appels et la plateforme de commerce électronique Dynamics).

Cette nouvelle fonctionnalité offre plus de souplesse aux organisations en matière de calcul des frais automatiques au niveau de l’en-tête et d’application aux transactions de vente.

Dans les versions de l’application antérieures à la version 10.0.1, les frais automatiques au niveau de l’en-tête avec un mode de livraison spécifiques sont calculés uniquement lorsqu’il y a une correspondance avec le mode de livraison défini sur l’en-tête de la commande client.

Par exemple, les frais automatiques au niveau de l’en-tête sont définis pour le mode de livraison **99** et le mode de livraison **11**. Une commande client est créée, et le mode de livraison **99** est défini sur l’en-tête de la commande. Toutefois, certaines des lignes de vente sont paramétrées pour une expédition via le mode de livraison **11**. Dans ce cas, seuls les frais au niveau de l’en-tête liés au mode de livraison **99** sont pris en compte et appliqués à la commande client.

Dans Commerce, les frais au niveau de l’en-tête ont une fonctionnalité supplémentaire qui permet de définir une [configuration des frais progressifs](/dynamics365/unified-operations/retail/configure-call-center-delivery) basée sur la valeur de la commande. Par exemple, si la valeur de la commande figure entre 50 USD et 200 USD, une organisation peut facturer des frais de transport de 5 USD. Toutefois, si la valeur de la commande est située entre 200,01 USD et 500 USD, les frais de transport peuvent s’élever à 4 USD.

Certaines organisations souhaitent bénéficier des avantages du calcul des frais progressifs inclus avec les frais au niveau de l’en-tête. Toutefois, dans les scénarios qui impliquent des modes de livraison mixtes, elles souhaitent également veiller à ce que les frais calculés soient basés sur une correspondance avec le mode de livraison définie sur chaque ligne de vente.

Vous pouvez désormais configurer les frais automatiques au niveau de l’en-tête de telle sorte que tous les modes de livraison figurant sur la commande sont pris en compte lors du calcul des frais. Cette fonctionnalité exige une logique de calcul plus complexe pour calculer les frais au niveau de l’en-tête. La logique regroupe tous les éléments envoyés par le même mode de livraison, et considère ce groupe comme le groupe de calcul pour les éléments lorsqu’elle calcule les frais automatiques au niveau du groupe. Pour les éléments ayant le même mode de livraison, les frais automatiques sont calculés selon la valeur des ventes combinées des éléments. Ainsi, le niveau de frais automatiques approprié est déterminé.

Une fois les frais appropriés au niveau de l’en-tête obtenus pour les lignes de vente qui se caractérisent par le même mode de livraison, les frais calculés sont réduits au prorata de la ligne des ventes. Parce que ces frais sont au niveau de la ligne, et non conservés au niveau de l’en-tête, un lien plus spécifique est effectué entre l’article et la valeur des frais calculés à cet effet. Ce comportement peut être utile dans des scénarios de retour partiel, lorsqu’une organisation souhaite rembourser uniquement une partie des frais plutôt que l’intégralité des frais lorsque seulement quelques articles sont renvoyés.

## <a name="scenarios"></a>Scénarios

Les deux scénarios suivants soulignent comment ces frais sont calculés à la fois lorsque la nouvelle fonctionnalité est utilisée et lorsqu’elle ne l’est pas.

### <a name="scenario-1"></a>Scénario 1

Ce scénario souligne le comportement lorsque l’option **Calculer au prorata les frais d’en-tête par rapport aux lignes de vente correspondantes** est définie sur **Non** dans la configuration des frais automatiques. (Ce comportement est équivalent au comportement des frais au niveau de l’en-tête dans les versions de l’application antérieures à la version 10.0.1.)

Dans ce scénario, l’organisation a défini des frais au niveau de l’en-tête pour le mode de livraison **99** et le mode de livraison **11**. Aucun frais automatique n’est configuré pour le mode de livraison **21**.

![Frais automatiques pour le mode de livraison 99 lorsque le calcul au prorata de la ligne correspondante est désactivé.](media/99_disabled.png)

![Frais automatiques pour le mode de livraison 11 lorsque le calcul au prorata de la ligne correspondante est désactivé.](media/11_disabled.png)

Une commande client est créée dans le centre d’appels, et le mode de livraison est défini sur **99**. Cette commande contient cinq articles. Deux lignes de commande ont été configurées pour utiliser le mode de livraison **99**, deux lignes ont été configurées pour utiliser le mode de livraison **11**, et une ligne a été configurée pour utiliser le mode de livraison **21**, comme indiqué dans le tableau suivant.

| Article  | Quantité de ligne | Mode de distribution | Prix unitaire |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | 10 USD            |
| 81332 | 1             | 99            | 50 $            |
| 81333 | 2             | 11            | 30 USD            |
| 81334 | 3             | 99            | 10 USD            |
| 81334 | 3             | 21            | 5 USD             |

Dans ce scénario, la commande toute entière est évaluée par rapport au tableau des frais automatiques pour le mode de livraison **99**. Le montant total de l’intégralité des lignes de vente est utilisé pour déterminer un niveau correspondant dans la configuration des frais automatiques, et ces frais sont appliqués au niveau de l’en-tête de la commande. Dans cet exemple, le total de la commande s’élève à 165 USD et des frais de transport de 15 USD sont appliqués à l’en-tête de la commande. Les frais automatiques pour le mode de livraison **11** ne sont jamais référencés ou appliqués.

Dans ce scénario, si un client renvoie certains articles de la commande, et si le [code des frais a été configuré de manière à ce qu’ils soient remboursés](/dynamics365/unified-operations/retail/omni-auto-charges#setup-and-configuration-2), le total des frais au niveau de l’en-tête est systématiquement appliqué au remboursement, même si seuls certains articles sont renvoyés.

### <a name="scenario-2"></a>Scénario 2

Dans ce scénario, les frais au niveau de l’en-tête sont définis pour le mode de livraison **99** et le mode de livraison **11**. Toutefois, l’option **Calculer au prorata les frais d’en-tête par rapport aux lignes de vente correspondantes** est définie sur **Oui** pour ces tables des frais automatiques.

![Frais automatiques pour le mode de livraison 99 lorsque le calcul au prorata de la ligne correspondante est activé.](media/99_enabled.png)

![Frais automatiques pour le mode de livraison 11 lorsque le calcul au prorata de la ligne correspondante est activé.](media/11_enabled.png)

Ce scénario utilise la même commande client qui contient cinq lignes. Le mode de livraison dans l’en-tête de commande est défini sur **99**, mais le mode de livraison pour chaque article sur la commande client est configuré comme indiqué dans le tableau suivant.

| Article  | Quantité de ligne | Mode de distribution | Prix unitaire |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | 10 USD            |
| 81332 | 1             | 99            | 50 $            |
| 81333 | 2             | 11            | 30 USD            |
| 81334 | 3             | 99            | 10 USD            |
| 81334 | 3             | 21            | 5 USD             |

Parce que la configuration des frais automatiques est définie pour calculer au prorata des lignes de vente correspondantes, le système exécute les étapes de calcul suivantes.

1. Tous les articles ayant le même mode de livraison sont regroupés, et le système calcule la valeur totale des articles dans le groupe.

    **Mode de livraison 11**

    - Article 81331, quantité 1 = 10 USD
    - Article 81333, quantité 2 = 60 USD nets (30 USD par unité)
    - **Valeur totale des produits pour le mode de livraison 11 = 70 USD**

    **Mode de livraison 99**

    - Article 81332, quantité 1 = 50 USD
    - Article 81334, quantité 3 = 30 USD nets
    - **Valeur totale des produits pour le mode de livraison 99 = 80 USD**

    **Mode de livraison 21**

    - Article 81334, quantité 3 = 15 USD nets
    - **Valeur totale des produits pour le mode de livraison 21 = 15 USD**

2. Le système recherche la configuration pour les frais automatiques au niveau de l’en-tête qui correspond aux paramètres du mode de livraison et du client pour chaque groupe d’articles. Si la recherche identifie la configuration, le système observe la configuration progressive pour trouver les frais applicables, selon la valeur totale des articles dans le mode du groupe de livraison.

    **Mode de livraison 11**

    - Valeur totale des produits = 70 $
    - **Valeur des frais = 7 USD**

    **Mode de livraison 99**

    - Valeur totale des produits = 80 $
    - **Valeur des frais = 15 USD**

    **Mode de livraison 21**

    - Valeur totale des produits = 15 $
    - **Valeur des frais = 0 USD** (Aucun frais automatique n’a été configuré pour cette combinaison d’un client et d’un mode de livraison.)

    ![Les frais du mode de livraison 11 s’inscrivent dans le niveau mis en surbrillance.](media/step2mode11.png)

    ![Les frais du mode de livraison 99 s’inscrivent dans le niveau mis en surbrillance.](media/step2mode99.png)

3. Le système calcule la valeur des frais applicables à chaque ligne, selon une logique au prorata qui tient compte de la valeur proportionnelle de la ligne par rapport à la valeur totale des produits du groupe.

    **Mode de livraison 11**

    - Valeur des frais = 7 USD
    - Valeur des produits du groupe = 70 USD
    - Valeur ligne 1 = 10 USD (= 14,2857 pour cent de la valeur du groupe)
    - Valeur ligne 3 = 60 USD (= 85,7143 pour cent de la valeur du groupe)
    - **Frais de ligne pour la ligne 1 = 1 USD**
    - **Frais de ligne pour la ligne 3 = 6 USD**

    **Mode de livraison 99**

    - Valeur des frais = 15 USD
    - Valeur des produits du groupe = 80 USD
    - Valeur ligne 2 = 50 USD (= 62,5 pour cent de la valeur du groupe)
    - Valeur ligne 4 = 30 USD (= 37,5 pour cent de la valeur du groupe)
    - **Frais de ligne pour la ligne 2 = 9,38 USD**
    - **Frais de ligne pour la ligne 4 = 5,62 USD**

    **Mode de livraison 21**

    - Valeur des frais = 0 USD
    - Valeur des produits du groupe = 15 USD
    - Valeur ligne 5 = 15 USD (= 100 pour cent de la valeur du groupe)
    - **Frais de ligne pour la ligne 5 = 0 USD**

Par conséquent, pour cet exemple, l’article 81334 se voit attribuer des frais de transport de 5,62 USD. Vous pouvez afficher ces frais sur la page **Tenir les frais à jour** pour la ligne de vente. L’illustration suivante présente à quoi cette page ressemble pour l’article 81334.

![Frais calculés au prorata sur la ligne des ventes pour l’article 81334.](media/proratedlinecharge.png)

Lorsque ce mode de calcul est utilisé dans un scénario de retour partiel, si le code de frais est remboursable, seule la part des frais attribués à cette ligne est remboursée en cas de retour de l’article.

## <a name="additional-resources"></a>Ressources supplémentaires

[Frais automatiques avancés omnicanaux](omni-auto-charges.md)

[Activer et configurer les frais automatiques par canal](auto-charges-by-channel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]