---
title: Remplacer le principe de réservation par défaut pour les articles en production
description: Cet article décrit comment définir un principe de réservation par défaut pour chaque groupe de modèles d’article, afin que différents principes de réservation puissent être automatiquement appliqués pour chaque article faisant partie d’une nomenclature de production ou d’une formule de commande par lots.
author: johanhoffmann
ms.date: 12/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-10
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 381b7fa5046df8f2734e4b242058eb9a673388cf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907230"
---
# <a name="override-the-default-reservation-principle-for-materials-in-production"></a>Remplacer le principe de réservation par défaut pour les articles en production

[!include [banner](../includes/banner.md)]

La fonctionnalité *Remplacer la réservation de production par défaut* vous permet de définir un principe de réservation par défaut pour chaque groupe de modèles d’article. Par conséquent, différents principes de réservation peuvent être automatiquement appliqués pour chaque article faisant partie d’une nomenclature de production ou d’une formule de commande par lots. Vous pouvez choisir si chaque groupe de modèles d’article doit remplacer le principe de réservation par défaut défini pour une commande, et quel principe de réservation doit être utilisé à la place (*manuel*, *estimation*, *planification*, *lancement* ou *démarrage*).

Lorsque vous créez un ordre de fabrication ou une commande par lots, vous êtes invité à sélectionner le principe de réservation qui doit être appliqué à cette commande et à toutes ses lignes de nomenclature ou lignes de formule. Lorsque la fonctionnalité *Remplacer la réservation de production par défaut* est utilisée, une partie ou la totalité des lignes de nomenclature ou de formule peuvent remplacer ce principe de réservation et, à la place, utiliser le principe de réservation défini pour le groupe de modèles d’article pertinent.

Par exemple, si des matières premières ou des ingrédients nécessitent un travail de prélèvement, les lignes de nomenclature ou de formule créées pour ces produits nécessitent une réservation physique, car la réservation physique est une condition préalable à la génération du travail en entrepôt. Généralement, si vous souhaitez que la réservation se produise automatiquement, vous sélectionnez l’un des principes de réservation suivants : *estimation*, *planification*, *lancement* ou *démarrage*. En revanche, si des matières premières ou des ingrédients ne nécessitent pas de travail de prélèvement, car ils sont consommés directement à partir d’un emplacement, vous sélectionnez généralement le principe de réservation *manuel*, qui ne crée aucune réservation physique ni génère aucun travail de prélèvement.

## <a name="turn-the-override-default-production-reservation-feature-on-or-off"></a>Activer ou désactiver la fonctionnalité Remplacer la réservation de production par défaut

À compter de la version 10.0.25 de Supply Chain Management, cette fonctionnalité sera activée par défaut. Les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Remplacer la réservation de production par défaut* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="assign-a-production-reservation-policy-to-an-item-model-group"></a>Attribuer une stratégie de réservation de production à un groupe de modèles d’article

1. Accédez à **Gestion des coûts \> Paramétrage des stratégies comptables de stock \> Groupes de modèles d’article**.
1. Créez ou sélectionnez un groupe de modèles d’article.
1. Dans le raccourci **Stratégies de stock**, cochez la case **Remplacer la réservation de production d’article**.
1. Dans le champ **Réservation**, sélectionnez le principe de réservation pour les articles appartenant au groupe de modèles sélectionné. (Ces articles incluent les articles figurant sur une ligne de nomenclature ou de formule.)

    - **Manuel** : les articles du groupe de modèles ne seront pas automatiquement réservés physiquement pour la production. Cependant, ils peuvent toujours être réservés manuellement au besoin.
    - **Estimation** : les articles du groupe de modèles seront physiquement réservés pendant l’estimation de l’ordre de fabrication.
    - **Planification** : les articles du groupe de modèles seront physiquement réservés pendant la planification de l’ordre de fabrication.
    - **Lancement** : les articles du groupe de modèles seront physiquement réservés au lancement de l’ordre de fabrication.
    - **Démarrage** : les articles du groupe de modèles seront physiquement réservés au démarrage de l’ordre de fabrication.

## <a name="example-using-reservation-principles-in-a-bulkpack-scenario"></a>Exemple : utilisation des principes de réservation dans un scénario en vrac/pack

Une matière lubrifiante en vrac est produite dans un mélangeur de 1 000 litres. Une fois que la matière en vrac est prête, elle est pompée vers plusieurs stations de remplissage, où des bouteilles de différentes tailles sont remplies. Une fois le remplissage terminé, les bouteilles sont emballées dans des boîtes. Ces boîtes sont ensuite placées sur des palettes.

Dans ce scénario, une commande par lots pour fabriquer 1 000 litres de matière en vrac est créée. (Cette commande est la commande en vrac.) Lorsque cette commande par lots est terminée, elle est déclarée comme terminée dans l’emplacement d’entrée des matières des stations de remplissage. Une commande par lots pour remplir et emballer chaque taille de bouteille est ensuite créée. (Ces commandes sont les commandes en vrac.) Les commandes en pack ont une formule qui comprend la matière en vrac, une bouteille vide, une étiquette et d’autres matières d’emballage. Comme la matière en vrac est envoyée directement du réservoir du mélangeur vers les stations de remplissage, aucun travail d’entrepôt n’est nécessaire pour prélever cet ingrédient, et la matière en vrac est consommée directement à partir de l’emplacement d’entrée. Par conséquent, le principe de réservation est défini sur *manuel*. Les autres matières sont envoyées vers la station de remplissage par le travail de prélèvement. Par conséquent, le principe de réservation pour ces lignes est défini sur *lancement*, par exemple, pour que la réservation se produise automatiquement lorsque la commande en pack est lancée.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]