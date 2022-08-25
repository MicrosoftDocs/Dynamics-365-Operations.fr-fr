---
title: Fonction REPEAT ER
description: Cet article fournit des informations sur l’utilisation de la fonction REPEAT États électroniques (ER).
author: NickSelin
ms.date: 08/01/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-06-01
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: c56139a3c63b03f907b1dcbf4365990d2a13c35a
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220689"
---
# <a name="repeat-er-function"></a>Fonction REPEAT ER

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Cette fonctionnalité `REPEAT` crée un enregistrement qui contient le champ dont la valeur correspond à l’entrée spécifiée. Elle renvoie alors une nouvelle *Liste des enregistrements* d’un enregistrement répété un certain nombre de fois.

## <a name="syntax"></a>Syntaxe

```vb
REPEAT (item, number)
```

## <a name="arguments"></a>Arguments

`item` : Tout type de données [primitif](er-formula-supported-data-types-primitive.md) ou [composite](er-formula-supported-data-types-composite.md) pris en charge

La valeur à répéter.

`number` : *Entier*

Le nombre de répétitions.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d’utilisation

La liste des enregistrements répétés qui est renvoyée expose les champs suivants :

- La valeur spécifiée (champ `Item`)
- L’index des enregistrements actuels (champ `Number`)

> [!NOTE]
> Étant donné que la numérotation de base un est utilisée pour cette fonction, le champ `Number` est défini sur la valeur **1** pour renvoyer le premier enregistrement de la liste résultante.

Vous pouvez utiliser cette fonction pour multiplier les données existantes afin de pouvoir tester les performances et le volume des solutions [Rapports électroniques (ER)](general-electronic-reporting.md) en utilisant [Regression Suite Automation Tool (RSAT)](../perf-test/rsat/rsat-overview.md).

## <a name="example"></a>Exemple

Vous souhaitez générer un document au format XML qui doit contenir autant d’éléments XML `Party` que vous spécifiez dans un champ de saisie de données dans la boîte de dialogue au moment de l’exécution, avant le début de l’exécution d’un format ER.

L’illustration suivante présente le [format](er-overview-components.md#format-component) ER. Dans ce format, l’élément XML `Party` individuel est ajouté pour exposer les propriétés d’une seule partie.

<a href="./media/er-repeat-function-1.png"><img src="./media/er-repeat-function-1.png" alt="Format structure on the Format tab of the Format designer page." class="alignnone size-full" width="929" height="548" /></a>

L’illustration suivante montre les sources de données configurées suivantes :

- La source de données `Party` qui représente une seule partie. Le champ `Party.Value` est utilisé pour exposer une seule valeur de texte.
- La `NumberOfRepeats` [source de données](er-user-input-parameter-data-sources.md) qui permet de proposer un champ de saisie dans la boîte de dialogue à l’exécution, afin de pouvoir préciser le nombre d’intervenants à saisir dans le document généré.
- La source de données `Party2` qui répète l’enregistrement `Party` le nombre de fois que vous avez spécifié dans la source de données `NumberOfRepeats`.

<a href="./media/er-repeat-function-2.png"><img src="./media/er-repeat-function-2.png" alt="Configured data sources on the Mapping tab of the Format designer page." class="alignnone size-full" width="1044" height="411" /></a>

L’illustration suivante montre les liaisons de données du format ER modifiable qui sont créées pour générer une sortie au format XML. Cette sortie répertorie des parties individuelles comme nœuds énumérés.

<a href="./media/er-repeat-function-3.png"><img src="./media/er-repeat-function-3.png" alt="Configured data bindings on the Mapping tab of the Format designer page." class="alignnone size-full" width="1051" height="417" /></a>

L’illustration suivante montre le résultat lorsque le format conçu est exécuté et la valeur de la source de données `NumberOfRepeats` est spécifiée sur **5**.

<a href="./media/er-repeat-function-4.png"><img src="./media/er-repeat-function-4.png" alt="Result of running the format on a new web browser tab." class="alignnone wp-image-290711 size-full" width="400" height="380" /></a>

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
