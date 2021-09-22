---
title: Le nombre maximum de décimales pour l’unité de gestion des stocks est 0
description: 'Lorsque vous essayez de valider une transaction de stock ou une réservation de stock, vous recevez le message d’erreur : « Le nombre maximal de décimales pour l’unité de gestion des stocks est 0 ».'
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9dec198e2d77efd2253c80e14d15791cc37f88e1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476375"
---
# <a name="maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>Le nombre maximum de décimales pour l’unité de gestion des stocks est 0


## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de valider une transaction de stock ou une réservation de stock, vous recevez le message d’erreur suivant :

> Le nombre maximum de décimales pour l’unité de gestion des stocks est 0.

Ce problème se produit lorsque la quantité de transactions de stock est spécifiée sous la forme d’une valeur décimale inférieure au niveau de précision pris en charge par le champ. Par exemple, une quantité de *0,5* a été spécifiée pour une transaction de stock, mais seules les quantités entières sont prises en charge. Par conséquent, la valeur doit être *1* au lieu de *0,5*.

## <a name="resolution"></a>Résolution

1. Exécutez le script suivant sur votre instance de SQL Server pour arrondir les quantités dans les transactions de stock. Ce script corrigera les valeurs dans la table **inventTrans**.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Exécutez un contrôle de cohérence disponible où l’option **corriger l’erreur** est activée. Ce contrôle corrigera les valeurs dans la table **inventSum**.

> [!IMPORTANT]
> Il est vivement recommandé de modifier attentivement le script selon les besoins de votre environnement, de le tester dans un environnement de test, puis de vérifier les données résultantes avant d’exécuter le script dans un environnement de production.
