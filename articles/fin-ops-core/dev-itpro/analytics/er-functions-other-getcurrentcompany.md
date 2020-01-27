---
title: Fonction GETCURRENTCOMPANY ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction GETCURRENTCOMPANY États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: a0b4c93a4705cd0e382b9b6c7af1d199beeceabe
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915991"
---
# <a name="GETCURRENTCOMPANY">Fonction GETCURRENTCOMPANY ER</a>

[!include [banner](../includes/banner.md)]

La fonction `GETCURRENTCOMPANY` renvoie une valeur de *Chaîne* qui représente le code de l'entité juridique (société) à laquelle un utilisateur est actuellement connecté.

## <a name="syntax"></a>Syntaxe

```
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example"></a>Exemple

`GETCURRENTCOMPANY ()` renvoie **USMF** pour un utilisateur connecté à la société **Contoso Entertainment System USA**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d'affaires)](er-functions-category-other.md)
