---
title: Types de données primitifs pris en charge pour les formules des États électroniques
description: Cette rubrique fournit des informations sur les types de données primitifs pris en charge dans les formules des États électroniques (ER).
author: NickSelin
ms.date: 06/02/2021
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 96fdf33f4cc5f22015c00c57858bd438e6465764
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8323638"
---
# <a name="supported-primitive-data-types-for-electronic-reporting-formulas"></a>Types de données primitifs pris en charge pour les formules des États électroniques

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les types de données primitifs pris en charge dans les expressions des [États électroniques (ER)](general-electronic-reporting.md) expressions. Voici une liste des types de données primitifs :

- [booléen](#boolean)
- [date](#date)
- [dateheure](#datetime)
- [énumeration](#enumeration)
- [guid](#guid)
- [entier](#integer)
- [int64](#int64)
- [réel](#real)
- [chaîne](#string)

## <a name="boolean"></a><a name="boolean"></a>Booléen

Le type de données primitif *booléen* contient une valeur qui est évaluée comme *true* ou *false*. Vous pouvez utiliser les mots-clés littéraux réservés **True** et **False** partout où l’on attend une expression *booléenne*. La valeur par défaut est *false*.

La représentation interne d’un *booléen* est un *entier*. La veleur *entière* 0 (zéro) est évaluée comme *false*, et toutes les autres valeurs *entières* sont évaluées comme *true*. Lorsque vous [validez](general-electronic-reporting-formula-designer.md#TestFormula) une expression configurée qui renvoie un *booléen* dans le [Concepteur de formules ER](er-advanced-formula-editor.md), le volet des résultats du test présente *0* (zéro) lorsqu’une expression retourne *false*. Sinon, le volet des résultats du test présente *1*.

Un *booléen* n’a pas de conversions implicites. Cependant, vous pouvez utiliser la fonction [TEXT](er-functions-text-text.md) pour convertir explicitement un *booléen* en *chaîne* :

- La valeur *false* est convertie en chaîne de texte **False**.
- La valeur *true* est convertie en chaîne de texte **True**.

> [!NOTE]
> Cette conversion ne dépend pas du [contexte](er-design-multilingual-reports.md) de langue et de culture fourni.

Les [opérateurs](er-formula-language.md#Operators) de comparaison sont le seul type d’opérateur qui peut être utilisé avec le type de données *booléen*. Les opérateurs suivants peuvent être utilisés pour comparer deux valeurs *booléennes* : \<\> et =.

## <a name="date"></a><a name="date"></a>Date

Le type de données primitif *date* contient le jour, le mois et l’année. Les dates peuvent être initiées à l’aide des fonctions suivantes :

- [DATEVALUE](er-functions-datetime-datevalue.md)
- [NULLDATE](er-functions-datetime-nulldate.md)
- [SESSIONTODAY](er-functions-datetime-sessiontoday.md)
- [TODAY](er-functions-datetime-today.md)

Le type de données *date* peut contenir des dates comprises entre le 1er janvier 1900 et le 31 décembre 2154. La valeur par défaut est **null**, et la représentation interne est la date du 1er janvier 1900.

Une *date* n’a pas de conversions implicites. Cependant, vous pouvez utiliser les fonctions de conversion explicites suivantes :

- [DATEFORMAT](er-functions-datetime-dateformat.md)
- [DATETODATETIME](er-functions-datetime-datetodatetime.md)
- [TEXT](er-functions-text-text.md)

La fonction [ADDDAYS](er-functions-datetime-adddays.md) vous permet d’ajouter et de soustraire des jours aux dates. De cette façon, vous pouvez déplacer la date d’un nombre spécifique de jours dans le futur et le passé. La fonction [DAYS](er-functions-datetime-days.md) vous permet de soustraire des dates les unes des autres et de calculer la différence en jours. Pour plus d’informations sur la transformation des valeurs *date*, voir [Liste des fonctions ER dans la catégorie de date et d’heure](er-functions-category-datetime.md).

Les [opérateurs](er-formula-language.md#Operators) de comparaison sont le seul type d’opérateur qui peut être utilisé avec le type de données *date*. Les opérateurs suivants peuvent être utilisés pour comparer deux valeurs *date* : \<\>, \<, \<=, =, \> et \>=.

## <a name="datetime"></a><a name="datetime"></a>DateHeure

Le type de données primitif *dateheure* combine le type *date* et une valeur qui représente le temps qui s’est écoulé depuis minuit. Le temps est exprimé en heures, minutes, secondes et fractions de seconde. Une valeur *dateheure* contient également des informations sur le fuseau horaire.

Le type de données *dateheure* peut contenir des dates entre le 1er janvier 1900 (1900-01-01T00:00:00.0000000+00:00 au [format](/dotnet/standard/base-types/standard-date-and-time-format-strings) aller-retour) et le 31 décembre 2154 (2154/12/31T11:59:59.9999999+00:00 au format aller-retour). La plus petite unité de temps dans une valeur *dateheure* est un dix millionième de seconde.

> [!NOTE]
> Quand le [spécificateur](/dotnet/standard/base-types/standard-date-and-time-format-strings) **hh** est utilisé pour les heures, les valeurs de temps supérieures à 12:59:59:9999999 ne peuvent pas être interprétées comme des heures valides.
>
> Quand le spécificateur **HH** est utilisé pour les heures, les valeurs de temps supérieures à 23:59:59:9999999 ne peuvent pas être interprétées comme des heures valides.

La valeur par défaut est **null**, et la représentation interne est la date du 1er janvier 1900 (1900-01-01T00:00:00.0000000+00:00 au format aller-retour).

Les valeurs dateheure peuvent être initiées à l’aide des fonctions suivantes :

- [DATETIMEVALUE](er-functions-datetime-datetimevalue.md)
- [NULNULLDATETIMELDATE](er-functions-datetime-nulldatetime.md)
- [SESSIONNOW](er-functions-datetime-sessionnow.md)
- [NOW](er-functions-datetime-now.md)

Une *dateheure* n’a pas de conversions implicites. Cependant, vous pouvez utiliser les fonctions de conversion explicites suivantes :

- [DATETIMEFORMAT](er-functions-datetime-datetimeformat.md)
- [TEXT](er-functions-text-text.md)

Pour plus d’informations sur la transformation des valeurs *dateheure*, voir [Liste des fonctions ER dans la catégorie de date et d’heure](er-functions-category-datetime.md).

Les [opérateurs](er-formula-language.md#Operators) de comparaison sont le seul type d’opérateur qui peut être utilisé avec le type de données *dateheure*. Les opérateurs suivants peuvent être utilisés pour comparer deux valeurs *dateheure* : \<\>, \<, \<=, =, \> et \>=.

## <a name="enumeration"></a><a name="enumeration"></a>Énumération

Le type de données primitif *énumération* est une liste de littéraux. Vous pouvez utiliser des énumérations définies dans le [code source](../dev-ref/xpp-data-primitive.md#enum) de l’application. Vous pouvez également introduire vos propres énumérations dans le modèle de données ER et dans les composants de format ER.

Une *énumération* d’application peut être utilisé dans les expressions de tout mappage de modèle ER et de format ER.

L’illustration suivante montre comment ajouter l’énumération du modèle **CustVendCorrectiveReasonCode** au modèle de données ER modifiable.

[![Configuration d’une énumération de modèle dans le concepteur de modèle de données ER](./media/er-formula-supported-data-types-primitive-enum1.gif)](./media/er-formula-supported-data-types-primitive-enum1.gif)

Une *énumération* de modèle peut être utilisée dans les expressions de tout mappage de modèle ER et format ER qui ont été créés sous un modèle de données où l’*énumération* a été introduite.

L’illustration suivante montre comment ajouter l’énumération de format **Liste des sous-catégories de taxe au preneur Natura** au format ER modifiable.

[![Configuration d’une énumération de format dans le concepteur de format ER.](./media/er-formula-supported-data-types-primitive-enum2.gif)](./media/er-formula-supported-data-types-primitive-enum2.gif)

Une *énumération* de format ne peut être utilisée que dans les expressions du format ER où l’*énumération* a été introduite.

Vous devez utiliser le type approprié de sources de données ER pour intégrer une énumération spécifique dans un composant ER configuré en tant que constante ou en tant que valeur que l’utilisateur qui exécute une solution ER a définie dans la boîte de dialogue au moment de l’exécution.

- Les énumérations d’applications sont accessibles en utilisant les sources de données **Dynamics 365 for Operations \ Énumération** et **Général \ Paramètres d’entrée utilisateur**. L’illustration suivante montre comment ajouter au format ER modifiable les sources de données **appenumNoYes** et **uipNoYes** qui se réfèrent à l’énumération d’applications **NoYes**.

    [![Ajout de sources de données d’énumération d’applications dans le concepteur de format ER.](./media/er-formula-supported-data-types-primitive-enum3a.gif)](./media/er-formula-supported-data-types-primitive-enum3a.gif)

- Les énumérations de modèles de données sont accessibles en utilisant les sources de données **Modèle de données\Énumération** et **Modèle de données\Paramètres d’entrée utilisateur d’énumération**. L’illustration suivante montre comment ajouter au format ER modifiable la source de données **CustVendCorrectiveReasonCode** qui se réfère à l’énumération de modèles de données **CustVendCorrectiveReasonCode**.

    [![Ajout de sources de données d’énumération de modèles dans le concepteur de format ER.](./media/er-formula-supported-data-types-primitive-enum3b.gif)](./media/er-formula-supported-data-types-primitive-enum3b.gif)

- Les énumérations de formats sont accessibles en utilisant les sources de données **Format\Énumération** et **Format\Paramètres d’entrée utilisateur d’énumération**. L’illustration suivante montre comment ajouter au format ER modifiable la source de données **NaturaReverseCharge** qui se réfère à l’énumération de format **Sous-catégories de taxe au preneur Natura**.

    [![Ajout de sources de données d’énumération de formats dans le concepteur de format ER.](./media/er-formula-supported-data-types-primitive-enum3c.gif)](./media/er-formula-supported-data-types-primitive-enum3c.gif)

Une *énumération* n’a pas de conversions implicites. Cependant, vous pouvez utiliser la fonction de conversion [TEXT](er-functions-text-text.md) pour convertir une *énumération* en chaîne de texte. Cette conversion ne dépend pas de la langue. Pour savoir comment associer un valeur *énumération* avec les étiquettes spécifiques à la langue appropriées, voir les exemples d’utilisation des fonctions [LISTOFFIELDS](er-functions-list-listoffields.md) et [GETENUMVALUEBYNAME](er-functions-text-getenumvaluebyname.md).

Les [opérateurs](er-formula-language.md#Operators) de comparaison sont le seul type d’opérateur qui peut être utilisé avec le type de données *énumération*. Les opérateurs suivants peuvent être utilisés pour comparer deux valeurs *énumération* : \<\> et =.

## <a name="guid"></a><a name="guid"></a>Guid

Le type de données primitif *guid* contient une valeur d’identificateur global unique (GUID). Un GUID est une valeur qui peut être utilisée sur tous les ordinateurs et réseaux, partout où un identifiant unique est requis. Il est peu probable que ce numéro existe en double. Un GUID valide répond à toutes les spécifications suivantes :

- Il doit comporter 32 digits hexadécimaux.
- De plus, il doit comporter quatre tirets intégrés aux emplacements suivants : 8-4-4-4-12.
- De plus, des accolades facultatives \{\} peuvent être ajoutées au début et à la fin de la chaîne. Par exemple, **\{2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212\}** et **2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212** sont tous deux des chaînes GUID valides.
- Par conséquent, il doit y avoir un total de 36 ou 38 caractères, selon que des accolades sont ajoutées.
- Les lettres utilisées comme digits hexadécimaux peuvent être des majuscules (A–F), des minuscules (a–f) ou les deux.

Vous pouvez utiliser les fonctions de conversion explicites suivantes :

- [GUIDVALUE](er-functions-text-guidvalue.md)
- [TEXT](er-functions-text-text.md)

Les [opérateurs](er-formula-language.md#Operators) de comparaison sont le seul type d’opérateur qui peut être utilisé avec le type de données *guid*. Les opérateurs suivants peuvent être utilisés pour comparer deux valeurs *guid* : \<\> et =.

## <a name="integer"></a><a name="integer"></a>Entier

Le type de données primitif *entier* représente un nombre sans décimales. Les entiers sont utilisés comme variables de contrôle dans les instructions répétitives ou comme index dans les listes d’enregistrements.

Un littéral *entier* est l’entier tel qu’il est entré directement dans une [expression](general-electronic-reporting-formula-designer.md#formula-designer-overview) ER (formule), comme **12345**. Un *entier* a une taille de 32 bits. La valeur par défaut est **0**, et la représentation interne est un nombre long. Un *entier* est automatiquement converti en *réel*.

De plus, vous pouvez utiliser les fonctions de conversion explicites suivantes :

- [INTVALUE](er-functions-conversion-intvalue.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

La plage d’un *entier* est \[-2 147 483 647 : 2 147 483 647\]. Tous les entiers de cette plage peuvent être utilisés comme littéraux.

Tous les [opérateurs](er-formula-language.md#Operators) de comparaison et mathématiques peuvent être utilisés avec le type de données *entier*.

## <a name="int64"></a><a name="int64"></a>Int64

Le type de données primitif *int64* représente un nombre sans décimales. Les valeurs *Int64* sont utilisées comme variables de contrôle dans les instructions répétitives ou comme index dans les identificateurs d’enregistrements.

Un *int64* a une taille de 64 bits. La valeur par défaut est **0**, et la représentation interne est un nombre long. Un *int64* est automatiquement converti en *réel*.

De plus, vous pouvez utiliser les fonctions de conversion explicites suivantes :

- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

La plage d’un *int64* est \[-9 223 372 036 854 775 807 : 9 223 372 036 854 775 807\].

Tous les [opérateurs](er-formula-language.md#Operators) de comparaison et mathématiques peuvent être utilisés avec le type de données *int64*.

## <a name="real"></a><a name="real"></a>Réel

Le type de données *réel* peut contenir des valeurs décimales en plus des entiers. Vous pouvez utiliser des littéraux décimaux partout où un *réel* est attendu. Un littéral décimal est le nombre décimal tel qu’il est entré directement dans le code, tel que **2.19**.

> [!NOTE]
> Dans les expressions ER, un point (.) est toujours utilisé comme séparateur décimal.

Les réels peuvent être utilisés dans toutes les expressions, et ils peuvent être utilisés à la fois avec des opérateurs de comparaison et des opérateurs arithmétiques. Un *réel* a une précision de 16 chiffres significatifs. La valeur par défaut d’un *réel* est **0.0**, et la représentation interne est un nombre numérique codé en binaire (BCD). Le codage BCD permet des représentations exactes de valeurs multiples de 0,1. La plage d’une variable *réelle* est -(10)<sup>127</sup> à (10)<sup>127</sup>. Tous les réels de cette plage peuvent être utilisés comme littéraux dans les expressions ER.

Un *réel* n’a pas de conversions implicites. Cependant, vous pouvez utiliser les fonctions suivantes pour convertir explicitement un *réel* en d’autres types de données et d’autres types de données en *réel* :

- [INTVALUE](er-functions-conversion-intvalue.md)
- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)
- [VALUE](er-functions-conversion-value.md)

Tous les [opérateurs](er-formula-language.md#Operators) de comparaison et mathématiques peuvent être utilisés avec le type de données *réel*.

## <a name="string"></a><a name="string"></a>Chaîne

Le type de données primitif *chaîne* représente une séquence de caractères utilisés comme textes, numéros de compte, adresses et numéros de téléphone.

Les littéraux *chaîne* sont des caractères placés entre guillemets droits (""). Les littéraux *chaîne* peuvent être utilisés partout où des valeurs *chaîne* sont attendues dans les expressions ER. Vous pouvez utiliser des chaînes dans des expressions logiques, telles que des comparaisons. Vous pouvez également concaténer des valeurs *chaîne* en utilisant l’opérateur **\&** ou la fonction [CONCATENATE](er-functions-text-concatenate.md).

> [!NOTE]
> Si vous concaténez deux valeurs *chaîne* et que vous voulez que la *chaîne* résultante s’étende sur plusieurs lignes, utilisez le séparateur de saut de ligne entre les valeurs. Pour la sortie TEXT, ce séparateur peut être un caractère généré à l’aide de l’expression [CHAR](er-functions-text-char.md)(10) ou CHAR(13). Pour le HTML, il peut s’agir de la balise **\<br\>**.

La valeur par défaut d’une *chaîne* est une chaîne de texte vide qui ne contient pas de caractère et la représentation interne est une liste de caractères.

Il n’y a pas de conversions automatiques pour les chaînes. Cependant, vous pouvez utiliser les fonctions de conversion explicites suivantes :

- [CHAR](er-functions-text-char.md)
- [FORMAT](er-functions-text-format.md)
- [LEFT](er-functions-text-left.md)
- [LEN](er-functions-text-len.md)
- [MID](er-functions-text-mid.md)
- [PADLEFT](er-functions-text-padleft.md)
- [REPLACE](er-functions-text-replace.md)
- [RIGHT](er-functions-text-right.md)
- [TEXT](er-functions-text-text.md)
- [TRANSLATE](er-functions-text-translate.md)
- [TRIM](er-functions-text-trim.md)
- [UPPER](er-functions-text-upper.md)

Pour en savoir plus sur la transformation des valeurs *chaîne*, voir [Liste des fonctions ER de la catégorie texte](er-functions-category-text.md).

Une *chaîne* peut contenir un nombre indéfini de caractères.

Tous les [opérateurs](er-formula-language.md#Operators) de comparaison peuvent être utilisés avec le type de données *chaîne*.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des États électroniques](general-electronic-reporting.md)
- [Langage de formule dans la gestion des états électroniques](er-formula-language.md)
- [Types de données composites pris en charge](er-formula-supported-data-types-composite.md)
