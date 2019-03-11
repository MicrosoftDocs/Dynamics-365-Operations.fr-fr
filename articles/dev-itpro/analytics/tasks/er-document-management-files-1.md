---
title: ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 1 - Préparer le modèle de données)
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00d366e61077e27a13b13e31a55acc89ae2b0cd0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "345235"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1-prepare-data-model"></a>ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 1 : Préparer le modèle de données)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER. Ces étapes peuvent être effectuées dans n'importe quelle société.

Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».

Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Accéder à la liste des configurations fournies par Microsoft
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Assurez-vous que le fournisseur « Litware, Inc. » est disponible et marqué comme actif.  
2. Sélectionnez le fournisseur « Litware, Inc. » .
3. Cliquez sur Référentiels.
    * Si un référentiel du type « Ressources opérationnelles » existe déjà, ignorez les étapes restantes de la sous-tâche actuelle.  
4. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
5. Dans le champ Type du référentiel de configuration, entrez « Ressources opérationnelles ».
6. Cliquez sur Créer un référentiel.
7. Cliquez sur OK.

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a>Obtenir les configurations de modèle de facture client fournies par Microsoft
1. Cliquez sur Afficher les filtres.
2. Appliquez les filtres suivants : entrez la valeur de filtre « Ressources opérationnelles » dans le champ « Nom » en utilisant l'opérateur de filtre « commence par ». Entrez la valeur de filtre « » dans le champ « Description » en utilisant l'opérateur de filtre « commence par »
3. Cliquez sur Afficher les filtres.
4. Cliquez sur Ouvrir.
5. Dans l'arborescence, sélectionnez « Modèle de facture client ».
    * Sélectionnez la configuration du modèle « Modèle de facture client » pour l'importer.  
6. Cliquez sur Importer.
    * Cliquez sur Importer pour la version 1 de la configuration sélectionnée.  
7. Cliquez sur Oui.
8. Fermez la page.
9. Fermez la page.
10. Cliquez sur Configurations des états.
11. Dans l'arborescence, sélectionnez « Modèle de facture client ».

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a>Créez le modèle dérivé pour prendre en charge l'accès aux fichiers de gestion des documents.
    * Vous créerez votre propre configuration du modèle de facture client en la dérivant de la configuration fournie par Microsoft. Vous utiliserez cette configuration pour implémenter l'accès aux fichiers de gestion des documents et les rendre disponibles pour les documents électroniques que vous créerez en fonction de ce modèle.  
1. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
2. Dans le champ Nouveau, entrez « Provenant du nom : Modèle de facture client, Microsoft ».
3. Dans le champ Nom, tapez « Modèle de facture client (personnalisé) ».
    * Modèle de facture client (personnalisé)  
4. Cliquez sur Créer une configuration.

