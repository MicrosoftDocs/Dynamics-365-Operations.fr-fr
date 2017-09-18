--- 
title: "Importer une configuration dans Lifecycle Services pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut créer une configuration pour la génération d'états électronique (ER) et la charger dans Microsoft Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
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
ms.openlocfilehash: e0681ff81ea673e90b3d281a8e8836e0afb9f5f0
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="upload-a-configuration-into-lifecycle-services-for-electronic-reporting-er"></a>Importer une configuration dans Lifecycle Services pour la gestion des états électroniques (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut créer une configuration pour la génération d'états électronique (ER) et la charger dans Microsoft Lifecycle Services (LCS).

Dans cet exemple, vous allez créer une configuration et la télécharger dans LCS pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les configurations ER sont partagées entre les sociétés. Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ». L'accès à LCS est également requis pour réaliser ces étapes.

1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Sélectionnez « Litware, Inc. » et définissez-le comme actif.
3. Cliquez sur Configurations.

## <a name="create-a-new-data-model-configuration"></a>Créer une configuration de modèle de données
1. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
    * Vous allez créer une configuration qui contient un modèle de données pour les paiements électroniques. Cette configuration de modèle de données sera téléchargée dans LCS ultérieurement.  
2. Tapez « Exemple de configuration de modèle » dans le champ Nom.
    * Exemple de configuration de modèle  
3. Tapez « Exemple de configuration de modèle » dans le champ Description.
    * Exemple de configuration de modèle  
4. Cliquez sur Créer une configuration.
5. Cliquez sur Concepteur de modèles.
6. Cliquez sur Nouveau.
7. Tapez « Point d'entrée » dans le champ Nom.
    * Point d'entrée  
8. Cliquez sur Ajouter.
9. Cliquez sur Enregistrer.
10. Fermez la page.
11. Cliquez sur Modifier le statut.
12. Cliquez sur Terminé.
13. Cliquez sur OK.

## <a name="register-a-new--repository"></a>Enregistrez un nouveau référentiel.
1. Fermez la page.
2. Cliquez sur Référentiels.
    * Cela vous permet d'ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.  
3. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
    * Cela vous permet d'ajouter un référentiel.  
4. Sélectionnez LCS dans le champ Type du référentiel de configuration.
5. Cliquez sur Créer un référentiel.
6. Dans le champ Projet, saisissez ou sélectionnez une valeur.
    * Sélectionnez le projet LCS souhaité. Vous devez avoir accès au projet.  
7. Cliquez sur OK.
    * Effectuez une nouvelle entrée de référentiel.  
8. Dans la liste, marquez la ligne sélectionnée.
    * Sélectionnez l'enregistrement Référentiel LCS.  
    * Notez qu'un référentiel enregistré est marqué par le fournisseur actuel, ce qui signifie que seules les configurations détenues par ce fournisseur peuvent être placées dans ce référentiel et donc être chargées dans le projet LCS sélectionné.  
9. Cliquez sur Ouvrir.
    * Ouvrez le référentiel pour afficher la liste des configurations d'ER. Elle est vide si ce projet n'a pas encore été utilisé pour le partage de configurations d'ER.  
10. Fermez la page.
11. Fermez la page.

## <a name="upload-configuration-into-lcs"></a>Téléchargez la configuration dans LCS.
1. Cliquez sur Configurations.
2. Dans l'arborescence, sélectionnez « Exemple de configuration de modèle ».
    * Sélectionnez une configuration qui est déjà terminée.  
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez la version de la configuration sélectionnée ayant le statut « Terminé ».  
4. Cliquez sur Modifier le statut.
5. Cliquez sur Partager.
    * Le statut de configuration passe de « Terminé » à « Partagé » lorsqu'il est attribué dans LCS.  
6. Cliquez sur OK.
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez la version de configuration dont le statut est « Partagé ».  
    * Notez que le statut de la version sélectionnée est passé de « Terminé » à « Partagé ».  
8. Fermez la page.
9. Cliquez sur Référentiels.
    * Cela vous permet d'ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.  
10. Cliquez sur Ouvrir.
    * Sélectionnez le référentiel LCS et ouvrez- le.  
    * Notez que la configuration sélectionnée est indiquée comme un actif du projet LCS sélectionné.  
    * Ouvrez LCS à l'aide de https://lcs.dynamics.com. Ouvrez un projet utilisé précédemment pour l'enregistrement du référentiel, ouvrez la bibliothèque d'actifs de ce projet, et développez le contenu du type d'actif Configuration GER, la configuration ER téléchargée est disponible. Notez que la configuration LCS téléchargée peut être importée dans une autre instance de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition si les fournisseurs ont accès à ce projet LCS.  

