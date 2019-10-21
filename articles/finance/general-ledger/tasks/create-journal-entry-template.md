---
title: Créer une entrée de journal à l'aide d'un modèle
description: Les N° document du journal validés peuvent être enregistrés comme Modèles de n° document et être appliqués dans un nouveau N° document de journal.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: babbc5ee067743d368680970556f8e5d3d8585f0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177669"
---
# <a name="create-a-journal-entry-using-template"></a>Créer une entrée de journal à l'aide d'un modèle

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les N° document du journal validés peuvent être enregistrés comme Modèles de n° document et être appliqués dans un nouveau N° document de journal. La société fictive USMF sert d'exemple dans cette procédure.

1. Allez dans le **Volet de navigation > Modules > Comptabilité > Entrées de journal > Journaux des opérations diverses**.
2. Dans le **volet Actions**, cliquez sur **Nouveau**. Cette procédure commence par la création et la validation d'un N° document de journal, mais n'importe quel N° document de journal validé précédemment peut être enregistré comme modèle.  
3. Dans le champ **Nom**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Cliquez sur **Lignes**.
7. Dans le champ **Type de compte**, tapez une valeur.
8. Tapez une valeur dans le champ **Description**.
9. Dans le champ **Débit**, tapez une valeur.
10. Cliquez sur **Nouveau**.
11. Dans le champ **Type de compte**, tapez une valeur.
12. Tapez une valeur dans le champ **Description**.
13. Dans le champ **Débit**, tapez une valeur.
14. Cliquez sur **Nouveau**.
14. Dans le champ **Compte**, spécifiez les valeurs souhaitées.
15. Tapez une valeur dans le champ **Description**.
16. Dans le champ **Crédit**, tapez une valeur pour solder le document.
17. Dans le volet **Actions**, cliquez sur **Valider**.
18. Cliquez sur **Fonctions**.
19. Cliquez sur **Enregistrer le modèle de n° document**.
20. Cette procédure suppose un type de **modèle de pourcentage**. Cliquez sur OK.
    - Pourcentage : Les montants du document sont convertis en facteurs de pourcentage, ce qui permet d'appliquer n'importe quel montant lorsque le modèle de document est sélectionné.
    - Montant : Les montants effectifs sont enregistrés et appliqués.  
21. Cliquez sur **Journaux des opérations diverses**.
22. Cliquez sur **Nouveau**.
23. Dans le champ **Nom**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
24. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
25. Cliquez sur **Lignes**.
26. Cliquez sur **Fonctions**.
27. Cliquez sur **Sélectionner le modèle de n° document**.
28. Recherchez le modèle créé précédemment. Cliquez sur **OK**. Vous devrez peut-être cliquer sur **Étape précédente**, puis sélectionner le modèle correct si d'autres modèles existent.  
29. Dans le champ **Montant**, entrez le montant à appliquer au document. Le champ **Montant** est affiché uniquement si le type du modèle de n° document est Pourcentage.  
30. Cliquez sur **OK**.

