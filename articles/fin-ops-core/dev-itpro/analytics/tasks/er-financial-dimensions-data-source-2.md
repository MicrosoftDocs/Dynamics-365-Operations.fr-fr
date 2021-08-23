---
title: ER Utiliser les dimensions financières comme source de données (Partie 2 – Mise en correspondance des modèles)
description: Cette rubrique décrit comment configurer un modèle de gestion des états électroniques pour utiliser les dimensions financières comme source de données pour les rapports de gestion des états électroniques. (Partie 2)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 921077cb3bc2d01c418f653194e948a2f29cc90dbd562d022ca69aa083a6ef54
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713892"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a>ER Utiliser les dimensions financières comme source de données (Partie 2 – Mise en correspondance des modèles)

[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un modèle de génération d’états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER. Ces étapes peuvent être effectuées dans n’importe quelle société.

Pour effectuer ces étapes, vous devez d’abord effectuer les étapes de la procédure « ER Utiliser les dimensions financières comme source de données (Partie 1 : créer un modèle de données) ».


## <a name="add-required-data-sources-to-model-mapping"></a>Ajouter les sources de données requises au mappage de modèle
1. Accédez à Administration d’organisation > États électroniques > Configurations.
2. Dans l’arborescence, sélectionnez « Exemple de modèle de dimensions financières ».
3. Cliquez sur Concepteur.
4. Cliquez sur Mettre en correspondance le modèle à la source de données.
5. Cliquez sur Nouveau.
6. Dans le champ Définition, sélectionnez Entrée.
7. Dans le champ Nom, tapez « Mise en correspondance des données de dimensions ».
8. Dans le champ Description, tapez « Mise en correspondance des données de dimensions ».
9. Cliquez sur Enregistrer.
10. Cliquez sur Concepteur.
11. Dans l’arborescence, sélectionnez « Dynamics 365 for Operations\Table ».
12. Cliquez sur Ajouter racine.
13. Dans le champ Nom, tapez « Société ».
14. Dans le champ Table, tapez « CompanyInfo ».
15. Cliquez sur OK.
16. Dans l’arborescence, sélectionnez « Fonctions\Détails des dimensions financières ».
17. Cliquez sur Ajouter racine.
    * Cette source de données spécifie la façon dont la portée des dimensions financières est définie pour un état qui utilise ce modèle comme source de données.  
18. Tapez une valeur dans le champ Nom.
19. Sélectionnez Oui dans le champ Demander les dimensions.
    * Sélectionnez Oui pour autoriser l’utilisateur à sélectionner des dimensions au moment de l’exécution dans l’écran Boîte de dialogue utilisateur. Si cette option est définie sur Non, toutes les dimensions financières de l’instance actuelle sont utilisées par défaut.  
20. Dans le champ Sélection de dimensions financières, sélectionnez « Entité juridique ».
    * Sélectionnez Tout pour autoriser l’utilisateur à sélectionner les dimensions souhaitées pour l’instance actuelle dans le champ de recherche.  Sélectionnez Entité juridique pour autoriser l’utilisateur à sélectionner des dimensions pour la société dans le champ de recherche.  Sélectionnez Dimension pour autoriser l’utilisateur à sélectionner des dimensions à l’aide d’un ensemble de dimensions unique.  
21. Sélectionnez Oui dans le champ Demander le compte principal.
    * Définissez « Demander le compte principal » sur Oui pour autoriser les utilisateurs à sélectionner le compte principal dans le cadre de la liste de dimensions.   Si cette option est définie sur Non, le compte principal n’est pas inclus dans la liste des dimensions et l’option « Compte principal obligatoire » est activée. Si « Compte principal obligatoire » est défini sur Oui, incluez le compte principal dans la liste des dimensions quelle que soit la sélection de l’utilisateur.  
22. Cliquez sur OK.
![Page du concepteur de mise en correspondance des modèles ER.](../media/er-financial-dimensions-guides-model-mapping1.png)
23. Dans l’arborescence, sélectionnez « Dynamics 365 for Operations\Enregistrements de la table ».
24. Cliquez sur Ajouter racine.
25. Dans le champ Nom, tapez « LedgerJournal ».
26. Sélectionnez Oui dans le champ Demander une requête.
27. Dans le champ Table, tapez « LedgerJournalTable ».
28. Cliquez sur OK.
![Page du concepteur de mise en correspondance des modèles ER.](../media/er-financial-dimensions-guides-model-mapping2.png)

## <a name="map-data-model-elements-to-added-data-sources"></a>Mettre en correspondance les éléments de modèle de données avec les sources de données ajoutées
1. Dans l’arborescence, développez « Journal »
2. Dans l’arborescence, développez « Journal\Transaction ».
3. Dans l’arborescence, développez « Journal\Transaction\Données de dimensions ».
4. Dans l’arborescence, développez « Paramètre de dimensions ».
5. Dans l’arborescence, développez « LedgerJournal ».
6. Dans l’arborescence, développez « LedgerJournal\<Relations ».
7. Dans l’arborescence, développez « LedgerJournal\<Relations\LedgerJournalTrans ».
8. Dans l’arborescence, sélectionnez « LedgerJournal\<Relations\LedgerJournalTrans\N° document ».
9. Dans l’arborescence, sélectionnez « Journal\Transaction\N° document ».
10. Cliquez sur Lier.
11. Dans l’arborescence, sélectionnez « LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension) ».
    * Notez que pour toute référence aux dimensions financières qui est définie sur LedgerDimension par exemple, un article de source de données correspondant est disponible (LedgerDimension.Dimension). Cet article de source de données offre les dimensions financières de cet ensemble de dimensions comme liste de l’enregistrement.  
