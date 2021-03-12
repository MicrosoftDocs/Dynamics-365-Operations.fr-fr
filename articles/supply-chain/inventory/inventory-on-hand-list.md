---
title: Liste du stock disponible
description: Cette rubrique décrit comment utiliser la page Liste disponible pour inspecter les détails du stock disponible. Elle présente quelques-unes des façons dont les différentes options de filtrage et de tri fonctionnent ensemble, et comment ces options peuvent parfois produire des résultats inattendus lorsqu’elles sont combinées.
author: sherry-zheng
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnhandItem, InventOnHandItemListPage, WHSOnHand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 94e54220a68889fd31ac3b269f7a7f6f8dd98c8e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005200"
---
# <a name="inventory-on-hand-list"></a>Liste du stock disponible

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment utiliser la page **Liste disponible** pour inspecter les détails du stock disponible. Elle présente quelques-unes des façons dont les différentes options de filtrage et de tri fonctionnent ensemble, et comment ces options peuvent parfois produire des résultats inattendus lorsqu’elles sont combinées.

## <a name="query-your-on-hand-inventory"></a>Rechercher votre stock disponible

Pour vérifier la disponibilité du stock, allez dans **Gestion des stocks \> Recherches et états \> Liste disponible**.

La page **Liste disponible** est automatiquement mise à jour lorsque des transactions sont effectuées dans le stock. Ces transactions peuvent être des transactions prévues, physiques ou financières.

Utilisez les outils suivants pour trouver l’ensemble de produits que vous recherchez :

