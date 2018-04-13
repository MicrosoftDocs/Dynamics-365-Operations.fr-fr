--- 
title: "Journaliser les entrées de journal validées"
description: "Cette procédure indique comment journaliser les entrées de journal validées."
author: aprilolson
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 490e9a4beda43f6e32b87792b11153c3e8e322d6
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="journalize-posted-journal-entries"></a>Journaliser les entrées de journal validées

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment journaliser les entrées de journal validées. La société fictive USMF sert d'exemple dans cette procédure.

1. Validez les paramètres de journalisation sous Comptabilité > Paramétrage de la comptabilité > Paramètres de comptabilité.
2. Le champ Journal comptable étendu peut être défini sur Oui ou Non. S'il est défini sur Oui, la sortie d'état est différente.
3. Indiquez si la période peut être clôturée si le processus de journalisation n'a pas été exécuté.
    * Si cette option est définie Oui, la période ne peut pas être clôturée tant que le processus de journalisation n'a pas été terminé pour cette période.  
4. Fermez la page.
5. Accédez à Comptabilité > Tâches périodiques > Journalisation.
6. Cliquez sur Filtre.
7. Mettez en surbrillance la ligne avec les critères de filtre que vous souhaitez définir.
8. Dans le champ Critères, entrez ou sélectionnez les critères de filtre.
9. Cliquez sur OK pour fermer la page de filtre.
10. Cliquez sur OK pour démarrer le processus de journalisation.
    * Un état est généré à la fin du processus.  


