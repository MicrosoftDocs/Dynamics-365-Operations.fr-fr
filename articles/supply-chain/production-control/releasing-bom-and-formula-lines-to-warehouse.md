---
title: "Lancer les lignes de nomenclature et de formule dans l'entrepôt"
description: "Cette rubrique décrit le processus de lancement des matières premières des lignes de nomenclature et de formule dans l'entrepôt."
author: johanhoffmann
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validfrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 838dc1e5867b8380823275aba5fc425003a54523
ms.contentlocale: fr-fr
ms.lasthandoff: 03/07/2018

---

# <a name="release-bom-and-formula-lines-to-the-warehouse"></a>Lancer les lignes de nomenclature et de formule dans l'entrepôt

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le processus de lancement des matières premières des lignes de nomenclature et de formule dans l'entrepôt. Lorsque vous lancez une ligne de nomenclature ou de formule dans l'entrepôt, le système détermine d'abord si les matières sont déjà disponibles dans l'emplacement d'entrée en production de l'atelier où les matières sont consommées pour le processus de production.

- Si les matières sont disponibles dans l'emplacement d'entrée en production, elles sont prélevées dans cet emplacement immédiatement après le signal de lancement des matières dans l'entrepôt.
- Si les matières ne sont pas disponibles dans l'emplacement d'entrée en production, le processus de lancement des matières indique que les matières doivent être déplacées des emplacements de l'entrepôt vers l'emplacement d'entrée en production. Les matières sont déplacées via le travail d'entrepôt pour le prélèvement des matières premières. Par conséquent, les processus d'entrepôt pour le prélèvement des matières premières doivent être configurés. Pour plus d'informations, voir [Réapprovisionnement](../warehousing/replenishment.md) et [Contrôler le travail d'entrepôt à l'aide de modèles de travail et d'instructions d'emplacement](../warehousing/control-warehouse-location-directives.md).

## <a name="methods-for-releasing-bom-and-formula-lines"></a>Méthodes de lancement des lignes de nomenclature et de formule

Vous pouvez configurer le lancement des lignes de nomenclature et de formule de manière à ce qu'il entre dans le cadre du lancement d'un ordre de fabrication ou d'un lot de commandes. Le lancement peut également être contrôlé par un traitement par lots ou effectué en tant qu'interaction manuelle.

La méthode utilisée pour lancer les lignes de nomenclature et de formule est contrôlée par le paramètre **Lancement de la ligne de production**. Ce paramètre est disponible sous **Contrôle de la production** \> **Paramétrage** \> **Paramètres de production**.

- **Lancer les lignes de nomenclature et de formule dans le cadre du lancement d'un ordre de fabrication ou d'un lot de commandes** – Dans cette méthode, les lignes de nomenclature et de formule d'un ordre de fabrication ou d'un lot de commandes sont lancées dans le cadre du processus de lancement de la commande. Généralement, lors du lancement d'un ordre de fabrication ou d'un lot de commandes, les tâches de production sont affectées aux employés de l'atelier, et les documents de production sont imprimés. Durant ce processus, le statut de la commande est également modifié en **Lancé**.
- **Lancer les lignes de nomenclature et de formule via un traitement par lots ou en tant qu'interaction manuelle** – Dans cette méthode, les lignes de nomenclature et de formule ne peuvent être lancées que via le traitement par lots **Lancement automatique des lignes de nomenclature et de formule** ou en tant qu'interaction manuelle. Pour lancer manuellement les lignes de nomenclature et de formule, dans la page de liste des ordres de fabrication ou la page des détails de l'ordre de fabrication, dans le volet Actions, sélectionnez **Libérer dans l'entrepôt**.

