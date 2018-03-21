--- 
title: "Créer une configuration de mise en correspondance de modèle (ER)"
description: "Cette procédure permet de créer une configuration de mise en correspondance des modèles d'états électroniques et d'utiliser les fonctions ER intégrées pour effectuer des calculs globaux efficaces."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
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
ms.sourcegitcommit: 74606b1378e94e8a6945a408520c8b68648970d8
ms.openlocfilehash: f7206126bfa6150078f1bfb4f7e07c1cf2819ce0
ms.contentlocale: fr-fr
ms.lasthandoff: 02/07/2018

---
# <a name="create-a-model-mapping-configuration-er"></a>Créer une configuration de mise en correspondance de modèle (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure permet de créer une configuration de mise en correspondance des modèles d'états électroniques et d'utiliser les fonctions ER intégrées pour effectuer des calculs globaux efficaces. Dans cette procédure, vous créerez une configuration pour la société fictive, Litware, Inc. 

Cette procédure est créée pour les utilisateurs auxquels le rôle Administrateur système ou Développeur d'états électroniques a été affecté.

Ces étapes peuvent être effectuées à l'aide d'un ensemble de données quelconque. Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».

1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme actif. Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure, « Créer un fournisseur de configuration et le marquer comme actif ».  
2. Cliquez sur Configurations des états.
3. Cliquez sur Afficher les filtres.
4. Dans le champ « Nom », entrez la valeur de filtre « Déclaration d'échanges de biens » et utilisez l'opérateur de filtre « commence par ».
    * Appliquez ce filtre permettent de rechercher la configuration du modèle de données « Déclaration d'échanges de biens ». Il peut exister dans l'arborescence de configurations. Dans ce cas, ignorez la prochaine sous-tâche.   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a>Obtenir la configuration du modèle de déclaration d'échanges de biens fournie par Microsoft
1. Fermez la page.
2. Fermez la page.
3. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez la vignette Fournisseur Microsoft.  
5. Cliquez sur Référentiels.
    * Cliquez sur Référentiels dans la vignette Fournisseur Microsoft.  
6. Cliquez sur Afficher les filtres.
7. Dans le champ « Nom du type », entrez la valeur de filtre « ressources » et utilisez l'opérateur de filtre « contient ». 
8. Cliquez sur Ouvrir.
9. Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens ».
10. Cliquez sur Importer.
11. Cliquez sur Oui.
    * Vous avez importé la configuration de modèle ER contenant le modèle de données que vous utiliserez pour explorer la façon dont la nouvelle fonctionnalité ER peut être utilisée.  
12. Fermez la page.
13. Fermez la page.
14. Cliquez sur Configurations des états.

## <a name="add-a-new-model-mapping-configuration"></a>Ajouter une nouvelle configuration de mise en correspondance de modèle
1. Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens ».
2. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
3. Dans le champ Nouveau, entrez « Mise en correspondance de modèle basée sur le modèle de données Déclaration d'échanges de biens ».
4. Dans le champ Nom, tapez « Exemple de mise en correspondance de déclaration d'échanges de biens ».
    * Exemple de mise en correspondance de déclaration d'échanges de biens  
5. Cliquez sur Créer une configuration.

