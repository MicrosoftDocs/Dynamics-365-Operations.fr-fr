---
title: Générer des documents contenant des données d'application
description: Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, « ER Générer des documents avec la mise à jour des données d'application (Partie 4 - Modifier le format) ».
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 759869577ef30cd3f81eb74103a93cc5d1a3d608
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042848"
---
# <a name="generate-documents-that-have-application-data"></a>Générer des documents contenant des données d'application

[!include [task guide banner](../../includes/task-guide-banner.md)]

Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, « ER Générer des documents avec la mise à jour des données d'application (Partie 4 : Modifier le format) ».



Les étapes de cette procédure expliquent comment créer des configurations ER pour générer un document électronique et mettre à jour les données d'application. Dans cette procédure, vous exécutez la configuration du format ER pour générer l'état de déclaration d'échanges de biens et mettre à jour les données d'application pour archiver les détails du processus de génération d'états.



Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d'états électroniques a été affecté. Ces étapes peuvent être effectuées à l'aide de l'ensemble de données DEMF. Avant de commencer, vérifiez que le contexte de pays pour la société DEMF est BEL (Belgique).


## <a name="set-up-foreign-trade-parameters"></a>Définir les paramètres de commerce extérieur
1. Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres de commerce extérieur.
2. Cliquez sur l'onglet Souches de numéros.

    Archivage des détails du processus de génération d'états de déclaration d'échanges de biens, nous devons identifier les enregistrements de chaque archive que nous avons créés. Une souche de numéros spéciale doit être configurée à cet effet.  

3. Sélectionnez la référence « ID archive de la déclaration d'échanges de biens ».
4. Tapez une valeur dans le champ Code souche de numéros.

    Dans le champ Code souche de numéros, entrez ou sélectionnez la valeur « Fore_2 ».  

5. Résolvez les modifications du code souche de numéros.
6. Cliquez sur Enregistrer.
7. Fermez la page.

## <a name="run-modified-er-format"></a>Exécuter le format ER modifié
1. Accédez à Administration d'organisation > États électroniques > Configurations.
2. Dans l'arborescence, développez « Déclaration d'échanges de biens (modèle) ».
3. Dans l'arborescence, sélectionnez « Déclaration d'échanges de biens (modèle)\Déclaration d'échanges de biens (format) ».
4. Cliquez sur Exécuter.
5. Dans le champ Entrer le nom du fichier, tapez « intrastat2.xml ».
6. Cliquez sur OK.

## <a name="review-er-format-executions-results"></a>Examiner les résultats de l'exécution du format ER
Examinez le fichier XML généré.  
1. Fermez la page.
2. Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d'échanges de biens.

    Ouvrez cet écran contenant les transactions de déclaration d'échanges de biens qui ont été incluses dans le document électronique généré.  

3. Cliquez sur Archive de la déclaration d'échanges de biens.

    Comme le format ER exécuté contient maintenant les paramètres pour la mise à jour des données d'application, les détails de la génération d'états de déclaration d'échanges de biens ont été archivés. Dans cet écran, vous pouvez voir l'enregistrement d'en-tête de l'archive créée.  

4. Cliquez sur Détails.

    Dans cet écran, vous pouvez voir les détails de l'archive créée.  

5. Fermez la page.
6. Fermez la page.
7. Fermez la page.

