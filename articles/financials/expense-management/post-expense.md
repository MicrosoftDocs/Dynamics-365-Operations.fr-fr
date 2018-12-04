---
title: "Valider un état de dépenses"
description: "Cette rubrique explique comment valider un état de dépenses dans la comptabilité."
author: saraschi2
manager: AnnBe
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvPerDiems
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: cc3aae061038202ec4f314654d9149c31e2575bb
ms.contentlocale: fr-fr
ms.lasthandoff: 03/13/2018

---

# <a name="post-an-expense-report"></a>Valider un état de dépenses

[!include [banner](../includes/banner.md)]

Après son approbation et son transfert dans le journal des opérations diverses, un état de dépenses peut être validé dans la comptabilité. Lorsque vous validez un état des dépenses, les dépenses admissibles pour la récupération de la taxe sur la valeur ajoutée (TVA) sont identifiées. La tâche de vérification et de récupération des paiements de TVA est affectée à l'employé responsable de la vérification de l'état de dépenses.

Si les dépenses figurant sur un état de dépenses sont facturées à une société autre que celle qui emploie le collaborateur, vous devez vérifier la société pour laquelle les dépenses sont dues et la société qui les doit. Par exemple, l'employé qui a envoyé un état de dépenses travaille pour la société DAT mais a facturé une dépense à la société DIR. Dans ce cas, DAT est la société à laquelle la dépense est due, et DIR est la société qui doit la dépense. Une fois ces lignes de journal vérifiées, vous pouvez valider les lignes de dépense dans la comptabilité.

Pour valider un état de dépenses, sur la page **États de dépenses approuvés**, sélectionnez l'état de dépenses, puis, dans le volet Actions, sélectionnez **Valider**.

Vous pouvez également valider tous les états de dépenses dans la liste simultanément. Sélectionnez tous les états de dépenses, puis **Valider**.