- Dans le volet Actions, sélectionnez [**Dimensions**](#dimensions) pour ouvrir une boîte de dialogue dans laquelle vous pouvez ajouter ou supprimer des colonnes affichées dans la grille **Disponible**.
- Dans le [volet **Filtres**](#filters-pane), entrez des valeurs pour des champs spécifiques pour afficher uniquement les enregistrements correspondant à ces valeurs. Notez que les filtres que vous définissez ici s’appliquent aux tables source qui peuvent être regroupées par la suite, en fonction des dimensions que vous avez choisi d’afficher. Pour plus d’informations sur la façon dont ce comportement peut affecter vos résultats, consultez les [exemples](#examples) plus loin dans cette rubrique.
- Dans le volet **Filtres**, sélectionnez **Appliquer** pour générer la liste du stock disponible correspondant dans la grille **Disponible**.
- Dans la grille **Disponible**, sélectionnez n’importe quel en-tête de colonne pour trier ou filtrer les valeurs de cette colonne. Un filtre rapide en haut de la grille fournit des options de filtrage supplémentaires. Ces filtres s’appliquent aux résultats, et non aux tables source. Pour plus d’informations sur la façon dont ce comportement peut affecter vos résultats, consultez les [exemples](#examples) plus loin dans cette rubrique.

Pour chaque article correspondant, la grille **Disponible** fournit les colonnes suivantes d’informations sur le stock.

| Colonne | Description |
|---|---|
| Stock physique | Quantité physique disponible en stock. |
| Physique réservé | Quantité totale réservée physiquement. |
| Physique disponible | Quantité disponible (non réservée) disponible dans le stock physique.<p>**Physique disponible** est un champ calculé. La valeur est égale à la valeur **Stock physique** moins la valeur **Physique réservé**.</p> |
| Physique disponible sur les dimensions supplémentaires | Quantité physique disponible pour toutes les dimensions affichées dans la grille. |
| Total commandé | Quantité totale incluse sur les commandes entrantes ou dont la quantité est positive dans les différents journaux de stock. |
| En commande | Quantité totale incluse sur les commandes sortantes ou dont la quantité est négative dans les différents journaux de stock. |
| Commandé réservé | Quantité totale réservée sur les réceptions commandées. La valeur de ce champ représente la quantité totale d’articles dans les transactions sortantes qui présentent le statut _Commandé réservé_. Les articles réservés comme commandés ne sont pas physiquement disponibles en stock. Par conséquent, ils ne peuvent pas être directement prélevés et livrés. |
| Disponible pour réservation | Quantité totale de stock disponible pouvant être réservé.<p>**Remarque :** si la case à cocher **Réserver les articles commandés** est activée sur la page **Paramètres de gestion des stocks et des entrepôts**, la valeur de ce champ inclut les réceptions prévues. Si la case à cocher est désactivée, la valeur exclut les réceptions prévues.</p> |
| Total disponible | Quantité totale disponible.<p>**Total disponible** est un champ calculé. La valeur est égale à la valeur **Physique disponible** plus la valeur **Total commandé** moins la valeur **En commande**.</p> |

## <a name="apply-filters-to-find-the-records-that-youre-looking-for"></a><a name="filters-pane"></a>Appliquer des filtres pour trouver les enregistrements que vous recherchez

Utilisez le volet **Filtres** pour filtrer la liste du stock disponible afin de n’inclure que les enregistrements dont les valeurs de champ correspondent aux critères de filtrage. Pour définir un filtre, procédez comme suit.

1. Dans le volet **Filtres**, recherchez le champ que vous souhaitez filtrer.
2. Dans le champ sous le nom du champ cible, sélectionnez un opérateur logique (par exemple, *commence par*, *égal à* ou *supérieur à*).
3. Entrez ou sélectionnez la valeur à rechercher.

> [!IMPORTANT]
> La page **Liste disponible** est assemblée à partir d’une table du stock disponible détaillée qui comprend toutes les dimensions disponibles. Cependant, la liste sur cette page est un résumé. Par conséquent, elle peut combiner des lignes de la table source en regroupant les valeurs en fonction des dimensions affichées.
>
> Les filtres que vous définissez dans le volet **Filtres** s’appliquent à la table source, et non à la liste regroupée. Ce comportement peut parfois produire des résultats inattendus. Pour plus d’informations sur la façon dont ce comportement peut affecter vos résultats, consultez les [exemples](#examples) plus loin dans cette rubrique.
> 
> Cependant, les [filtres disponibles dans la grille](#grid-filters) *s’appliquent* à la liste regroupée. Ces filtres comprennent à la fois le filtre rapide en haut de la grille et le filtre pour chaque en-tête de colonne.

Vous pouvez modifier l’ensemble des filtres disponibles dans le volet **Filtres** en procédant comme suit.

- Pour supprimer un filtre du volet, cliquez sur son bouton **Fermer** (**X**).
- Pour ajouter un filtre, cliquez sur **Ajouter** en haut du volet **Filtres**. La boîte de dialogue **Ajouter des champs de filtre** qui apparaît répertorie la liste des champs disponibles. Elle affiche également des informations sur le type de données et la table de chaque champ. Utilisez les en-têtes de colonne pour filtrer et trier la liste selon vos besoins, puis activez la case à cocher de chaque champ que vous souhaitez ajouter au volet **Filtres**. Une fois que vous avez terminé, cliquez sur **Insérer** pour appliquer vos modifications.

## <a name="select-which-dimensions-to-show"></a><a name="dimensions"></a>Sélectionner les dimensions à afficher

Les dimensions vous donnent des informations supplémentaires sur chaque article de la liste du stock disponible. Elles vous offrent également d’autres moyens de trier et de filtrer la liste. Les dimensions que vous choisissez d’afficher affectent également la façon dont les lignes sont regroupées sur la page **Liste disponible**. Ce regroupement, à son tour, peut affecter la manière dont les lignes des tables source sont combinées dans les résultats affichés. Pour plus d’informations sur la façon dont ce comportement peut affecter vos résultats, consultez les [exemples](#examples) plus loin dans cette rubrique.

Pour personnaliser la sélection des dimensions de stock affichées, procédez comme suit.

1. Dans le volet Actions, sélectionnez **Dimensions**.

    La boîte de dialogue **Affichage des dimensions** qui apparaît répertorie chaque dimension.

2. Activez la case à cocher de chaque dimension à inclure dans la grille.
3. Si vous souhaitez que votre sélection soit utilisée par défaut lors de la prochaine ouverture de la page **Liste disponible**, définissez l’option **Enregistrer le paramétrage** sur **Oui**. Si vous définissez cette option sur **Non**, votre sélection n’est utilisée que pendant la session en cours. Par conséquent, la prochaine fois que vous ouvrirez la page, la sélection actuelle par défaut sera utilisée.
4. Cliquez sur **OK** pour fermer la boîte de dialogue et appliquer vos modifications.

## <a name="filter-on-the-output-of-the-inventory-on-hand-list"></a><a name="grid-filters"></a>Filtrer la sortie de la liste du stock disponible

Vous pouvez sélectionner n’importe quel en-tête de colonne dans la grille **Disponible** pour trier ou filtrer les valeurs de cette colonne. Un filtre rapide en haut de la grille fournit des options de filtrage supplémentaires. Ces filtres s’appliquent aux résultats, et non aux tables source. Pour plus d’informations sur la façon dont ce comportement peut affecter vos résultats, consultez les [exemples](#examples) plus loin dans cette rubrique.

> [!NOTE]
> Vous ne pouvez pas filtrer et trier toutes les colonnes. La plupart des colonnes de quantité ne comprennent pas de contrôles de tri et de filtrage, car ce sont des champs calculés. La colonne **En commande** est une exception.

## <a name="examples"></a><a name="examples"></a>Exemples

Votre système comprend une table de stock détaillée (non regroupée) qui répertorie le stock disponible suivant.

| Numéro d’article | Site | Entrepôt | Stock physique | Physique disponible |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 2 | 2 | 2 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-1"></a>Scénario 1

La page **Liste disponible** est configurée pour afficher les dimensions finales suivantes :

- Numéro d’article
- Site
- Entrepôt

Dans le volet **Filtres**, les critères de filtrage suivants sont définis :

- **Numéro d’article** \| **est exactement** \| _IA0001_
- **Physique disponible** \| **inférieur ou égal à** \| _1_

Voici la sortie qui en résulte.

| Numéro d’article | Site | Entrepôt | Stock physique | Physique disponible |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-2"></a>Scénario 2

La page **Liste disponible** est configurée pour afficher les dimensions finales suivantes :

- Numéro d’article
- Site

Dans le volet **Filtres**, les critères de filtrage suivants sont définis :

- **Numéro d’article** \| **est exactement** \| _IA0001_
- **Physique disponible** \| **inférieur ou égal à** \| _1_

Voici la sortie qui en résulte.

| Numéro d’article | Site | Stock physique | Physique disponible |
|---|---|---|---|
| IA0001 | 1 | 2 | 2 |

Notez que les paramètres du volet **Filtres** s’appliquent à la table de stock détaillée (non regroupée) affichée au début de cette section. Par conséquent, le critère **Physique disponible** \| **inférieur ou égal à** \| _1_ trouve deux lignes dans cette table (les première et troisième lignes, chacune indiquant une valeur **Physique disponible** de _1_). Cependant, dans ce scénario, la page **Liste disponible** n’est pas configurée pour afficher la dimension **Entrepôt**. Par conséquent, elle regroupe les deux lignes d’origine en une seule ligne résultante, car les deux lignes ont des valeurs identiques dans toutes les dimensions affichées. Cette ligne semble enfreindre le critère de filtrage, car la valeur **Physique disponible** indique _2_. Cependant, le résultat est correct, car les paramètres du volet **Filtres** s’appliquent à la table source, et non à la table regroupée affichée sur la page **Liste disponible**.
