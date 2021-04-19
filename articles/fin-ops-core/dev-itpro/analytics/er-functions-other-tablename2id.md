---
title: Fonction TABLENAME2ID ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction TABLENAME2ID États électroniques (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 0f94d00d9d40830d895e906ffbaa2a236f1efc43
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746553"
---
# <a name="tablename2id-er-function"></a>Fonction TABLENAME2ID ER

[!include [banner](../includes/banner.md)]

La fonction `TABLENAME2ID` renvoie une représentation numérique de l’ID de table pour le nom de table spécifié en tant que valeur *Entier*.

## <a name="syntax"></a>Syntaxe

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur de texte qui représente un nom de table valide.

## <a name="return-values"></a>Valeurs de retour

*Entier*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d’utilisation

L’exécution de cette fonction peut avoir des résultats différents dans différentes instances de Microsoft Dynamics 365 Finance, même si le même nom de société est utilisé.

## <a name="example"></a>Exemple

`TABLENAME2ID ("Intrastat")` renvoie **1510**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d’affaires)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]