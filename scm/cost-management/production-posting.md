---
title: Validation de la production
description: "Cet article fournit des informations sur différents types de validations du processus de production."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventItemGroup, ProjCategory, WrkCtrResourceGroup, WrkCtrTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 54591
ms.assetid: 0917fe64-f643-46ae-98ff-5013b266a067
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4a400463c4b84ac8e3e5300bd710fb330458cafd
ms.lasthandoff: 03/31/2017


---

# <a name="production-posting"></a>Validation de la production

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur différents types de validations du processus de production.

Les activités de validation de la production suivent les processus de production décrits dans les sections ci-dessous.

## <a name="material-consumption"></a>Consommation de matières
Les matières sont enregistrées comme consommées durant la production lorsque le journal de prélèvement en production est validé. Ce processus génère des transactions de sortie qui sont déduites du stock disponible. Dans les paramètres de production, vous pouvez spécifier si la valeur des matières premières en cours (travaux en cours \[WIP\]) doit être validée dans la comptabilité. La valeur des matières premières en cours (travaux en cours) est ensuite validée dans un compte de prélèvements dédié et dans un compte de contrepartie des prélèvements dédié.

## <a name="time-consumption"></a>consommation de temps.
Le temps passé par les collaborateurs sur les tâches de production est enregistré dans le journal des fiches productions ou dans le journal des bons de travail. Lorsque ces journaux sont validés, la validation de la comptabilité dans un compte dédié pour les ressources en cours (travaux en cours) est traitée. Cette validation représente la valeur du temps passé sur l'ordre de fabrication. Une fois l'ordre de fabrication enregistré comme terminé, les comptes de travaux en cours sont réglés.

## <a name="reporting-finished-goods-and-error-quantities"></a>Déclaration des produits finis et des quantités d'erreur
Lorsqu'un ordre de fabrication est déclaré terminé, la quantité des produits finis déclarés terminés est mise à jour dans Gestion des stocks via le journal de Déclaration de fin. Si vous utilisez la gestion des travaux en cours, qui peut être configurée dans les paramètres de production, un journal comptable est établi pour réduire la gestion des travaux en cours et accroître le stock de produits finis. Le journal utilise le coût standard défini pour le produit.

## <a name="ending-the-production-order"></a>Fin de l'ordre de fabrication
Avant la fin d'un ordre de fabrication, les coûts réels sont calculés pour la quantité produite. Tous les coûts estimés de matière, main d'œuvre et frais généraux sont contrepassés et remplacés par les coûts réels. Le coût total de l'article fini est débité du compte de réception en stock et crédité sur le compte de sortie de stock. Si vous sélectionnez la case à cocher **Tâche de fin** lors du calcul des coûts, le statut de l'ordre de fabrication passe sur **Terminé**. Ce statut empêche que tout coût supplémentaire soit validé par erreur dans un ordre de fabrication terminé. Vous pouvez spécifier que la valeur des quantités d'erreur déclarées lors de la déclaration de fin doit être attribuée aux bonnes quantités déclarées comme terminées. Sinon, vous pouvez spécifier que la valeur des quantités d'erreur doit être validée dans un compte des rebuts dédié.

## <a name="controlling-the-level-of-ledger-posting"></a>Contrôle du niveau de validation de la comptabilité
Dans **Paramètres de contrôle de production**, vous pouvez utiliser le champ **Validation dans la comptabilité** pour définir le niveau de validation de la comptabilité pour les processus de production. Les valeurs disponibles sont les suivantes :

-   **Article et ressource** : permet d'utiliser les comptes généraux paramétrés dans les groupes d'articles pour les matières premières et les produits finis. Les travaux en cours pour la consommation de temps sont extraits de la ressource ou du groupe de ressources des opérations de gamme.
-   **Article et catégorie** : permet d'utiliser les comptes généraux paramétrés dans les groupes d'articles pour les matières premières et les produits finis. Les travaux en cours pour la consommation de temps sont extraits des catégories de coûts associées aux opérations de gamme.
-   **Groupes de production** : permet d'utiliser les comptes généraux paramétrés dans les groupes de production à la fois pour la consommation des matières et du temps. Les groupes de production sont associés aux produits lancés et copiés dans les ordres de fabrication lorsque ces commandes sont créées. La validation des ordres de fabrication suivra ensuite les groupes de production associés à l'ordre de fabrication.

**Remarque :** Si la méthode standard de calcul du coût de l'article fini a été appliquée, les transactions finales tiennent également compte de cela. Si les coûts réels et les coûts calculés par la méthode standard sont différents, la différence est validée sur le compte qui affiche un profit ou une perte.




