--- 
title: "Créer et traiter une conformité"
description: "Utilisez cette procédure pour effectuer la gestion de non-conformité, en fonction d'un ordre de qualité existant."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 4082caf2cc8393345d4f79a991f2cf205b06b142
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-process-a-conformance"></a>Créer et traiter une conformité

[!include[task guide banner](../../includes/task-guide-banner.md)]

Utilisez cette procédure pour effectuer la gestion de non-conformité, en fonction d'un ordre de qualité existant. Vous pouvez exécuter cet enregistrement de la société de démonstration USMF et utiliser les valeurs suggérées. Généralement, cette procédure est réalisée par le commis à la qualité.  Comme préalable, exécutez l'enregistrement de la tâche « Inspecter la qualité des marchandises ». Pour traiter l'approbation d'une non-conformité, l'utilisateur qui exécute l'enregistrement de la tâche doit spécifier une valeur « Nom » affectée sur la page Utilisateurs. Pour utiliser les notes de document, l'utilisateur doit également avoir activé la gestion des documents dans les options d'utilisateur. 


## <a name="select-a-quality-order"></a>Sélectionnez un ordre de qualité.
1. Accédez à Ordres de qualité.
2. Dans la liste, marquez la ligne sélectionnée.
    * Sélectionnez l'ordre de qualité créé à partir de l'enregistrement de la tâche « Inspecter la qualité des marchandises ».  

## <a name="create-a-nonconformance"></a>Créer une non-conformité
1. Cliquez sur Recherches.
2. Cliquez sur Non-conformités.
3. Cliquez sur Nouveau.
4. Dans le champ Type de problème, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionnez le problème qui a été indiqué lors du processus d'inspection.  
5. Dans le champ Type de problème, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Cliquez sur OK.

## <a name="approvereject-a-nonconformance"></a>Approuver/rejeter une non-conformité
1. Cliquez sur Fonctions.
2. Cliquez sur Approuver la non-conformité.
    * Pour cet exemple, approuvez la non-conformité. Les non-conformités approuvées peuvent être associées à des opérations associées au travail d'enregistrement qui est exécuté dans le cadre de la gestion de la non-conformité et, comme dans cet enregistrement de tâche, le traitement de la gestion des corrections.  
3. Cliquez sur Oui.

## <a name="create-a-correction-action"></a>Créer une action de correction
1. Cliquez sur Corrections.
2. Cliquez sur Nouveau.
3. Dans la liste, marquez la ligne sélectionnée.
4. Dans le champ Numéro personnel, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Cliquez sur Sélectionner.
7. Cliquez Joindre.
    * Créez une remarque sur la correction. Pour cet exemple, l'action consiste à contacter le fournisseur pour présenter l'incident de non-conformité.  
8. Cliquez sur Nouveau.
9. Cliquez sur Remarque.
    * Notez que selon le paramétrage d'état, différents types de documents peuvent être imprimés sur les états associés à la gestion de non-conformité.  
10. Dans le champ Description, entrez une valeur.
11. Fermez la page.

## <a name="maintain-a-correction"></a>Maintenir une correction
1. Cliquez sur Marquer comme terminé.
2. Cliquez sur OK.
3. Fermez la page.

## <a name="close-a-nonconformance"></a>Clôturer une non-conformité
1. Cliquez sur Fonctions.
2. Cliquez sur Clôturer la non-conformité.
3. Cliquez sur Oui.
4. Fermez la page.
5. Fermez la page.


