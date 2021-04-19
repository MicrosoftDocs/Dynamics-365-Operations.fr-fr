---
title: Définir des stratégies d’audit pour les documents sources
description: Cette rubrique décrit comment paramétrer et exécuter des règles de stratégie d’audit.
author: panolte
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 62ebe3d6ba1208bd5f9a2082969b1960c413c152
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836959"
---
# <a name="define-audit-policies-for-source-documents"></a>Définir des stratégies d’audit pour les documents sources

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment paramétrer et exécuter des règles de stratégie d’audit. L’exemple utilise des états de dépenses avec le type de dépense Hôtel. La société fictive USMF sert d’exemple dans cette procédure. Le rôle d’auditeur contient les autorisations adéquates afin d’exécuter ces tâches.

1. Dans le volet de navigation, allez dans **Modules > Console d’audit > Configuration > Type de règle de stratégie**.
2. Sélectionnez **Nouveau**.
3. Tapez une valeur dans le champ **Nom de la règle**.
4. Tapez une valeur dans le champ **Description**.
5. Sélectionnez **Ligne d’état de dépenses** dans le champ **Nom de la requête**
6. Sélectionnez **Regroupement** dans le champ de **type de requête**
7. Sélectionnez **Entité juridique** dans le champ **Entité juridique**
8. Dans le champ **Référence de date du document**, sélectionnez **Date et heure de modification**
9. Sélectionnez **Enregistrer**.
10. Dans le volet de navigation, allez dans **Modules > Console d’audit > Configuration > Stratégies d’audit**.
11. Sélectionnez **Nouveau**.
12. Tapez une valeur dans le champ **Nom**.
13. Développez la section **Organisations de stratégie**.
14. Dans l’arborescence, sélectionnez **Contoso Entertainment System USA**, puis sélectionnez **Ajouter**.
15. Dans l’arborescence, sélectionnez **Contoso Consulting USA**, puis sélectionnez **Ajouter**.
16. Dans l’arborescence, sélectionnez **Contoso Retail USA**, puis sélectionnez **Ajouter**.
17. Réduisez la section **Organisations de stratégie**.
18. Développez la section **Règles de stratégie**.
19. Dans la liste, recherchez et sélectionnez la règle de stratégie créée précédemment.
20. Sélectionnez **Créer une règle de stratégie**.
21. Entrez une date et une heure dans le champ **Date d’effet**.
22. Sélectionnez **Filtrer**.
23. Dans la liste, sélectionnez la ligne en regard de la catégorie **Dépense**, puis indiquez **Hôtel** dans les détails.
24. Dans le champ **Critères**, saisissez ou sélectionnez une valeur.
25. Cliquez sur l’onglet **Regroupement**.
26. Sélectionnez **Ajouter**.
27. Dans la liste, sélectionnez une valeur de champ pour **Montant de la transaction**.
28. Saisissez ou sélectionnez une valeur dans le champ **Champ**.
29. Sélectionnez **Somme** dans le champ **AggregateFunction**.
30. Sélectionnez l’onglet **Grouper par**.
31. Sélectionnez **Ajouter**.
32. Sélectionnez une valeur pour **Employé** dans la liste.
33. Sélectionnez **Ajouter**.
34. Sélectionnez une valeur pour **Catégorie de dépenses** dans la liste.
35. Saisissez ou sélectionnez une valeur dans le champ **Champ**.
36. Sélectionnez l’onglet **Ayant**.
37. Sélectionnez **Ajouter**.
38. Sélectionnez le **montant de la transaction**.
39. Saisissez ou sélectionnez une valeur dans le champ **Champ**.
40. Sélectionnez **Somme** dans le champ **AggregateFunction**.
41. Tapez `>2000` dans le champ **Critères**.
42. Cliquez sur **OK**.
43. Sélectionnez **Test**.
44. Entrez une date et une heure dans le champ **Date de début de la sélection de document**.
45. Entrez une date et une heure dans le champ **Date de fin de la sélection de document**.
46. Sélectionnez **Exécuter le test**.
47. Dans le volet Actions, cliquez sur **Stratégie d’audit**.
48. Sélectionnez **Options supplémentaires**.
49. Entrez une date et une heure dans le champ **Date de début**.
50. Entrez une date et une heure dans le champ **Date de fin**.
51. Sélectionnez **Traitement par lots**.
52. Développez la section **Exécuter à l’arrière-plan**.
53. Sélectionnez **Oui** dans le champ **Traitement par lots**.
54. Cliquez sur **OK**.
55. Dans le volet de navigation, allez dans **Modules > Console d’audit > Dossiers d’audit**.
56. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
57. Développez la section **Associations**.
58. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]