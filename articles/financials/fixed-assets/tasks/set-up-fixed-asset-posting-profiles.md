--- 
title: "Paramétrage de profils de validation d'immobilisation"
description: "Ce guide de tâche va paramétrer les profils de validation d'immobilisation."
author: saraschi2
manager: AnnBe
ms.date: 02/24/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b9766d96d16429d0ce0864695a3157f54cad4054
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-fixed-asset-posting-profiles"></a>Paramétrage de profils de validation d'immobilisation

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche va paramétrer les profils de validation d'immobilisation.  Il utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.  Les exemples donnés dans le guide de tâches concernent un profil de validation de base, même s'il faut créer des profils de validation pour les besoins spécifiques de vos plans de comptes et de vos états financiers.

1. Accédez à Immobilisations > Paramétrage > Profils de validation d'immobilisation.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Profil de validation.
4. Dans le champ Description, entrez une valeur.
    * Vous devrez créer un profil de validation pour chaque type de transaction d'immobilisation que vous utiliserez lors de l'utilisation des immobilisations.  Ce guide de tâche débute par le type de transaction d'acquisition.  
5. Cliquez sur Ajouter.
6. Dans le champ Registre, entrez ou sélectionnez une valeur.
    * Le champ Regroupements vous permet de définir le profil de validation dans Tableau (un compte défini pour chaque immobilisation) ou Groupe (un compte défini pour chaque groupe d'immobilisations).  Pour ce Guide de tâche, je laisserai la valeur définie sur « Tout » pour appliquer le registre spécifié à toutes les immobilisations.  
7. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
    * Pour les acquisitions, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.    
8. Dans le champ Type de transaction, sélectionnez Ajustement d'acquisition.
    * Pour les transactions d'ajustement d'acquisition, nous utiliserons les mêmes comptes que ceux utilisés pour les transactions d'acquisition.  
9. Cliquez sur Ajouter.
10. Dans le champ Registre, entrez ou sélectionnez une valeur.
11. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
    * Pour les ajustements d'acquisition, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.    
12. Sélectionnez « Amortissement » dans le champ Type de transaction.
13. Cliquez sur Ajouter.
14. Dans le champ Registre, entrez ou sélectionnez une valeur.
15. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
16. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
17. Sélectionnez « Ajustement de l'amortissement » dans le champ Type de transaction.
    * Pour les transactions d'ajustement d'amortissement, nous utiliserons les mêmes comptes que ceux utilisés pour les transactions d'amortissement.  
18. Cliquez sur Ajouter.
19. Dans le champ Registre, entrez ou sélectionnez une valeur.
20. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
21. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
22. Sélectionnez « Cession - Vente » dans le champ Type de transaction.
23. Cliquez sur Ajouter.
24. Dans le champ Registre, entrez ou sélectionnez une valeur.
25. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
    * Pour les cessions, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.  
26. Sélectionnez « Cession - Mise au rebut » dans le champ Type de transaction.
    * Nous utiliserons les mêmes comptes pour la vente de cession et la mise au rebut.  
27. Cliquez sur Ajouter.
28. Dans le champ Registre, entrez ou sélectionnez une valeur.
29. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
    * Pour les cessions, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.  
30. Développer la section Cession.
    * Vous devez paramétrer des profils de validation de cession pour la vente et la mise au rebut.  Nous commencerons par des transactions de cession.  
31. Cliquez sur Ajouter.
32. Dans le champ Registre, entrez ou sélectionnez une valeur.
33. Sélectionnez « Valeur d'acquisition » dans le champ Valider la valeur.
    * La valeur d'acquisition prend en compte l'acquisition et les valeurs d'ajustement de l'acquisition pour toutes les années.  Vous pouvez également définir des comptes pour ces types de transactions séparément.  
    * Vous pouvez définir le processus de cession afin d'utiliser différents comptes, selon que la cession débouche sur un profit ou une perte.  Je définirai le type de prix de vente sur « Tout » pour utiliser les mêmes comptes pour tous les types de cessions.  
34. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
35. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
36. Cliquez sur Ajouter.
37. Dans le champ Registre, entrez ou sélectionnez une valeur.
    * Sélectionnez « Amortissement (exercices précédents) » dans le champ Valider la valeur.  
38. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
39. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
40. Cliquez sur Ajouter.
41. Dans le champ Registre, entrez ou sélectionnez une valeur.
42. Sélectionnez « Amortissement (cet exercice) » dans le champ Valider la valeur.
43. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
44. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
45. Cliquez sur Ajouter.
46. Dans le champ Registre, entrez ou sélectionnez une valeur.
47. Sélectionnez « Ajustements de l'amortissement (exercices précédents) » dans le champ Valider la valeur.
48. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
49. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
50. Cliquez sur Ajouter.
51. Dans le champ Registre, entrez ou sélectionnez une valeur.
52. Sélectionnez « Ajustements de l'amortissement (cet exercice) » dans le champ Valider la valeur.
53. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
54. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
55. Cliquez sur Ajouter.
56. Dans le champ Registre, entrez ou sélectionnez une valeur.
57. Sélectionnez « Valeur nette » dans le champ Valider la valeur.
58. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
59. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
60. Sélectionnez « Rebut » dans le champ Vente ou mise au rebut.
61. Cliquez sur Ajouter.
62. Dans le champ Registre, entrez ou sélectionnez une valeur.
63. Sélectionnez « Valeur d'acquisition » dans le champ Valider la valeur.
64. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
65. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
66. Cliquez sur Ajouter.
67. Dans le champ Registre, entrez ou sélectionnez une valeur.
    * Sélectionnez « Amortissement (exercices précédents) » dans le champ Valider la valeur.  
68. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
69. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
70. Cliquez sur Ajouter.
71. Dans le champ Registre, entrez ou sélectionnez une valeur.
72. Sélectionnez « Amortissement (cet exercice) » dans le champ Valider la valeur.
73. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
74. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
75. Cliquez sur Ajouter.
76. Dans le champ Registre, entrez ou sélectionnez une valeur.
77. Sélectionnez « Ajustements de l'amortissement (exercices précédents) » dans le champ Valider la valeur.
78. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
79. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
80. Cliquez sur Ajouter.
81. Dans le champ Registre, entrez ou sélectionnez une valeur.
82. Sélectionnez « Ajustements de l'amortissement (cet exercice) » dans le champ Valider la valeur.
83. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
84. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
85. Cliquez sur Ajouter.
86. Dans le champ Registre, entrez ou sélectionnez une valeur.
87. Sélectionnez « Valeur nette » dans le champ Valider la valeur.
88. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
89. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.


