---
title: Concevoir des configurations pour générer des documents avec des données d’application
description: Cet article décrit comment créer des configurations d’états électroniques pour générer un document électronique entrant. (Partie 1 - Importer les configurations).
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3a52ce08458868ae717c650d4b96754c297cd07a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900191"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a>Concevoir des configurations pour générer des documents avec des données d’application

[!include [banner](../../includes/banner.md)]

Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, ER Générer des documents avec la mise à jour des données d’application (Partie 1 : Importer les configurations).



Les étapes de cette procédure expliquent comment créer des configurations ER pour générer un document électronique. Dans cette procédure, vous exécutez la configuration importée du format ER qui a été créée pour la société fictive, Litware, Inc. pour générer des documents électroniques.



Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d’états électroniques a été affecté. Ces étapes peuvent être effectuées à l’aide de l’ensemble de données DEMF. 



Avant de commencer, modifiez le contexte de pays pour la société DEMF de DEU (Allemagne) à BEL (Belgique). Cliquez sur Administration d’organisation > Organisations > Entités juridiques pour mettre à jour le code pays dans l’adresse principale de l’entité juridique DEMF. Redémarrez votre application.


## <a name="run-imported-er-format"></a>Exécuter le format ER importé
1. Accédez à Administration d’organisation > États électroniques > Configurations.
2. Dans l’arborescence, développez « Déclaration d’échanges de biens (modèle) ».
3. Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens (modèle)\Déclaration d’échanges de biens (format) ».
4. Cliquez sur Exécuter.
    * Exécutez la version brouillon de la configuration du format ER pour générer l’état de déclaration d’échanges de biens.  
5. Dans le champ Entrer le nom du fichier, tapez « intrastat.xml ».
    * Entrez le nom du fichier.  
6. Cliquez sur OK.
    * Examinez le fichier XML généré.  
7. Fermez la page.
8. Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d’échanges de biens.
    * Ouvrez cet écran pour afficher les transactions de déclaration d’échanges de biens qui sont incluses dans le document électronique généré.  
9. Cliquez sur Archive de la déclaration d’échanges de biens.
    * Comme le format ER exécuté ne contient pas de paramètres pour la mise à jour des données d’application, les détails de l’état de déclaration d’échanges de biens n’ont pas été archivés.  
10. Fermez la page.
11. Fermez la page.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]