---
title: Paramétrer la retenue à la source
description: Cette rubrique explique comment paramétrer la retenue à la source.
author: twheeloc
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10e7018c79e54841d0729636b08ad475a94d20d5
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834732"
---
# <a name="set-up-withholding-tax"></a>Paramétrer la retenue à la source

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette rubrique explique comment paramétrer la retenue à la source. La *retenue à la source* est une taxe sur les fournisseurs qui ne crée pas de transaction de taxe. La retenue à la source calculée sur les paiements des fournisseurs fait partie du passif. Par conséquent, seuls les comptes de passif ou de bilan sont utilisés pour la validation de la retenue à la source. Ce guide de tâche décrit comment paramétrer la retenue à la source.

1. Allez dans **Volet de navigation > Modules > Taxes > Taxes indirectes > Retenue à la source > Codes de retenue à la source**.
2. Sélectionnez **Nouveau**.
3. Tapez une valeur dans le champ **Code de retenue à la source**.
4. Dans le champ **Nom de retenue à la source**, entrez le nom du code retenue à la source.
5. Dans le champ **Compte principal**, sélectionnez le compte principal pour la validation de l'assujettissement de la retenue à la source.
6. Sélectionnez **Enregistrer**.
7. Sélectionnez **Valeurs** et marquez l'enregistrement souhaité dans la liste.
8. Dans le champ **Valeur**, entrez un pourcentage utilisé pour le calcul de la retenue à la source.
9. Sélectionnez **Enregistrer**.
10. Fermez la page.
11. Sélectionnez **Enregistrer**.
12. Fermez la page.
13. Allez dans **Volet de navigation > Modules > Taxes > Taxes indirectes > Retenue à la source > Groupes de retenue à la source**.
14. Sélectionnez **Nouveau**.
15. Dans le champ **Groupe de retenue à la source**, entrez l'identificateur du groupe de retenues à la source.
16. Dans le champ **Description**, entrez le nom du groupe de retenues à la source.
17. Sélectionnez le code de retenue à la source dans le champ **Code de retenue à la source**.
18. Sélectionnez **Enregistrer**.
19. Fermez la page.

