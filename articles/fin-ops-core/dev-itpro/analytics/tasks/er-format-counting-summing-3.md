---
title: ER Configurer le format pour effectuer le comptage et la synthèse (Partie 3 – Utiliser les calculs pour générer la sortie)
description: Cette rubrique décrit comment configurer un format de gestion des états électroniques pour effectuer le comptage et la somme en fonction des données de la sortie de texte déjà générée. (Partie 3)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7073539ed4c1d9d5acbb0ca84b43538d87fc8b4b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748995"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a>ER Configurer le format pour effectuer le comptage et la synthèse (Partie 3 – Utiliser les calculs pour générer la sortie)

[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un format de génération d’états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée. Ces étapes peuvent être effectuées dans n’importe quelle société.

Pour effectuer ces étapes, vous devez d’abord effectuer les étapes de la procédure « ER Configurer le format pour effectuer le comptage et la synthèse (Partie 2 : Configurer des calculs) ».

Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="configure-this-report-to-use-counting-and-summing-info"></a>Configurer cet état pour utiliser les informations de comptage et de synthèse
1. Accédez à Administration d’organisation > Espaces de travail > États électroniques.
2. Cliquez sur Configurations des états.
3. Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens ».
4. Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne) ».
5. Dans l’arborescence, sélectionnez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne)\Déclaration d’échanges de biens (Allemagne) avec comptage et synthèse ».
6. Cliquez sur Concepteur.
7. Cliquez sur l’onglet Mise en relation.
8. Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.
    * Ajoutez une nouvelle source de données pour obtenir la liste des blocs mémorisés.  
9. Dans l’arborescence, sélectionnez « Fonctions\Champ calculé ».
10. Dans le champ Nom, tapez « $BlocksList ».
    * $BlocksList  
11. Cliquez sur Modifier la formule.
12. Dans l’arborescence, sélectionnez « Fonctions de collecte des données\COLLECTEDLIST ».
13. Cliquez sur Ajouter une fonction.
14. Cliquez sur Ajouter une source de données.
15. Dans le champ Formule, entrez ’COLLECTEDLIST(’$BlockName’, ’.
    * COLLECTEDLIST(’$BlockName’,  
16. Dans le champ Formule, entrez ’COLLECTEDLIST(’$BlockName’, "*")’.
    * COLLECTEDLIST(’$BlockName’, "*")  
17. Cliquez sur Enregistrer.
    * Le modèle « * » signifie que tous les blocs sont inclus dans la liste pour cet enregistrement.  
18. Fermez la page.
19. Cliquez sur OK.
20. Cliquez sur l’onglet Format.
21. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données ».
22. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
23. Dans l’arborescence, sélectionnez « Texte\Souche ».
24. Dans le champ Nom, tapez « Totaux par bloc ».
    * Totaux par bloc  
25. Dans le champ Caractères spéciaux, sélectionnez « Nouvelle ligne – Windows (CR LF) ».
26. Cliquez sur OK.
27. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Totaux par bloc ».
28. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
29. Dans l’arborescence, sélectionnez « Texte\Chaîne ».
30. Dans le champ Nom, tapez « Code du bloc ».
    * Code du bloc  
31. Cliquez sur OK.
32. Cliquez sur Ajouter une chaîne.
33. Dans le champ Nom, tapez « Comptage des lignes ».
    * Comptage des lignes  
34. Cliquez sur OK.
35. Cliquez sur Ajouter une chaîne.
36. Dans le champ Nom, tapez « Montant total ».
    * Montant total  
37. Cliquez sur OK.
38. Cliquez sur l’onglet Mise en relation.
39. Dans l’arborescence, sélectionnez « $BlocksList ».
40. Cliquez sur Lier.
    * Créez une ligne de synthèse pour chaque bloc mémorisé.  
41. Cliquez sur l’onglet Format.
42. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Totaux par bloc\Code du bloc ».
43. Cliquez sur l’onglet Mise en relation.
44. Cliquez sur Modifier la formule.
45. Dans le champ Formule, entrez ’"ID bloc : " & ’.
    * "ID bloc : " &  
46. Dans l’arborescence, développez « $BlocksList ».
47. Dans l’arborescence, sélectionnez « $BlocksList\Valeur ».
48. Cliquez sur Ajouter une source de données.
49. Cliquez sur Enregistrer.
50. Fermez la page.
51. Cliquez sur l’onglet Format.
52. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Totaux par bloc\Comptage des lignes ».
53. Cliquez sur l’onglet Mise en relation.
54. Cliquez sur Modifier la formule.
    * Créez une sortie pour le nombre de lignes pour chaque bloc présenté dans cet état.  
55. Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc : " & ’.
    * "Nombre de lignes dans ce bloc : " &  
56. Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc : " & TEXT(’.
    * "Nombre de lignes dans ce bloc : " & TEXT(  
57. Dans l’arborescence, sélectionnez « Fonctions de collecte des données\COUNTIFS ».
58. Cliquez sur Ajouter une fonction.
59. Cliquez sur Ajouter une source de données.
60. Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’.
    * "Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’,  
61. Dans l’arborescence, développez « $BlocksList ».
62. Dans l’arborescence, sélectionnez « $BlocksList\Valeur ».
63. Cliquez sur Ajouter une source de données.
64. Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’$BlocksList’.Value, ’.
    * "Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’$BlocksList’.Value,  
65. Dans l’arborescence, sélectionnez « RecName ».
66. Cliquez sur Ajouter une source de données.
67. Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’$BlocksList’.Value, ’$RecName’, "*"))’.
    * "Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’$BlocksList’.Value, ’$RecName’, "*"))  
68. Cliquez sur Enregistrer.
69. Fermez la page.
70. Cliquez sur l’onglet Format.
71. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Totaux par bloc\Montant total ».
72. Cliquez sur l’onglet Mise en relation.
73. Cliquez sur Modifier la formule.
    * Créez une sortie qui est égale au total du montant facturé pour chaque bloc présenté dans cet état.  
74. Dans le champ Formule, entrez ’"Somme du montant facturé : " & TEXT(SUMIFS(’$InvName’, ’$BlockName’, ’$BlocksList’.Value, ’$RecName’, "*"))’.
    * "Somme du montant facturé : " & TEXT(SUMIFS(’$InvName’, ’$BlockName’, ’$BlocksList’.Value, ’$RecName’, "*"))  
75. Cliquez sur Enregistrer.
76. Fermez la page.
77. Cliquez sur Enregistrer.
78. Fermez la page.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]