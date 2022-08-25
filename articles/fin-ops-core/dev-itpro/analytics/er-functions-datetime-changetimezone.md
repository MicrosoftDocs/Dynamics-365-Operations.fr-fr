---
title: Fonction CHANGETIMEZONE ER
description: Cet article fournit des informations sur l’utilisation de la fonction CHANGETIMEZONE États électroniques (ER).
author: kfend
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: AX 10.0.23
ms.custom: 58771
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: d732fd8bd44c4c131f376919b2546a7ecf668495
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286117"
---
# <a name="changetimezone-er-function"></a>Fonction CHANGETIMEZONE ER

[!include [banner](../includes/banner.md)]

La fonction `CHANGETIMEZONE` renvoie une valeur de *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* en temps universel coordonné (Heure de Greenwich, \[GMT\]) qui est convertie d’une valeur de date donnée d’un fuseau horaire en une valeur de date/heure d’un autre fuseau horaire.

## <a name="syntax"></a>Syntaxe

```vb
CHANGETIMEZONE (datetime, base time zone, target time zone)
```

## <a name="arguments"></a>Arguments

`datetime` : *DateTime*

Valeur de date/heure dans le fuseau horaire Temps universel coordonné qui représente la valeur date/heure à convertir.

`base time zone`: *[Chaîne](er-formula-supported-data-types-primitive.md#string)*

Nom du fuseau horaire vers lequel une valeur de date/heure donnée est déplacée avant la conversion.

`target time zone` : *Chaîne*

Nom du fuseau horaire vers lequel une valeur de date/heure convertie est déplacée pendant la conversion.

## <a name="return-values"></a>Valeurs de retour

*Date et heure*

Valeur de date/heure résultante dans le fuseau horaire Temps universel coordonné.

## <a name="usage-notes"></a>Notes d’utilisation

Pour spécifier les fuseaux horaires source et cible, vous pouvez utiliser des noms de fuseau horaire qui sont [fournis](https://data.iana.org/time-zones/releases/) par l’[IANA (Internet Assigned Numbers Authority)](https://www.iana.org/) ou qui sont [pris en charge](/windows-hardware/manufacture/desktop/default-time-zones) par Microsoft Windows.

Au moment de l’exécution, l’exception « Le fuseau horaire "\<time zone name\>" n’existe pas » est renvoyée si le nom fourni ne figure pas dans la liste IANA ou dans le registre Windows.

Pour les fuseaux horaires où l’heure d’été est appliquée, la conversion prend en compte le décalage d’heure d’été Temps universel coordonné. Les dernières informations disponibles sur ce décalage sont utilisées lors de la conversion.

## <a name="example-1"></a>Exemple 1

Dans cet exemple, les noms de fuseau horaire pour Windows sont utilisés.

Vous configurez la source de données **DSX** du type **Champ calculé**. Elle contient l’expression suivante :

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "E. Europe Standard Time", "Hawaiian Standard Time"), "O")
)
```

Si vous configurez l’expression de la source de données **DSY** du type **Champ calculé** en tant que `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, la source de données **DSX** renvoie le texte **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**. Ce texte montre que le décalage horaire entre les deux fuseaux horaires fournis le 1er juin est de plus de 24 heures. Par conséquent, la valeur de date/heure convertie est un jour plus tôt que la valeur date/heure donnée, car le fuseau horaire de base est en avance sur le fuseau horaire cible.

Si vous configurez l’expression de la source de données **DSY** du type **Champ calculé** en tant que `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, la source de données **DSX** renvoie le texte **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**. Ce texte montre que le décalage horaire entre les deux fuseaux horaires fournis le 1er décembre est de moins de 24 heures. Par conséquent, la valeur date/heure convertie est égale à la valeur date/heure donnée.

> [!NOTE]
> La même expression renvoie un écart différent entre les valeurs date/heure fournies et converties pour la même paire de fuseaux horaires, car un décalage d’heure d’été Temps universel coordonné différent est appliqué pour les fuseaux horaires fournis à une date/heure donnée.

## <a name="example-2"></a>Exemple 2

Dans cet exemple, les noms de fuseau horaire IANA sont utilisés.

Vous configurez la source de données **DSX** du type **Champ calculé**. Elle contient l’expression suivante :

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "Europe/Athens", "US/Hawaii"), "O")
)
```

Si vous configurez l’expression de la source de données **DSY** du type **Champ calculé** en tant que `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, la source de données **DSX** renvoie le texte **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**. Ce texte montre que le décalage horaire entre les deux fuseaux horaires fournis le 1er juin est de plus de 24 heures. Par conséquent, la valeur de date/heure convertie est un jour plus tôt que la valeur date/heure donnée, car le fuseau horaire de base est en avance sur le fuseau horaire cible.

Si vous configurez l’expression de la source de données **DSY** du type **Champ calculé** en tant que `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, la source de données **DSX** renvoie le texte **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**. Ce texte montre que le décalage horaire entre les deux fuseaux horaires fournis le 1er décembre est de moins de 24 heures. Par conséquent, la valeur date/heure convertie est égale à la valeur date/heure donnée.

## <a name="example-3"></a>Exemple 3

Vous configurez la source de données **DSX** du type **Champ calculé**. Elle contient l’expression suivante :

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "US/Hawaii", "Europe/Athens"), "O")
)
```

Si vous configurez l’expression de la source de données **DSY** du type **Champ calculé** en tant que `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, la source de données **DSX** renvoie le texte **2021-06-01T12:55:00.0000000+00:00 -> 2021-06-02T01:55:00.0000000+00:00’**. Ce texte montre que le décalage horaire entre les deux fuseaux horaires fournis le 1er juin est de plus de 24 heures. Par conséquent, la valeur de date/heure convertie est un jour plus tard que la valeur date/heure donnée, car le fuseau horaire de base est en avance sur le fuseau horaire de base.

## <a name="example-4"></a>Exemple 4

Vous pouvez recevoir un horodatage d’une source externe sous forme de texte ne contenant aucune information de fuseau horaire. Cependant, vous connaissez peut-être le fuseau horaire dans lequel la source est exploitée. Par exemple, vous recevez l’horodatage **01/12/2021 12:55:00** d’un service exploité en Espagne. Pour enregistrer correctement cette valeur date/heure dans la base de données, effectuez la conversion suivante :

- Configurez la source de données **DSY** du type **Champ calculé** pour convertir un horodatage de texte en valeur de date/heure Temps universel coordonné.

    `DATETIMEVALUE ("01/12/2021 12:55:00", "dd/MM/yyyy HH:mm:ss", "ES")`

- Configurez la source de données **DSX** du type **Champ calculé** pour basculer la valeur date/heure convertie en Temps universel coordonné comme valeur date/heure du fuseau horaire de la source externe.

    `CHANGETIMEZONE(DSY, "Romance Standard Time", "GMT Standard Time")`

> [!NOTE]
> Lorsque vous utilisez la fonction `CHANGETIMEZONE` pour la conversion date/heure, sachez que toute valeur date/heure est stockée dans la base de données en tant que valeur dans le fuseau horaire Temps universel coordonné. Avant que cette valeur puisse être présentée sur les pages d’application, elle est transformée. La transformation prend en compte le fuseau horaire qui est [défini](../../fin-ops/organization-administration/tasks/set-users-preferred-time-zone.md) comme zone préférée pour l’utilisateur de l’application actuellement connecté.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
