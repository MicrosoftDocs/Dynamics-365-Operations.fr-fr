---
title: Liste des fonctions ER dans la catégorie spécifique au domaine d’affaires
description: Cette rubrique fournit des informations sur les fonction spécifiques à un domaine d’affaires prises en charge dans les États électroniques (ER).
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
ms.openlocfilehash: a3d2055be7a755e35d0e88230e19038cf2d02ccc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748013"
---
# <a name="list-of-er-functions-in-the-business-domainspecific-category"></a>Liste des fonctions ER dans la catégorie spécifique au domaine d’affaires

[!include [banner](../includes/banner.md)]

Les fonctions spécifiques au domaine d’états électroniques (ER) peuvent être utilisées pour effectuer des calculs et des demandes d’accès aux données spécifiques à la mise en œuvre de Microsoft Dynamics 365 Finance. Cette rubrique fournit un résumé de ces fonctions.

## <a name="list-of-supported-functions"></a>Liste des fonctions prises en charge

| Fonction| Description |
|---------|-------------|
| [CH_Bank_Mod_10](er-functions-other-chbankmode10.md) | Cette fonction renvoie une valeur *Chaîne* qui représente une référence de créancier en tant qu’expression MOD10, sur la base des chiffres du numéro de facture spécifié. |
| [CN_GBT_AdditionalDimensionID](er-functions-other-cngbtadditionaldimensionid.md) | Cette fonction renvoie une valeur de *Chaîne* qui représente un ID de dimension financière unique extrait de la chaîne spécifiée. La chaîne spécifiée présente toutes les dimensions sous la forme d’une liste d’ID séparés par des virgules. |
| [ConvertCurrency](er-functions-other-convertcurrency.md) | Cette fonction renvoie une valeur de *Réel* qui représente le résultat de la conversion du montant en devises spécifié de la devise source spécifiée dans la devise cible spécifiée à l’aide des paramètres de la société spécifiée à la date spécifiée. |
| [CurCredRef](er-functions-other-curcredref.md) | Cette fonction renvoie une valeur *Chaîne* qui représente une référence de créancier, sur la base des chiffres du numéro de facture spécifié. |
| [FA_Balance](er-functions-other-fabalance.md) | Cette fonction renvoie une valeur de *Conteneur (enregistrement)* constituée des données relatives au solde des immobilisations pour l’élément d’immobilisation spécifié, le code du modèle de valeur, l’année de déclaration et la date de déclaration. |
| [FA_Sum](er-functions-other-fasum.md) | Cette fonction renvoie une valeur de *Conteneur (enregistrement)* constituée des données des montants des immobilisations pour l’élément d’immobilisation spécifié, le code du modèle de valeur et la période des dates. |
| [GetCurrentCompany](er-functions-other-getcurrentcompany.md) | Cette fonction renvoie une valeur de *Chaîne* qui représente le code de l’entité juridique (société) à laquelle un utilisateur est actuellement connecté. |
| [ISOCredRef](er-functions-other-isocredref.md) | Cette fonction renvoie une valeur de *Chaîne* qui représente une référence créditeur ISO (Organisation internationale de normalisation), en fonction des chiffres et des symboles alphabétiques du numéro de facture spécifié. |
| [IsValidCharacterISO7064](er-functions-other-isvalidchariso7064.md) | Cette fonction renvoie une valeur *Booléenne* de **TRUE** si la chaîne donnée représente un numéro de compte bancaire international (IBAN) valide. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**. |
| [Mod_97](er-functions-other-mod97.md) | Cette fonction renvoie une valeur *Chaîne* qui représente une référence de créancier en tant qu’expression MOD97, sur la base des chiffres du numéro de facture spécifié. |
| [NumSeqValue](er-functions-other-numseqvalue.md) | Cette fonction renvoie une valeur de *Chaîne* qui représente la nouvelle valeur générée d’une souche de numéros, en fonction de la souche de numéros, de l’étendue et de l’ID d’étendue spécifiés. L’ID d’étendue est égal à la société fournie par le contexte sous lequel le format ER est exécuté. |
| [RoundAmount](er-functions-other-roundamount.md) | Cette fonction renvoie une valeur *Réelle* qui représente le résultat de l’arrondi du montant spécifié au nombre spécifié de décimales selon la règle d’arrondi spécifiée. |
| [TableName2ID](er-functions-other-tablename2id.md) | Cette fonction renvoie une représentation numérique de l’ID de table pour le nom de table spécifié en tant que valeur *Entier*. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des États électroniques](general-electronic-reporting.md)

[Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)

[Langage de formule dans la gestion des états électroniques](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]