---
title: Créer un code intérêt avec une plage
description: Vous pouvez paramétrer les codes intérêt de sorte à calculer différents montants d'intérêt en fonction d'une plage de valeurs.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d684eedd5b40ee9775ab779c243d05cdc6e01f58
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188853"
---
# <a name="create-an-interest-code-with-a-range"></a>Créer un code intérêt avec une plage

[!include [task guide banner](../../includes/task-guide-banner.md)]

Vous pouvez paramétrer les codes intérêt de sorte à calculer différents montants d'intérêt en fonction d'une plage de valeurs. Cette procédure vous indique comment ajouter un code intérêt et ajouter une plage à celui-ci.

1. Accédez à Crédit et relances > Intérêts > Paramétrer les codes intérêt.
2. Cliquez sur Nouveau.
3. Dans le champ Code intérêt, entrez le nom du code intérêt.
4. Dans le champ Description, entrez une description du code intérêt.
5. Sélectionnez un mois.
6. Développez la section Bénéfices.
7. Développez la section Bénéfices par devise.
8. Dans le champ Compte général de validation, indiquez les valeurs souhaitées.
9. Dans le champ Intérêts par tranche, sélectionnez « Mois ».
10. Cliquez sur Ajouter.
11. Dans le champ Description, entrez une description cette devise et cette plage.
12. Cliquez sur Enregistrer.
13. Cliquez sur Plages.
14. Cliquez sur Nouveau.
15. Spécifiez 0 pour la valeur De, puis entrez le pourcentage d'intérêt par mois qui sera utilisé pour calculer les intérêts. Dans notre exemple, la valeur est 1,5.
16. Cliquez sur Nouveau.
17. Spécifiez 4 pour la valeur suivante, ce qui correspond au premier mois où vous calculerez un nouveau montant des intérêts.
18. Spécifiez le pourcentage d'intérêt par mois qui sera utilisé pour calculer les intérêts à partir du mois 4. Dans notre exemple, la valeur est 2,0.
19. Cliquez sur Nouveau.
20. Spécifiez 7 pour la valeur suivante, ce qui correspond au prochain mois où vous calculerez un nouveau montant des intérêts.
21. Spécifiez le pourcentage d'intérêt par mois qui sera utilisé pour calculer les intérêts à partir du mois 7. Dans notre exemple, la valeur est 2,5.
22. Cliquez sur Fermer pour terminer le paramétrage.

