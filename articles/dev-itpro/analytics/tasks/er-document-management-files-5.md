---
title: ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 5 - Modifier et exécuter le format)
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 23e91b6aee62157da9141cc7b6c4fae39c19ce32
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "329181"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5-modify-and-run-format"></a>ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 5 : Modifier et exécuter le format)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER. Ces étapes peuvent être effectuées dans la société DEMF.

Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 4 : Exécuter le format) ».

Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a>Modifier le format pour compléter les pièces jointes en générant des messages au format binaire
1. Accédez à Administration d'organisation > États électroniques > Configurations.
2. Dans l'arborescence, développez « Modèle de facture client ».
3. Dans l'arborescence, développez « Modèle de facture client\Modèle de facture client (personnalisé) ».
4. Dans l'arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé)\Exemple de message de facture électronique ».
5. Cliquez sur Concepteur.
    * Vous complétez le message de la facture dans la sortie de génération en tant que fichier XML à l'aide du codage UNICODE.  
6. Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.
7. Dans l'arborescence, sélectionnez « Common\File ».
8. Dans le champ Nom, tapez « Message Xml ».
    * Message Xml  
9. Dans le champ Encodage, tapez « UTF-8 ».
    * UTF-8  
10. Cliquez sur OK.
    * Configurez la sortie de génération en tant que fichier compressé.  
11. Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.
12. Dans l'arborescence, sélectionnez « Commun\Dossier ».
13. Dans le champ Nom, tapez « Compresser la sortie ».
    * Compresser la sortie  
14. Cliquez sur OK.
15. Dans l'arborescence, sélectionnez « Compresser la sortie ».
    * Ajoutez les pièces jointes au fichier compressé en tant que fichiers avec les noms et les extensions d'origine.  
16. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
17. Dans l'arborescence, sélectionnez « Common\File ».
18. Dans le champ Nom, tapez « Fichier joint ».
    * Fichier joint  
19. Cliquez sur OK.
20. Dans l'arborescence, sélectionnez « Compresser la sortie\Fichier joint ».
21. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
22. Dans l'arborescence, sélectionnez « Texte\Base64 ».
23. Cliquez sur OK.

## <a name="map-new-format-elements-to-data-model"></a>Mettre en correspondance les nouveaux éléments de format avec le modèle de données
1. Cliquez sur l'onglet Mise en relation.
2. Dans l'arborescence , développez « model ».
3. Dans l'arborescence, développez « Modèle\Pièces jointes à la facture ».
4. Dans l'arborescence, sélectionnez « Compresser la sortie\Fichier joint\Base64 ».
5. Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Contenu du fichier ».
6. Cliquez sur Lier.
7. Dans l'arborescence, sélectionnez « Compresser la sortie\Fichier joint ».
8. Cliquez sur Modifier le nom de fichier.
9. Dans l'arborescence , développez « model ».
10. Dans l'arborescence, développez « Modèle\Pièces jointes à la facture ».
11. Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Nom de fichier ».
12. Cliquez sur Ajouter une source de données.
13. Cliquez sur Enregistrer.
14. Fermez la page.
15. Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture ».
16. Cliquez sur Lier.
17. Cliquez sur Enregistrer.
18. Fermez la page.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>Exécuter l'état désigné pour la facture sélectionnée
1. Cliquez sur Exécuter.
2. Développez la section Enregistrements à inclure ().
3. Cliquez sur Filtre.
4. Sélectionnez la ligne de la table Journal des factures client et du champ Commande client.
5. Dans le champ Critères, dans le champ « Commande client », tapez le numéro de commande 000148.
    * 000148  
6. Cliquez sur OK.
7. Cliquez sur OK.
    * Examinez la sortie générée. Notez qu'en plus du message de la facture au format XML, un fichier unique a été créé pour chaque pièce jointe. Les fichiers joints sont renseignés avec la sortie compressée au format binaire.  

