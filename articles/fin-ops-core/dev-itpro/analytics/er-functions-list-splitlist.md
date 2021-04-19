---
title: Fonction SPLITLIST ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction SPLITLIST États électroniques (ER).
author: NickSelin
ms.date: 03/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99e199e238b3132622a8b305895637b430e8f6d2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745567"
---
# <a name="splitlist-er-function"></a>Fonction SPLITLIST ER

[!include [banner](../includes/banner.md)]

La fonction `SPLITLIST` fractionne la liste spécifiée en sous-listes (ou lots), dont chacun contient le nombre d’enregistrements spécifié. Elle renvoie ensuite le résultat en tant que nouvelle valeur de *Liste des enregistrements* constituée des lots.

## <a name="syntax-1"></a>Syntaxe 1

```vb
SPLITLIST (list, number)
```

## <a name="syntax-2"></a>Syntaxe 2

```vb
SPLITLIST (list, number, on-demand reading flag)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

`number` : *Entier*

Nombre maximal d’enregistrements par lot.

`on-demand reading flag` : *Booléen*

Une valeur *Booléenne* qui spécifie si les éléments des sous-listes doivent être générés à la demande.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d’utilisation

La liste des traitements par lots renvoyée contient les éléments suivants :

 - **Valeur :** *liste*

    Liste des enregistrements qui appartiennent au lot en cours.

- **Numéro de lot :** *Entier*

    Numéro du lot actuel dans la liste renvoyée.

Lorsque l’indicateur de lecture à la demande est défini sur **True**, les sous-listes sont générées sur demande, ce qui permet de réduire la consommation de mémoire mais peut entraîner une dégradation des performances si les éléments ne sont pas utilisés séquentiellement.

## <a name="example"></a>Exemple

Dans l’illustration suivante, une source de données **Lignes** est créée sous la forme d’une liste avec trois enregistrements. Cette liste est divisée en lots, dont chacun contient jusqu’à deux enregistrements.

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

L’illustration suivante présente la structure de format conçue. Dans cette structure de format, les liaisons à la source de données **Lignes** sont créées pour générer une sortie au format XML. Cette sortie répertorie les nœuds individuels de chaque lot et les enregistrements qu’il contient.

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

L’illustration suivante présente le résultat de l’exécution du format conçu.

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
