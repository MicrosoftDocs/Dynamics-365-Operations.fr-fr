---
title: États de dépenses et approbateurs multiples
description: Cette rubrique fournit des informations sur les états de dépenses qui nécessitent l'approbation de plusieurs personnes.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d83a473e2e894856c12b36b4d005c6cb06b765a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177721"
---
# <a name="expense-reports-and-multiple-approvers"></a>États de dépenses et approbateurs multiples

[!include [banner](../includes/banner.md)]

En fonction des stratégies d'approbation des dépenses de votre organisation, il se peut que plusieurs personnes doivent approuver un état de dépenses envoyé par un employé. Lorsque vous paramétrez le processus de workflow pour l'approbation des états de dépenses, vous pouvez ajouter des éléments de workflow qui incluent des tâches ou des étapes pour un ou plusieurs approbateurs des états de dépenses. Par exemple, vous pouvez exiger que tous les états de dépenses soient approuvés d'abord par le responsable de l'employé ayant soumis l'état, puis par le coordinateur des Achats.

Si vous décidez d'exiger plusieurs approbateurs des états de dépenses, vous pouvez ajouter des éléments de workflow de l'une des manières suivantes :

- Ajoutez un seul élément d'approbation qui contient une étape unique. Par exemple, l'étape peut exiger qu'un état de dépenses soit affecté à un groupe d'utilisateurs et qu'il soit approuvé par 50 % des membres du groupe d'utilisateurs.
- Ajoutez un seul élément d'approbation qui contient plusieurs étapes. Par exemple, l'élément d'approbation peut comporter les étapes suivantes :

    1. Le responsable de l'employé qui a soumis l'état de dépenses l'approuve.
    2. Le commis aux Achats vérifie les réceptions et les éléments de l'état de dépenses.
    3. Le propriétaire du budget approuve l'état de dépenses.

- Ajoutez plusieurs éléments d'approbation, chacun contenant une étape. Par exemple, vous pouvez ajouter un élément d'approbation distinct pour chacune des étapes suivantes :

    1. Le responsable de l'employé approuve l'état de dépenses.
    2. Le propriétaire du budget approuve l'état de dépenses.
