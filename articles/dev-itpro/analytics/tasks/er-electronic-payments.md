--- 
title: "Générer les documents électroniques pour les paiements à l'aide d'une configuration de format pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut utiliser une nouvelle configuration de format pour la génération d'états électronique (ER) pour générer des documents électroniques pour traiter les paiements."
author: NickSelin
manager: AnnBe
ms.date: 11/10/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: a5d958d3b55bfa76f3cfbb3c1a289e4e89c49146
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="generate-electronic-documents-for-payments-using-a-format-configuration-for-electronic-reporting-er"></a>Générer les documents électroniques pour les paiements à l'aide d'une configuration de format pour la gestion des états électroniques (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut utiliser une nouvelle configuration de format pour la génération d'états électronique (ER) pour générer des documents électroniques pour traiter les paiements. Ces étapes peuvent être effectuées dans la société fictive GBSI.

Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer une configuration avec le format du document de paiement ».


## <a name="change-the-configuration-of-the-electronic-payment-method"></a>Modifier la configuration de la méthode de paiement électronique
1. Accédez à Comptabilité fournisseur > Paramétrage des paiements > Modes de paiement.
2. Basculez la section de format de fichier pour la développer, si nécessaire.
3. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez le champ Mode de paiement avec une valeur « Électronique ».
4. Cliquez sur Modifier.
5. Définissez le champ de génération d'états électroniques génériques sur Oui.
    * Sélectionnez Oui pour utiliser le modèle de génération d'états électroniques génériques pour la génération des fichiers de paiement.  
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
    * DE - 01001  
10. Tapez Paiement dans le champ Description.
    * Paiement  
11. Entrez un nombre dans le champ Débit.
    * 1 000  
12. Cliquez sur l'onglet Paiement.
13. Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
14. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez la valeur électronique.  
15. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
16. Cliquez sur Enregistrer.
17. Cliquez sur Générer les paiements.
18. Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
19. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
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


