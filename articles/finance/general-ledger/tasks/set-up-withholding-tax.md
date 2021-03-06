---
title: Paramétrer la retenue à la source
description: Cette rubrique explique comment paramétrer la retenue à la source.
author: twheeloc
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 592afb7542fa44dcb1bf3f7354937d3c21fb1a87
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813466"
---
# <a name="set-up-withholding-tax"></a>Paramétrer la retenue à la source

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment paramétrer la retenue à la source. La *retenue à la source* est une taxe sur les fournisseurs qui ne crée pas de transaction de taxe. La retenue à la source calculée sur les paiements des fournisseurs fait partie du passif. Par conséquent, seuls les comptes de passif ou de bilan sont utilisés pour la validation de la retenue à la source. Ce guide de tâche décrit comment paramétrer la retenue à la source.

1. Allez dans **Volet de navigation > Modules > Taxes > Taxes indirectes > Retenue à la source > Codes de retenue à la source**.
2. Sélectionnez **Nouveau**.
3. Tapez une valeur dans le champ **Code de retenue à la source**.
4. Dans le champ **Nom de retenue à la source**, entrez le nom du code retenue à la source.
5. Dans le champ **Compte principal**, sélectionnez le compte principal pour la validation de l’assujettissement de la retenue à la source.
6. Sélectionnez **Enregistrer**.
7. Sélectionnez **Valeurs** et marquez l’enregistrement souhaité dans la liste.
8. Dans le champ **Valeur**, entrez un pourcentage utilisé pour le calcul de la retenue à la source.
9. Sélectionnez **Enregistrer**.
10. Fermez la page.
11. Sélectionnez **Enregistrer**.
12. Fermez la page.
13. Allez dans **Volet de navigation > Modules > Taxes > Taxes indirectes > Retenue à la source > Groupes de retenue à la source**.
14. Sélectionnez **Nouveau**.
15. Dans le champ **Groupe de retenue à la source**, entrez l’identificateur du groupe de retenues à la source.
16. Dans le champ **Description**, entrez le nom du groupe de retenues à la source.
17. Sélectionnez le code de retenue à la source dans le champ **Code de retenue à la source**.
18. Sélectionnez **Enregistrer**.
19. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]