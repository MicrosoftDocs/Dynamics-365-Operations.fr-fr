--- 
title: "Exécuter un format pour utiliser les fichiers de gestion des documents dans les sorties de format pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER."
author: NickSelin
manager: AnnBe
ms.date: 10/31/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 6e1d7a54055829a1e9215a44f8eba346291f6717
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="run-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a>Exécuter un format pour utiliser les fichiers de gestion des documents dans les sorties de format pour la gestion des états électroniques (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER. Ces étapes peuvent être effectuées dans la société DEMF.

Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 3 : Créer un format) ».

Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a>Ajoutez les pièces jointes nécessaires pour la commande client d'une facture unique
1. Accédez à Comptabilité client > Factures > Factures client en cours.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez le champ Facture avec la valeur « CIV-000148 ».
    * CIV-000148  
3. Cliquez pour suivre le lien de la facture sélectionnée.
    * CIV-000148  
4. Cliquez pour suivre le lien du champ Commande client.
    * 000148  
5. Dans le champ Lignes ou en-tête, sélectionnez l'option En-tête.
    * Sélectionnez En-tête pour indiquer que cette valeur désigne la cible pour ajouter des pièces jointes.  
6. Cliquez Joindre.
    * Ajoutez quelques fichiers en pièces jointes pour cette commande client. Utilisez les fichiers des types de documents pris en charge par la gestion des documents (avec les extensions de fichier DOCX, DPF, XML, JPG, etc.). Parcourez et sélectionnez les fichiers à joindre et à traiter davantage avec la facture associée dans le message électronique ER.  
7. Cliquez sur Nouveau.
8. Cliquez sur Fichier.
9. Cliquez sur Nouveau.
10. Cliquez sur Fichier.
11. Fermez la page.
12. Fermez la page.
13. Fermez la page.
14. Fermez la page.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>Exécuter l'état désigné pour la facture sélectionnée
1. Accédez à Administration d'organisation > États électroniques > Configurations.
2. Dans l'arborescence, développez « Modèle de facture client ».
3. Dans l'arborescence, développez « Modèle de facture client\Modèle de facture client (personnalisé) ».
4. Dans l'arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé)\Exemple de message de facture électronique ».
5. Cliquez sur Exécuter.
6. Développez la section Enregistrements à inclure ().
7. Cliquez sur Filtre.
8. Sélectionnez la ligne de la table Journal des factures client et du champ Commande client.
9. Dans le champ Critères, tapez « 000148 ».
    * Dans le champ « Commande client » des critères, tapez le numéro de commande 000148.  
10. Cliquez sur OK.
11. Cliquez sur OK.
    * Examinez la sortie générée. Notez que pour chaque pièce jointe, un nœud XML simple a été créé. Le contenu de la pièce jointe est rempli avec la sortie XML au format MIME (base64).  


