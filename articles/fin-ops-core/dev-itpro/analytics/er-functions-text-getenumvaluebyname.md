---
title: Fonction GETENUMVALUEBYNAME ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction GETENUMVALUEBYNAME États électroniques (ER).
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
ms.openlocfilehash: 87613978c149b5d41aefc58f9896424229819626
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041169"
---
# <a name="GETENUMVALUEBYNAME">Fonction GETENUMVALUEBYNAME ER</a>

[!include [banner](../includes/banner.md)]

La fonction `GETENUMVALUEBYNAME` recherche une valeur *Enum* spécifique dans la source de données d'énumération spécifiée à l'aide du nom d'énumération spécifié en tant que valeur de *Chaîne*. Si la valeur *Enum*, la fonction la renvoie. Sinon, la fonction renvoie la valeur d'énumération **null**.

## <a name="syntax"></a>Syntaxe

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a>Arguments

`enumeration data source path` : *Énumération*

Chemin d'accès valide d'une source de données de l'un des types d'énumération suivants :

- Énumération du modèle de gestion des états électroniques
- Énumération de format ER
- Énumération Microsoft Dynamics 365 Finance

`enumeration value text` : *Chaîne*

Valeur de chaîne qui représente le nom d'une seule valeur d'énumération.

## <a name="return-values"></a>Valeurs de retour

*Enum* pouvant être null

Valeur d'énumération résultante.

## <a name="usage-notes"></a>Notes d'utilisation

Aucune exception n'est levée si aucune valeur *Enum* n'est trouvée en utilisant le nom de la valeur d'énumération spécifié en tant que valeur de *Chaîne*.

## <a name="example"></a>Exemple

Dans l'illustration suivante, l'énumération **ReportDirection** est présentée dans un modèle de données. Notez que les étiquettes sont définies pour les valeurs d'énumération.

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

Les détails suivants sont illustrés dans le graphique ci-dessous :

- La source de données **$Direction** est configurée dans un état ER. Cette source de données est configurée en fonction de l'énumération du modèle **ReportDirection**.
- L'expression `$IsArrivals` est conçue pour utiliser la source de données **$Direction** basée sur l'énumération du modèle comme paramètre de cette fonction.
- La valeur de cette expression de comparaison est **TRUE**.

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)
