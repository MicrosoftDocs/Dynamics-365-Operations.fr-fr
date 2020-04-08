---
title: Paramétrage de profils de validation d'immobilisation
description: Ce guide de tâche va paramétrer les profils de validation d'immobilisation.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 07961d8613b6b5e0e1c5dc6a91b554305dcb17f5
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138159"
---
# <a name="set-up-fixed-asset-posting-profiles"></a>Paramétrage de profils de validation d'immobilisation

[!include [banner](../../includes/banner.md)]

Ce guide de tâche va paramétrer les profils de validation d'immobilisation.  Il utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.  Les exemples donnés dans le guide de tâches concernent un profil de validation de base, même s'il faut créer des profils de validation pour les besoins spécifiques de vos plans de comptes et de vos états financiers.

1. Dans le volet de navigation, accédez à **Modules > Immobilisations > Paramétrage > Profils de validation d'immobilisation**.
2. Cliquez sur **Nouveau**.
3. Tapez une valeur dans le champ **Profil de validation**.
4. Tapez une valeur dans le champ **Description**. Vous devrez créer un profil de validation pour chaque type de transaction d'immobilisation que vous utiliserez lors de l'utilisation des immobilisations. Ce guide de tâche débute par le type de transaction d'acquisition.  
5. Cliquez sur **Ajouter** dans la barre d'outils.
6. Dans le champ **Registre**, entrez ou sélectionnez une valeur. Le champ **Regroupements** vous permet de définir le profil de validation dans Tableau (un compte défini pour chaque immobilisation) ou Groupe (un compte défini pour chaque groupe d'immobilisations). Pour ce guide de tâche, laissez la valeur définie sur « Tout » pour appliquer le registre spécifié à toutes les immobilisations.  
7. Spécifiez les valeurs souhaitées dans le champ **Compte principal**. Pour les acquisitions, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.    
8. Dans le menu déroulant sous le raccourci **Comptes généraux**, sélectionnez « Ajustement de l'acquisition ». Pour les transactions d'ajustement de l'acquisition, nous utiliserons les mêmes comptes que ceux utilisés pour les transactions d'acquisition.  
9. Cliquez sur **Ajouter**.
10. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
11. Spécifiez les valeurs souhaitées dans le champ **Compte principal**. Pour les ajustements de l'acquisition, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.    
12. Dans le menu déroulant sous le raccourci **Comptes généraux**, sélectionnez « Amortissement ».
13. Cliquez sur **Ajouter**.
14. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
15. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
16. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
17. Dans le menu déroulant sous le raccourci **Comptes généraux**, sélectionnez « Ajustement de l'amortissement ». Pour les transactions d'ajustement de l'amortissement, nous utiliserons les mêmes comptes que ceux utilisés pour les transactions d'amortissement.  
18. Cliquez sur **Ajouter**.
19. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
20. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
21. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
22. Dans le menu déroulant sous le raccourci **Comptes généraux**, sélectionnez « Cession - Vente ».
23. Cliquez sur **Ajouter**.
24. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
25. Spécifiez les valeurs souhaitées dans le champ **Compte principal**. Pour les cessions, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.  
26. Dans le menu déroulant sous le raccourci **Comptes généraux**, sélectionnez « Cession - Mise au rebut ». Utilisez les mêmes comptes pour « Cession - Vente » et « Cession - Mise au rebut ».  
27. Cliquez sur **Ajouter**.
28. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
29. Spécifiez les valeurs souhaitées dans le champ **Compte principal**. Pour les cessions, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.  
30. Développez le raccourci **Cession**. Vous devez paramétrer des profils de validation de cession pour la vente et la mise au rebut.  Nous commencerons par des transactions de cession.  
31. Cliquez sur **Ajouter**.
32. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
33. Sélectionnez « Valeur d'acquisition » dans le champ **Valider la valeur**.
    * La valeur d'acquisition prend en compte l'acquisition et les valeurs d'ajustement de l'acquisition pour toutes les années. Vous pouvez également définir des comptes pour ces types de transactions séparément.  
    * Vous pouvez définir le processus de cession afin d'utiliser différents comptes, selon que la cession débouche sur un profit ou une perte. Je définirai le type de prix de vente sur « Tout » pour utiliser les mêmes comptes pour tous les types de cessions.  
34. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
35. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
36. Cliquez sur **Ajouter**.
37. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
38. Sélectionnez « Amortissement (exercices précédents) » dans le champ **Valider la valeur**.  
38. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
39. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
40. Cliquez sur **Ajouter**.
41. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
42. Sélectionnez « Amortissement (cet exercice) » dans le champ **Valider la valeur**.
43. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
44. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
45. Cliquez sur **Ajouter**.
46. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
47. Sélectionnez « Ajustements de l'amortissement (exercices précédents) » dans le champ **Valider la valeur**.
48. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
49. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
50. Cliquez sur **Ajouter**.
51. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
52. Sélectionnez « Ajustements de l'amortissement (cet exercice) » dans le champ **Valider la valeur**.
53. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
54. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
55. Cliquez sur **Ajouter**.
56. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
57. Sélectionnez « Valeur nette » dans le champ **Valider la valeur**.
58. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
59. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
60. Sélectionnez « Rebut » dans le champ **Vente ou mise au rebut**.
61. Cliquez sur **Ajouter**.
62. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
63. Sélectionnez « Valeur d'acquisition » dans le champ **Valider la valeur**.
64. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
65. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
66. Cliquez sur **Ajouter**.
67. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
67. Sélectionnez « Amortissement (exercices précédents) » dans le champ **Valider la valeur**.  
68. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
69. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
70. Cliquez sur **Ajouter**.
71. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
72. Sélectionnez « Amortissement (cet exercice) » dans le champ **Valider la valeur**.
73. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
74. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
75. Cliquez sur **Ajouter**.
76. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
77. Sélectionnez « Ajustements de l'amortissement (exercices précédents) » dans le champ **Valider la valeur**.
78. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
79. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
80. Cliquez sur **Ajouter**.
81. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
82. Sélectionnez « Ajustements de l'amortissement (cet exercice) » dans le champ **Valider la valeur**.
83. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
84. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
85. Cliquez sur **Ajouter**.
86. Dans le champ **Registre**, entrez ou sélectionnez une valeur.
87. Sélectionnez « Valeur nette » dans le champ **Valider la valeur**.
88. Spécifiez les valeurs souhaitées dans le champ **Compte principal**.
89. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.

