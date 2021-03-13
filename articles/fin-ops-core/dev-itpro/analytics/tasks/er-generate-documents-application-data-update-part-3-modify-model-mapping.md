---
title: Modifier des modèles et des mises en correspondance pour générer des documents avec des données d’application
description: Cette rubrique décrit comment créer des configurations d’états électroniques pour générer un document électronique entrant et mettre à jour les données d’application. (Partie 2 - Générer des documents).
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
ms.openlocfilehash: 025429c8e6775d20634703853df04d63c0651b98
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092895"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a>Modifier des modèles et des mises en correspondance pour générer des documents avec des données d’application

[!include [banner](../../includes/banner.md)]

Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, « ER Générer des documents avec la mise à jour des données d’application (Partie 2 : Générer des documents) ». 

Les étapes de cette procédure expliquent comment créer des configurations ER pour générer un document électronique et mettre à jour les données d’application. Dans cette procédure, vous modifierez les configurations ER pour commencer à les utiliser pour générer des documents électroniques et mettre à jour les données d’application. Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d’états électroniques a été affecté. Ces étapes peuvent être effectuées à l’aide de l’ensemble de données DEMF.


## <a name="modify-data-model"></a>Modifier le modèle de données
1. Accédez à Administration d’organisation > États électroniques > Configurations.
2. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens (modèle) ».
    * Vous étendrez la façon d’utiliser le modèle de données. En plus de l’utiliser comme source de données pour générer l’état de déclaration d’échanges de biens, le modèle de données sera utilisé pour collecter des détails sur le processus de génération d’états de déclaration d’échanges de biens. Les détails seront ensuite utilisés pour mettre à jour les données d’application.   
3. Cliquez sur Concepteur.
4. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
5. Dans le nœud Nouveau sous forme de champ, entrez « Racine du modèle ».
6. Dans le champ Nom, tapez « Pour la mise à jour des données d’application ».
    * Pour la mise à jour des données d’application  
7. Cliquez sur Ajouter.
8. Dans l’arborescence, sélectionnez « Pour la mise à jour des données de l’application ».
    * Ce nouvel élément racine est ajouté pour spécifier le flux de données permettant de déplacer des données de l’état de déclaration d’échanges de biens (utilisé comme source de données) vers les tables d’application (la destination de mise à jour). Notez que différents éléments racine doivent être utilisés pour obtenir des données validées dans le document sortant et pour obtenir des données du document utilisé pour mettre à jour les données d’application.   
9. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
10. Dans le champ Nom, tapez « En-tête d’archive ».
    * En-tête d’archive  
11. Sélectionnez « Liste d’enregistrements » dans le champ Type d’article.
12. Cliquez sur Ajouter.
    * Comme vous créerez un enregistrement pour chaque état de déclaration d’échanges de biens généré, vous devez créer un nouvel élément à cet effet.  
13. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
14. Dans le champ Nom, tapez « Nom de fichier ».
    * Nom de fichier  
15. Sélectionnez « Chaîne » dans le champ Type d’article.
16. Cliquez sur Ajouter.
17. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
18. Dans le champ Nom, tapez « Nombre de lignes ».
    * Nombre de lignes  
19. Dans le champ Type d’article, sélectionnez « Entier ».
20. Cliquez sur Ajouter.
    * Ajoutez cet élément pour représenter le nombre de transactions de déclaration d’échanges de biens qui sont déclarées au cours du processus actuel de génération d’états.  
21. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
22. Dans le champ Nom, tapez « Lignes d’archive ».
    * Lignes d’archive  
23. Sélectionnez « Liste d’enregistrements » dans le champ Type d’article.
24. Cliquez sur Ajouter.
    * Ajoutez cet élément pour représenter la liste des transactions de déclaration d’échanges de biens qui sont déclarées au cours du processus actuel de génération d’états.  
25. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
26. Dans le champ Nom, tapez « Montant ».
    * Montant  