Pour une démonstration rapide de la façon de libérer des lignes de nomenclature et des formules en production à l'aide d'un traitement par lots, visionnez cette petite vidéo YouTube :
[!Video <https://www.youtube.com/embed/8urAJn50dQ8>]

## <a name="releasing-the-bom-and-formula-lines-by-using-a-batch-job"></a>Lancement des lignes de nomenclature et de formule à l'aide d'un traitement par lots

Le traitement par lots **Lancement automatique des lignes de nomenclature et de formule** parcourt les lignes de nomenclature et de formule sélectionnées qui ont une quantité restante à lancer. Il ne tient compte que des commandes qui ont le statut **Lancé**, **Commencé** ou **Déclaré terminé**. Si une ligne de nomenclature ou de formule a une quantité restante à lancer, le traitement par lots procède au lancement à hauteur de la quantité pouvant être couverte par la quantité qui a déjà été physiquement réservée et la quantité physiquement disponible.

### <a name="example-of-a-batch-job-release"></a>Exemple de lancement d'un traitement par lots

| Scénario | Quantité restante à libérer | Quantité physiquement réservée | Quantité physiquement disponible | Quantité lancée par le traitement par lots |
|----------|-------------------------------|------------------------------|-------------------------------|------------------------------------|
| 1        | 100                           | 20                           | 90                            | 100                                |
| 2        | 100                           | 20                           | 70                            | 90                                 |
| 3        | 100                           | 0                            | 90                            | 90                                 |
| 4        | 100                           | 0                            | 110                           | 100                                |
| 5        | 100                           | 20                           | 0                             | 20                                 |

### <a name="batch-job-setup"></a>Paramétrage du traitement par lots

Dans la requête du traitement par lots **Lancement automatique des lignes de nomenclature et de formule**, vous pouvez paramétrer un critère de filtre pour spécifier le nombre de jours pendant lesquels le traitement par lots doit rechercher des lignes avec des quantités non lancées. Dans la requête du traitement par lot, dans le champ **Date de conso. prévue**, utilisez la fonction **(LessThanDate())** comme critère de filtre.

L'illustration suivante présente un ordre de fabrication qui a deux traitements par lot, 10 et 20, qui couvrent l'assembly et l'emballage pour l'ordre de fabrication. Chaque traitement par lot est paramétré pour consommer une quantité de matières. Dans cette illustration, la plage de lancement indiquée par la flèche verte sous la ligne de temps correspond au nombre de jours spécifiés dans le critère **(LessThanDate())**. Par exemple, **(LessThanDate(2))** indique que le traitement par lot doit rechercher des quantités non lancées uniquement dans une plage de deux jours.

![Exemple d'ordre de fabrication qui a deux traitements par lots](media/bach-job-setup.PNG)

## <a name="releasing-material-per-operation-number-or-in-proportion-to-the-amount-of-finished-goods"></a>Lancement de matières par numéro d'opération ou sur la base de la quantité de produits finis

Si vous lancez des matières à l'aide du paramètre **Au lancement de l'ordre de fabrication**, lorsque vous effectuez un lancement manuel, deux options permettent de contrôler le lancement des matières :

- Lancez les matières par numéro d'opération.
- Lancez les matières sur la base de la quantité de produits finis.

### <a name="release-material-per-operation-number"></a>Lancer les matières par numéro d'opération

Pour contrôler les opérations pour lesquelles des matières doivent être lancées, utilisez la page **Libérer dans l'entrepôt**.

- Sélectionnez **Contrôle de la production** \> **Ordres de fabrication** \> **Tous les ordres de fabrication**, sélectionnez un ordre de fabrication, puis sous l'onglet **Entrepôt**, sélectionnez **Libérer dans l'entrepôt**. Utilisez ensuite les champs **Du n° opér.** et **Au n° opér.** pour spécifier la plage de numéros d'opération.

L'illustration suivante présente un ordre de fabrication contenant deux opérations, 10 et 20. Dans cet exemple, si vous limitez le lancement à l'opération 10, seules les matières M9203 sont lancées.

![Exemple de lancement de matières par numéro d'opération](media/two-operations.PNG)

Pour une démonstration rapide de la façon de lancer des matières en proportion à la quantité de produits finis, regardez cette petite vidéo YouTube :
[!Video <https://www.youtube.com/embed/Rm3ojAz6Zu0>]

### <a name="release-material-in-proportion-to-the-amount-of-finished-goods"></a>Lancer les matières sur la base de la quantité de produits finis

Vous pouvez lancer les matières premières pour une quantité partielle de produits finis ou dans une unité spécifique.

- Pour lancer les matières pour une quantité partielle de produits finis, sélectionnez **Contrôle de la production** \> **Ordres de fabrication** \> **Tous les ordres de fabrication**, sélectionnez un ordre de fabrication, puis sous l'onglet **Entrepôt**, sélectionnez **Libérer dans l'entrepôt**. Entrez ensuite une quantité dans le champ **Quantité**.

    Par exemple, un ordre de fabrication est créé et planifié pour 1 000 pièces. Le superviseur de l'atelier planifie la production de 100 pièces pour l'équipe de travail suivante et souhaite lancer les matières uniquement pour cette équipe de travail. Dans ce cas, le superviseur peut utiliser le champ **Quantité** pour lancer les matières pour les 100 pièces. prévues pour l'équipe de travail suivante.

- Pour lancer les matières dans une unité spécifique, sélectionnez **Contrôle de la production** \> **Ordres de fabrication** \> **Tous les ordres de fabrication**, sélectionnez un ordre de fabrication, puis sous l'onglet **Entrepôt**, sélectionnez **Libérer dans l'entrepôt**. Utilisez ensuite le champ **Unité** pour sélectionner l'unité du produit fini dans laquelle lancer les matières.

    Les unités disponibles sont définies dans l'ID de groupe de séquences d'unités du produit fini.

    Par exemple, un produit fini a la conversion d'unité suivante entre kilos (kg) et palette (PL) : 1 PL = 100 kg. Pour créer un ordre de fabrication pour 10 000 kg du produit fini, vous pouvez lancer les matières premières pour le nombre de palettes que vous prévoyez de produire. Sélectionnez **PL** comme unité, puis sélectionnez un nombre correspondant dans le champ **Quantité**.

