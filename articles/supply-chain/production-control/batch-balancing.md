---
title: Équilibrage du lot
description: Cette rubrique décrit le processus d’équilibrage du lot.
author: johanhoffmann
manager: tfehr
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMTable, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: f9216a77ebcf23ef3f732a8c3cb17a911f8a3851
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246451"
---
# <a name="batch-balancing"></a>Équilibrage du lot

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la prise en charge du processus d’équilibrage du lot.

Pour plus d’informations, visionnez une [vidéo sur l’équilibrage du lot](https://www.youtube.com/watch?v=4SNLWsU9KyI&feature=youtu.be).

Lors du processus d’équilibrage du lot, le nombre de substances à utiliser dans un lot de production est calculé à partir de la concentration de substances actives dans les lots de produits sélectionnés.

## <a name="products-that-have-an-active-ingredient"></a>Produits composés d’une substance active

Un produit peut être défini par sa concentration en substance active. La substance active d’un produit est modélisée à l’aide d’un attribut de lot spécifique au produit avec une valeur minimale, une valeur maximale et un niveau cible.

Le niveau cible d’un attribut de lot représente le pourcentage estimé d’une substance active dans un produit. Les valeurs minimale et maximale représentent l’écart accepté par rapport au niveau cible. Elles peuvent être utilisées, par exemple, en guise de tolérance acceptable pour les lots lors de la réception des marchandises.

Un produit ne peut être composé que d’une substance active. Pour spécifier la substance active d’un produit, vous devez définir un attribut de lot spécifique au produit. Ensuite, vous associez l’attribut comme attribut de base du produit.

Au niveau du produit, vous devez également spécifier la façon dont le niveau de la substance active d’un lot de produit doit être enregistré : dans le cadre du processus de réception de l’achat ou dans le cadre d’un processus d’ordre de qualité.

Pour associer un attribut de base à un produit, le paramétrage suivant est requis :

- Le produit doit être contrôlé par lots. Pour effectuer un contrôle par lots d’un produit, vous devez affecter un groupe de dimensions de suivi au produit ayant une dimension de lot active.

- L’attribut indiquant les niveaux des substances doit être défini comme attribut de lot spécifique au produit pour le produit.

Pour rechercher et modifier la valeur réelle de la substance active pour un traitement par lots :
1. Accédez à **Gestion des stocks \> Recherches et états \> Dimensions de suivi \> Suivi d’article**.
1. Sélectionnez un numéro de lot dans la grille.
1. Dans le volet Actions, ouvrez l’onglet **Afficher** et sélectionnez **Attributs de lot du stock**.

## <a name="ingredient-types-and-how-they-interact-in-the-batch-balancing-process"></a>Types de substances et leur interaction dans le processus d’équilibrage du lot

Une ligne de formule créée peut avoir l’un des types de substances suivants :

- None
- Active
- Compensation
- Remplissage

Le reste de cette section fournit des exemples montrant la manière dont chaque type de substance fonctionne. Ces exemples sont basés sur la formule suivante dont la taille de lot totale est de 100 litres.

| Type de substance | Numéro d’article | Quantité de la ligne de formule | Unité |
|---|---|---|---|
| None | A | 20 | Litre |
| Actif.ve | o | 30 | Litre |
| Compensation | C | 10 | Litre |
| Remplissage | D | 40 | Litre |

Le tableau suivant donne un aperçu des résultats de chaque exemple.

| Numéro d’article | Type de substance | Quantité estimée | Quantité équilibrée | Quantité active | Unité | Valeur de base |
|---|---|---|---|---|---|---|
| A | None | 20 | 20 | | Litre | |
| B | Active | 30 | 25,71 | 9,00 | Litre | 30.00 |
| C | Compensation | 10 | 14.72 | | Litre | |
| D | Remplissage | 40 | 39.57 | | Litre | |

### <a name="active-ingredients"></a>Substances actives

Lorsqu’un produit avec un attribut de base est ajouté à une ligne de formule, on parle alors de *substance active* de la formule. Les lots de commandes ayant des formules incluant des substances actives peuvent être utilisés lors du processus d’équilibrage du lot. Pour chaque substance de la formule, le processus d’équilibrage du lot estime la quantité nécessaire pour produire le produit. L’estimation des quantités est basée sur la concentration des substances actives dans les lots sélectionnés.

#### <a name="active-ingredient-example"></a>Exemple de substance active

La substance B dispose de l’attribut de base X et d’un niveau cible de 30. Elle est également incluse dans une formule qui requiert 30 litres de la substance B pour chaque lot de 100 litres du produit. Un lot de commandes est créé avec une taille de lot de 100 litres. Le lot de commandes est lancé, et lors du processus d’équilibrage du lot, l’utilisateur sélectionne un lot de la substance B avec un niveau de potence de 35. Du fait que le niveau de potence de 35 est supérieur au niveau cible de 30, la quantité équilibrée de la substance B est réduite à l’aide du ratio de la valeur de potence et du niveau cible du lot, multiplié par la quantité estimée. Le calcul de la quantité équilibrée est le suivant :

(30 ÷ 35) × 30 litres = 25,71 litres

### <a name="none-ingredients"></a>Aucune substance

Lorsque vous appliquez le processus d’équilibrage du lot et que le **Type de substance** est *Aucun*, la quantité estimée et la quantité équilibrée de la ligne de formule dans le lot de commandes sont identiques.

#### <a name="none-ingredient-example"></a>Exemple Aucune substance

La substance A est affectée à une substance de type *Aucun* et ajoutée à une formule pour un produit fini. La formule requiert 10 litres de la substance A pour chaque lot de 100 litres du produit fini. Lorsqu’un lot de commandes requiert 200 litres, la quantité estimée et la quantité équilibrée de la substance A sont calculées comme 20 litres.

### <a name="compensating-ingredients"></a>Substances de compensation

Une substance de compensation peut compenser ou compléter l’effet de la substance active dans un produit. Par conséquent, la quantité d’une substance de compensation consommée dépend de la potence du produit :

- **Effet inverse** : si la quantité de substance active est supérieure à la quantité prévue, vous devez ajouter moins de substance de compensation.

- **Effet complémentaire** : si la quantité de substance active est inférieure à la quantité prévue, vous devez ajouter davantage de substance de compensation.

La relation entre une substance active et une substance complémentaire est paramétrée sur la page **Principe de compensation**.

Pour définir les relations entre les substances, procédez comme suit :

1. Sélectionnez **Gestion d’informations de produit \> Nomenclatures et formules \> Formules**.
1. Ouvrez une ligne de formule, puis sélectionnez **Ingrédients** pour ouvrir la page **Principe de compensation**.
1. Sélectionnez la ligne qui représente un principe de compensation, puis sélectionnez la substance active à compenser.

Dans le principe de compensation, vous pouvez également entrer un facteur de compensation positif ou négatif pour spécifier la quantité compenser, et si le principe doit être inverse ou complémentaire. Un facteur positif indique un effet complémentaire, tandis qu’un facteur négatif indique un effet inverse.

#### <a name="compensating-ingredient-example"></a>Exemple de substance de compensation

La substance B est une substance active avec l’attribut de base X et un niveau cible de 30. Elle est incluse dans une formule qui requiert 30 litres de la substance B pour chaque lot de 100 litres du produit. La substance C est une substance de compensation, et une quantité de 10 est incluse dans la même formule. Un facteur de compensation de 1,10 est défini pour le principe de compensation. Par conséquent, la quantité équilibrée de la substance de compensation est réduite de la différence entre la quantité équilibrée de substance active et la quantité requise estimée multipliée par 1,10.

Dans l’exemple du type de substance *Active*, la quantité équilibrée de la substance active requise est de 25,71, et la quantité requise estimée est de 30. Dans ce cas, la quantité équilibrée de la substance de compensation est calculée comme ceci :

1. La différence entre la quantité estimée et la quantité équilibrée est déterminée come suit :  
    25,71 – 30 = –4,29

1. Le résultat est multiplié par le facteur de compensation :  
    4,29 × 1,10 = –4,72

1. – 4,72 est ensuite soustrait à la quantité de compensation estimée pour déterminer la quantité de compensation équilibrée :  
    10 – (–4,72) = 14,72

Comme 1,10 est un facteur de compensation positif, ce principe de compensation a un effet complémentaire. Dans ce cas, la substance active est plus puissante que prévu. Par conséquent, davantage de substance de compensation est requis.

### <a name="filler-ingredients"></a>Substances de remplissage

Une *substance de remplissage* est une substance neutre utilisée pour atteindre la quantité de sortie souhaitée du produit fini. Les ajustements des quantités de remplissage sont calculées en fonction des modifications apportées à la substance active et à la substance de compensation par rapport à la quantité standard.

#### <a name="filler-ingredient-example"></a>Exemple de substance de remplissage

Vous avez formulé un produit qui inclut les substances A, B, C et D pour un volume de formule de 100 litres. Vous avez calculé la quantité équilibrée de tous les types de substances, sauf le type de substance *de remplissage* qui est utilisé sur une ligne.
La quantité équilibrée de la substance de remplissage est calculée comme la différence entre la taille de lot de 100 litres et la somme des substances A, B et C :

100 – (20 + 25,71 + 14,72) = 39,57

## <a name="the-batch-balancing-process"></a>Processus d’équilibrage du lot

Le processus d’équilibrage du lot est exécuté sur la page **Équilibrage du lot**.
Sélectionnez **Gestion des coûts \> Lots de commandes**, puis, sous l’onglet **Processus**, sélectionnez **Équilibrage du lot**. L’équilibrage du lot est disponible pour les lots de commandes ayant un statut de **Commencé**.

En général, l’équilibrage du lot peut être appliqué aux lots de commandes si la formule contient au moins une ligne de formule dont le **Type de substance** est *Active*. (Pour connaître l’exception à cette règle, voir la section « Lots de commandes ne s’appliquant pas à l’équilibrage du lot » plus loin dans cette rubrique.)

Le processus d’équilibrage du lot peut être divisé en deux sous-processus :

1. Équilibrer les substances du lot
1. Confirmer et lancer la formule

### <a name="balance-batch-ingredients"></a>Équilibrer les substances du lot

Lors du sous-processus Équilibrer les substances du lot, le nombre de substances à utiliser dans un lot de production est calculé en fonction des lots sélectionnés composés de substances actives. En règle générale, le calcul peut être effectué uniquement s’il existe une couverture globale de toutes les substances. Vous ne pouvez pas équilibrer uniquement une partie du lot que le lot de commandes est paramétré pour produire.

> [!NOTE]
> Vous ne pouvez pas enregistrer un calcul puis terminer le processus d’équilibrage du lot ultérieurement. Si vous fermez la page **Équilibrage du lot**, vous devez répéter le calcul pour exécuter le processus.

### <a name="confirm-and-release-the-formula"></a>Confirmer et lancer la formule

Une fois les quantités de substances calculées, vous pouvez confirmer et lancer la formule. Le processus de lancement diffère selon que les produits sont activés pour les processus de gestion des entrepôts :

- Si un produit est activé pour les processus de gestion des entrepôts, la ligne de formule est lancée à l’entrepôt selon les principes appliqués aux processus de gestion des entrepôts. La ligne de formule est lancée dans des quantités correspondant aux quantités équilibrées, et elle est lancée pour les lots spécifiques sélectionnés pour les substances actives.

    > [!NOTE]
    > Les lignes de formule peuvent être lancées à l’entrepôt uniquement dans le cadre du processus d’équilibrage du lot. Bien qu’il existe d’autres options de lancement des matières premières pour la production à l’entrepôt, celles-ci ne peuvent pas être utilisées pour les lignes de formule.

- Si un produit n’est pas activé pour les processus de gestion des entrepôts, un prélèvement en production est créé pour le produit lorsque vous confirmez et lancez la formule.

En une seule formule, vous pouvez combiner des produits qui sont activés pour les processus de gestion des entrepôts et des produits qui ne sont pas activés pour les processus de gestion des entrepôts. Lorsque les deux types de produits sont inclus dans une formule, les produits qui sont activés pour les processus de gestion des entrepôts sont débloqués à l’entrepôt. Pour les produits qui ne sont pas activés pour les processus de gestion des entrepôts, un prélèvement est créé lorsque la formule est confirmée et lancée.

### <a name="batch-orders-that-arent-applicable-for-batch-balancing"></a>Lots de commandes ne s’appliquant pas à l’équilibrage du lot

Il existe deux exceptions à la règle selon laquelle les lots de commandes peuvent être appliqué à l’équilibrage du lot si la formule contient au moins une ligne de formule dont le **Type de substance** est *Active*.

1. Si une formule contient une substance active pour un produit qui est activé pour les processus de gestion des entrepôts, mais que le numéro de lot est situé sous à un emplacement dans la hiérarchie de réservation, le lot de commandes ne s’applique pas à l’équilibrage du lot.
1. Si l’unité de mesure de la formule est différente de l’unité de mesure du stock de la substance active, l’ordre des lots n’est pas applicable pour l’équilibrage des lots.

Un lot de commandes qui ne s’applique pas à l’équilibrage du lot passe par le cycle de processus habituel des lots de commandes.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]