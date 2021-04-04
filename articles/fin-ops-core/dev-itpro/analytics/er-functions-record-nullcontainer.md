---
title: Fonction NULLCONTAINER ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction NULLCONTAINER États électroniques (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: d08a4a12d2b142744d3f35c6f1088ec25158c97c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563220"
---
# <a name="nullcontainer-er-function"></a>Fonction NULLCONTAINER ER

[!include [banner](../includes/banner.md)]

La fonction `NULLCONTAINER` renvoie une valeur de *Conteneur (enregistrement)* nulle avec la même structure que la liste d’enregistrements ou de l’enregistrement spécifiés.

## <a name="syntax"></a>Syntaxe

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a>Arguments

`list` : *Liste des enregistrements* ou *Conteneur (enregistrement)*

Chemin d’accès valide d’une source de données de type *Liste des enregistrements* ou *Conteneur (enregistrement)*.

## <a name="return-values"></a>Valeurs de retour

*Conteneur (enregistrement)*

Valeur de l’enregistrement résultante.

## <a name="usage-notes"></a>Notes d’utilisation

> [!NOTE] 
> Cette fonction est obsolète. Utilisez la fonction `EMPTYRECORD` à la place. Pour plus d’informations, voir [EMPTYRECORD](er-functions-record-emptyrecord.md).

## <a name="example"></a>Exemple

`NULLCONTAINER (SPLIT ("abc", 1))` renvoie un nouvel enregistrement vide ayant la même structure que la liste qui est renvoyée par la fonction `SPLIT`. Pour plus d’informations, voir [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions d’enregistrement](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]