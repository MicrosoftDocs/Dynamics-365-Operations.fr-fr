---
title: Fonction QRCODE ER
description: Cet article fournit des informations sur l’utilisation de la fonction QRCODE États électroniques (ER).
author: kfend
ms.date: 12/10/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 9de62eefb82942ccc72e81bd9bf36eed07c99dba
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287186"
---
# <a name="qrcode-er-function"></a>Fonction QRCODE ER

[!include [banner](../includes/banner.md)]

La fonction `QRCODE` renvoie une valeur de *Conteneur* qui présente l’une image de code à réponse rapide (code QR) de la chaîne spécifiée au format binaire.

## <a name="syntax"></a>Syntaxe

```vb
QRCODE (text)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur *Chaîne* qui représente le texte d’origine.

## <a name="return-values"></a>Valeurs de retour

*Conteneur*

Flux binaire résultant.

## <a name="example"></a>Exemple

Vous pouvez configurer un format d’états électroniques (ER) pour générer un document sortant dans le format Microsoft Office (classeurs Excel ou documents Word) en utilisant un modèle prédéfini. Ce modèle peut contenir un objet **Image** (classeur Excel) ou un **Contrôle du contenu de l’image** (Document Word) comme espace réservé pour une image de code QR. Vous devez ajouter au format ER configuré un élément **Cellule** qui sera utilisé pour remplir cet espace réservé. Pour spécifier quelles informations seront stockées dans un code QR, vous devez définir une liaison pour cet élément **Cellule**. Par exemple, vous pouvez configurer une telle liaison comme contenant l’expression suivante :

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

Lorsque vous exécutez le format ER configuré, la valeur de texte du champ **LabelText** de la source de données **model.ListOfShelfLabels** sera utilisée pour générer une image de code QR. Cette image remplacera un espace réservé d’image de code QR dans le modèle de document en utilisant pour générer un document sortant. Lorsque cette image du document généré est numérisée, elle renvoie le texte qui a été extrait du champ **LabelText** de la source de données **model.ListOfShelfLabels**. Pour plus d’informations, voir [Intégrer des images et des formes dans les documents que vous générez à l’aide de la gestion d’ER](electronic-reporting-embed-images-shapes.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
