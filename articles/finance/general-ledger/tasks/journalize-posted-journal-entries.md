---
title: Journaliser les entrées de journal validées
description: Cette procédure indique comment journaliser les entrées de journal validées.
author: aprilolson
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5028db1db2359a54d565fc299c9a3353a4cf8297
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826152"
---
# <a name="journalize-posted-journal-entries"></a>Journaliser les entrées de journal validées

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment journaliser les entrées de journal validées. La société fictive USMF sert d’exemple dans cette procédure.

1. Dans le **Volet de navigation**, accédez à **Modules > Comptabilité > Paramétrage de la comptabilité > Paramètres de comptabilité**.
2. Le champ **Journal comptable étendu** peut être défini sur Oui ou Non. S’il est défini sur Oui, la sortie d’état est différente.
3. Indiquez si la période peut être clôturée si le processus de journalisation n’a pas été exécuté. Si cette option est définie Oui, la période ne peut pas être clôturée tant que le processus de journalisation n’a pas été terminé pour cette période.  
4. Fermez la page.
5. Dans le **Volet de navigation**, accédez à **Modules > Comptabilité > Tâches périodiques > Journalisation**.
6. Cliquez sur **Filtre**.
7. Mettez en surbrillance la ligne avec les critères de filtre que vous souhaitez définir.
8. Dans le champ **Critères**, entrez ou sélectionnez les critères de filtre.
9. Cliquez sur **OK** pour fermer la page de filtre.
10. Cliquez sur **OK** pour démarrer le processus de journalisation. Un état est généré à la fin du processus.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]