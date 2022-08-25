---
title: Générer des états dans des formats Office avec des images intégrées
description: Cet article décrit comment créer des configurations pour la gestion des états électroniques pour générer des documents électroniques dans Excel et Word contenant des images intégrées.
author: kfend
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dfd4aca1013d7fdf408f9057810feedc4b44e586
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290272"
---
# <a name="generate-reports-in-office-format-that-have-embedded-images"></a>Générer des états dans des formats Office avec des images intégrées

[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur jouant le rôle de « Administrateur système » ou de « Développeur d’états électroniques » peut créer des configurations d’états électroniques (ER) pour générer des documents électroniques au format MS Office (Excel et Word) contenant des images intégrées.

Dans cet exemple, vous utiliserez les configurations ER créées pour la société fictive, « Litware, Inc. ».  Pour réaliser ces étapes, vous devez d’abord effectuer les étapes du guide de tâche « ER Créer des états aux formats MS Office avec des images intégrées (Partie 2 : Examiner les configurations) ». Ces étapes peuvent être effectuées dans la société « USMF ».


## <a name="run-format-with-initial-model-mapping"></a>Exécuter le format avec la mise en correspondance initiale du modèle
1. Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires.
2. Utilisez le filtre rapide pour filtrer sur le champ Compte bancaire avec une valeur de « USMF OPER ».
3. Dans le volet Actions, cliquez sur Paramétrer.
4. Cliquez sur Vérifier.
5. Cliquer sur Test d’impression.
    * Exécutez le format à des fins de test.  
6. Sélectionnez Oui dans le champ Format de chèque négociable.
7. Cliquez sur OK.
    * Examinez la sortie créée. Le logo de la société est présenté dans l’état ainsi que la signature de la personne autorisée. L’image de la signature est extraite du champ du type de données « Conteneur » de l’enregistrement de mise en page de chèque associé au compte bancaire sélectionné.  
8. Développez la section Copies.
9. Cliquez sur Modifier.
10. Dans le champ Filigrane, entrez « Imprimer le filigrane comme annulé ».
    * Modifiez le paramètre de mise en page du filigrane pour afficher le texte du filigrane lors de la génération du document dans un élément au format Excel.  
11. Cliquer sur Test d’impression.
12. Cliquez sur OK.
    * Examinez la sortie créée. Le filigrane s’affiche dans l’état créé conformément à l’option de sélection.  
13. Fermez la page.
14. Dans le volet Actions, cliquez sur Gérer les paiements.
15. Cliquez sur Chèques.
16. Cliquez sur Afficher les filtres.
17. Appliquez les filtres suivants : entrez la valeur de filtre « 381 », « 385 », « 389 » dans le champ « Numéro de chèque » en utilisant l’opérateur de filtre « est l’un de ».
18. Dans la liste, marquez toutes les lignes.
19. Cliquez sur Imprimer une copie du chèque.
    * Exécutez le format pour réimprimer les chèques sélectionnés.  
    * Examinez la sortie créée. Les chèques sélectionnés ont été réimprimés. Le logo et les libellés de la société ne sont pas imprimés, car ils sont présentés sur le formulaire pré-imprimé.  

## <a name="modify-the-mapping-of-the-imported-data-model"></a>Modifier la mise en correspondance du modèle de données importé
1. Fermez la page.
2. Fermez la page.
3. Accédez à Administration d’organisation > États électroniques > Configurations.
4. Dans l’arborescence, sélectionnez « Modèle pour les chèques »
5. Cliquez sur Concepteur.
6. Cliquez sur Mettre en correspondance le modèle à la source de données.
7. Cliquez sur Concepteur.
    * Nous modifierons la liaison de l’élément de signature du modèle de données pour obtenir l’image de la signature à partir du fichier qui a été lié à l’enregistrement de mise en page de chèque associé au compte bancaire sélectionné.  
8. Désactivez Afficher les détails.
9. Dans l’arborescence, développez « layout ».
10. Dans l’arborescence, développez « layout\signature »
11. Dans l’arborescence, sélectionnez « layout\signature\image = chequesaccount.’<Relations’.BankChequeLayout.Signature1Bmp ».
12. Dans l’arborescence, développez « chequesaccount ».
13. Dans l’arborescence, développez « chequesaccount\<Relations ».
14. Dans l’arborescence, développez « chequesaccount\<Relations\BankChequeLayout ».
15. Dans l’arborescence, développez « chequesaccount\<Relations\BankChequeLayout\<Relations ».
16. Dans l’arborescence, développez « chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents ».
17. Dans l’arborescence, sélectionnez « chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer() ».
18. Cliquez sur Lier.
19. Cliquez sur Enregistrer.
20. Fermez la page.
21. Fermez la page.
22. Fermez la page.
23. Fermez la page.

## <a name="run-format-using-the-adjusted-model-mapping"></a>Exécuter le format avec la mise en correspondance ajustée du modèle
1. Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez le champ Compte bancaire avec la valeur « USMF OPER ».
3. Dans le volet Actions, cliquez sur Paramétrer.
4. Cliquez sur Vérifier.
5. Cliquer sur Test d’impression.
6. Cliquez sur OK.
    * Examinez la sortie créée. L’image de la pièce jointe Gestion des documents est présentée comme la signature d’une personne autorisée.  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a>Utiliser le document MS Word comme modèle dans le format importé
1. Fermez la page.
2. Fermez la page.
3. Accédez à Administration d’organisation > États électroniques > Configurations.
4. Dans l’arborescence, développez « Modèle pour les chèques »
5. Dans l’arborescence, sélectionnez « Modèle pour les chèques\Format d’impression des chèques ».
6. Cliquez sur Concepteur.
7. Cliquez sur Documents joints.
8. Cliquez sur Supprimer.
9. Cliquez sur Oui.
10. Cliquez sur Nouveau.
11. Cliquez sur Fichier.
    * Cliquez sur Parcourir et sélectionnez le fichier « Modèle de chèque Word.docx » téléchargé à l’avance.  
12. Fermez la page.
13. Dans le champ Modèle, entrez ou sélectionnez une valeur.
14. Cliquez sur Enregistrer.
15. Fermez la page.
16. Cliquez sur Modifier.
17. Sélectionnez Oui dans le champ Exécuter le brouillon.
18. Fermez la page.
19. Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires.
20. Utilisez le filtre rapide pour filtrer sur le champ Compte bancaire avec une valeur de « USMF OPER ».
21. Cliquez sur Vérifier.
22. Cliquer sur Test d’impression.
23. Cliquez sur OK.
    * Examinez la sortie créée. La sortie a été générée en tant que document Word avec des images intégrées présentant le logo de la société, la signature d’une personne autorisée et le texte sélectionné du filigrane.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
