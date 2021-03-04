---
title: ER Utiliser les dimensions financières comme source de données (Partie 3 - Créer l’état)
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un modèle de génération d’états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a12f88f1e8b5e451bc8a5c5486d820da61bf3ad0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684785"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a>ER Utiliser les dimensions financières comme source de données (Partie 3 - Créer l’état)

[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un modèle de génération d’états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER. Ces étapes peuvent être effectuées dans n’importe quelle société.

Pour effectuer ces étapes, vous devez d’abord effectuer les étapes de la procédure « ER Utiliser les dimensions financières comme source de données (Partie 2 : mise en correspondance des modèles) ».


## <a name="design-a-report-to-present-financial-dimensions"></a>Créer un état pour présenter des dimensions financières
1. Accédez à Administration d’organisation > États électroniques > Configurations.
2. Dans l’arborescence, sélectionnez « Exemple de modèle de dimensions financières ».
3. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
4. Dans le champ Nouveau, entrez « Format basé sur l’exemple de modèle de dimensions financières pour le modèle de données ».
    * Utilisez le modèle créé à l’avance comme source de données de votre nouvel état.  
5. Dans le champ Nom, tapez « État du journal comptable ».
6. Dans le champ Définition du modèle de données, sélectionnez Entrée.
7. Cliquez sur Créer une configuration.
8. Cliquez sur Concepteur.
9. Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.
10. Dans l’arborescence , sélectionnez « XML\Élément ».
11. Dans le champ Nom, tapez « Racine ».
12. Cliquez sur OK.
13. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
14. Dans l’arborescence, sélectionnez « XML\Attribut ».
15. Dans le champ Nom, tapez « Société ».
16. Cliquez sur OK.
17. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
18. Dans l’arborescence , sélectionnez « XML\Élément ».
19. Dans le champ Nom, tapez « Journal ».
20. Cliquez sur OK.
21. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML ».
22. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
23. Dans l’arborescence, sélectionnez « XML\Attribut ».
24. Dans le champ Nom, tapez « Traitement par lots ».
25. Cliquez sur OK.
26. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
27. Dans l’arborescence , sélectionnez « XML\Élément ».
28. Dans le champ Nom, tapez « Transaction ».
29. Cliquez sur OK.
30. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML ».
31. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
32. Dans l’arborescence, sélectionnez « XML\Attribut ».
33. Dans le champ Nom, tapez « N° document ».
34. Cliquez sur OK.
35. Cliquez sur Ajouter un attribut.
36. Dans le champ Nom, tapez « Date ».
37. Cliquez sur OK.
38. Cliquez sur Ajouter un attribut.
39. Tapez « Devise » dans le champ Nom.
40. Cliquez sur OK.
41. Cliquez sur Ajouter un attribut.
42. Dans le champ Nom, tapez « Dt ».
43. Cliquez sur OK.
44. Cliquez sur Ajouter un attribut.
45. Dans le champ Nom, tapez « Ct ».
46. Cliquez sur OK.
47. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
48. Dans l’arborescence , sélectionnez « XML\Élément ».
49. Dans le champ Nom, tapez « Dimensions ».
50. Cliquez sur OK.
51. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML ».
52. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
53. Dans l’arborescence, sélectionnez « XML\Attribut ».
54. Dans le champ Nom, tapez « Code ».
55. Cliquez sur OK.
56. Cliquez sur Ajouter un attribut.
57. Dans le champ Nom, tapez « Valeur ».
58. Cliquez sur OK.
59. Cliquez sur Ajouter un attribut.
60. Dans le champ Nom, tapez « Desc ».
61. Cliquez sur OK.
![Page Concepteur d’opérations de gestion des états électroniques](../media/er-financial-dimensions-guides-format1.png)

## <a name="map-report-elements-to-data-sources"></a>Mettre en correspondance les éléments d’état avec les sources de données
1. Cliquez sur l’onglet Mise en relation.
2. Dans l’arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données ».
3. Dans l’arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements ».
4. Dans l’arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements ».
5. Dans l’arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Données de dimensions : Liste d’enregistrements ».
6. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Desc : Attribut XML ».
7. Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Données de dimensions : Liste d’enregistrements\Description : Chaîne ».
8. Cliquez sur Lier.
9. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Valeur : Attribut XML ».
10. Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Données de dimensions : Liste d’enregistrements\Code : Chaîne ».
11. Cliquez sur Lier.
12. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Code : Attribut XML ».
13. Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Données de dimensions : Liste d’enregistrements\Nom : Chaîne ».
14. Cliquez sur Lier.
15. Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Données de dimensions : Liste d’enregistrements ».
16. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML ».
17. Cliquez sur Lier.
18. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Ct : Attribut XML ».
19. Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Crédit : Réel ».
20. Cliquez sur Lier.
21. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dt : Attribut XML ».
22. Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Débit : Réel ».
23. Cliquez sur Lier.
24. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Devise : Attribut XML ».
25. Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Devise : Chaîne ».
26. Cliquez sur Lier.
27. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Date : Attribut XML ».
28. Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Date : Date ».
29. Cliquez sur Lier.
30. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\N° document : Attribut XML ».
31. Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\N° document : Chaîne ».
32. Cliquez sur Lier.
33. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML ».
34. Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements ».
35. Cliquez sur Lier.
36. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Lot : Attribut XML ».
37. Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Lot : Chaîne ».
38. Cliquez sur Lier.
39. Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML ».
40. Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements ».
41. Cliquez sur Lier.
42. Dans l’arborescence, sélectionnez « Racine : Élément XML\Société : Attribut XML ».
43. Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Société : Chaîne ».
44. Cliquez sur Lier.
45. Cliquez sur Enregistrer.
46. Fermez la page.
![Page Concepteur d’opérations de gestion des états électroniques](../media/er-financial-dimensions-guides-format2.png)



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]