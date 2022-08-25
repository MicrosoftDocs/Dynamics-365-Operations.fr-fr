---
title: Fonction GETLABELTEXT ER
description: Cet article fournit des informations sur l’utilisation de la fonction GETLABELTEXT États électroniques (ER).
author: kfend
ms.date: 03/18/2022
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: AX 10.0.25
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: dad87548518b77f2def1cf2383a21607f45170e1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285937"
---
# <a name="getlabeltext-er-function"></a>Fonction GETLABELTEXT ER

[!include [banner](../includes/banner.md)]

La fonction `GETLABELTEXT` recherche une étiquette spécifique pour renvoyer une valeur de type *[Chaîne](er-formula-supported-data-types-primitive.md#string)* qui représente la traduction de l’étiquette spécifiée dans la langue spécifiée.

## <a name="syntax"></a>Syntaxe

```vb
GETLABELTEXT (label id, language)
```

## <a name="arguments"></a>Arguments

### <a name="label-id"></a>ID libellé

`label id` : *Chaîne* ou *ID d’étiquette*

ID valide de l’un des types d’étiquettes suivants :

- Étiquette [Vue d’ensemble des états électroniques](general-electronic-reporting.md)
- Étiquette Microsoft Dynamics 365 Finance

#### <a name="usage-notes"></a>Notes d’utilisation

Cet argument ne peut être défini que comme une constante, en utilisant l’un des modèles pris en charge suivants :

- Pour les étiquettes ER :

    - `@"GER_LABEL:<LABEL ID>"`
    - `"GER_LABEL:<LABEL ID>"`

- Pour les étiquettes Finance :

    - `@"<LABEL ID>"`
    - `"<LABEL ID>"`

> [!NOTE]
> À la conception, un message d’erreur de validation s’affiche sur la page **[Concepteur de formule](er-advanced-formula-editor.md)** si aucune étiquette ne peut être trouvée à l’aide de l’ID d’étiquette fourni.

### <a name="language"></a>Langue

`language` : *Chaîne*

Chaîne qui représente un code de langue.

#### <a name="usage-notes"></a>Notes d’utilisation

Cet argument peut être défini soit comme une constante de texte, soit comme le chemin d’un champ de source de données qui renvoie une valeur *Chaîne*.

> [!NOTE]
> Au moment de la conception, un message d’erreur de validation s’affiche si aucun code de langue ne peut être trouvé en utilisant l’argument `language` lorsqu’il a été défini comme une constante de texte.
>
> Lors de l’exécution, la traduction de la langue du système `EN-US` est renvoyée pour une étiquette spécifiée si aucun code de langue n’a été trouvé à l’aide de l’argument `language` fourni.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example-1-system-label"></a><a name=example-1></a>Exemple 1 : étiquette système

Les expressions `GETLABELTEXT (@"SYS70894", "en-us")` et `GETLABELTEXT ("SYS70894", "en-us")` renvoient la traduction anglaise « Nothing to print » (Rien à imprimer) pour l’étiquette d’application `@SYS70894`.

## <a name="example-2-er-label"></a><a name=example-2></a>Exemple 2 : étiquette de gestion des états électroniques

Vous commencez à modifier une [configuration](general-electronic-reporting.md#Configuration) de gestion des états électroniques [issue](er-quick-start2-customize-report.md#DeriveProvidedFormat) de la configuration **Transfert de crédits ISO20022 (DE)**, entrez une nouvelle source de données de type *[Champ calculé](er-calculated-field-ds-performance.md)* et configurez l’expression `GETLABELTEXT(@"GER_LABEL:VendorName", "de")` pour cette source de données. Dans ce cas, lors de l’exécution, la source de données renvoie la traduction allemande « Kreditorenname » (Nom du créditeur) pour l’étiquette de gestion des états électorniques `@GER_LABEL:VendorName` initialement configurée dans la configuration de base de gestion des états électroniques **Transfert de crédits ISO20022 (DE)**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de texte](er-functions-category-text.md)

[Concevoir des états multilingues dans les états électroniques](er-design-multilingual-reports.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