12. Dans l’arborescence, développez « LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension) ».
13. Dans l’arborescence, développez « LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Compte principal et dimensions ».
14. Dans l’arborescence, développez « LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Compte principal et dimensions\Valeur ».
15. Dans l’arborescence, développez « LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Compte principal et dimensions\Définition ».
16. Dans l’arborescence, sélectionnez « LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Compte principal et dimensions\Définition\Nom ».
17. Dans l’arborescence, sélectionnez « Journal\Transaction\Données de dimensions\Nom ».
18. Cliquez sur Lier.
19. Dans l’arborescence, sélectionnez « LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Compte principal et dimensions\Valeur\Description ».
20. Dans l’arborescence, sélectionnez « Journal\Transaction\Données de dimensions\Description ».
21. Cliquez sur Lier.
22. Dans l’arborescence, sélectionnez « LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Compte principal et dimensions\Valeur\Code ».
23. Dans l’arborescence, sélectionnez « Journal\Transaction\Données de dimensions\Code ».
24. Cliquez sur Lier.
25. Dans l’arborescence, sélectionnez « LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Compte principal et dimensions ».
26. Dans l’arborescence, sélectionnez « Journal\Transaction\Données de dimensions ».
27. Cliquez sur Lier.
![Page du concepteur de mise en correspondance des modèles ER.](../media/er-financial-dimensions-guides-model-mapping3.png)
28. Dans l’arborescence, sélectionnez « LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit) ».
29. Dans l’arborescence, sélectionnez « Journal\Transaction\Débit ».
30. Cliquez sur Lier.
31. Dans l’arborescence, sélectionnez « LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate) ».
32. Dans l’arborescence, sélectionnez « Journal\Transaction\Date ».
33. Cliquez sur Lier.
34. Dans l’arborescence, sélectionnez « LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode) ».
35. Dans l’arborescence, sélectionnez « Journal\Transaction\Devise ».
36. Cliquez sur Lier.
37. Dans l’arborescence, sélectionnez « LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit) ».
38. Dans l’arborescence, sélectionnez « Journal\Transaction\Crédit ».
39. Cliquez sur Lier.
40. Dans l’arborescence, sélectionnez « LedgerJournal\<Relations\LedgerJournalTrans ».
41. Dans l’arborescence, sélectionnez « Journal\Transaction ».
42. Cliquez sur Lier.
43. Dans l’arborescence, sélectionnez « LedgerJournal\Numéro de lot du journal(JournalNum) ».
44. Dans l’arborescence, sélectionnez « Journal\Lot ».
45. Cliquez sur Lier.
46. Dans l’arborescence, sélectionnez « LedgerJournal ».
47. Dans l’arborescence, sélectionnez « Journal ».
48. Cliquez sur Lier.
49. Dans l’arborescence, développez « Dimensions ».
50. Dans l’arborescence, développez « Dimensions\Compte principal et dimensions ».
51. Dans l’arborescence, développez « Dimensions\Compte principal et dimensions\Définition ».
52. Dans l’arborescence, sélectionnez « Dimensions\Compte principal et dimensions\Définition\Nom ».
53. Dans l’arborescence, sélectionnez « Paramètre de dimensions\Code ».
54. Cliquez sur Lier.
55. Dans l’arborescence, sélectionnez « Dimensions\Compte principal et dimensions\Définition\Nom de la colonne de l’état ».
56. Dans l’arborescence, sélectionnez « Paramètre de dimensions\Nom ».
57. Cliquez sur Lier.
58. Dans l’arborescence, sélectionnez « Dimensions\Compte principal et dimensions ».
59. Dans l’arborescence, sélectionnez « Paramètre de dimensions ».
60. Cliquez sur Lier.
61. Dans l’arborescence, sélectionnez « Société ».
62. Cliquez sur Modifier.
63. Dans le champ expressionAsStringText, entrez « Company.’find()’.’name() ».
    * Company.’find()’.’name()’  
64. Cliquez sur Enregistrer.
![Page du concepteur de mise en correspondance des modèles ER.](../media/er-financial-dimensions-guides-model-mapping4.png)
65. Fermez la page.
66. Cliquez sur Enregistrer.
67. Fermez la page.

## <a name="complete-this-draft-models-version"></a>Terminer la version de ce modèle de brouillon
1. Fermez la page.
2. Fermez la page.
3. Cliquez sur Modifier le statut.
4. Cliquez sur Terminé.
5. Cliquez sur OK.
![Page du concepteur de mise en correspondance des modèles ER.](../media/er-financial-dimensions-guides-model-mapping5.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]