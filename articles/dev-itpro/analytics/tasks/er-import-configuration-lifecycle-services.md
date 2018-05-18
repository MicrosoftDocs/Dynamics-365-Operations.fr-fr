--- 
title: "Importer une configuration à partir de Lifecycle Services pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut importer une nouvelle version d'une configuration pour la génération d'états électroniques (ER) à partir de Microsoft Lifecycle Services (LCS)."
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 9eb4f54897c84b98828c927f0f93613583fd4599
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="import-a-configuration-from-lifecycle-services-for-electronic-reporting-er"></a>Importer une configuration à partir de Lifecycle Services pour la gestion des états électroniques (ER)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut importer une nouvelle version d'une configuration pour la génération d'états électroniques (ER) à partir de Microsoft Lifecycle Services (LCS).

Dans cet exemple, vous allez sélectionner la version souhaitée de la configuration ER et l'importer pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les configurations ER sont partagées entre les sociétés. Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Charger une configuration ER dans Lifecycle Services ». L'accès à LCS est également requis pour réaliser ces étapes.

1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Cliquez sur Configurations.

## <a name="delete-a-shared-version-of-data-model-configuration"></a>Supprimer une version partagée de la configuration du modèle de données
1. Dans l'arborescence, sélectionnez « Exemple de configuration de modèle ».
    * La première version d'un exemple de configuration de modèle de données a été créée et publiée dans LCS durant la procédure « Charger une configuration ER dans Lifecycle Services ». Dans cette procédure, vous supprimerez cette version de la configuration ER. Cette version d'un exemple de configuration de modèle de données sera importée ultérieurement à partir de LCS.  
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez la version de cette configuration dont le statut est « Partagé ». Ce statut indique que la configuration a été publiée dans LCS.  
3. Cliquez sur Modifier le statut.
4. Cliquez sur Interrompre.
    * Faites passer le statut de la version sélectionnée de « Partagé » à « Interrompu » pour le rendre disponible pour la suppression.  
5. Cliquez sur OK.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez la version de cette configuration dont le statut est « Interrompu ».  
7. Cliquez sur Supprimer.
8. Cliquez sur Oui.
    * Notez que seule la version temporaire 2 de la configuration de modèle de données sélectionnée est disponible.  
9. Fermez la page.

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a>Importer une version partagée de la configuration du modèle de données à partir de LCS
1. Dans la liste, marquez la ligne sélectionnée.
    * Ouvrez la liste des référentiels pour le fournisseur de configuration « Litware, Inc. » .  
2. Cliquez sur Référentiels.
3. Cliquez sur Ouvrir.
    * Sélectionnez le référentiel LCS et ouvrez- le.  
4. Dans la liste, marquez la ligne sélectionnée.
    * Sélectionnez la première version « Exemple de configuration de modèle » dans la liste des versions.  
5. Cliquez sur Importer.
6. Cliquez sur Oui.
    * Confirmez l'importation de la version sélectionnée de LCS.  
    * Notez que le message d'information (au-dessus de l'écran) confirme la réussite de l'importation de la version sélectionnée.  
7. Fermez la page.
8. Fermez la page.
9. Cliquez sur Configurations.
10. Dans l'arborescence, sélectionnez « Exemple de configuration de modèle ».
11. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez la version de cette configuration dont le statut est « Partagé ».  
    * Notez que seule la version partagée 1 de la configuration de modèle de données sélectionnée est maintenant disponible.  


