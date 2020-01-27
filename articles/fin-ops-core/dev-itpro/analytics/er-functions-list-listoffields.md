---
title: Fonction LISTOFFIELDS ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction LISTOFFIELDS États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 91e4658043278b9b8d73766cc0deac5d50d51a59
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916152"
---
# <a name="LISTOFFIELDS">Fonction LISTOFFIELDS ER</a>

[!include [banner](../includes/banner.md)]

La fonction `LISTOFFIELDS` renvoie une valeur *Liste des enregistrements* créée en fonction de la structure de l'argument spécifié du type *Énumération* ou *Conteneur (enregistrement)*.

## <a name="syntax-1"></a>Syntaxe 1

```
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a>Syntaxe 2

```
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a>Arguments

`path` : Référence de source de données

Chemin d'accès de référence valide d'une source de données de l'un des types de données suivants :

- Énumération du modèle
- Énumération de format
- Énumération des applications
- Conteneur (enregistrement)

`language` : *Chaîne*

Texte qui représente un code de langue.

## <a name="return-values"></a>Valeurs de retour

*Liste d'enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d'utilisation

La liste créée comprend des enregistrements avec les champs suivants :

- **Nom** (type de données *Chaîne*)
- **Étiquette** (type de données *Chaîne*)
- **Description** (type de données *Chaîne*)
- **IsTranslated** (type de données *Booléen*)

Si l'argument `path` fait référence à une source de données de type *Conteneur (enregistrement)*, pour chaque champ de l'enregistrement de conteneur référencé, un nouvel enregistrement est ajouté à la liste qui est créée. Pour chaque enregistrement créé, le champ **Nom** renvoie le nom du champ de l'enregistrement de conteneur référencé pour lequel l'enregistrement en cours a été créé.

Si l'argument `path` fait référence à une source de données de l'un des types *Énumération*, pour chaque valeur d'énumération de l'énumération référencée, un nouvel enregistrement est ajouté à la liste qui est créée. Pour chaque enregistrement créé, le champ **Nom** renvoie la valeur de l'énumération référencée pour laquelle l'enregistrement en cours a été créé, le champ **Description** renvoie la description de cette énumération et le champ **Étiquette** renvoie l'étiquette de cette énumération.

Au moment de l'exécution, lorsque la syntaxe 1 est utilisée, les champs **Étiquette** et **Description** doivent renvoyer des valeurs basées sur les paramètres de langue du format d'états électroniques (ER) en cours d'exécution :

- Si les étiquettes et les descriptions de la langue demandée sont disponibles, les champs **Étiquette** et **Description** renvoient des valeurs basées sur cette langue, et le champ **IsTranslated** renvoie **True**.
- Si les étiquettes et les descriptions de la langue demandée ne sont pas disponibles, les champs **Étiquette** et **Description** renvoient des valeurs basées sur la langue **EN-US** par défaut, et le champ **IsTranslated** renvoie **False**.

Au moment de l'exécution, lorsque la syntaxe 2 est utilisée, les champs **Étiquette** et **Description** doivent renvoyer des valeurs basées sur la langue définie comme deuxième argument de la fonction appelée :

- Si les étiquettes et les descriptions de la langue demandée sont disponibles, les champs **Étiquette** et **Description** renvoient des valeurs basées sur cette langue, et le champ **IsTranslated** renvoie **True**.
- Si les étiquettes et les descriptions de la langue demandé ne sont pas disponibles, les champs **Étiquette** et **Description** renvoient des valeurs basées sur la langue **EN-US**, et le champ **IsTranslated** renvoie **False**.

## <a name="example-1"></a>Exemple 1

Dans l'illustration suivante, une énumération est présentée dans un modèle de données ER.

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

Les détails suivants sont illustrés dans le graphique ci-dessous :

- L'énumération du modèle est insérée dans un état comme source de données.
- Une expression ER utilise l'énumération de modèle comme paramètre de la fonction `LISTOFFIELDS`.
- Une source de données du type *Liste d'enregistrements* est insérée dans un état à l'aide de l'expression ER créée.

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

L'exemple suivant montre les éléments de format ER liés à la source de données du type *Liste d'enregistrements* créée à l'aide de la fonction `LISTOFFIELDS`.

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

L'illustration suivante présente le résultat de l'exécution du format conçu.

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> Selon les paramètres de langue configurés pour les éléments de format **FILE** et **FOLDER** parents, le texte traduit pour les étiquettes et les descriptions est renseigné dans la sortie du format ER.

## <a name="example-2"></a>Exemple 2

Vous utilisez le type de source de données *Champ calculé* pour configurer les sources de données **enumType\_de** et **enumType\_deCH** pour l'énumération du modèle de données **enumType** :

- **enumType\_de** = `LISTOFFIELDS (enumType, "de")`
- **enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`

Dans ce cas, vous pouvez utiliser l'expression suivante pour obtenir l'étiquette de la valeur d'énumération en allemand suisse, si la traduction est disponible. Si la traduction suisse-allemande n'est pas disponible, l'étiquette est en allemand.

```
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)
