---
title: Utiliser des configurations de mise en correspondance de modèles pour les calculs globaux au niveau de la base de données
description: Cette rubrique décrit comment créer une configuration de mise en correspondance de modèles d’états électroniques et utiliser les fonctions ER intégrées pour effectuer des calculs globaux efficaces.
author: NickSelin
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9f4ca926414e36e04e6e908a55eebeca8c24a696da4bca0c1c3a6f836373627d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745862"
---
# <a name="use-model-mapping-configurations-for-aggregate-calculations-at-the-database-level"></a>Utiliser des configurations de mise en correspondance de modèles pour les calculs globaux au niveau de la base de données

[!include [banner](../../includes/banner.md)]

Cette procédure fournit des informations sur la création d’une configuration de mise en correspondance des modèles d’états électroniques et l’utilisation des fonctions ER intégrées pour effectuer des calculs globaux efficaces. Dans cette procédure, vous créerez une configuration pour la société fictive, Litware, Inc. 

Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d’états électroniques a été affecté. Ces étapes peuvent être effectuées à l’aide d’un ensemble de données quelconque.

 Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Les états électroniques améliorent l’efficacité des calculs globaux en les effectuant au niveau de la base de données (Partie 1 : Préparer les configurations) ».

1. Accédez à Administration d’organisation > États électroniques > Configurations.
2. Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens ».
3. Dans l’arborescence, sélectionnez « Modèle de déclaration d’échanges de biens\Exemple de mise en correspondance de déclaration d’échanges de biens ».
4. Cliquez sur Concepteur.
5. Cliquez sur Concepteur.
6. Dans l’arborescence, sélectionnez « Dynamics 365 for Operations\Enregistrements de la table ».
7. Cliquez sur Ajouter racine.
    * Ajoutez une nouvelle source de données représentant les enregistrements que vous souhaitez regrouper.  
8. Dans le champ Nom, tapez « Transactions ».
    * Transactions  
9. Dans le champ Table, tapez « Déclaration d’échanges de biens ».
    * Déclaration d’échanges de biens  
10. Cliquez sur OK.
11. Dans l’arborescence, sélectionnez Fonctions\Grouper par.
    * Ce type de source de données est utilisé pour introduire une nouvelle source de données au moment de l’exécution pour regrouper les enregistrements et calculer les agrégations requises.  
12. Cliquez sur Ajouter racine.
13. Dans le champ Nom, tapez « TransactionsGroups ».
    * TransactionsGroups  
14. Cliquez sur Modifier le groupe par.
15. Dans l’arborescence, sélectionnez « Transactions ».
    * Sélectionnez la source de données ajoutée de type « Liste d’enregistrements » qui représente les enregistrements que vous souhaitez regrouper.  
16. Cliquez sur Ajouter le champ à.
17. Cliquez sur Éléments à grouper.
18. Dans l’arborescence , développer « Transactions ».
19. Dans l’arborescence, sélectionnez « Transactions\Direction ».
20. Cliquez sur Ajouter le champ à.
21. Cliquez sur Champs groupés.
    * Sélectionnez le champ pour spécifier le niveau de regroupement. En fonction de cette sélection, la source de données retourne au moment de l’exécution autant de groupes de transactions qu’il existe de codes de direction dans la table de déclaration d’échanges de biens.  
22. Dans l’arborescence, sélectionnez « Transactions\Montant de la facture (AmountMST) ».
    * Sélectionnez le champ pour spécifier la source pour le calcul d’agrégation.  
23. Cliquez sur Ajouter le champ à.
24. Cliquez sur Champs d’agrégation.
25. Dans la liste, marquez la ligne sélectionnée.
26. Dans le champ Méthode, sélectionnez « Somme ».
    * Sélectionnez le type d’agrégation.  
27. Dans le champ Nom, tapez « SumOfAmountMST ».
    * Spécifiez le nom de cette agrégation dans la source de données configurée.  
28. Cliquez sur Enregistrer.
    * Notez que le champ « Exécution à » indique que ce regroupement est exécuté au moment de l’exécution dans la base de données SQL.  
