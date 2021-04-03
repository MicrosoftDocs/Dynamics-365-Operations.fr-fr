---
title: ER Configurer le format pour effectuer le comptage et la synthèse (Partie 2 - Configurer les calculs)
description: Cette rubrique décrit comment configurer un format de gestion des états électroniques pour effectuer le comptage et la somme en fonction des données de la sortie de texte déjà générée. (Partie 2)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d6eb3d686e8f60de51001deffb4c2460c181a4ab
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565163"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-2---configure-computations"></a>ER Configurer le format pour effectuer le comptage et la synthèse (Partie 2 - Configurer les calculs)

[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un format de génération d’états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée. Ces étapes peuvent être effectuées dans n’importe quelle société.

Pour effectuer ces étapes, vous devez d’abord effectuer les étapes de la procédure « ER Configurer le format pour effectuer le comptage et la synthèse (Partie 1 : Créer un format) ».

Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a>Créer une configuration de format pour ajouter les détails de comptage et de synthèse
1. Accédez à Administration d’organisation > Espaces de travail > États électroniques.
2. Cliquez sur Configurations des états.
3. Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens ».
4. Dans l’arborescence, sélectionnez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne) ».
    * Supposons que vous deviez personnaliser le format fourni par Microsoft en ajoutant des lignes avec des détails récapitulatifs à la fin de l’état de déclaration d’échanges de biens. Pour ce faire, vous devez dériver notre propre instance de la configuration de déclaration d’échanges de biens de l’instance de Microsoft pour apporter des modifications.  
5. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
6. Dans le champ Nouveau, entrez « Provenant du nom : Déclaration d’échanges de biens (Allemagne), Microsoft ».
7. Dans le champ Nom, tapez « Déclaration d’échanges de biens (Allemagne) avec comptage et synthèse ».
8. Cliquez sur Créer une configuration.

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a>Configurer cet état pour effectuer le comptage et la synthèse en fonction des détails de la sortie
1. Cliquez sur Concepteur.
2. Sélectionnez Oui dans le champ Collecter les détails sur les sorties.
    * Cet indicateur active au moment de l’exécution le processus de collecte des détails de sortie pour générer le fichier de déclaration d’échanges de biens.  
    * Vous devez effectuer le comptage pour différentes directions de déclaration d’échanges de biens. Par conséquent, ajoutez une énumération de modèle dédiée à la liste des sources de données de cette configuration de format.  
3. Cliquez sur l’onglet Mise en relation.
4. Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.
5. Dans l’arborescence, sélectionnez « Modèle de données\Énumération ».
6. Dans le champ Nom, tapez « Direction ».
7. Dans le champ Énumération du modèle, entrez ou sélectionnez une valeur.
    * Sélectionnez la valeur Direction.  
8. Cliquez sur OK.
9. Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.
10. Dans l’arborescence, sélectionnez « Fonctions\Champ calculé ».
11. Dans le champ Nom, tapez « $BlockName ».
12. Cliquez sur Modifier la formule.
13. Dans le champ Formule, entrez « bloc ».
14. Cliquez sur Enregistrer.
15. Fermez la page.
16. Cliquez sur OK.
17. Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.
18. Dans l’arborescence, sélectionnez « Fonctions\Champ calculé ».
19. Dans le champ Nom, tapez « $RecName ».
20. Cliquez sur Modifier la formule.
21. Dans le champ Formule, entrez « enregistrement ».
22. Cliquez sur Enregistrer.
23. Fermez la page.
24. Cliquez sur OK.
25. Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.
26. Dans l’arborescence, sélectionnez « Fonctions\Champ calculé ».
27. Dans le champ Nom, tapez « $InvName ».
28. Cliquez sur Modifier la formule.
29. Dans le champ Formule, entrez « InvoicedAmountEUR ».
30. Cliquez sur Enregistrer.
31. Fermez la page.
32. Cliquez sur OK.
33. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données ».
34. Cliquez sur le bouton Modifier pour le champ « Nom de clé de données collectées »
35. Cliquez sur Ajouter une source de données.
    * $BlockName  
36. Cliquez sur Enregistrer.
37. Fermez la page.
38. Cliquez sur le bouton Modifier pour le champ Valeur de clé de données collectées.
39. Dans le champ Formule, entrez « IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export") ».
    * IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")  
