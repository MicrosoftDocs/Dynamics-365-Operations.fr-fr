---
title: Définir les mises en correspondance de modèles de gestion d'états électroniques et sélectionner des sources de données pour eux
description: Les étapes suivantes expliquent comment un utilisateur doté du rôle Administrateur système ou Développeur d'états électroniques peut sélectionner des sources de données pour un modèle de données de génération d'états électroniques.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5f2f2c699514d723f42f5d1fb25724f46dfc4f4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "348869"
---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a>Définir les mises en correspondance de modèles de gestion d'états électroniques et sélectionner des sources de données pour eux

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur doté du rôle Administrateur système ou Développeur d'états électroniques peut sélectionner des sources de données pour un modèle de données de génération d'états électroniques (ER). Les sources de données seront liées aux composants du modèle de données sélectionné au moment de la création et des données commerciales seront renseignées dans ce modèle de données au moment de l'exécution. Dans cet exemple, vous allez sélectionner des sources de données pour un modèle de données existant qui a été créé pour la société témoin, Litware, Inc. Pour effectuer ces étapes, vous devez d'abord accomplir celles de la procédure « Créer un modèle de données ».


## <a name="open-the-electronic-reporting-configurations-tree"></a>Ouvrir l'arborescence des configurations d'états électroniques
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Cliquez sur Configurations des états.

## <a name="insert-a-new-model-mapping"></a>Insérer une nouvelle mise en correspondance de modèle
1. Dans l'arborescence, sélectionnez « Paiements (modèle simplifié) ».
2. Cliquez sur Concepteur.
3. Cliquez sur Mettre en correspondance le modèle à la source de données.
4. Cliquez sur Nouveau.
    * Cette opération crée un enregistrement qui mappera le modèle de données aux sources de données. Dans cet exemple, vous mapperez le modèle de données aux sources de données pour le type désiré de paiement : virement.     Il est possible de concevoir plusieurs mises en correspondance pour un modèle de données spécifique. Par exemple, vous pouvez créer une mise en correspondance pour les différents types de paiements, comme le débit direct ou les virements bancaires. Dans cet exemple, vous créerez une mise en correspondance pour les virements.  
5. Dans le champ Nom, tapez « Mise en correspondance VMT ».
    * Mise en correspondance VMT  
6. Dans le champ Description, entrez « Mise en correspondance de modèle de paiement VMT ».
    * Mise en correspondance de modèle de paiement VMT  
7. Dans le champ Définition, tapez « CustomerCreditTransferInitiation ».
    * CustomerCreditTransferInitiation  
8. Résolvez les modifications de la définition.
9. Cliquez sur Enregistrer.

## <a name="define-required-data-sources-for-the-current-model-mapping"></a>Définir des sources de données pour la mise en correspondance de modèle existante
1. Cliquez sur Concepteur.
2. Dans l'arborescence, sélectionnez « Dynamics 365 for Operations\Enregistrements de la table ».
3. Cliquez sur Ajouter racine.
    * Entrez cette source de données pour accéder à des transactions de paiement.  
4. Dans le champ Nom, tapez « Transactions ».
    * Transactions  
5. Dans le champ Étiquette, tapez « Transactions ».
    * Transactions  
6. Dans le champ Aide, entrez « Lignes de journal comptable ».
    * Lignes de journal comptable  
7. Sélectionnez Oui dans le champ Demander une requête.
    * Sélectionnez Oui.  
8. Dans le champ Table, tapez « LedgerJournalTrans ».
    * LedgerJournalTrans  
9. Cliquez sur OK.
    * Sélectionnez la table LedgerJournalTrans comme source de données pour le modèle de données actuel.  
10. Dans l'arborescence, sélectionnez « Fonctions\Champ calculé ».
11. Cliquez sur Ajouter.
    * Cliquez sur Ajouter pour ajouter un champ calculé.  
12. Dans le champ Nom, tapez « $EndToEndID ».
    * $EndToEndID  
13. Cliquez sur Modifier la formule.
14. Dans l'arborescence, sélectionner « String\CONCATENATE ».
15. Cliquez sur Ajouter une fonction.
16. Dans l'arborescence , développer « Transactions ».
17. Dans l'arborescence, sélectionnez « Transactions\Document ».
18. Cliquez sur Ajouter une source de données.
19. Dans le champ Formule, entrez « CONCATENATE(Transactions.Voucher, "-", ».
    * Tapez [ , “-“, ] à la fin de la formule.  
20. Dans l'arborescence , sélectionnez « Chaîne\TEXTE ».
21. Cliquez sur Ajouter une fonction.
22. Dans l'arborescence, sélectionnez « Transactions\ID enregistrement (RecId) ».
23. Cliquez sur Ajouter une source de données.
24. Dans le champ Formule, entrez « CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId)) ».
    * Tapez [))] à la fin de la formule.  