27. Sélectionnez « Réel » dans le champ Type d’article.
28. Cliquez sur Ajouter.
29. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
30. Dans le champ Nom, tapez « ID enregistrement de marchandise ».
    * ID enregistrement de marchandise  
31. Dans le champ Type d’article, sélectionnez « Int64 ».
32. Cliquez sur Ajouter.
33. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
34. Dans le champ Nom, tapez « Numéro d’article ».
    * numéro d’article  
35. Sélectionnez « Chaîne » dans le champ Type d’article.
36. Cliquez sur Ajouter.
37. Cliquez sur Enregistrer.
38. Fermez la page.

## <a name="modify-model-mapping"></a>Modifier la mise en correspondance du modèle
1. Dans l’arborescence, développez « Déclaration d’échanges de biens (modèle) ».
2. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens (modèle)\Déclaration d’échanges de biens (mise en correspondance) ».
    * Modifiez la mise en correspondance de modèle existante pour commencer à l’utiliser pour la mise à jour des données d’application et pour archiver les détails de la génération d’états de déclaration d’échanges de biens.  
3. Cliquez sur Concepteur.
4. Cliquez sur Nouveau.
5. Dans le champ Nom, tapez « Mettre à jour l’archive ».
    * Mettre à jour l’archive  
6. Dans le champ Direction, sélectionnez « Vers la destination ».
7. Cliquez sur Enregistrer.
    * Cette nouvelle mise en correspondance spécifie le flux de données permettant de déplacer des données (détails de la génération d’états de déclaration d’échanges de biens) du modèle de données vers les tables d’application (la destination de mise à jour). Notez que différents éléments racine du modèle doivent être utilisés pour obtenir des données de l’application pour le processus de génération d’états et utiliser les données du modèle de données pour la mise à jour des données d’application.   
8. Cliquez sur Concepteur.
9. Dans l’arborescence, sélectionnez « Modèle de données\Modèle de données ».
    * Ajoutez la source de données requise. Il s’agit du modèle de données qui contient les détails des transactions de déclaration d’échanges de biens déclarées qui doivent être archivées.  
10. Cliquez sur Ajouter racine.
11. Dans le champ Nom, tapez « modèle ».
    * modèle  
12. Dans le champ Définition, entrez ou sélectionnez la valeur « Pour la mise à jour des données d’application ».
    * Pour la mise à jour des données d’application  
13. Cliquez sur OK.
14. Dans l’arborescence , développez « model ».
15. Dans l’arborescence, sélectionnez « Fonctions\Champ calculé ».
16. Dans l’arborescence, sélectionnez « modèle\En-tête d’archive ».
17. Cliquez sur Ajouter.
    * Comme vous souhaitez énumérer les transactions de déclaration d’échanges de biens déclarées pour l’archivage, la source de données appropriée doit être ajoutée.  
18. Dans le champ Nom, tapez « Lignes énumérées ».
    * Lignes énumérées  
19. Cliquez sur Modifier la formule.
20. Dans l’arborescence, sélectionnez « Liste\ENUMERATE ».
21. Cliquez sur Ajouter une fonction.
22. Dans l’arborescence , développez « model ».
23. Dans l’arborescence, développez « modèle\En-tête d’archive ».
24. Dans l’arborescence, sélectionnez « modèle\En-tête d’archive\Lignes d’archive ».
25. Cliquez sur Ajouter une source de données.
26. Dans le champ Formule, entrez « ENUMERATE(model.’Archive header’.’Archive lines’) ».
    * ENUMERATE(model.’Archive header’.’Archive lines’)  
27. Cliquez sur Enregistrer.
28. Fermez la page.
29. Cliquez sur OK.
30. Cliquez sur Ajouter une destination.
    * Ajoutez les tables d’application comme destinations requises qui nécessitent des mises à jour pour archiver les détails des transactions de déclaration d’échanges de biens déclarées.  
