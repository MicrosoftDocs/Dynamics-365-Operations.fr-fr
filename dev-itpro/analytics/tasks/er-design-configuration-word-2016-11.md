--- 
title: "Définir une configuration pour générer des états au format Microsoft Word pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur bénéficiant du rôle Administrateur système ou Développeur d'états électroniques peut configurer des formats de données de génération d'états électronique (ER) pour générer des états sous forme de fichiers Microsoft Word."
author: NickSelin
manager: AnnBe
ms.date: 12/21/2016
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5adf1d6e6314ac7ea4084cfb3fcde8b83168c7ae
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="design-a-configuration-for-generating-reports-in-microsoft-word-format-for-electronic-reporting-er"></a>Définir une configuration pour générer des états au format Microsoft Word pour la gestion des états électroniques (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur bénéficiant du rôle Administrateur système ou Développeur d'états électroniques peut configurer des formats de données de génération d'états électronique (ER) pour générer des états sous forme de fichiers Microsoft Word. Ces étapes peuvent être effectuées dans la société GBSI.

Pour réaliser ces étapes, vous devez d'abord effectuer les étapes du Guide de tâche de la section « Créer une configuration ER pour générer des états au format OPENXML ». Au préalable, vous devez également télécharger et enregistrer localement les modèles suivants pour l'exemple d'état : http://msdynamics.blob.core.windows.net/media/2016/10/SampleVendPaymDocReport.docx http://msdynamics.blob.core.windows.net/media/2016/10/SampleVendPaymDocReportBounded.docx. Au préalable, vous devez également télécharger et enregistrer localement les modèles suivants pour l'exemple d'état :

http://msdynamics.blob.core.windows.net/media/2016/10/SampleVendPaymDocReport.docx

http://msdynamics.blob.core.windows.net/media/2016/10/SampleVendPaymDocReportBounded.docx

Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Microsoft Dynamics 365 for Operations.


## <a name="select-the-existing-er-report-configuration"></a>Sélectionnez la configuration d'états électroniques existante
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Assurez-vous que le fournisseur de la configuration « Litware, Inc. » est sélectionné comme actif.  
2. Cliquez sur Configurations des états.
    * Nous réutiliserons la configuration ER existante conçue initialement pour générer la sortie d'état au format OPENXML.  
3. Dans l'arborescence, développez « Payment model ».
4. Sélectionnez Modèle de paiement\Exemple d'état sur les feuilles de calcul dans l'arborescence.
5. Cliquez sur Concepteur.

## <a name="replace-the-excel-template-with-the-word-template"></a>Remplacez le modèle Excel par le modèle Word
    * Actuellement, le document Excel est utilisé comme modèle pour générer la sortie au format OPENXML. Nous importerons le modèle de l'état au format de Word.  
1. Cliquez sur Documents joints.
    * Remplacez le modèle Excel existant par le modèle Word SampleVendPaymDocReport.docx, que vous avez téléchargé antérieurement. Notez que ce modèle ne contient que la mise en page du document que nous souhaitons générer comme sortie ER.  
2. Cliquez sur Supprimer.
3. Cliquez sur Oui.
4. Cliquez sur Nouveau.
5. Cliquez sur Fichier.
6. Cliquez sur Parcourir. Accédez à et sélectionnez SampleVendPaymDocReport.docx que vous avez précédemment téléchargé. Cliquez sur OK.
    * Sélectionnez le modèle téléchargé au cours de l'étape précédente.  
7. Dans le champ Modèle, entrez ou sélectionnez une valeur.

## <a name="extend-the-word-template-by-adding-a-custom-xml-part"></a>Développez le modèle Word en ajoutant une partie XML personnalisée
1. Cliquez sur Enregistrer.
    * Outre les modifications de configuration de stockage, l'action Enregistrer met également à jour le modèle Word joint. La structure du format conçu est déplacée vers le document Word joint en tant que nouvelle partie XML personnalisée nommée « État ». Notez que le modèle Word joint contient non seulement la mise en page du document que nous souhaitons générer comme sortie d'ER, mais également la structure des données que l'ER renseignera dans ce modèle au moment de l'exécution.  
2. Cliquez sur Documents joints.
    * Maintenant vous devez lier les éléments de la partie XML personnalisée « État » aux parties du document Word.  
    * Si vous êtes familier avec les documents Word pouvant être conçus comme des formulaires contenant des contrôles de contenu liés avec des éléments de parties XML personnalisées, effectuez toutes les étapes de la prochaine sous-tâche pour créer un document de ce type. Pour plus d'informations, consultez le lien : https://support.office.com/en-us/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US. Sinon, ignorez toutes les étapes de la prochaine sous-tâche.  

## <a name="get-word-with-custom-xml-part-to-do-data-bindings"></a>Faites que Word effectue des liaisons de données avec la partie XML personnalisée
    * Ouvrez ce document dans Word et procédez comme suit : - Ouvrez l'onglet Développeur de Word (personnalisez le ruban s'il n'est pas encore activé).  - Sélectionnez Volet Mappage XML.  - Sélectionnez la partie XML personnalisée « État » dans la recherche.  - Effectuez la mise en correspondance des éléments de la partie XML personnalisée sélectionnée et des contrôles de contenu du document Word.  - Enregistrez le document Word mis à jour sur un lecteur local.  

## <a name="upload-the-word-template-with-custom-xml-part-bounded-to-content-controls"></a>Téléchargez le modèle Word avec la partie XML personnalisée liée aux contrôles de contenu
1. Cliquez sur Supprimer.
2. Cliquez sur Oui.
    * Ajouter un nouveau modèle Si vous avez effectué les étapes de la sous-tâche précédente, sélectionnez le document Word que vous avez préparé et enregistré localement. Sinon, sélectionnez le modèle MS Word SampleVendPaymDocReportBounded.docx de que vous avez téléchargé précédemment.  
3. Cliquez sur Nouveau.
4. Cliquez sur Fichier.
5. Cliquez sur Parcourir. Accédez à et sélectionnez SampleVendPaymDocReportBounded.docx que vous avez précédemment téléchargé. Cliquez sur OK.
6. Dans le champ Modèle, sélectionnez le document téléchargé au cours de l'étape précédente.
7. Cliquez sur Enregistrer.
8. Fermez la page.

## <a name="execute-the-format-to-create-word-output"></a>Exécutez le format pour créer une sortie Word
1. Dans le volet Actions, cliquez sur Configurations.
2. Cliquez sur Paramètres utilisateur.
3. Sélectionnez Oui dans le champ Paramètres d'exécution.
4. Cliquez sur OK.
5. Cliquez sur Modifier.
6. Sélectionnez Oui dans le champ Exécuter le brouillon.
7. Cliquez sur Enregistrer.
8. Fermez la page.
9. Fermez la page.
10. Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.
11. Cliquez sur Lignes.
12. Dans la liste, cochez ou décochez toutes les lignes.
13. Cliquez sur Statut de paiement.
14. Cliquez sur Aucun.
15. Cliquez sur Générer les paiements.
16. Cliquez sur OK.
17. Cliquez sur OK.
    * Analysez la sortie générée. Notez que la sortie créée se présente sous le format Word et contient les détails des paiements traités.  


