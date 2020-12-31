---
title: Concevoir des configurations pour générer des états dans des formats Office avec des images intégrées
description: Les étapes de cette rubrique donnent des informations sur la création de configurations d’états électroniques qui génèrent des documents électroniques aux formats Microsoft Office (Excel et Word) qui contiennent des images intégrées.
author: NickSelin
manager: AnnBe
ms.date: 01/23/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0145565ba060308162620f29a42499b0bffe6496
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684400"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>Concevoir des configurations pour générer des états dans des formats Office avec des images intégrées

[!include [banner](../../includes/banner.md)]

Pour réaliser les étapes de cette procédure, commencez par effectuer la procédure, « ER Créer un fournisseur de configuration et le marquer comme actif ». Cette procédure explique comment créer des configurations d’états électroniques pour générer un document Microsoft Excel ou Word contenant des images intégrées. Dans cette procédure, vous créerez les configurations d’états électroniques requises pour la société fictive, Litware, Inc. Ces étapes peuvent être effectuées à l’aide de l’ensemble de données USMF. Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d’états électroniques a été affecté. Avant de commencer, téléchargez et enregistrez les fichiers répertoriés dans la rubrique d’aide [Intégrer des images et des formes dans les documents commerciaux générés à l’aide de la gestion des états électroniques](../electronic-reporting-embed-images-shapes.md). Les fichiers sont : Modèle pour les chèques.xml, Format d’impression des chèques.xml, Logo de société.png, Image de signature.png, Image de signature 2.png et Modèle de chèque Word.docx.

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
 25. Cliquez sur Parcourir et sélectionnez le fichier que vous avez téléchargé précédemment, Image de signature 2.png.   
 26. Fermez la page.  
 27. Fermez la page.  
 28. Fermez la page.  
 29. Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque.  
 30. Sélectionnez Oui dans le champ Autoriser la création d’une note préliminaire sur des comptes bancaires inactifs.  
 31. Cliquez sur Enregistrer.  
 32. Fermez la page.  
