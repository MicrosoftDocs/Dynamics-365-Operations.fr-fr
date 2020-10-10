---
title: Fonction GETENUMVALUEBYNAME ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction GETENUMVALUEBYNAME États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 722ea8ea233d617b0584e21e98073428f16c0801
ms.sourcegitcommit: ad5b7676fc1213316e478afcffbfaee7d813f3bb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2020
ms.locfileid: "3885225"
---
# <a name="getenumvaluebyname-er-function"></a>Fonction GETENUMVALUEBYNAME ER

[!include [banner](../includes/banner.md)]

La fonction `GETENUMVALUEBYNAME` recherche une valeur *Enum* spécifique dans la source de données d’énumération spécifiée à l’aide du nom d’énumération spécifié en tant que valeur de *Chaîne*. Si la valeur *Enum*, la fonction la renvoie. Sinon, la fonction renvoie la valeur d’énumération **null**.

## <a name="syntax"></a>Syntaxe

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a>Arguments

`enumeration data source path` : *Énumération*

Chemin d’accès valide d’une source de données de l’un des types d’énumération suivants :

- Énumération du modèle de gestion des états électroniques
- Énumération de format ER
- Énumération Microsoft Dynamics 365 Finance

`enumeration value text` : *Chaîne*

Valeur de chaîne qui représente le nom d’une seule valeur d’énumération.

## <a name="return-values"></a>Valeurs de retour

*Enum* pouvant être null

Valeur d’énumération résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Aucune exception n’est levée si aucune valeur *Enum* n’est trouvée en utilisant le nom de la valeur d’énumération spécifié en tant que valeur de *Chaîne*.

## <a name="example-1"></a>Exemple 1

Dans l’illustration suivante, l’énumération **ReportDirection** est présentée dans un modèle de données. Notez que les étiquettes sont définies pour les valeurs d’énumération.

![Valeurs disponibles pour une énumération de modèle de données](./media/ER-data-model-enumeration-values.PNG)

Les détails suivants sont illustrés dans le graphique ci-dessous :

- La source de données **$Direction** est configurée dans un état ER. Cette source de données est configurée en fonction de l’énumération du modèle **ReportDirection**.
- L’expression `$IsArrivals` est conçue pour utiliser la source de données **$Direction** basée sur l’énumération du modèle comme paramètre de cette fonction.
- La valeur de cette expression de comparaison est **TRUE**.

![Exemple d'énumération de modèle de données](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a>Exemple 2

Les fonctions `GETENUMVALUEBYNAME` et [`LISTOFFIELDS`](er-functions-list-listoffields.md) vous permettent d'extraire les valeurs et les étiquettes des énumérations prises en charge sous forme de valeurs de texte. (Les énumérations prises en charge sont les énumérations d'application, les énumérations de modèle de données et les énumérations de format.)

Dans l'illustration suivante, la source de données **TransType** est introduite dans un mappage de modèle. Cette source de données fait référence à l'énumération d'application **LedgerTransType**.

![Source de données d'un mappage de modèle faisant référence à une énumération d'application](./media/er-functions-text-getenumvaluebyname-example2-1.png)

L'illustration suivante présente la source de données **TransTypeList** configurée dans un mappage de modèle. Cette source de données est configurée en fonction de l’énumération d'application **TransType**. La fonction `LISTOFFIELDS` permet de renvoyer toutes les valeurs d'énumération sous la forme d'une liste d'enregistrements contenant des champs. De cette façon, les détails de chaque valeur d'énumération sont exposés.

> [!NOTE]
> Le champ **EnumValue** est configuré pour la source de données **TransTypeList** à l'aide de l'expression `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)`. Ce champ renvoie une valeur d'énumération pour chaque enregistrement de cette liste.

![Source de données d'un mappage de modèle qui renvoie toutes les valeurs d'énumération d'une énumération sélectionnée sous la forme d'une liste d'enregistrements](./media/er-functions-text-getenumvaluebyname-example2-2.png)

L'illustration suivante présente la source de données **VendTrans** qui est configurée dans un mappage de modèle. Cette source de données renvoie les enregistrements de transaction fournisseur à partir de la table d'application **VendTrans**. Le type comptable de chaque transaction est défini par la valeur du champ **TransType**.

> [!NOTE]
> Le champ **TransTypeTitle** est configuré pour la source de données **VendTrans** à l'aide de l'expression `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label`. Ce champ renvoie l'étiquette d'une valeur d'énumération de la transaction actuelle sous forme de texte, si cette valeur d'énumération est disponible. Sinon, il renvoie une valeur de chaîne vide.
>
> Le champ **TransTypeTitle** est lié au champ **LedgerType** d'un modèle de données qui permet d'utiliser ces informations dans chaque format d'état électronique qui utilise le modèle de données comme source de données.

![Source de données d'un mappage de modèle qui renvoie les transactions fournisseur](./media/er-functions-text-getenumvaluebyname-example2-3.png)

L'illustration suivante montre comment utiliser le [débogueur de source de données](er-debug-data-sources.md) pour tester le mappage de modèle configuré.

![Utilisation du débogueur de source de données pour tester le mappage de modèle configuré](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

Le champ **LedgerType** d'un modèle de données expose les étiquettes des types de transaction comme prévu.

Si vous prévoyez d'utiliser cette approche pour une grande quantité de données transactionnelles, vous devez tenir compte des performances d'exécution. Pour plus d'informations, consultez [Suivre l'exécution des formats d'état électronique pour résoudre les problèmes de performances](trace-execution-er-troubleshoot-perf.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de texte](er-functions-category-text.md)

[Suivre l'exécution des formats d'état électronique pour résoudre les problèmes de performances](trace-execution-er-troubleshoot-perf.md)

[Fonction LISTOFFIELDS ER](er-functions-list-listoffields.md)

[Fonction FIRSTORNULL ER](er-functions-list-firstornull.md)

[Fonction WHERE ER](er-functions-list-where.md)
