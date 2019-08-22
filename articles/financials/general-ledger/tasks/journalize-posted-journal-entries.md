---
title: Journaliser les entrées de journal validées
description: Cette procédure indique comment journaliser les entrées de journal validées.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cbf7ee8063487303cd4c8d2b76a8b44bacc86193
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846389"
---
# <a name="journalize-posted-journal-entries"></a>Journaliser les entrées de journal validées

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

