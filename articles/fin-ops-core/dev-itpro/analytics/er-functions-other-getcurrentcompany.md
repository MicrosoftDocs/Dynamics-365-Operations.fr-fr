---
title: Fonction GETCURRENTCOMPANY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction GETCURRENTCOMPANY États électroniques (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 87bef4aa11c01b42af19f7dc20ca8731b9fb4111
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752827"
---
# <a name="getcurrentcompany-er-function"></a>Fonction GETCURRENTCOMPANY ER

[!include [banner](../includes/banner.md)]

La fonction `GETCURRENTCOMPANY` renvoie une valeur de *Chaîne* qui représente le code de l’entité juridique (société) à laquelle un utilisateur est actuellement connecté.

## <a name="syntax"></a>Syntaxe

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example"></a>Exemple

`GETCURRENTCOMPANY ()` renvoie **USMF** pour un utilisateur connecté à la société **Contoso Entertainment System USA**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d’affaires)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]