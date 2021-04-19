---
title: Fonction DATETODATETIME ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction DATETODATETIME États électroniques (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: bb90c58544eeba804cd39542cc70fab3b840af80
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746961"
---
# <a name="datetodatetime-er-function"></a>Fonction DATETODATETIME ER

[!include [banner](../includes/banner.md)]

La fonction `DATETODATETIME` renvoie une valeur de *DateTime* qui est convertie d’une valeur de date donnée en une valeur de date/heure en temps universel coordonné (Heure de Greenwich, \[GMT\]).

## <a name="syntax"></a>Syntaxe

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a>Arguments

`date` : *Date*

Valeur de date qui représente la date à convertir.

## <a name="return-values"></a>Valeurs de retour

*Date et heure*

Valeur de date/heure résultante.

## <a name="example-1"></a>Exemple 1

`DATETODATETIME (CompInfo. 'getCurrentDate()')` renvoie la date de la session Microsoft Dynamics 365 Finance actuelle, le 24 décembre 2015, **12/24/2015 12:00:00 AM**. Dans cet exemple, **CompInfo** est une source de données de génération d’états électroniques de type **Finance and Operations/Table** qui fait référence à la table CompanyInfo.

## <a name="example-2"></a>Exemple 2

`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` renvoie la valeur de date/heure **11/12/2019 12:00:00 AM**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]