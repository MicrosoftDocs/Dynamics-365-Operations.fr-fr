---
title: ER Utiliser les dimensions financières comme source de données (Partie 1 - Créer un modèle de données)
description: Les étapes suivantes expliquent comment un administrateur système ou un développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b951c9074c68a9f7592c17e0688498880397b223
ms.sourcegitcommit: d9125c20b21459076e4fd92fd9ebfe2e53a0431b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2020
ms.locfileid: "3406541"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a>ER Utiliser les dimensions financières comme source de données (Partie 1 - Créer un modèle de données)

[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un administrateur système ou un développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER. Ces étapes peuvent être effectuées dans n'importe quelle société.

Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».


## <a name="create-a-new-data-model"></a>Créer un modèle de données
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Assurez-vous que le fournisseur « Litware, Inc. » est disponible et marqué comme actif.  
2. Cliquez sur Configurations des états.
3. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
4. Dans le champ Nom, tapez « Exemple de modèle de dimensions financières ».
5. Cliquez sur Créer une configuration.
6. Cliquez sur Concepteur.
7. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
8. Dans le champ Nom, tapez « Entrée ».
9. Cliquez sur Ajouter.
10. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
11. Dans le champ Nom, tapez « Société ».
12. Cliquez sur Ajouter.
    * Nous ajouterons une nouvelle liste d'enregistrements à notre modèle. Cette liste exposera (pour les états ER utilisant ce modèle comme source de données) les paramètres des dimensions financières sélectionnées. Chaque dimension financière sera présentée dans cette liste en tant qu'enregistrement avec les champs appropriés représentant les paramètres de la dimension.  
13. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
14. Dans le champ Nom, tapez « Paramètre de dimensions ».
15. Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.
16. Cliquez sur Ajouter.
17. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
18. Dans le champ Nom, tapez « Code ».
19. Sélectionnez « Chaîne » dans le champ Type d'article.
20. Cliquez sur Ajouter.
21. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
22. Tapez « Nom » dans le champ Nom.
23. Cliquez sur Ajouter.
24. Dans l'arborescence, sélectionnez « Entrée ».
25. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
26. Dans le champ Nom, tapez « Journal ».
27. Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.
28. Cliquez sur Ajouter.
29. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
30. Dans le champ Nom, tapez « Traitement par lots ».
31. Sélectionnez « Chaîne » dans le champ Type d'article.
32. Cliquez sur Ajouter.
33. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
34. Dans le champ Nom, tapez « Transaction ».
35. Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.
36. Cliquez sur Ajouter.
37. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
38. Dans le champ Nom, tapez « Date ».
39. Sélectionnez « Date » dans le champ Type d'article.
40. Cliquez sur Ajouter.
41. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
42. Dans le champ Nom, tapez « Débit ».
43. Sélectionnez « Réel » dans le champ Type d'article.
44. Cliquez sur Ajouter.
45. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
46. Dans le champ Nom, tapez « Crédit ».
47. Cliquez sur Ajouter.
48. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
49. Tapez « Devise » dans le champ Nom.
50. Sélectionnez « Chaîne » dans le champ Type d'article.
51. Cliquez sur Ajouter.
52. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
53. Dans le champ Nom, tapez « N° document ».
54. Cliquez sur Ajouter.
55. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
56. Dans le champ Nom, tapez « Données de dimensions ».
57. Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.
58. Cliquez sur Ajouter.
    * Nous avons ajouté une nouvelle liste d'enregistrements à notre modèle. Cette liste exposera (pour les états ER utilisant ce modèle comme source de données) les valeurs des dimensions financières sélectionnées. Chaque dimension financière sera présentée dans cette liste en tant qu'enregistrement avec les champs appropriés représentant les valeurs de la dimension. Le nom de la dimension sera également présenté dans cet enregistrement en tant que champ à utiliser, si nécessaire, à des fins de sélection.  
59. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
60. Dans le champ Nom, tapez « Code ».
61. Sélectionnez « Chaîne » dans le champ Type d'article.
62. Cliquez sur Ajouter.
63. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
64. Tapez « Description » dans le champ Nom.
65. Cliquez sur Ajouter.
66. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
67. Tapez « Nom » dans le champ Nom.
68. Cliquez sur Ajouter.
69. Cliquez sur Enregistrer.
70. Fermez la page.

![Page du concepteur des modèles de gestion des états électroniques](../media/er-financial-dimensions-guides-data-model.png)

