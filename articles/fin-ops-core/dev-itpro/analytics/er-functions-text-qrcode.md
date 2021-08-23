---
title: Fonction QRCODE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction QRCODE États électroniques (ER).
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: e9d5bd1fee8c310053b01ababb0eaafc6d5470a62786de1f502f175e634bda64
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746609"
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