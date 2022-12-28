---
title: Erreurs de validation de relevé en raison d’un stock non disponible ou de conflits de mise à jour
description: Cet article fournit des solutions de contournement possibles pour les problèmes liés à l’inventaire lors de la publication des relevés dans Microsoft Dynamics 365 Commerce.
author: Shajain
ms.date: 12/19/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: cebb890b42def6e9b002b01be63266b88bfc35a4
ms.sourcegitcommit: 4ad87483ba0bfea3e04fdb7e578d8abc34e607a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2022
ms.locfileid: "9887627"
---
# <a name="statement-posting-errors-due-to-unavailable-inventory-or-update-conflicts"></a>Erreurs de validation de relevé en raison d’un stock non disponible ou de conflits de mise à jour

[!include [banner](../../includes/banner.md)]

Cet article fournit des solutions de contournement possibles pour les problèmes liés à l’inventaire lors de la publication des relevés dans Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Description

Lors de la publication de transactions Commerce, vous pouvez recevoir des messages d’erreur liés à des problèmes d’inventaire ou à des conflits de mise à jour.

### <a name="inventory-issues-error-message"></a>Message d’erreur des problèmes d’inventaire

Si vous rencontrez des problèmes d’inventaire, le message d’erreur que vous recevez ressemblera à cet exemple :

> xx ne peut pas prélever, car seul(s) yy est/sont en stock

### <a name="update-conflict-error-messages"></a>Mettre à jour les messages d’erreur de conflit

Un conflit de mise à jour peut se produire lorsque la méthode d’évaluation du stock est *Coût standard* ou *Moyenne mobile*. Étant donné que ces deux méthodes sont des méthodes d’établissement des coûts perpétuels, le coût final est déterminé au moment de la publication.

Si vous utilisez la méthode *moyenne mobile*, le message d’erreur de conflit de mise à jour ressemble à cet exemple :

> La valeur de stock xx.xx n’est pas attendue après le calcul des dépenses proportionnelles

Si vous utilisez la méthode *coût standard*, le message d’erreur de conflit de mise à jour ressemble à cet exemple :

> Le coût standard ne correspond pas à la valeur de stock financière après la mise à jour. Valeur = xx.xx, Qté = yy.yy, Coût standard = zz.zz

## <a name="resolutions"></a>Résolutions

### <a name="workaround-for-the-inventory-error"></a>Solution de contournement pour l’erreur d’inventaire

Vous pouvez atténuer l’erreur d’inventaire en mettant à jour manuellement l’inventaire de l’article ou en activant l’inventaire physique négatif pour le groupe de modèles d’article associé à l’article dans Commerce headquarters.

Pour une expérience de validation homogène, Microsoft vous recommande d’activer le stock négatif physique dans le groupe de modèles d’article. Dans certains scénarios, il n’est pas possible de valider des relevés sauf si un stock négatif physique est activé.

Par exemple, aucun inventaire n’est disponible pour un article, mais un caissier retourne l’article, puis l’ajoute à la même transaction à un prix réduit pour imiter une correspondance de prix. Dans ce cas, la transaction de retour et la transaction de vente seront extraites dans le même relevé de la commande client unique. Cependant, étant donné qu’il n’y a aucune garantie que la ligne de retour (qui augmente le stock) sera validée avant la ligne de vente (qui réduit le stock), des erreurs de stock peuvent se produire. Si le stock négatif physique est activé dans ce scénario, la validation de la transaction n’est pas affectée négativement, et le système reflète correctement le stock.

#### <a name="enable-negative-physical-inventory-for-an-item-model-group"></a>Activer l’inventaire physique négatif pour un groupe de modèles d’articles

Pour activer l’inventaire physique négatif pour un groupe de modèles d’articles à Commerce headquarters, procédez comme suit.

1. Accédez à **Gestion des stocks \> Paramétrage \> Stock**.
1. Dans le volet de navigation de gauche, sélectionnez le groupe de modèles d’articles.
1. Dans la section **Stratégies de stock**, sous **Inventaire négatif**, cochez la case **Inventaire négatif physique**.

![Stock physique négatif activé.](./media/Physical_Negative_Inventory.png)

### <a name="workaround-for-the-update-conflict-error"></a>Solution de contournement pour l’erreur de conflit de mise à jour

Pour des solutions de contournement possibles pour résoudre l’erreur de conflit de mise à jour, voir [Un conflit de mise à jour se produit lorsque la méthode d’évaluation du stock est Coût standard ou Moyenne mobile](/troubleshoot/dynamics-365/supply-chain/costing/update-conflict-standard-cost-moving-average-inventory-valuation).

> [!NOTE]
> Pour l’erreur de conflit de mise à jour, vous n’avez pas besoin de supprimer les commandes client qui ont été générées à l’aide de l’étape d’agrégation de la validation. Après avoir implémenté les solutions de contournement suggérées, la déclaration doit être publiée si vous réessayez de publier la déclaration.
