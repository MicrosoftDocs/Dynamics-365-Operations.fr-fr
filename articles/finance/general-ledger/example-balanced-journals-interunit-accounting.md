---
title: Journaux équilibrés pour la comptabilité interunités
description: Cet article décrit la manière dont un journal est automatiquement équilibré lorsqu’une dimension financière d’équilibrage est activée dans la page de comptabilité.
author: ShylaThompson
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5a926adcc631ec286f37796713466eb0144494c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818390"
---
# <a name="balanced-journals-for-interunit-accounting"></a>Journaux équilibrés pour la comptabilité interunités

[!include [banner](../includes/banner.md)]

Cet article décrit la manière dont un journal est automatiquement équilibré lorsqu’une dimension financière d’équilibrage est activée dans la page de comptabilité. 

Si les écritures de compte ne sont pas équilibrées au niveau des valeurs de dimension financière, des écritures de compte supplémentaires sont créées automatiquement pour équilibrer le journal. Ces écritures de compte utilisent les types de validation **Interunités – débit** et **Interunités – crédit** dans la page **Comptes pour transactions automatiques** pour déterminer le compte principal. Par exemple, Unité commerciale, qui est le deuxième segment du compte général, est sélectionné comme dimension financière d’équilibrage, et les écritures comptables suivantes sont sur le point d’être créées.

| &nbsp;               | &nbsp;    |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100.00 DR |
| 6100 – NY – OU\_249  | 100.00 DR |
| 2100 – MSP – OU\_256 | 200.00 CR |

Dans ce cas, les soldes suivants sont déterminés :

-   Pour l’unité commerciale MSP = 100,00 CR
-   Pour l’unité commerciale NY = 100,00 DR

Par conséquent, les écritures comptables suivantes sont créées automatiquement pour équilibrer le journal au niveau des valeurs de dimension financière.

| &nbsp;                            | &nbsp;    |
|-----------------------------------|-----------|
| (Débit interunités) – MSP – OU\_256 | 100.00 DR |
| (Crédit interunités) – NY – OU\_249 | 100.00 CR |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]