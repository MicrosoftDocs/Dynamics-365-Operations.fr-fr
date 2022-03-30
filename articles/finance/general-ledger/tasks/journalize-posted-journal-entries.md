---
title: Journaliser les entrées de journal validées
description: Cette procédure indique comment journaliser les entrées de journal validées.
author: aprilolson
ms.date: 03/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8fca167563b14c825ebe29874c6488ddfb4d9a
ms.sourcegitcommit: 06acdfbccd7bd213a2397ea7b85d104f01914437
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2022
ms.locfileid: "8400873"
---
# <a name="journalize-posted-journal-entries"></a>Journaliser les entrées de journal validées

[!include [banner](../../includes/banner.md)]

Le processus de journalisation en comptabilité permet de regrouper et de générer des rapports sur les écritures de document validées pour votre comptabilité. Sur la base des critères que vous fournissez, le traitement génère une liste de documents qui utilisent une suite de numéros unique et dont la valeur **Numéro de journal** de comptabilité comme référence.

Procédez comme suit pour journaliser les entrées de journal validées. La société fictive **USMF** sert d’exemple dans cette procédure.

1. Accédez à **Comptabilité** \> **Paramétrage de la comptabilité** \> **Paramètres de comptabilité**.
2. Dans le champ **Journal comptable étendu**, sélectionnez une valeur. Si vous sélectionnez **Oui**, la sortie d’état est différente.
3. Indiquez si la période peut être clôturée si le processus de journalisation n’a pas été exécuté. Si vous sélectionnez **Oui**, la période ne peut pas être clôturée tant que le processus de journalisation n’a pas été terminé pour cette période.
4. Fermez la page.
5. Accédez à **Comptabilité** \> **Tâches périodiques** \> **Journalisation**, et sélectionnez **Filtre**.
6. Sélectionnez la ligne pour les critères de filtre que vous souhaitez définir.
7. Dans le champ **Critères**, entrez ou sélectionnez les critères de filtre.
8. Sélectionnez **OK** pour fermer la page.
9. Sélectionnez **OK** pour démarrer le processus de journalisation. Un état est généré à la fin du processus.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
