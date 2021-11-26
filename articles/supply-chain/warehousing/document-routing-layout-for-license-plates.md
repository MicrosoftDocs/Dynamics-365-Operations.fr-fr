---
title: Mise en page d’acheminement de document pour les étiquettes de contenant
description: Cette rubrique décrit comment utiliser les méthodes de mise en forme pour imprimer les valeurs sur des étiquettes.
author: perlynne
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 5311c13154baafdc7225ee869b3ef524eecc0d00
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2021
ms.locfileid: "7778351"
---
# <a name="document-routing-layout-for-license-plate-labels"></a>Mise en page d’acheminement de document pour les étiquettes de contenant

[!include [banner](../includes/banner.md)]


La mise en page d’acheminement de document définit la mise en page des étiquettes de contenant et les données y sont imprimées. Vous configurez les points de déclenchement d’impression lorsque vous configurez les articles de menu d’appareil mobile et les modèles de travail.

Dans un scénario type, les commis de réception à l’entrepôt impriment les étiquettes de contenant immédiatement après avoir enregistré le contenu des palettes qui arrivent dans la zone de réception. Les étiquettes physiques sont appliquées aux palettes. Elles peuvent ensuite être utilisée pour validation dans le cadre du processus de rangement qui suit et des futures opérations de prélèvement sortant.

Vous pouvez imprimer des étiquettes très complexes, à condition que l’appareil d’impression puisse interpréter le texte qu’il reçoit. Par exemple, une mise en page ZPL (Zebra Programming Language) qui inclut un code barres pourrait ressembler à l’exemple suivant.

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

Dans le cadre du processus d’impression d’étiquettes, le texte `$LicensePlateId$` de cet exemple sera remplacé par une valeur de données.

Pour voir les valeurs qui seront imprimées, accédez à **Gestion d’entrepôt \> Demandes de renseignements et rapports \> Étiquettes de contenants**.

Plusieurs outils de génération d’étiquettes largement disponibles peuvent vous aider à formater le texte pour la mise en page de l’étiquette. Nombre de ces outils prennent en charge le format `$FieldName$`. De plus, Microsoft Dynamics 365 Supply Chain Management utilise une logique de formatage spéciale dans le cadre du mappage de champ pour la mise en page d’acheminement de document.

## <a name="turn-on-this-feature-for-your-system"></a>Activez cette fonctionnalité pour votre système

Si votre système n’inclut pas déjà les fonctionnalités décrites dans cette rubrique, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez la fonctionnalité *Mises en page améliorées des étiquettes de contenant*. (Depuis la version 10.0.21 de Supply Chain Management, cette fonctionnalité est activée par défaut.)

## <a name="custom-number-formats"></a>Formats de numéro personnalisés

Vous pouvez personnaliser la mise en forme des valeurs du champ numérique qui sont imprimées à l’aide de codes qui ont le format suivant.

```dos
$FieldName:FormatString$
```

Voici une explication de ce format :

- `FieldName` est le nom du champ de données (tel que **Qté**).
- `FormatString` définit comment les données doivent être imprimées.

Les exemples suivants montrent comment personnaliser le champ de quantité de travail (**Qté**) :

- Pour toujours afficher quatre chiffres (en utilisant des zéros comme espaces réservés), utilisez `$Qty:0000$`. Par exemple, si la quantité est de 10, l’étiquette affichera « 0010 ».
- Pour toujours afficher deux décimales, utilisez `$Qty:0.00$`. Par exemple, si la quantité est de 10, l’étiquette affichera « 10.00 ».

Pour une liste complète des chaînes de format numérique disponibles, consultez [Chaînes de format numérique personnalisées](/dotnet/standard/base-types/custom-numeric-format-strings).

## <a name="custom-string-formats"></a>Formats de chaîne personnalisés

Vous pouvez supprimer les premiers caractères d’une chaîne en utilisant le champ et le code de format suivants.

```dos
$FieldName:#..$
```

Ici, `#` spécifie le nombre de caractères à ignorer. Par exemple, pour imprimer un numéro de contenant SSCC (Serial Shipping Container Code) qui ne comprend pas les deux premiers caractères, utilisez `$LicensePlateId:2..$`. Dans ce cas, le numéro de contenant 0011111111111222221 sera imprimé comme « 11111111111222221 ».

## <a name="custom-datetime-formats"></a>Formats date/heure personnalisés

L’exemple suivant montre comment contrôler le format utilisé pour imprimer les dates.

```dos
$PrintedDate:dd-MM-yyyy$
```

Dans cet exemple, la date du 30 avril 2020 sera imprimée comme « 30-04-2020 ».

Pour une liste complète des formats date/heure disponibles, consultez [Chaînes de format date/heure personnalisées](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="print-individual-lines-from-multiline-data"></a>Imprimer des lignes individuelles à partir de données multilignes

Si un champ de données contient plusieurs lignes (c’est-à-dire des lignes séparées par des sauts de ligne), vous pouvez imprimer une ligne individuelle en utilisant le format suivant.

```dos
$FieldName[#]$
```

Ici, `#` est le numéro de ligne que vous souhaitez imprimer. (Utilisez 1 pour la première ligne.)

Par exemple, votre système a un champ `AdditionalAddress` qui stocke l’adresse multiligne suivante :

Contoso Inc.  
123 Nom de la rue  
Une ville, un État

Vous pouvez imprimer cette adresse, une ligne à la fois, en utilisant les codes suivants.

| Code | Texte imprimé |
|---|---|
| `$AdditionalAddress[1]$` | Contoso Inc. |
| `$AdditionalAddress[2]$` | 123 Nom de la rue |
| `$AdditionalAddress[3]$` | Une ville, un État |

## <a name="print-and-format-from-a-display-method"></a>Imprimer et formater à partir d’une méthode d’affichage

Vous pouvez imprimer à partir d’une méthode d’affichage en utilisant le format suivant.

```dos
$DisplayMethod()$
```

Vous pouvez combiner ce format avec d’autres types décrits précédemment dans cette rubrique. Par exemple, vous disposez d’une méthode d’affichage nommée `DisplayListOfItemsNumbers()` et vous souhaitez imprimer le premier numéro d’élément de cette méthode. Dans ce cas, vous pouvez utiliser le code suivant.

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a>En savoir plus sur l’impression d’étiquettes

Pour plus d’informations sur la configuration et l’impression d’étiquettes, voir [Activer l’impression d’étiquette de contenant](tasks/license-plate-label-printing.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]