---
title: Concevoir des configurations pour générer des états dans des formats Office avec des images intégrées
description: Cet article décrit comment créer des configurations pour générer des documents électroniques aux formats Excel et Word contenant des images intégrées.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 255b9a4e5276a9a80a4fbc15076f78a25c918e80
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886641"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>Concevoir des configurations pour générer des états dans des formats Office avec des images intégrées

[!include [banner](../../includes/banner.md)]

Pour réaliser les étapes de cette procédure, commencez par effectuer la procédure, « ER Créer un fournisseur de configuration et le marquer comme actif ». Cette procédure explique comment créer des configurations d’états électroniques pour générer un document Microsoft Excel ou Word contenant des images intégrées. Dans cette procédure, vous créerez les configurations d’états électroniques requises pour la société fictive, Litware, Inc. Ces étapes peuvent être effectuées à l’aide de l’ensemble de données USMF. Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d’états électroniques a été affecté. Avant de commencer, téléchargez et enregistrez les fichiers suivants : 

| Description                                          | Nom de fichier                   |
|------------------------------------------------------|-----------------------------|
| Configuration de modèle de données ER                          | [Modèle pour les chèques.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| Configuration de format ER                              | [Format d’impression des chèques.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| Image du logo de l’entreprise                                   | [Logo de société au format .png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| Image de signature                                      | [Image de signature au format .png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| Image de signature alternative                          | [Signature image 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Modèle Microsoft Word pour l’impression des chèques de paiement  | [Cheque template Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

## <a name="verify-prerequisites"></a>Vérification des conditions requises  
 1. Accédez à Administration d’organisation > Espaces de travail > États électroniques.  
 2. Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme actif. Si ce fournisseur de configuration ne s’affiche pas, effectuez les étapes de la procédure, « Créer un fournisseur de configuration et le marquer comme actif. »   
 3. Cliquez sur Configurations des états.  
 
## <a name="add-a-new-er-model-configuration"></a>Ajouter une nouvelle configuration du modèle ER  
 1. Au lieu de créer un modèle, vous pouvez charger le fichier de configuration du modèle ER (Modèle pour les chèques.xml) que vous avez enregistré précédemment. Ce fichier contient l’exemple de modèle de données pour les chèques de paiement et la mise en correspondance du modèle de données avec les composants de données de l’application Dynamics 365 for Operations.   
 2. Dans l’organisateur Versions, cliquez sur Exchange.   
 3. Cliquez sur Charger depuis le fichier XML.  
 4. Cliquez sur Parcourir, puis sélectionnez Modèle pour les chèques.xml.   
 5. Cliquez sur OK.  
 6. Le modèle chargé sera utilisé comme source de données d’informations pour générer des documents contenant des images au format Excel et Word.  

## <a name="add-a-new-er-format-configuration"></a>Ajouter une nouvelle configuration du format ER  
 1. Au lieu de créer un format, vous pouvez charger le fichier de configuration du format ER (Format d’impression des chèques.xml) que vous avez enregistré précédemment. Ce fichier contient l’exemple de mise en page du format d’impression des chèques avec le formulaire préimprimé et la mise en correspondance de ce format avec le modèle de données « Modèle pour les chèques ».   
 2. Cliquez sur Échanger.  
 3. Cliquez sur Charger depuis le fichier XML.  
 4. Cliquez sur Parcourir et sélectionnez le fichier Format d’impression des chèques.xml.   
 5. Cliquez sur OK.  
 6. Dans l’arborescence, développez « Modèle pour les chèques »  
 7. Dans l’arborescence, sélectionnez « Modèle pour les chèques\Format d’impression des chèques ».  
 8. Le format chargé est utilisé pour générer des documents contenant des images au format Excel et Word.   

## <a name="configure-er-user-parameters"></a>Configurer les paramètres utilisateur ER  
 1. Dans le volet Actions, cliquez sur Configurations.  
 2. Cliquez sur Paramètres utilisateur.  
 3. Sélectionnez Oui dans le champ Paramètres d’exécution.  
  Activez l’indicateur « Exécuter le brouillon » pour démarrer la version brouillon du format sélectionné au lieu de la version terminée.  
 4. Cliquez sur OK.  

## <a name="configure-cash--bank-management-parameters"></a>Configurer les paramètres de gestion des disponibilités et des banques  
 1. Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires.  
 2. Utilisez le filtre rapide pour filtrer sur le champ Compte bancaire avec une valeur de « USMF OPER ».  
 3. Dans le volet Actions, cliquez sur Paramétrer.  
 4. Cliquez sur Vérifier.  
 5. Développez la section Paramétrage.  
 6. Cliquez sur Modifier.  
 7. Sélectionnez Oui dans le champ Logo de société.  
 8. Cliquez sur Logo de société.  
 9. Cliquez sur Modifier.  
 10. Cliquez sur Parcourir et sélectionnez le fichier que vous avez téléchargé précédemment, Logo de société.png.   
 11. Cliquez sur Enregistrer.  
 12. Fermez la page.  
 13. Développez la section Signature.  
 14. Sélectionnez Oui dans le champ Imprimer la première signature.  
 15. Cliquez sur Modifier.  
 16. Cliquez sur Parcourir et sélectionnez le fichier que vous avez téléchargé précédemment, Image de signature.png.   
 17. Développez la section Copies.  
 18. Dans le champ Filigrane, sélectionnez une option.  
 19. Sélectionnez Oui dans le champ Format d’exportation électronique générique.  
 20. Sélectionnez la configuration « Format d’impression des chèques ».  
 21. Le format ER sélectionné est utilisé pour l’impression des chèques.  
 22. Cliquez Joindre.  
 23. Cliquez sur Nouveau.  
 24. Cliquez sur Fichier.  
 25. Cliquez sur Parcourir et sélectionnez le fichier que vous avez téléchargé précédemment, Signature image 2.png.   
 26. Fermez la page.  
 27. Fermez la page.  
 28. Fermez la page.  
 29. Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque.  
 30. Sélectionnez Oui dans le champ Autoriser la création d’une note préliminaire sur des comptes bancaires inactifs.  
 31. Cliquez sur Enregistrer.  
 32. Fermez la page.  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
