---
title: ER Configurer le format pour effectuer le comptage et la synthèse (Partie 4 - Exécuter le format)
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 17989b7fa2baf14472ec19a041cb5ce7e5c0380d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544562"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4-run-format"></a>ER Configurer le format pour effectuer le comptage et la synthèse (Partie 4 : Exécuter le format)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée. Ces étapes peuvent être effectuées dans la société DEMF.

Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Configurer le format pour effectuer le comptage et la synthèse (Partie 3 : Utiliser les calculs pour générer la sortie) ».

Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a>Tester cette configuration pour la génération des états de déclaration d'échanges de biens
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Cliquez sur Configurations des états.
3. Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens ».
4. Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».
5. Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne)\Déclaration d'échanges de biens (Allemagne) avec comptage et synthèse ».
6. Dans le volet Actions, cliquez sur Configurations.
7. Cliquez sur Paramètres utilisateur.
8. Sélectionnez Oui dans le champ Paramètres d'exécution.
9. Cliquez sur OK.
10. Cliquez sur Modifier.
11. Sélectionnez Oui dans le champ Exécuter le brouillon.
12. Cliquez sur Enregistrer.
13. Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres de commerce extérieur.
14. Développez la section Génération d'états électroniques.
15. Sélectionnez la configuration « Déclaration d'échanges de biens (Allemagne) avec comptage et synthèse ».
16. Sélectionnez la configuration « Déclaration d'échanges de biens (Allemagne) avec comptage et synthèse ».
17. Cliquez sur Enregistrer.
18. Fermez la page.
19. Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d'échanges de biens.
20. Cliquez sur Résultat.
21. Cliquez sur État.
    * Exécutez le processus de génération d'états de déclaration d'échanges de biens.  
22. Dans le champ Date de début, définissez la date sur « 01-01-2000 ».
    * Définissez les dates de début et de fin de la période de déclaration qui incluent celles existantes dans les transactions du formulaire.  
23. Dans le champ Date de fin, définissez la date sur « 31-12-2022 ».
    * Définissez les dates de début et de fin de la période de déclaration qui incluent celles existantes dans les transactions du formulaire.  
24. Dans le champ Direction, sélectionnez « Arrivées ».
25. Sélectionnez Oui dans le champ Générer un fichier.
26. Cliquez sur OK.
    * Examinez la sortie créée avec les lignes de synthèse à la fin.  
27. Cliquez sur Nouveau.
28. Dans la liste, marquez la ligne sélectionnée.
29. Dans le champ Direction, sélectionnez « Répartitions ».
30. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
31. Saisissez ou sélectionnez une valeur dans le champ Marchandise.
32. Définissez le poids sur « 10 ».
33. Définissez le montant de la facture sur « 10000 »
34. Définissez le montant statistique sur « 10000 »
35. Cliquez sur Résultat.
36. Cliquez sur État.
37. Dans le champ Direction, sélectionnez « Répartitions ».
38. Cliquez sur OK.
    * Examinez la sortie créée avec les lignes de synthèse à la fin. Notez qu'elle a été modifiée par rapport à la première exécution.  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a>Exécuter cette configuration en mode débogage pour examiner les données de comptage et de synthèse collectées
1. Accédez à Administration d'organisation > États électroniques > Configurations.
2. Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens ».
3. Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».
4. Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne)\Déclaration d'échanges de biens (Allemagne) avec comptage et synthèse ».
5. Dans le volet Actions, cliquez sur Configurations.
6. Cliquez sur Paramètres utilisateur.
7. Sélectionnez Oui dans le champ Exécuter en mode débogage.
8. Cliquez sur OK.
9. Fermez la page.
10. Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d'échanges de biens.
11. Cliquez sur Résultat.
12. Cliquez sur État.
13. Cliquez sur OK.
14. Fermez la page.
15. Accédez à Administration d'organisation > États électroniques > Configurations.
16. Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens ».
17. Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».
18. Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne)\Déclaration d'échanges de biens (Allemagne) avec comptage et synthèse ».
19. Cliquez sur Journaux de débogage.
    * Notez qu'un enregistrement du journal de débogage a été créé pour le processus d'exécution de la configuration sélectionnée.  
20. Cliquez Joindre.
21. Cliquez sur Ouvrir.
    * Examinez le fichier XML créé qui contient les détails de comptage et de synthèse qui ont été collectés lors de l'exécution de la configuration sélectionnée.  

