---
title: Modifier des formats pour générer des documents avec des données d’application
description: 'Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, « ER Générer des documents avec la mise à jour des données d’application (Partie 3 : Modifier le modèle et la mise en correspondance) ».'
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7dfa8fcb3525876da66659fe3bd8bbe3b81a37a3
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684545"
---
# <a name="modify-formats-to-generate-documents-that-have-application-data"></a>Modifier des formats pour générer des documents avec des données d’application

[!include [banner](../../includes/banner.md)]

Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, « ER Générer des documents avec la mise à jour des données d’application (Partie 3 : Modifier le modèle et la mise en correspondance) ».

Les étapes de cette procédure expliquent comment créer des configurations ER pour générer un document électronique et mettre à jour les données d’application. Dans cette procédure, vous modifierez les configurations ER non seulement pour les utiliser pour générer des documents électroniques, mais aussi pour mettre à jour les données d’application. Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d’états électroniques a été affecté. Ces étapes peuvent être effectuées à l’aide de l’ensemble de données DEMF.


## <a name="modify-format-to-collect-details-of-reporting"></a>Modifier le format pour collecter les détails de la génération d’états
1. Accédez à Administration d’organisation > États électroniques > Configurations.
2. Dans l’arborescence, développez « Déclaration d’échanges de biens (modèle) ».
3. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens (modèle)\Déclaration d’échanges de biens (format) ».
4. Cliquez sur Concepteur.
5. Dans l’arborescence, développez « Fichier ».
6. Dans l’arborescence, développez « Fichier\Déclaration ».
7. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données ».
8. Dans le champ Multiplicité, sélectionnez « Un plusieurs ».
    * Configurez cet élément de format pour archiver les détails du processus de génération d’états de déclaration d’échanges de biens. Cet élément représente l’enregistrement d’en-tête de l’archive.  
9. Dans l’arborescence, développez « Fichier\Déclaration\Données ».
10. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données\Article ».
11. Dans le champ Multiplicité, sélectionnez « Zéro plusieurs ».
    * Configurez cet élément de format pour archiver les détails du processus de génération d’états de déclaration d’échanges de biens. Cet article représentera la liste des lignes archivées.  
12. Dans l’arborescence, développez « Fichier\Déclaration\Données\Article ».
13. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données\Article\Dim1 ».
14. Sélectionnez Oui dans le champ Exclu.
    * Vous n’archiverez pas ces données, vous pouvez donc exclure cet élément de format de la source de données des détails de génération d’états de déclaration d’échanges de biens.  
15. Dans l’arborescence, développez « Fichier\Déclaration\Données\Article\Dim1 ».
16. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données\Article\Dim1\propriété ».
17. Sélectionnez Oui dans le champ Exclu.
18. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données\Article\Dim1\date ».
19. Sélectionnez Oui dans le champ Exclu.
20. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données\Article\Dim2 ».
21. Sélectionnez Oui dans le champ Exclu.
22. Dans l’arborescence, développez « Fichier\Déclaration\Données\Article\Dim2 ».
23. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données\Article\Dim2\propriété ».
24. Sélectionnez Oui dans le champ Exclu.
25. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données\Article\Dim2\code ».
26. Sélectionnez Oui dans le champ Exclu.
27. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données\Article\Dim3 ».
    * Plusieurs éléments de format peuvent avoir le même nom. Par exemple, Dim. Vous ne pouvez pas explicitement les reconnaître si vous utilisez ce format comme source de données pour archiver les détails de la génération d’états de déclaration d’échanges de biens. Vous devez définir les noms de remplacement pour ces éléments de format.   
28. Dans le champ Nom, tapez « Montant ».
    * Montant  
29. Dans le champ Multiplicité, sélectionnez « Un seul ».
30. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données\Article\Dim4 ».
31. Dans le champ Nom, tapez « Article ».
    * Article  
32. Dans le champ Multiplicité, sélectionnez « Un seul ».
    * Outre les éléments de format de conception, les détails de la génération d’états de déclaration d’échanges de biens doivent être archivés : l’identification d’enregistrement unique de chaque article de marchandise déclaré et le nom du fichier généré. Comme ces données ne sont pas renseignées dans l’état de déclaration d’échanges de biens, vous devez ajouter le format associé à ces éléments de détail comme éléments de la source de données.  
33. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données ».
34. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
35. Dans l’arborescence, sélectionnez « Source de données\Article ».
36. Dans le champ Nom, tapez « Nom de fichier ».
    * Nom de fichier  
37. Dans le champ Type de données, sélectionnez « Chaîne ».
38. Cliquez sur OK.
39. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données\Article ».
40. Cliquez sur Ajouter article.
41. Dans le champ Nom, tapez « ID enregistrement de marchandise ».
    * ID enregistrement de marchandise  
42. Dans le champ Type de données, sélectionnez « Int64 ».
43. Cliquez sur OK.
44. Cliquez sur l’onglet Mise en relation.
45. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données\Nom de fichier ».
46. Cliquez sur Lier.
47. Dans l’arborescence , développez « model ».
48. Dans l’arborescence, développez « modèle\Transactions ».
49. Dans l’arborescence, sélectionnez « Fichier\Déclaration\Données\Article = model.Transactions\ID enregistrement de marchandise ».
50. Dans l’arborescence, sélectionnez « modèle\Transactions\ID enregistrement de marchandise ».
51. Cliquez sur Lier.
52. Cliquez sur Enregistrer.

