---
title: Inclure la valeur physique
description: Vous utilisez la case à cocher Inclure la valeur physique dans l’organisateur Modèle de stock de la page Groupes de modèles d’article pour spécifier si les transactions mises à jour physiquement sont considérées dans le calcul du prix de revient moyen en cours pour un article.
author: JennySong-SH
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6fb7a2a401bd7900555646c3ff0e1be9bf4a50d3
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672400"
---
# <a name="include-physical-value"></a>Inclure la valeur physique

[!include [banner](../includes/banner.md)]

Vous utilisez la case à cocher Inclure la valeur physique dans l’organisateur Modèle de stock de la page Groupes de modèles d’article pour spécifier si les transactions mises à jour physiquement sont considérées dans le calcul du prix de revient moyen en cours pour un article.

La case à cocher **Inclure la valeur physique** possède les valeurs suivantes.

| Valeur    | Résultat                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| Sélectionné | Les transactions mises à jour physiquement et financièrement sont utilisées pour calculer le prix de revient moyen en cours. |
| Désactivé  | Seules les transactions mises à jour financièrement sont utilisées pour calculer le prix de revient moyen en cours.                                     |

La case à cocher produit des résultats légèrement différents en fonction du modèle de stock que vous utilisez.

-   Si vous activez la case à cocher **Inclure la valeur physique** lorsque vous utilisez les modèles de stock par date FIFO (Premier entré, premier sorti), LIFO (Dernier entré, premier sorti), ou LIFO, la clôture de stock engendre également des ajustements sur les transactions mises à jour physiquement.
-   Si vous n’activez pas la case à cocher **Inclure la valeur physique** lorsque vous utilisez ces modèles de stock, la clôture de stock engendre des règlements uniquement pour les transactions mises à jour financièrement.
-   Lorsque vous utilisez les modèles de stock de moyenne pondérée ou de date moyenne pondérée, la clôture de stock règle uniquement les transactions mises à jour financièrement, à moins que vous n’activiez la case à cocher **Inclure la valeur physique**.

**Exemple 1** Vous avez activé la case à cocher **Inclure la valeur physique** et vous recevez les commandes fournisseur suivantes :

-   Une commande fournisseur comportant 2 articles à un prix de revient de 10,00 EUR qui a été mise à jour par bon de livraison.
-   Une commande fournisseur comportant 3 articles à un prix de revient de 12,00 EUR qui a été mise à jour par une facture.

Dans ce cas, le prix de revient moyen en cours sera de 11,20 EUR = (2x10+3x12)/(2+3), car les transactions mises à jour physiquement et financièrement sont utilisées pour calculer le prix de revient. 

**Exemple 2** Vous n’avez pas activé la case à cocher **Inclure la valeur physique** et le prix de revient sur le paramétrage de l’article est de 10,00 EUR. 

-   Vous recevez une commande fournisseur comportant 20 articles à un prix de revient de 12,00 EUR qui a été mise à jour par bon de livraison.

Lorsque une commande client est validée, le montant du coût validé est de 10,00 EUR car le prix de revient moyen en cours n’inclut pas les transactions validées physiquement. 

> [!NOTE]
> À des fins de comparaison, si vous activez la case à cocher **Inclure la valeur physique** pour cet article, lorsqu’une commande client est validée, le montant du coût validé sera de 12,00 EUR.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]