40. Cliquez sur Enregistrer.
41. Fermez la page.
    * Dénombrez les lignes de cette séquence. Les résultats sont utilisés avec le nom « bloc » séparément pour différentes directions. La valeur « Importer » est utilisée pour les transactions de déclaration d’échanges de biens à l’arrivée. La valeur « Exporter » est utilisée pour les transactions de déclaration d’échanges de biens à l’expédition. Considérez cela comme une feuille de calcul Excel virtuelle. À chaque transaction correspond une ligne dont la première colonne « bloc » est remplie avec les valeurs « Importer » et « Exporter » en conséquence.  
42. Dans l’arborescence, développez « Déclaration d’échanges de biens\Données : Souche ».
43. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données : Souche\Arrivées ? ».
44. Cliquez sur le bouton Modifier pour le champ « Nom de clé de données collectées ».
    * Dénombrez les lignes de cette séquence. Les résultats sont mémorisés à l’aide du nom « enregistrement ».  
45. Dans l’arborescence, sélectionnez « RecName ».
46. Cliquez sur Ajouter une source de données.
47. Cliquez sur Enregistrer.
48. Fermez la page.
49. Cliquez sur le bouton Modifier pour le champ « Valeur de clé de données collectées ».
50. Dans le champ Formule, entrez « Intrastat.CommodityRecord.CommodityCode ».
51. Cliquez sur Enregistrer.
52. Fermez la page.
    * Dénombrez les lignes de cette séquence. Les résultats sont utilisés avec le nom « enregistrement » séparément pour différents codes marchandise. Considérez cela comme une feuille de calcul Excel virtuelle. À chaque transaction correspond une ligne dont la première colonne « bloc » est remplie avec les valeurs « Importer » et « Exporter » en conséquence et le second bloc « enregistrement » est rempli avec la valeur du code marchandise.  
53. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données : Souche\Répartitions ? ».
54. Cliquez sur le bouton Modifier pour le champ « Nom de clé de données collectées »
55. Dans l’arborescence, sélectionnez « RecName ».
56. Cliquez sur Ajouter une source de données.
57. Cliquez sur Enregistrer.
58. Fermez la page.
59. Cliquez sur le bouton Modifier pour le champ « Valeur de clé de données collectées ».
60. Dans le champ Formule, entrez « Intrastat.CommodityRecord.CommodityCode ».
61. Cliquez sur Enregistrer.
62. Fermez la page.
63. Dans l’arborescence, développez « Déclaration d’échanges de biens\Données : Souche\Répartitions : Souche ? ».
64. Dans l’arborescence, développez « Déclaration d’échanges de biens\Données : Souche\Répartitions : Souche ?\Enregistrement = Intrastat.CommodityRecord ».
65. Cliquez sur l’onglet Format.
66. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Répartitions\Enregistrement\Montant de la facture EUR ».
67. Cliquez sur l’onglet Mise en relation.
68. Cliquez sur le bouton Modifier pour le champ « Nom de clé de données collectées ».
69. Dans l’arborescence, sélectionnez « $InvName ».
70. Cliquez sur Ajouter une source de données.
71. Cliquez sur Enregistrer.
72. Fermez la page.
    * Récapitulez les valeurs du montant facturé pour les lignes de cette séquence. Les résultats sont utilisés avec le nom « InvoicedAmountEUR » séparément pour différentes directions de déclaration d’échanges de biens et différents codes marchandise. Considérez cela comme une création virtuelle dans une feuille de calcul Excel. À chaque transaction correspond une ligne dont la première colonne « bloc » est remplie avec les valeurs « Importer » et « Exporter » en conséquence. Le second bloc « enregistrement » est rempli avec la valeur du code marchandise, et la troisième colonne « InvoicedAmountEUR » est remplie avec la valeur du montant de la facture.  
73. Dans l’arborescence, développez « Déclaration d’échanges de biens\Données\Arrivées ? ».
74. Dans l’arborescence, développez « Déclaration d’échanges de biens\Données\Arrivées ?\Enregistrement = Intrastat.CommodityRecord ».
75. Cliquez sur l’onglet Format.
76. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Arrivées\Enregistrement\Montant de la facture EUR ».
77. Cliquez sur l’onglet Mise en relation.
78. Cliquez sur le bouton Modifier pour le champ « Nom de clé de données collectées ».
79. Dans l’arborescence, sélectionnez « $InvName ».
80. Cliquez sur Ajouter une source de données.
81. Cliquez sur Enregistrer.
82. Fermez la page.
83. Cliquez sur Enregistrer.
84. Fermez la page.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]