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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 450bb7fdcc866f45c2fd3357a5ee25e6c6f929c1
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="journalize-posted-journal-entries"></a>Journaliser les entrées de journal validées

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


