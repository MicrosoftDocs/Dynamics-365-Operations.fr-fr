---
title: ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 2 - Étendre le modèle de données)
description: Cette rubrique décrit comment configurer un format de gestion des états électroniques pour utiliser les fichiers de gestion des documents dans la sortie de gestion des états électroniques (pièces jointes). (Partie 2)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cd06cdfd9bae57577c2e3ec97848e319b197f41
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092588"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a>ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 2 - Étendre le modèle de données)

[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un format de génération d’états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER. Ces étapes peuvent être effectuées dans n’importe quelle société.

Pour effectuer ces étapes, vous devez d’abord effectuer les étapes du guide de tâche « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 1 : Préparer le modèle de données) ».

Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a>Étendre le modèle de données pour y présenter les fichiers de gestion des documents
1. Accédez à Administration d’organisation > Espaces de travail > États électroniques.
2. Cliquez sur Configurations des états.
3. Dans l’arborescence, développez « Modèle de facture client ».
4. Dans l’arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé) ».
5. Cliquez sur Concepteur.
6. Dans l’arborescence, sélectionnez « Facture client (InvoiceCustomer) ».
    * Nous étendrons ce modèle de données pour y exposer les fichiers joints à une commande client associée à une facture à traitement électronique.  
7. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
8. Dans le champ Nom, tapez «Pièces jointes à la facture ».
    * Pièces jointes à la facture  
9. Sélectionnez « Liste d’enregistrements » dans le champ Type d’article.
10. Cliquez sur Ajouter.
11. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
12. Dans le champ Nom, tapez « Contenu du fichier ».
    * Contenu du fichier  
13. Dans le champ Type d’article, sélectionnez « Conteneur ».
14. Cliquez sur Ajouter.
15. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
16. Dans le champ Nom, tapez « Nom de fichier ».
    * Nom de fichier  
17. Sélectionnez « Chaîne » dans le champ Type d’article.
18. Cliquez sur Ajouter.

## <a name="map-new-data-model-elements-to-data-sources"></a>Mettre en correspondance les nouveaux éléments de modèle de données avec les sources de données
1. Cliquez sur Mettre en correspondance le modèle à la source de données.
2. Utilisez le filtre rapide pour filtrer le champ Définition avec la valeur « InvoiceCustomer ».
    * InvoiceCustomer  
    * Nous mettrons en correspondance les nouveaux éléments de modèle avec les sources de données appropriées.  
3. Cliquez sur Concepteur.
4. Dans l’arborescence, sélectionnez « Pièces jointes à la facture ».
5. Dans l’arborescence, développez « Pièces jointes à la facture ».
6. Dans l’arborescence, sélectionnez « Pièces jointes à la facture\Nom de fichier ».
7. Cliquez sur Modifier.
8. Dans le champ Formule, entrez ’CustInvoiceJour.’>Relations’.SalesTable.’<Relations’.’<Documents’.’originalFileName()’’.
    * CustInvoiceJour.’>Relations’.SalesTable.’<Relations’.’<Documents’.’originalFileName()’  
9. Cliquez sur Enregistrer.
10. Fermez la page.
11. Dans l’arborescence, sélectionnez « Pièces jointes à la facture\Contenu du fichier ».
12. Cliquez sur Modifier.
13. Dans le champ Formule, entrez ’CustInvoiceJour.’>Relations’.SalesTable.’<Relations’.’<Documents’.’getFileContentAsContainer()’.
    * CustInvoiceJour.’>Relations’.SalesTable.’<Relations’.’<Documents’.’getFileContentAsContainer()’  
14. Cliquez sur Enregistrer.
15. Fermez la page.
16. Dans l’arborescence, sélectionnez « Pièces jointes à la facture ».
17. Cliquez sur Modifier.
18. Dans le champ Formule, entrez ’CustInvoiceJour.’>Relations’.SalesTable.’<Relations’.’<Documents’.
    * CustInvoiceJour.’>Relations’.SalesTable.’<Relations’.’<Documents’  
19. Cliquez sur Enregistrer.
20. Fermez la page.
21. Cliquez sur Enregistrer.
22. Fermez la page.
23. Fermez la page.
24. Fermez la page.
25. Cliquez sur Modifier le statut.
26. Cliquez sur Terminé.
27. Cliquez sur OK.

