---
title: Fonction DATETODATETIME ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction DATETODATETIME États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 961ccd18e70d4f9851027492366a7d9408a668c5
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042410"
---
# <a name="DATETODATETIME">Fonction DATETODATETIME ER</a>

[!include [banner](../includes/banner.md)]

La fonction `DATETODATETIME` renvoie une valeur de *DateTime* qui est convertie d'une valeur de date donnée en une valeur de date/heure en temps universel coordonné (Heure de Greenwich, \[GMT\]).

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

`DATETODATETIME (CompInfo. 'getCurrentDate()')` renvoie la date de la session Microsoft Dynamics 365 Finance actuelle, le 24 décembre 2015, **12/24/2015 12:00:00 AM**. Dans cet exemple, **CompInfo** est une source de données de génération d'états électroniques de type **Finance and Operations/Table** qui fait référence à la table CompanyInfo.

## <a name="example-2"></a>Exemple 2

`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` renvoie la valeur de date/heure **11/12/2019 12:00:00 AM**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d'heure](er-functions-category-datetime.md)
