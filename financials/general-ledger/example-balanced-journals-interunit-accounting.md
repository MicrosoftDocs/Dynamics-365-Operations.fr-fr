---
title: "Journaux équilibrés pour la comptabilité interunités"
description: "Cet article décrit la manière dont un journal est automatiquement équilibré lorsqu&quot;une dimension financière d&quot;équilibrage est activée dans la page de comptabilité."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0909b64a77024d551af0dad2de985887cf6ff06d
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="balanced-journals-for-interunit-accounting"></a>Journaux équilibrés pour la comptabilité interunités

[!include[banner](../includes/banner.md)]


Cet article décrit la manière dont un journal est automatiquement équilibré lorsqu'une dimension financière d'équilibrage est activée dans la page de comptabilité. 

Si les écritures de compte ne sont pas équilibrées au niveau des valeurs de dimension financière, des écritures de compte supplémentaires sont créées automatiquement pour équilibrer le journal. Ces écritures de compte utilisent les types de validation **Interunités - débit** et**Interunités - crédit** dans la page **Comptes pour transactions automatiques** pour déterminer le compte principal. Par exemple, Agence, qui est le deuxième segment du compte général, est sélectionné comme dimension financière d'équilibrage, et les écritures comptables suivantes sont sur le point d'être créées.

|                      |           |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100.00 DR |
| 6100 – NY – OU\_249  | 100.00 DR |
| 2100 – MSP – OU\_256 | 200.00 CR |

Dans ce cas, les soldes suivants sont déterminés :

-   Pour la branche MSP = 100.00 CR
-   Pour la branche NY = 100.00 DR

Par conséquent, les écritures comptables suivantes sont créées automatiquement pour équilibrer le journal au niveau des valeurs de dimension financière.

|                                   |           |
|-----------------------------------|-----------|
| (Débit interunités) – MSP – OU\_256 | 100.00 DR |
| (Crédit interunités) – NY – OU\_249 | 100.00 CR |






