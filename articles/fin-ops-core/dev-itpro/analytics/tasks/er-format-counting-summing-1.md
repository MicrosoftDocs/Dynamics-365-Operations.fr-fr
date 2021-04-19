---
title: ER Configurer le format pour effectuer le comptage et la synthèse (Partie 1 – Créer un format)
description: Cette rubrique décrit comment configurer un format de gestion des états électroniques pour effectuer le comptage et la somme en fonction des données de la sortie de texte déjà générée. (Partie 1)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f1db144b2bfafa72abeaa92c6b21de717e4acbf
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749043"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a>ER Configurer le format pour effectuer le comptage et la synthèse (Partie 1 – Créer un format)

[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un format de génération d’états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée. Ces étapes peuvent être effectuées dans n’importe quelle société.

Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».

Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Accéder à la liste des configurations fournies par Microsoft
1. Accédez à Administration d’organisation > Espaces de travail > États électroniques.
    * Assurez-vous que le fournisseur « Litware, Inc. » est disponible et marqué comme actif.  
2. Sélectionnez le fournisseur « Litware, Inc. » .
3. Cliquez sur Référentiels.
    * Si un référentiel du type « Ressources opérationnelles » existe déjà, ignorez les étapes restantes de la sous-tâche actuelle.  
4. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
5. Dans le champ Type du référentiel de configuration, entrez « Ressources opérationnelles ».
6. Cliquez sur Créer un référentiel.
7. Cliquez sur OK.

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a>Obtenir les configurations de déclaration d’échanges de biens fournies par Microsoft
1. Cliquez sur Ouvrir.
2. Dans l’arborescence, sélectionnez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne) ».
3. Cliquez sur Importer.
    * Cliquez sur Importer pour la version 1.1 de la configuration sélectionnée.  
4. Cliquez sur Oui.
5. Fermez la page.
6. Fermez la page.
7. Cliquez sur Configurations des états.
8. Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens ».
9. Dans l’arborescence, sélectionnez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne) ».



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]