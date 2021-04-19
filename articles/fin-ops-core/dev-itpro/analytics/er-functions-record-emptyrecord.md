---
title: Fonction EMPTYRECORD ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction EMPTYRECORD États électroniques (ER).
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
ms.openlocfilehash: e614c06b4cfad628bbd8a966719ed994ce05b792
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746529"
---
# <a name="emptyrecord-er-function"></a>Fonction EMPTYRECORD ER

[!include [banner](../includes/banner.md)]

La fonction `EMPTYRECORD` renvoie une valeur de *Conteneur (enregistrement)* nulle avec la même structure que la liste d’enregistrements ou de l’enregistrement spécifiés.

## <a name="syntax"></a>Syntaxe

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a>Arguments

`list` : *Liste des enregistrements* ou *Conteneur (enregistrement)*

Chemin d’accès valide d’une source de données de type *Liste des enregistrements* ou *Conteneur (enregistrement)*.

## <a name="return-values"></a>Valeurs de retour

*Conteneur (enregistrement)*

Valeur de l’enregistrement résultante.

## <a name="usage-notes"></a>Notes d’utilisation

> [!NOTE] 
> Un enregistrement null est un enregistrement où tous les champs ont une valeur vide. Une valeur vide correspond à **0** (zéro) pour les nombres, à une chaîne vide pour les chaînes, etc.

## <a name="example"></a>Exemple

`EMPTYRECORD (SPLIT ("abc", 1))` renvoie un nouvel enregistrement vide ayant la même structure que la liste qui est renvoyée par la fonction `SPLIT`. Pour plus d’informations, voir [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions d’enregistrement](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]