---
title: ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 4 – Exécuter le format)
description: Cette rubrique décrit comment configurer un format de gestion des états électroniques pour utiliser les fichiers de gestion des documents dans la sortie de gestion des états électroniques. (Partie 4)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 11b446d21a7ae57ffa2cccf983777beb882bf77de6b54c2d1aef810028a6d343
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727459"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4---run-format"></a>ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 4 – Exécuter le format)

[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un format de génération d’états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER. Ces étapes peuvent être effectuées dans la société DEMF.

Pour effectuer ces étapes, vous devez d’abord effectuer les étapes de la procédure « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 3 : Créer un format) ».

Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a>Ajoutez les pièces jointes nécessaires pour la commande client d’une facture unique
1. Accédez à Comptabilité client > Factures > Factures client en cours.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez le champ Facture avec la valeur « CIV-000148 ».
    * CIV-000148  
3. Cliquez pour suivre le lien de la facture sélectionnée.
    * CIV-000148  
4. Cliquez pour suivre le lien du champ Commande client.
    * 000148  
5. Dans le champ Lignes ou en-tête, sélectionnez l’option En-tête.
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

## <a name="run-the-designed-report-for-the-selected-invoice"></a>Exécuter l’état désigné pour la facture sélectionnée
1. Accédez à Administration d’organisation > États électroniques > Configurations.
2. Dans l’arborescence, développez « Modèle de facture client ».
3. Dans l’arborescence, développez « Modèle de facture client\Modèle de facture client (personnalisé) ».
4. Dans l’arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé)\Exemple de message de facture électronique ».
5. Cliquez sur Exécuter.
6. Développez la section Enregistrements à inclure ().
7. Cliquez sur Filtre.
8. Sélectionnez la ligne de la table Journal des factures client et du champ Commande client.
9. Dans le champ Critères, tapez « 000148 ».
    * Dans le champ « Commande client » des critères, tapez le numéro de commande 000148.  
10. Cliquez sur OK.
11. Cliquez sur OK.
    * Examinez la sortie générée. Notez que pour chaque pièce jointe, un nœud XML simple a été créé. Le contenu de la pièce jointe est rempli avec la sortie XML au format MIME (base64).  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]