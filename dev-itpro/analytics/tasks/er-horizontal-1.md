--- 
title: "Concevoir un format pour utiliser des plages extensibles horizontalement pour ajouter dynamiquement des colonnes dans les états Excel pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format d'états électroniques pour générer des états en tant que fichiers de feuilles de calcul (Excel) OPENXML dans lesquels les colonnes requises peuvent être créées dynamiquement sous forme de plages extensibles horizontalement."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 94898674f02de72111e131f563b33926dda8ac8e
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="design-a-format-to-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-for-electronic-reporting-er"></a>Concevoir un format pour utiliser des plages extensibles horizontalement pour ajouter dynamiquement des colonnes dans les états Excel pour la gestion des états électroniques (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format d'états électroniques pour générer des états en tant que fichiers de feuilles de calcul (Excel) OPENXML dans lesquels les colonnes requises peuvent être créées dynamiquement sous forme de plages extensibles horizontalement. Ces étapes peuvent être effectuées dans n'importe quelle société.

Pour réaliser ces étapes, vous devez d'abord effectuer les étapes des trois guides de tâche suivants : 

« ER Créer un fournisseur de configuration et le marquer comme actif »

« ER Utiliser les dimensions financières comme source de données (Partie 1 : Créer un modèle de données) »

« ER Utiliser les dimensions financières comme source de données (Partie 2 : Mise en correspondance des modèles) »

Vous devez également télécharger et enregistrer une copie locale du modèle avec un exemple d'état disponible ici : http://msdynamics.blob.core.windows.net/media/2016/09/SampleFinDimWsReport.xlsx

Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="create-a-new-report-configuration"></a>Créer une configuration d'état
1. Accédez à Administration d'organisation > États électroniques > Configurations.
2. Dans l'arborescence, sélectionnez « Exemple de modèle de dimensions financières ».
3. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
4. Dans le champ Nouveau, entrez « Format basé sur l'exemple de modèle de dimensions financières pour le modèle de données ».
    * Utilisez le modèle créé à l'avance comme source de données de votre nouvel état.  
5. Dans le champ Nom, tapez « Exemple de rapport avec des plages extensibles horizontalement ».
    * Exemple de rapport avec des plages extensibles horizontalement  
6. Dans le champ Description, tapez « Pour créer la sortie Excel avec ajout dynamique de colonnes ».
    * Pour créer la sortie Excel avec ajout dynamique de colonnes  
7. Dans le champ Définition du modèle de données, sélectionnez Entrée.
8. Cliquez sur Créer une configuration.

## <a name="design-the-report-format"></a>Créer le format d'état
1. Cliquez sur Concepteur.
2. Activez le bouton à bascule « Afficher les détails ».
3. Cliquez sur Importer dans le volet Actions.
4. Cliquez sur Importer depuis Excel.
5. Cliquez sur Documents joints.
    * Importez le modèle de l'état. Utilisez le fichier Excel que vous avez téléchargé à cet effet.  
6. Cliquez sur Nouveau.
7. Cliquez sur Fichier.
8. Fermez la page.
9. Dans le champ Modèle, entrez ou sélectionnez une valeur.
    * Sélectionnez le modèle téléchargé.  
10. Cliquez sur OK.
    * Ajoutez une nouvelle plage pour créer dynamiquement la sortie Excel avec autant de colonnes sélectionnées (dans l'écran Boîte de dialogue utilisateur) que pour les dimensions financières. Chaque cellule de chaque colonne représente le nom d'une dimension financière unique.  
11. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
12. Dans l'arborescence, sélectionnez « Excel\Plage ».
13. Dans le champ Plage Excel, tapez « DimNames ».
    * DimNames  
14. Dans le champ Direction de la réplication, sélectionnez « Horizontal ».
15. Cliquez sur OK.
16. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<DimNames>: Horizontal ».
17. Cliquez sur Déplacer vers le haut.
18. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Cell<DimNames> ».
19. Cliquez sur Couper.
20. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<DimNames>: Horizontal ».
21. Cliquez sur Coller.
22. Dans l'arborescence, développez « Excel = SampleFinDimWsReport\Range<DimNames>: Horizontal ».
23. Dans l'arborescence, développez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical ».
24. Dans l'arborescence, développez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical ».
25. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical ».
    * Ajoutez une nouvelle plage pour créer dynamiquement la sortie Excel avec autant de colonnes sélectionnées (dans l'écran Boîte de dialogue utilisateur) que pour les dimensions financières. Chaque cellule de chaque colonne représente la valeur d'une dimension financière unique pour chaque transaction de génération d'états.  
26. Cliquez sur Ajouter une plage.
27. Dans le champ Plage Excel, tapez « DimValues ».
    * DimValues  
28. Dans le champ Direction de la réplication, sélectionnez « Horizontal ».
29. Cliquez sur OK.
30. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<DimValues> ».
31. Cliquez sur Couper.
32. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical \Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal ».
33. Cliquez sur Coller.
34. Dans l'arborescence, développez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical \Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal ».

## <a name="map-format-elements-to-data-sources"></a>Mettre en correspondance les éléments de format avec les sources de données
1. Cliquez sur l'onglet Mise en relation.
2. Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données ».
3. Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements ».
4. Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements ».
5. Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements ».
6. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical \Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues> ».
7. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements\Code : Chaîne ».
8. Cliquez sur Lier.
9. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical \Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal ».
10. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements ».
11. Cliquez sur Lier.
12. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Credit> ».
13. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Crédit : Réel ».
14. Cliquez sur Lier.
15. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Debit> ».
16. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Débit : Réel ».
17. Cliquez sur Lier.
18. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Currency> ».
19. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Devise : Chaîne ».
20. Cliquez sur Lier.
21. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransDate> ».
22. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Date : Date ».
23. Cliquez sur Lier.
24. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransVoucher> ».
25. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\N° document : Chaîne ».
26. Cliquez sur Lier.
27. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransBatch> ».
28. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Lot : Chaîne ».
29. Cliquez sur Lier.
30. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical ».
31. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements ».
32. Cliquez sur Lier.
33. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical\Cell<Batch> ».
34. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Lot : Chaîne ».
35. Cliquez sur Lier.
36. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<JournalLine>: Vertical ».
37. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements ».
38. Cliquez sur Lier.
39. Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Paramètre de dimensions : Liste d'enregistrements ».
40. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Paramètre de dimensions : Liste d'enregistrements\Code : Chaîne ».
41. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<DimNames>: Horizontal\Cell<DimNames> ».
42. Cliquez sur Lier.
43. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Paramètre de dimensions : Liste d'enregistrements ».
44. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Range<DimNames>: Horizontal ».
45. Cliquez sur Lier.
46. Dans l'arborescence, sélectionnez « Excel = SampleFinDimWsReport\Cell<CompanyName> ».
47. Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Société : Chaîne ».
48. Cliquez sur Lier.
49. Cliquez sur Enregistrer.
50. Fermez la page.


