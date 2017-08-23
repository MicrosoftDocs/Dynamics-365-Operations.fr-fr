--- 
title: "Définir des stratégies d'audit pour les documents sources"
description: "Cette procédure décrit comment paramétrer et exécuter des règles de stratégie d'audit."
author: ryansandness
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ca4c8735258170c41dc907ed0ef8afca250ea9dd
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="define-audit-policies-for-source-documents"></a>Définir des stratégies d'audit pour les documents sources

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment paramétrer et exécuter des règles de stratégie d'audit. L'exemple utilise des états de dépenses avec le type de dépense Hôtel. La société fictive USMF sert d'exemple dans cette procédure. Le rôle d'auditeur contient les autorisations adéquates afin d'exécuter ces tâches.

1. Allez dans Console d'audit > Configuration > Type de règle de stratégie.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom de la règle.
4. Dans le champ Description, entrez une valeur.
5. Sélectionnez Ligne d'état de dépenses dans le champ Nom de la requête.
6. Sélectionnez Regroupement dans le champ de type de requête
7. Sélectionnez Entité juridique dans le champ Entité juridique
8. Dans le champ Référence de date du document, sélectionnez Date et heure de modification.
9. Cliquez sur Enregistrer.
10. Allez dans Console d'audit > Configuration > Stratégies d'audit.
11. Cliquez sur Nouveau.
12. Tapez une valeur dans le champ Nom.
13. Développez la section Organisations de stratégie.
14. Dans l'arborescence, sélectionnez Contoso Entertainment System USA.
15. Cliquez sur Ajouter.
16. Dans l'arborescence, sélectionnez Contoso Consulting USA.
17. Cliquez sur Ajouter.
18. Dans l'arborescence, sélectionnez Contoso Retail USA.
19. Cliquez sur Ajouter.
20. Réduisez la section Organisations de stratégie.
21. Développez la section Règles de stratégie.
22. Dans la liste, recherchez et sélectionnez la règle de stratégie créée précédemment.
23. Cliquez sur Créer une règle de stratégie.
24. Entrez une date et une heure dans le champ Date d'effet.
25. Cliquez sur Filtre.
26. Dans la liste, sélectionnez la ligne en regard de la catégorie Dépense, puis indiquez Hôtel dans les détails.
27. Dans le champ Critères, saisissez ou sélectionnez une valeur.
28. Cliquez sur l'onglet Regroupement.
29. Cliquez sur Ajouter.
30. Dans la liste, sélectionnez une valeur de champ pour Montant de la transaction.
31. Saisissez ou sélectionnez une valeur dans le champ Champ.
32. Sélectionnez « Somme » dans le champ AggregateFunction.
33. Cliquez sur l'onglet Grouper par.
34. Cliquez sur Ajouter.
35. Sélectionnez une valeur pour Employé dans la liste  
36. Cliquez sur Ajouter.
37. Sélectionnez une valeur pour Catégorie de dépenses dans la liste.
38. Saisissez ou sélectionnez une valeur dans le champ Champ.
39. Cliquez sur l'onglet Ayant.
40. Cliquez sur Ajouter.
41. Sélectionner le montant de la transaction
42. Saisissez ou sélectionnez une valeur dans le champ Champ.
43. Sélectionnez « Somme » dans le champ AggregateFunction.
44. Tapez « >2000 » dans le champ Critères.
45. Cliquez sur OK.
46. Cliquez sur Tester.
47. Entrez une date et une heure dans le champ Date de début de la sélection de document.
48. Entrez une date et une heure dans le champ Date de fin de la sélection de document.
49. Cliquez sur Exécuter le test.
50. Dans le volet Actions, cliquez sur Stratégie d'audit.
51. Cliquez sur Options supplémentaires.
52. Entrez une date et une heure dans le champ Date de début.
53. Entrez une date et une heure dans le champ Date de fin.
54. Cliquez sur Traitement par lots.
55. Développez la section Exécuter à l'arrière-plan.
56. Sélectionnez Oui dans le champ Traitement par lots.
57. Cliquez sur OK.
58. Allez dans Console d'audit > Dossiers d'audit.
59. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
60. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
61. Développez la section Associations.
62. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
63. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.


