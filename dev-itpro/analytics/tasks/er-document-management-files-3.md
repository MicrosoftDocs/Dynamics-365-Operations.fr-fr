--- 
title: "Créer un format pour utiliser les fichiers de gestion des documents dans les sorties de format pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER."
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
ms.openlocfilehash: 47c7bea976d1052f537068b6bcf79c78ac3befbf
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a>Créer un format pour utiliser les fichiers de gestion des documents dans les sorties de format pour la gestion des états électroniques (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER. Ces étapes peuvent être effectuées dans n'importe quelle société.

Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 2 : Étendre le modèle de données) ».

Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="create-a-format-to-process-invoices"></a>Créer un format pour traiter les factures
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Cliquez sur Configurations des états.
3. Dans l'arborescence, développez « Modèle de facture client ».
4. Dans l'arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé) ».
    * Vous créerez un format pour générer des messageries électroniques contenant des informations sur les fichiers joints à une commande client associée à une facture à traitement électronique.  
5. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
6. Dans le champ Nouveau, entrez « Format basé sur le modèle de données Modèle de facture client(personnalisé) ».
7. Dans le champ Nom, tapez « Exemple de message de facture électronique ».
    * Exemple de message de facture électronique  
8. Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.
    * InvoiceCustomer  
9. Cliquez sur Créer une configuration.

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a>Créer un format pour compléter les pièces jointes en générant un message au format MIME
1. Cliquez sur Concepteur.
2. Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.
3. Dans l'arborescence , sélectionnez « XML\Élément ».
4. Dans le champ Nom, tapez « Facture ».
    * Facture  
5. Cliquez sur OK.
6. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
7. Dans l'arborescence, sélectionnez « XML\Attribut ».
8. Dans le champ Nom, tapez « SalesOrder ».
    * SalesOrder  
9. Cliquez sur OK.
10. Cliquez sur Ajouter un attribut.
11. Dans le champ Nom, tapez « InvoiceNumber ».
    * InvoiceNumber  
12. Cliquez sur OK.
13. Cliquez sur Ajouter un attribut.
14. Dans le champ Nom, tapez « InvoiceAmount ».
    * InvoiceAmount  
15. Cliquez sur OK.
16. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
17. Dans l'arborescence , sélectionnez « XML\Élément ».
18. Dans le champ Nom, tapez « EnclosedDocs ».
    * EnclosedDocs  
19. Cliquez sur OK.
20. Dans l'arborescence, sélectionnez « Facture\EnclosedDocs ».
21. Cliquez sur Ajouter un élément.
22. Dans le champ Nom, tapez « Document ».
    * Document  
23. Cliquez sur OK.
24. Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document ».
25. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
26. Dans l'arborescence, sélectionnez « XML\Attribut ».
27. Dans le champ Nom, tapez « FileName ».
    * FileName  
28. Cliquez sur OK.
29. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
30. Dans l'arborescence , sélectionnez « XML\Élément ».
31. Dans le champ Nom, tapez « FileContent ».
    * FileContent  
32. Cliquez sur OK.
33. Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document\FileContent ».
34. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
35. Dans l'arborescence, sélectionnez « Texte\Base64 ».
36. Cliquez sur OK.

## <a name="map-format-elements-to-data-model-as-data-source"></a>Mettre en correspondance les éléments de format avec le modèle de données en tant que source de données
1. Dans l'arborescence, sélectionnez « Facture\SalesOrder ».
2. Cliquez sur l'onglet Mise en relation.
3. Dans l'arborescence , développez « model ».
4. Dans l'arborescence, sélectionnez « Modèle\Numéro de commande client (SalesId) ».
5. Cliquez sur Lier.
6. Dans l'arborescence, sélectionnez « Facture\InvoiceNumber ».
7. Dans l'arborescence, développez « Modèle\Facture de base (InvoiceBase) ».
8. Dans l'arborescence, sélectionnez « Modèle\Facture de base (InvoiceBase)\Numéro de facture (Id) ».
9. Cliquez sur Lier.
10. Dans l'arborescence, sélectionnez « Facture\InvoiceAmount ».
11. Dans l'arborescence, sélectionnez « Modèle\Facture de base (InvoiceBase)\Montant de la facture (Amount) ».
12. Cliquez sur Lier.
13. Dans l'arborescence, développez « Modèle\Pièces jointes à la facture ».
14. Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Contenu du fichier ».
15. Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document\FileContent\Base64 ».
16. Cliquez sur Lier.
17. Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Nom de fichier ».
18. Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document\FileName ».
19. Cliquez sur Lier.
20. Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture ».
21. Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document ».
22. Cliquez sur Lier.
23. Cliquez sur Enregistrer.
24. Fermez la page.

