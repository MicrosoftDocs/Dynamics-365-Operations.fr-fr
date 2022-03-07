---
title: ER Générer les documents électroniques pour les paiements à l’aide d’une configuration de format
description: Cette rubrique décrit comment utiliser une nouvelle configuration de format de gestion des états électroniques pour générer les documents électroniques pour le traitement des paiements.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f62d7cd690406647886f9d6d1cb1491b691d4159
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752482"
---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a>ER Générer les documents électroniques pour les paiements à l’aide d’une configuration de format

[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d’états électroniques peut utiliser une nouvelle configuration de format pour la génération d’états électronique (ER) pour générer des documents électroniques pour traiter les paiements. Ces étapes peuvent être effectuées dans la société fictive GBSI.

Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer une configuration avec le format du document de paiement ».


## <a name="change-the-configuration-of-the-electronic-payment-method"></a>Modifier la configuration de la méthode de paiement électronique
1. Accédez à Comptabilité fournisseur > Paramétrage des paiements > Modes de paiement.
2. Basculez la section de format de fichier pour la développer, si nécessaire.
3. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez le champ Mode de paiement avec une valeur « Électronique ».
4. Cliquez sur Modifier.
5. Définissez le champ de génération d’états électroniques génériques sur Oui.
    * Sélectionnez Oui pour utiliser le modèle de génération d’états électroniques génériques pour la génération des fichiers de paiement.  
6. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Sélectionnez la configuration de format BACS (nom fictif britannique).
8. Cliquez sur Enregistrer.
9. Fermez la page.

## <a name="test-the-format-of-generated-payment-files"></a>Tester le format des fichiers de paiement générés
1. Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.
2. Cliquez sur Nouveau.
3. Dans la liste, marquez la ligne sélectionnée.
4. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez VendPay.  
6. Cliquez sur Enregistrer.
7. Cliquez sur Lignes.
8. Tapez DEMF dans le champ Société.
    * DEMF  
9. Dans le champ Compte, spécifiez les valeurs « DE-01001 ».
    * DE – 01001  
10. Tapez Paiement dans le champ Description.
    * Paiement  
11. Entrez un nombre dans le champ Débit.
    * 1 000  
12. Cliquez sur l’onglet Paiement.
13. Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
14. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Sélectionnez la valeur électronique.  
15. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
16. Cliquez sur Enregistrer.
17. Cliquez sur Générer les paiements.
18. Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
19. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Sélectionnez la valeur électronique.  
20. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez la valeur électronique.  
21. Tapez une valeur dans le champ Nom du fichier.
    * Tapez Paiements, par exemple.  
22. Dans le champ Compte bancaire, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
23. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez la valeur GBSI OPER.  
24. Cliquez sur OK.
25. Cliquez sur OK.
    * Analysez le fichier de paiement créé au format XML. Comparez-le à la structure de document conçue et aux attributs de transaction de paiement définis.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]