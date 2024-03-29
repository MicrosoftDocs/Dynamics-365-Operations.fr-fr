---
title: Créer un code intérêt avec une plage
description: Vous pouvez paramétrer les codes intérêt de sorte à calculer différents montants d’intérêt en fonction d’une plage de valeurs.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d77fc88f606f4e690583fbcda79f628a35f14f6a
ms.sourcegitcommit: 6a269db08e8bb3bb3405c9f4a512091d13c80faa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119472"
---
# <a name="create-an-interest-code-with-a-range"></a>Créer un code intérêt avec une plage

[!include [banner](../../includes/banner.md)]
Vous pouvez paramétrer les codes intérêt de sorte à calculer différents montants d’intérêt en fonction d’une plage de valeurs. Cette procédure vous indique comment ajouter un code intérêt et ajouter une plage à celui-ci.

1. Accédez à **Crédit et relances > Intérêts > Paramétrer les codes intérêt**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Code intérêt**, entrez le nom du code intérêt.
4. Dans le champ **Description**, entrez une description du code intérêt.
5. Sélectionnez **Mois**.
6. Développez la section **Bénéfices**.
7. Développez la section **Bénéfices par devise**.
8. Dans le champ **Compte général de validation**, indiquez les valeurs souhaitées.
9. Dans le champ **Intérêts par tranche**, sélectionnez « Mois ».
10. Cliquez sur **Ajouter**.
11. Dans le champ **Description**, entrez une description cette devise et cette plage.
12. Cliquez sur **Enregistrer**.
13. Cliquez sur **Plages**.
14. Cliquez sur **Nouveau**.
15. Spécifiez 0 pour la **valeur De**, puis entrez le pourcentage d’intérêt par mois qui sera utilisé pour calculer les intérêts. Dans notre exemple, la valeur est 1,5.
16. Cliquez sur **Nouveau**.
17. Spécifiez 4 pour la valeur suivante, ce qui correspond au premier mois où vous calculerez un nouveau montant des intérêts.
18. Spécifiez le pourcentage d’intérêt par mois qui sera utilisé pour calculer les intérêts à partir du mois 4. Dans notre exemple, la valeur est 2,0.
19. Cliquez sur **Nouveau**.
20. Spécifiez 7 pour la valeur suivante, ce qui correspond au prochain mois où vous calculerez un nouveau montant des intérêts.
21. Spécifiez le pourcentage d’intérêt par mois qui sera utilisé pour calculer les intérêts à partir du mois 7. Dans notre exemple, la valeur est 2,5.
22. Cliquez sur **Fermer** pour terminer le paramétrage.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
