---
title: Concevoir des expressions de génération d’états électroniques pour appeler les méthodes de classe d’application
description: Ce guide fournit des informations sur la procédure de réutilisation de la logique d’application existante dans les configurations d’états électroniques en appelant les méthodes requises des classes d’application des expressions ER.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3d79d1a4e86731a62de4896a489a13f624ce159f
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682019"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>Concevoir des expressions de génération d’états électroniques pour appeler les méthodes de classe d’application

[!include [banner](../../includes/banner.md)]

Ce guide fournit des informations sur la procédure de réutilisation de la logique d’application existante dans les configurations d’états électroniques en appelant les méthodes requises des classes d’application des expressions ER. Les valeurs des arguments d’appel des classes peuvent être définies dynamiquement au moment de l’exécution : par exemple, sur la base des informations du document d’analyse pour garantir leur exactitude. Dans ce guide, vous allez créer les configurations ER requises pour l’exemple de société, Litware, Inc. Cette procédure est créée pour les utilisateurs ayant le rôle d’administrateur système ou de développeur de gestion des états électroniques. 

Ces étapes peuvent être effectuées à l’aide d’un ensemble de données quelconque. Vous devez également télécharger et enregistrer localement le fichier suivant : (https://go.microsoft.com/fwlink/?linkid=862266): SampleIncomingMessage.txt.

Pour réaliser ces étapes, vous devez commencer par effectuer les étapes de la procédure « Génération d’états électroniques - Créer un fournisseur de configuration et le marquer comme actif ».

1. Accédez à Administration d’organisation > Espaces de travail > États électroniques.
    * Vérifiez que le fournisseur de la configuration pour la société fictive Litware, Inc. est disponible et marqué comme actif. Si vous ne voyez pas ce fournisseur de configuration, vous devez d’abord effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».   
    * Supposons que vous créiez un processus d’analyse des relevés bancaires entrants pour une mise à jour des données d’application. Vous recevrez les relevés bancaires entrants en tant que fichiers TXT contenant les codes IBAN. Dans le cadre du processus d’importation des relevés bancaires, vous devez valider l’exactitude des codes IBAN à l’aide de la logique qui est déjà disponible.   

## <a name="import-a-new-er-model-configuration"></a>Importer une nouvelle configuration du modèle ER
1. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Sélectionnez la vignette Fournisseur Microsoft.  
2. Cliquez sur Référentiels.
3. Cliquez sur Afficher les filtres.
4. Ajoutez un champ de filtre « Nom du type ». Dans le champ Nom, entrez la valeur « ressources », sélectionnez l’opérateur de filtre « contient », puis cliquez sur Appliquer.
5. Cliquez sur Ouvrir.
6. Dans l’arborescence, sélectionnez « Modèle de paiement ».
    * Si le bouton Importer dans l’organisateur Versions n’est pas activé, vous avez déjà importé la version 1 de la configuration ER « Modèle de paiement ». Vous pouvez ignorer les étapes restantes de cette sous-tâche.   
7. Cliquez sur Importer.
8. Cliquez sur Oui.
9. Fermez la page.
10. Fermez la page.

## <a name="add-a-new-er-format-configuration"></a>Ajouter une nouvelle configuration du format ER
1. Cliquez sur Configurations des états.
    * Ajoutez un nouveau format ER pour analyser les relevés bancaires entrants au format TXT.  
2. Dans l’arborescence, sélectionnez « Modèle de paiement ».
3. Cliquez sur Créer la configuration pour ouvrir le menu associé.
4. Dans le champ Nouveau, entrez « Format basé sur le PaymentModel du modèle du paiement ».
5. Dans le champ Nom, tapez « Format d’importation des relevés bancaires (exemple) ».
    * Format d’importation des relevés bancaires (exemple)  
6. Sélectionnez Oui dans le champ Prend en charge l’importation de données.
7. Cliquez sur Créer une configuration.

## <a name="design-the-er-format-configuration---format"></a>Créer la configuration du format ER - format
1. Cliquez sur Concepteur.
    * Le format conçu représente la structure attendue du fichier externe au format TXT.  
2. Cliquez sur Ajouter racine pour ouvrir le menu associé.
3. Dans l’arborescence, sélectionnez « Texte\Souche ».
4. Dans le champ Nom, tapez « Racine ».
    * Racine  
5. Dans le champ Caractères spéciaux, sélectionnez « Nouvelle ligne - Windows (CR LF) ».
    * L’option « Nouvelle ligne - Windows (CR LF) » a été sélectionné dans le champ « Caractères spéciaux ». Selon ce paramètre, chaque ligne du fichier d’analyse est considérée comme un enregistrement distinct.  
6. Cliquez sur OK.
7. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
8. Dans l’arborescence, sélectionnez « Texte\Souche ».
9. Dans le champ Nom, tapez « Lignes ».
    * Lignes  
10. Dans le champ Multiplicité, sélectionnez « Un plusieurs ».
    * L’option « Un plusieurs » a été sélectionnée dans le champ « Multiplicité ». En fonction de ce paramètre, il est prévu qu’au moins une ligne soit présentée dans le fichier d’analyse.  
11. Cliquez sur OK.
12. Dans l’arborescence, sélectionnez « Racine\Lignes ».
13. Cliquez sur Ajouter une séquence.
14. Dans le champ Nom, tapez « Champs ».
    * Champs  
15. Dans le champ Multiplicité, sélectionnez « Un seul ».
16. Cliquez sur OK.
17. Dans l’arborescence, sélectionnez « Racine\Lignes\Champs ».
18. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
19. Dans l’arborescence, sélectionnez « Texte\Chaîne ».
20. Tapez « IBAN » dans le champ Nom.
    * IBAN  
21. Cliquez sur OK.
    * Il a été configuré de manière à ce que chaque ligne du fichier d’analyse contienne le code IBAN.  
22. Cliquez sur Enregistrer.

## <a name="design-the-er-format-configuration--mapping-to-data-model"></a>Créer la configuration du format ER – mise en correspondance avec le modèle de données
1. Cliquez sur Mettre en correspondance vers le modèle.
2. Cliquez sur Nouveau.
3. Dans le champ Définition, tapez « BankToCustomerDebitCreditNotificationInitiation ».
    * BankToCustomerDebitCreditNotificationInitiation  
4. Résolvez les modifications de la définition.
5. Dans le champ Nom, tapez « Mise en correspondance avec le modèle de données ».
    * Mise en correspondance avec le modèle de données  
6. Cliquez sur Enregistrer.
7. Cliquez sur Concepteur.
8. Dans l’arborescence, sélectionnez Dynamics 365 for Operations\Classe.
9. Cliquez sur Ajouter racine.
    * Ajoutez une nouvelle source de données pour appeler la logique d’application existante pour la validation des codes IBAN.  
10. Dans le champ Nom, tapez « check_codes ».
    * check_codes  
11. Dans le champ Classe, tapez « ISO7064 ».
    * ISO7064  
12. Cliquez sur OK.
13. Dans l’arborescence, développez « format ».
14. Dans l’arborescence, développez « format\Racine : Séquence (Racine) ».
15. Dans l’arborescence, sélectionnez « format\Racine : Séquence (Racine)\Lignes : Séquence 1.. * (Lignes) ».
16. Cliquez sur Lier.
17. Dans l’arborescence, développez « format\Racine : Séquence (Racine)\Lignes : Séquence 1.. * (Lignes) ».
18. Dans l’arborescence, développez « format\Racine : Séquence (Racine)\Lignes : Séquence 1..* (Lignes)\Champs : Séquence 1..1 (Champs) ».
19. Dans l’arborescence, sélectionnez « format\Racine : Séquence (Racine)\Lignes : Séquence 1..* (Lignes)\Champs : Séquence 1..1 (Champs)\IBAN : Chaîne (IBAN) ».
20. Dans l’arborescence, développez « Paiements = format.Root.Rows ».
21. Dans l’arborescence, développez « Paiements = format.Root.Rows\Compte créditeur (CreditorAccount) ».
22. Dans l’arborescence, développez « Paiements = format.Root.Rows\Compte créditeur (CreditorAccount)\Identification ».
23. Dans l’arborescence, sélectionnez « Paiements = format.Root.RowsCompte\créditeur(CreditorAccount)\Identification\IBAN ».
24. Cliquez sur Lier.
25. Cliquez sur l’onglet Validations.
26. Cliquez sur Nouveau.
    * Ajoutez une nouvelle règle de validation qui affiche une erreur pour toute ligne du fichier d’analyse qui contient un code IBAN incorrect.  
27. Cliquez sur Modifier la condition.
28. Dans l’arborescence, développez « check_codes ».
29. Dans l’arborescence, sélectionnez « check_codes\verifyMOD1271_36 ».
30. Cliquez sur Ajouter une source de données.
31. Dans le champ Formule, entrez « check_codes.verifyMOD1271_36( ».
    * check_codes.verifyMOD1271_36(  
32. Dans l’arborescence, développez « format ».
33. Dans l’arborescence, développez « format\Racine : Séquence (Racine) ».
34. Dans l’arborescence, développez « format\Racine : Séquence (Racine)\Lignes : Séquence 1.. * (Lignes) ».
35. Dans l’arborescence, développez « format\Racine : Séquence (Racine)\Lignes : Séquence 1..* (Lignes)\Champs : Séquence 1..1 (Champs) ».
36. Dans l’arborescence, sélectionnez « format\Racine : Séquence (Racine)\Lignes : Séquence 1..* (Lignes)\Champs : Séquence 1..1 (Champs)\IBAN : Chaîne (IBAN) ».
37. Cliquez sur Ajouter une source de données.
38. Dans le champ Formule, entrez « check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN) ».
    * check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)  
39. Cliquez sur Enregistrer.
40. Fermez la page.
    * La condition de validation a été configurée pour renvoyer FALSE pour tout code IBAN non valide en appelant la méthode existante « verifyMOD1271_36 » de la classe d’application « ISO7064 ». Notez que la valeur du code IBAN est définie dynamiquement au moment de l’exécution en tant qu’argument de la méthode d’appel basée sur le contenu du fichier TXT d’analyse.   
41. Cliquez sur Modifier le message.
42. Dans le champ Formule, entrez « CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN) ».
    * CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN)  
43. Cliquez sur Enregistrer.
44. Fermez la page.
45. Cliquez sur Enregistrer.
46. Fermez la page.

## <a name="run-the-format-mapping"></a>Exécuter la mise en correspondance des formats
À des fins de test, exécutez la mise en correspondance des formats à l’aide du fichier SampleIncomingMessage.txt que vous avez téléchargé. La sortie générée contient les données importées depuis le fichier TXT sélectionné et transférées vers le modèle de données personnalisé pendant l’importation réelle.   
1. Cliquez sur Exécuter.
    * Cliquez sur Parcourir et accédez au fichier SampleIncomingMessage.txt que vous avez précédemment téléchargé.  
2. Cliquez sur OK.
    * Examinez la sortie au format XML, qui représente les données importées depuis le fichier sélectionné et transférées vers le modèle de données. Notez que seules 3 lignes du fichier TXT importé ont été traitées. Le code IBAN sur la ligne 4 qui n’est pas valide a été ignoré et un message d’erreur s’affiche dans la fenêtre Informations.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]