25. Cliquez sur Enregistrer.
    * Assurez-vous qu'aucune erreur n'a été découverte dans la formule créée. Voir l'onglet ERREURS en dessous du contrôle d'éditeur de formule.  
26. Fermez la page.
27. Cliquez sur OK.
    * Ajoutez le champ calculé à cette source de données.  
28. Cliquez sur Ajouter.
    * Cliquez sur Ajouter pour ajouter un champ calculé.  
29. Dans le champ Nom, tapez « $Amount ».
    * $Montant  
30. Cliquez sur Modifier la formule.
31. Dans l'arborescence , développer « Transactions ».
32. Dans l'arborescence, sélectionnez « Transactions\Debit(AmountCurDebit) ».
33. Cliquez sur Ajouter une source de données.
34. Dans le champ Formule, entrez « Transactions.AmountCurDebit -  ».
    * Tapez [ - ] à la fin de la formule.  
35. Dans l'arborescence, sélectionnez « Transactions\Credit(AmountCurCredit) ».
36. Cliquez sur Ajouter une source de données.
37. Cliquez sur Enregistrer.
38. Fermez la page.
39. Cliquez sur OK.
    * Cela ajoutera le champ calculé de $Amount à la source de données sélectionnée pour le modèle de données actuel.  
40. Dans l'arborescence, sélectionnez « Transactions\$Amount ».
41. Dans l'arborescence , développer « Transactions ».
42. Dans l'arborescence, développez ou réduisez « Transactions\$Amount ».
43. Dans l'arborescence, développez ou réduisez « Transactions ».
44. Dans l'arborescence, sélectionnez « Dynamics 365 for Operations\Enregistrements de la table ».
45. Cliquez sur Ajouter racine.
    * Entrez cette source de données pour accéder aux détails du compte bancaire de la société.  
46. Dans le champ Nom, tapez « BankAccount ».
    * BankAccount  
47. Dans le champ Étiquette, tapez « Compte bancaire ».
    * Compte bancaire  
48. Dans le champ Aide, tapez « Compte bancaire ».
    * Compte bancaire  
49. Sélectionnez Oui dans le champ Demander une requête.
    * Sélectionnez Oui.  
50. Dans le champ Table, tapez « BankAccountTable ».
    * BankAccountTable  
51. Cliquez sur OK.
    * Sélectionnez la table BankAccountTable comme source de données pour le modèle de données actuel.  
52. Cliquez sur Ajouter racine.
    * Entrez cette source de données pour accéder aux conditions de la société.  
53. Dans le champ Nom, tapez « Société ».
    * Société  
54. Dans le champ Étiquette, tapez une valeur.
    * Informations sur la société  
55. Dans le champ Aide, entrez « Informations sur la société ».
    * Informations sur la société  
56. Sélectionnez Oui dans le champ Demander une requête.
    * Sélectionnez Oui.  
57. Dans le champ Table, tapez « CompanyInfo ».
    * CompanyInfo  
58. Cliquez sur OK.
    * Sélectionnez la table CompanyInfo comme source de données pour le modèle de données actuel.  
59. Dans l'arborescence, sélectionnez « Fonctions\Champ calculé ».
60. Cliquez sur Ajouter racine.
    * Insérez un champ calculé comme nouvelle source de données.  
61. Tapez « ProcessingDateTime » dans le champ Nom.
    * ProcessingDateTime  
62. Dans le champ Étiquette, entrez « Date et heure de traitement ».
    * Date et heure de traitement  
63. Cliquez sur Modifier la formule.
64. Dans l'arborescence, sélectionnez « Date/time\SESSIONNOW ».
65. Cliquez sur Ajouter une fonction.
66. Cliquez sur Enregistrer.
67. Fermez la page.
68. Cliquez sur OK.
    * Ajoutez le champ calculé de ProcessingDateTime comme source de données pour le modèle de données actuel.  
69. Cliquez sur Enregistrer.
70. Fermez la page.
71. Fermez la page.
72. Fermez la page.