## <a name="modify-format-to-memorize-details-of-reporting"></a>Modifier le format pour mémoriser les détails de la génération d’états

1. Cliquez sur Mettre en correspondance vers le modèle.
2. Cliquez sur Nouveau.
3. Dans le champ Définition, entrez ou sélectionnez l’élément racine « Pour la mise à jour des données d’application ».
    * Pour la mise à jour des données d’application.
4. Dans le champ Nom, tapez « Mise en correspondance pour mettre à jour les données ».
    * Mise en correspondance pour mettre à jour les données  
5. Cliquez sur Enregistrer.
    * Cette mise en correspondance définit la manière dont les détails de l’état de déclaration d’échanges de biens sont collectés dans le modèle de données, dont la structure est spécifiée par l’article racine sélectionné « Pour la mise à jour de données d’application ». Ces détails, la mise en correspondance du modèle avec le même article racine « Pour la mise à jour de données d’application » et la direction « Vers la destination » seront utilisés pour la mise à jour de données d’application. La mise à jour de données d’application démarre immédiatement après la génération de l’état de déclaration d’échanges de biens sortants. La mise à jour de données d’application peut être ignorée au moment de l’exécution, mais que le modèle de données doit être vide (contenant une liste d’enregistrements vide).
6. Cliquez sur Concepteur.
    * Le format de l’état de déclaration d’échanges de biens sortant est ajouté par défaut comme source de données pour cette mise en correspondance de modèle.  
    * Liez les éléments de l’état créé (présenté comme source de données) aux éléments du modèle de données, qui est filtré en fonction de l’élément racine du modèle sélectionné.  
7. Dans l’arborescence, développez « En-tête d’archive ».
8. Dans l’arborescence, développez « En-tête d’archive\Lignes d’archive ».
9. Dans l’arborescence, développez « format ».
10. Dans l’arborescence, développez « format\Déclaration : Élément XML(Déclaration) ».
11. Dans l’arborescence, développez « format\Déclaration : Élément XML(Déclaration)\Données : Élément XML 1. * (Données) ».
12. Dans l’arborescence, développez « format\Déclaration : Élément XML(Déclaration)\Données : Élément XML 1. * (Données)\Article : Élément XML 0..* (Article) ».
13. Dans l’arborescence, développez « format\Déclaration : Élément XML(Déclaration)\Données : Élément XML 1. * (Données)\Article : Élément XML 0..* (Article)\Dim3 : Élément XML 1..1 (Montant) ».
14. Dans l’arborescence, développez « format\Déclaration : Élément XML(Déclaration)\Données : Élément XML 1. * (Données)\Article : Élément XML 0..* (Article)\Dim4 : Élément XML 1..1 (Article) ».
15. Dans l’arborescence, sélectionnez « En-tête d’archive\Nombre de lignes ».
16. Cliquez sur Modifier.
17. Dans l’arborescence, sélectionnez « Liste\COUNT ».
18. Cliquez sur Ajouter une fonction.
19. Dans l’arborescence, développez « format ».
20. Dans l’arborescence, développez « format\Déclaration : Élément XML(Déclaration) ».
21. Dans l’arborescence, développez `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)`.
22. Dans l’arborescence, sélectionnez `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)`.
23. Cliquez sur Ajouter une source de données.
24. Dans le champ Formule, entrez « COUNT(format.Declaration.Data.Item) ».
    * COUNT(format.Declaration.Data.Item)  
25. Cliquez sur Enregistrer.
26. Fermez la page.
27. Dans l’arborescence, sélectionnez « En-tête d’archive\Nom de fichier ».
28. Dans l’arborescence, sélectionnez « format\Déclaration : Élément XML(Déclaration)\Données : Élément XML 1..* (Données)\Nom de fichier : Chaîne d’article(Nom de fichier) ».
29. Cliquez sur Lier.
30. Dans l’arborescence, sélectionnez `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)\number: String(number)`.
31. Dans l’arborescence, sélectionnez « En-tête d’archive\Lignes d’archive\Numéro d’article ».
32. Cliquez sur Lier.
33. Dans l’arborescence, sélectionnez `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)\value: Numeric Real(value)`.
34. Dans l’arborescence, sélectionnez « En-tête d’archive\Lignes d’archive\Montant ».
35. Cliquez sur Lier.
36. Dans l’arborescence, sélectionnez `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Commodity rec ID: Item Int64(Commodity rec ID)`.
37. Dans l’arborescence, sélectionnez « En-tête d’archive\Lignes d’archive\ID enregistrement de marchandise ».
38. Cliquez sur Lier.
39. Dans l’arborescence, sélectionnez « En-tête d’archive\Lignes d’archive ».
40. Dans l’arborescence, sélectionnez `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)`.
41. Cliquez sur Lier.
42. Dans l’arborescence, sélectionnez « En-tête d’archive ».
43. Dans l’arborescence, sélectionnez `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)`.
44. Cliquez sur Lier.
45. Cliquez sur Enregistrer.
46. Fermez la page.
47. Fermez la page.
48. Fermez la page.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]