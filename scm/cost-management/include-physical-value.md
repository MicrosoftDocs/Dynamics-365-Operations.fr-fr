---
title: Inclure la valeur physique
description: "Vous utilisez la case à cocher Inclure la valeur physique dans l&quot;organisateur Modèle de stock de la page Groupes de modèles d&quot;article pour spécifier si les transactions mises à jour physiquement sont considérées dans le calcul du prix de revient moyen en cours pour un article."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 961f768ac4b0044e138aeaec41c7f915b92c33df
ms.lasthandoff: 03/31/2017


---

# <a name="include-physical-value"></a>Inclure la valeur physique

Vous utilisez la case à cocher Inclure la valeur physique dans l'organisateur Modèle de stock de la page Groupes de modèles d'article pour spécifier si les transactions mises à jour physiquement sont considérées dans le calcul du prix de revient moyen en cours pour un article.

La case à cocher **Inclure la valeur physique** possède les valeurs suivantes.

| Valeur    | Résultat                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| Sélectionné | Les transactions mises à jour physiquement et financièrement sont utilisées pour calculer le prix de revient moyen en cours. |
| Désactivé  | Seules les transactions mises à jour financièrement sont utilisées pour calculer le prix de revient moyen en cours.                                     |

La case à cocher produit des résultats légèrement différents en fonction du modèle de stock que vous utilisez.

-   Si vous activez la case à cocher **Inclure la valeur physique** lorsque vous utilisez les modèles de stock par date FIFO (Premier entré, premier sorti), LIFO (Dernier entré, premier sorti), ou LIFO, la clôture de stock engendre également des ajustements sur les transactions mises à jour physiquement.
-   Si vous n'activez pas la case à cocher **Inclure la valeur physique** lorsque vous utilisez ces modèles de stock, la clôture de stock engendre des règlements uniquement pour les transactions mises à jour financièrement.
-   Lorsque vous utilisez les modèles de stock de moyenne pondérée ou de date moyenne pondérée, la clôture de stock règle uniquement les transactions mises à jour financièrement, à moins que vous n'activiez la case à cocher **Inclure la valeur physique**.

**Exemple 1** Vous avez activé la case à cocher** Inclure la valeur physique** et vous recevez les commandes fournisseur suivantes :

-   Une commande fournisseur comportant 2 articles à un prix de revient de 10,00 EUR qui a été mise à jour par bon de livraison.
-   Une commande fournisseur comportant 3 articles à un prix de revient de 12,00 EUR qui a été mise à jour par une facture.

Dans ce cas, le prix de revient moyen en cours sera de 11,20 EUR car les transactions mises à jour physiquement et financièrement sont utilisées pour calculer le prix de revient. **Exemple 2** Vous n'avez pas activé la case à cocher **Inclure la valeur physique** et le prix de revient sur le paramétrage de l'article est de 10,00 EUR. Vous recevez une commande fournisseur comportant 20 articles à un prix de revient de 12,00 EUR qui a été mise à jour par bon de livraison. Lorsque une commande client est validée, le montant du coût validé est de 10,00 EUR car le prix de revient moyen en cours n'inclut pas les transactions validées physiquement. **Remarque :** À des fins de comparaison, si vous activez la case à cocher **Inclure la valeur physique** pour cet article, lorsqu'une commande client est validée, le montant du coût validé sera de 12,00 EUR.


