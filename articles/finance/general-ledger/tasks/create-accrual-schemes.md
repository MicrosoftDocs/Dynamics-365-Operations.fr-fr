---
title: Créer des plans de régularisation
description: Cette rubrique explique comment créer un plan de régularisation.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e8f8cf8546187ae1c65d4966887e1c5842dff431
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175424"
---
# <a name="create-accrual-schemes"></a>Créer des plans de régularisation

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette rubrique explique comment créer un plan de régularisation. La société fictive USMF est citée en exemple dans cette tâche.

1. Allez dans **Volet de navigation > Modules > Comptabilité > Paramétrage du journal > Plans de régularisation**.
2. Sélectionnez **Nouveau**.
3. Entrez une valeur dans le champ **Identification de la régularisation**.
4. Entrez une valeur dans le champ **Description du plan de régularisation**.
5. Dans le champ **Débit**, spécifiez les valeurs souhaitées. Le compte principal défini remplacera le compte principal de débit dans la ligne de N° document de journal et il sera également utilisé pour la contrepassation des différés en fonction des transactions de régularisation des comptes.  
6. Dans le champ **Crédit**, spécifiez les valeurs souhaitées. Le compte principal défini remplacera le compte principal de crédit dans la ligne de N° document de journal et il sera également utilisé pour la contrepassation des différés en fonction des transactions de régularisation des comptes.  
7. Dans le champ **N° document**, sélectionnez la manière dont vous souhaitez que le N° document soit déterminé lorsque les transactions sont validées.
8. Dans le champ **Description**, entrez une valeur pour décrire les transactions qui seront validées.
9. Dans le champ **Fréquence**, sélectionnez la fréquence à laquelle les transactions doivent se produire.
10. Entrez un nombre dans le champ **Occurrences par période**.
11. Dans le champ **Valider les transactions**, sélectionnez à quel moment les transactions doivent être validées, comme **Mensuel**.