31. Dans le champ Nom, tapez « Archive ».
    * Archiver  
32. Dans le champ Nom de la table, tapez « IntrastatArchiveGeneral ».
    * IntrastatArchiveGeneral  
    * Conservez l’action d’enregistrement « Insérer » afin que vous puissiez ajouter des enregistrements durant l’archivage des détails de chaque processus de génération d’états de déclaration d’échanges de biens.  
33. Sélectionnez Oui dans le champ Enregistrer Infos.
    * Sélectionnez Oui pour obtenir des informations sur les problèmes liés à la mise à jour des données d’application.  
34. Sélectionnez Oui dans le champ Ignorer la validation de l’action d’enregistrement.
    * Sélectionnez Oui pour supprimer les erreurs de validation relatives au champ vide « ID archive de la déclaration d’échanges de biens ». Cette opération sera effectuée après l’ajout des enregistrements, selon les paramètres de numéro de souche configurés pour cette table dans l’écran Paramètres de commerce extérieur.  
35. Cliquez sur OK.
    * Liez les éléments de la source de données ajoutée (le modèle filtré selon l’élément racine sélectionné racine) aux éléments de la destination ajoutée.  
36. Dans l’arborescence, développez « Archive ».
37. Dans l’arborescence, développez « Archive\<Relations ».
38. Dans l’arborescence, développez « Archive\<Relations\IntrastatArchiveDetail ».
39. Dans l’arborescence, sélectionnez « Archive\<Relations\IntrastatArchiveDetail\Montant(AmountMST) ».
40. Dans l’arborescence, développez « modèle\En-tête d’archive\Lignes énumérées ».
41. Dans l’arborescence, développez « modèle\En-tête d’archive\Lignes énumérées\Valeur ».
42. Dans l’arborescence, sélectionnez « modèle\En-tête d’archive\Lignes énumérées\Valeur\Montant ».
43. Cliquez sur Lier.
44. Dans l’arborescence, sélectionnez « Archive\<Relations\IntrastatArchiveDetail\Marchandise(IntrastatCommodity) ».
45. Dans l’arborescence, sélectionnez « modèle\En-tête d’archive\Lignes énumérées\Valeur\ID enregistrement de marchandise ».
46. Cliquez sur Lier.
47. Dans l’arborescence, sélectionnez « Archive\<Relations\IntrastatArchiveDetail\Numéro d’article(ItemId) ».
48. Dans l’arborescence, sélectionnez « modèle\En-tête d’archive\Lignes énumérées\Valeur\Numéro d’article ».
49. Cliquez sur Lier.
50. Dans l’arborescence, sélectionnez « Archive\<Relations\IntrastatArchiveDetail\Numéro de ligne(LineNumber) ».
51. Dans l’arborescence, sélectionnez « modèle\En-tête d’archive\Lignes énumérées\Numéro ».
52. Cliquez sur Lier.
53. Dans l’arborescence, sélectionnez « Archive\<Relations\IntrastatArchiveDetail ».
54. Dans l’arborescence, sélectionnez « modèle\En-tête d’archive\Lignes énumérées ».
55. Cliquez sur Lier.
56. Dans l’arborescence, sélectionnez « Archive\Nom de fichier(FileName) ».
57. Dans l’arborescence, sélectionnez « modèle\En-tête d’archive\Nom de fichier ».
58. Cliquez sur Lier.
59. Dans l’arborescence, sélectionnez « Archive\Nombre de lignes(NumberOfLines) ».
60. Dans l’arborescence, sélectionnez « modèle\En-tête d’archive\Nombre de lignes ».
61. Cliquez sur Lier.
62. Dans l’arborescence, sélectionnez « Archive ».
63. Dans l’arborescence, sélectionnez « modèle\En-tête d’archive ».
64. Cliquez sur Lier.
65. Cliquez sur Enregistrer.
66. Fermez la page.
67. Fermez la page.