29. Fermez la page.
30. Cliquez sur OK.
31. Dans l’arborescence, développez « Totaux ».
32. Dans l’arborescence, développez « TransactionsGroups ».
33. Dans l’arborescence, développez « TransactionsGroups\aggregated ».
34. Dans l’arborescence, sélectionnez « TransactionsGroups\aggregated\SumOfAmountMST ».
35. Dans l’arborescence, sélectionnez « Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.’$AmountMSTRounded) ».
36. Cliquez sur Lier.
    * Selon ce paramètre, cette source de données calcule la somme des valeurs du champ « AmountMST » pour chaque groupe de transactions. Ce calcul d’agrégation est disponible en tant qu’élément TransactionsGroups.aggregated.TotalAmount.  
37. Dans l’arborescence, développez « TransactionsGroups ».
38. Dans l’arborescence, sélectionnez « TransactionsGroups ».
39. Cliquez sur Modifier.
40. Cliquez sur Modifier le groupe par.
41. Dans l’arborescence , développer « Transactions ».
42. Dans l’arborescence, sélectionnez « Transactions\Montant de la facture (AmountMST) ».
43. Cliquez sur Ajouter le champ à.
44. Cliquez sur Champs d’agrégation.
45. Dans la liste, marquez la ligne sélectionnée.
46. Dans le champ Méthode, sélectionnez « Max ».
47. Dans le champ Nom, tapez « MaxOfAmountMST ».
48. Cliquez sur Enregistrer.
    * Actuellement, l’exécution des sources de données GROUPBY peut être traduite au niveau de la base de données SQL avec certaines restrictions. La traduction peut être effectuée pour les sources de données de type « Liste d’enregistrements » ou les sources de données représentées comme expression à l’aide de la fonction FILTER. Elle peut également être effectuée lorsqu’une seule agrégation est configurée pour un champ unique des enregistrements de regroupement.  
    * Notez que même si plusieurs agrégations ont été configurées pour le champ AmountMST, le champ « Exécution à » indique toujours que ce regroupement est exécuté au moment de l’exécution dans la base de données SQL. En effet, une seule agrégation est liée à l’élément de modèle de données et est utilisée au moment de l’exécution pour extraire des données de cette source de données.  
49. Fermez la page.
50. Cliquez sur OK.
51. Dans l’arborescence, développez « TransactionsGroups ».
52. Dans l’arborescence, développez « TransactionsGroups\aggregated ».
53. Dans l’arborescence, sélectionnez « TransactionsGroups\aggregated\MaxOfAmountMST ».
54. Dans l’arborescence, sélectionnez « Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.’$StatisticalValueRounded’) ».
55. Cliquez sur Lier.
56. Dans l’arborescence, développez « TransactionsGroups ».
57. Dans l’arborescence, sélectionnez « TransactionsGroups ».
58. Cliquez sur Modifier.
59. Cliquez sur Modifier le groupe par.
    * Notez que le champ « Exécution à » indique que ce regroupement est exécuté au moment de l’exécution dans la mémoire, car les deux agrégations du même champ sont liées aux éléments du modèle de données.   
60. Dans la liste, cochez ou décochez toutes les lignes.
61. Cliquez sur Supprimer.
62. Cliquez sur Oui.
63. Cliquez sur Supprimer.
64. Cliquez sur Oui.
65. Cliquez sur Ajouter le champ à.
66. Cliquez sur Éléments à grouper.
67. Dans l’arborescence, développez « Commodity record(Intrastat) ».
68. Cliquez sur Enregistrer.
    * Notez que « exécution » dans le champ indique que ce regroupement est exécuté au moment de l’exécution dans la mémoire même s’il n’existe pas de regroupement défini et que la source de données sélectionnée de type « Enregistrements de table » fait référence à la même table « Déclaration d’échanges de biens ». Cela est dû au fait que la source de données contient certains champs calculés qui ne peuvent pas encore être convertis au niveau de base de données SQL.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]