--- 
title: "Définir la dépendance des configurations à partir d'autres composants pour la gestion des états électroniques (ER)"
description: "Pour réaliser ces étapes, vous devez commencer par effectuer les étapes du guide de tâche, ER Gérer les configurations de mise en correspondance de modèle, et vous devez avoir accès à Microsoft Dynamics Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 06/23/2017
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
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: a1ccd440353e986d296de370506fb1951331e2cf
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---
# <a name="define-the-dependency-of-configurations-from-other-components-for-electronic-reporting-er"></a>Définir la dépendance des configurations à partir d'autres composants pour la gestion des états électroniques (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Pour réaliser ces étapes, vous devez commencer par effectuer les étapes du guide de tâche, ER Gérer les configurations de mise en correspondance de modèle, et vous devez avoir accès à Microsoft Dynamics Lifecycle Services (LCS).

Cette procédure indique comment créer une configuration ER et spécifier sa dépendance vis-à-vis d'autres composants logiciels, afin vous puissiez garantir que la configuration est correctement téléchargée vers une version spécifique de Microsoft Dynamics 365 for Finance and Operations. Dans cet exemple, vous créerez les configurations ER requises pour la société fictive, Litware, Inc. 

Cette procédure est destinée aux utilisateurs auxquels le rôle Administrateur système ou Développeur d'états électroniques a été affecté. Les étapes peuvent être effectuées dans n'importe quelle société, car les configurations ER sont partagées entre les sociétés. 

1. Accédez à Administration d'organisation > États électroniques > Configurations.
    * Assurez-vous que l'arborescence de configurations contient la configuration « Exemple de modèle de données » et les articles subordonnés. Sinon, effectuez les étapes du guide de tâche, ER Gérer les configurations de mise en correspondance de modèle, puis redémarrez ce guide.   

## <a name="define-the-dependency-of-er-configurations-from-other-components"></a>Définir la dépendance des configurations ER vis-à-vis d'autres composants
1. Dans l'arborescence, développez « Exemple de modèle de données ».
2. Dans l'arborescence, sélectionnez « Exemple de modèle de données\Exemple de mise en correspondance ».
    * Nous avons sélectionné la version brouillon de la configuration de mise en correspondance de modèle « Exemple de mise en correspondance ». Nous allons définir sa dépendance vis-à-vis d'autres composants logiciels. Cette étape est considérée comme une condition préalable au contrôle du téléchargement de la version de cette configuration à partir d'un référentiel ER et à toute utilisation ultérieure de cette version.   
3. Développez la section Conditions préalables.
    * Notez que le groupe de composants prérequis « Implémentations » a été ajouté automatiquement à ce stade. Ce groupe contient le composant prérequis qui fait référence à la configuration de modèle de données et dont l'indicateur Implémentation est activé. Cet indicateur montre que la configuration de mise en correspondance de modèle « Exemple de mise en correspondance » est considérée comme l'implémentation du modèle de données « Exemple de modèle de données ». Ce composant forcera ER à télécharger la configuration de mise en correspondance « Exemple de mise en correspondance », à partir d'un référentiel ER lorsque la configuration de modèle « Exemple de modèle de données », est téléchargée.   
4. Cliquez sur Modifier.
    * Une seule dépendance de la version actuelle d'une configuration vis-à-vis d'un composant logiciel peut être spécifiée à l'aide de la définition du type du composant, et de la version du composant ou d'une plage de versions de composant.  
    * Les dépendances souhaitées peuvent être regroupées. Lorsque le type de regroupement « Tous sur » est sélectionné, la condition de dépendance de ce groupe est considérée comme remplie lorsque chaque condition de dépendance de ce groupe et du groupe subordonné est remplie. Lorsque le type de regroupement « Un sur » est sélectionné, la condition de dépendance de ce groupe est considérée comme remplie lorsqu'au moins une condition de dépendance de ce groupe est remplie.   
5. Cliquez sur Nouveau.
6. Sélectionnez le composant prérequis Produit.
7. Sélectionnez Microsoft Dynamics 365 for Operations (1611).
8. Dans le champ Version, tapez « [7.1.1541.3036,8) ».
    * [7.1.1541.3036,8)  
    * Les dépendances entrées sont évaluées lorsque cette configuration est téléchargée à partir d'un référentiel ER. Cette version de configuration est téléchargée à partir du référentiel ER lorsque la version 1 de la configuration « Exemple de modèle de données » est déjà en place ou téléchargée à l'avance. Si elle est téléchargée à l'avance, elle doit être exécutée dans Finance and Operations, dont la version doit être 7.1.1541.3036 ou ultérieure, mais ne doit pas dépasser la version principale 8.   
9. Cliquez sur Enregistrer.
10. Fermez la page.
11. Cliquez sur Modifier le statut.
12. Cliquez sur Terminé.
13. Cliquez sur OK.
14. Dans l'arborescence, sélectionnez « Exemple de modèle de données\Exemple de mise en correspondance (autre) ».
15. Cliquez sur Modifier.
16. Cliquez sur Nouveau.
17. Sélectionnez le composant prérequis Produit.
18. Sélectionnez Microsoft Dynamics AX 7.0 RTW.
19. Dans le champ Version, tapez « [7.0.1265.3015,7.1) ».
    * [7.0.1265.3015,7.1)  
    * Les dépendances sont évaluées lorsque la configuration est téléchargée à partir d'un référentiel ER. Cette version de configuration est téléchargée à partir du référentiel ER lorsque la version 1 de la configuration « Exemple de modèle de données » est déjà en place ou téléchargée à l'avance. Si elle est téléchargée à l'avance, elle doit être exécutée dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, dont la version doit être 7.0.1265.3015 ou ultérieure, mais ne doit pas dépasser la version secondaire 1.   
20. Cliquez sur Enregistrer.
21. Fermez la page.
22. Cliquez sur Modifier le statut.
23. Cliquez sur Terminé.
24. Cliquez sur OK.

## <a name="configure-the-er-repository"></a>Configurer le référentiel ER
1. Fermez la page.
2. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Ouvrez la liste des référentiels ER pour le fournisseur ER actuel, Litware, Inc.  
3. Dans la liste, marquez la ligne sélectionnée.
4. Cliquez sur Référentiels.
5. Cliquez sur Afficher les filtres.
6. Entrez la valeur de filtre « LCS » dans le champ « Nom du type » à l'aide de l'opérateur de filtre « contient ».
    * Si le référentiel LCS est déjà enregistré pour le fournisseur ER actuel, vous pouvez ignorer les étapes restantes de cette sous-tâche. Si le référentiel LCS n'est pas déjà enregistré, effectuez les étapes restantes.   
7. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
8. Dans le champ Type du référentiel de configuration, entrez « LCS ».
9. Cliquez sur Créer un référentiel.
10. Dans le champ Projet, saisissez ou sélectionnez une valeur.
    * Sélectionnez le projet LCS souhaité dans la recherche du champ « Projet ».  
11. Cliquez sur OK.
12. Fermez la page.

## <a name="upload-configurations-to-lcs"></a>Télécharger les configurations dans LCS
1. Cliquez sur Configurations des états.
2. Dans l'arborescence, sélectionnez « Exemple de modèle de données ».
3. Sélectionnez la version terminée de cette configuration.
4. Cliquez sur Modifier le statut.
5. Cliquez sur Partager.
6. Cliquez sur OK.
    * La version 1 de cette configuration de modèle a été téléchargée dans LCS à l'aide du projet LCS pour le référentiel ER précédemment configuré.   
7. Dans l'arborescence, développez « Exemple de modèle de données ».
8. Dans l'arborescence, sélectionnez « Exemple de modèle de données\Exemple de mise en correspondance ».
9. Sélectionnez la version terminée de cette configuration.
10. Cliquez sur Modifier le statut.
11. Cliquez sur Partager.
12. Cliquez sur OK.
    * La version 1.1 de cette configuration de mise en correspondance de modèle a été téléchargée dans LCS à l'aide du projet LCS pour le référentiel ER précédemment configuré.   
13. Dans l'arborescence, sélectionnez « Exemple de modèle de données\Exemple de mise en correspondance (autre) ».
14. Sélectionnez la version terminée de cette configuration.
15. Cliquez sur Modifier le statut.
16. Cliquez sur Partager.
17. Cliquez sur OK.
    * La version 1.1 de cette configuration de mise en correspondance de modèle a été téléchargée dans LCS à l'aide du projet LCS pour le référentiel ER précédemment configuré.   

## <a name="evaluate-er-configuration-dependencies"></a>Évaluer les dépendances de configuration ER
    * Nous supprimerons les configurations créées du système et les téléchargerons à partir du référentiel LCS.  
1. Dans l'arborescence, sélectionnez « Exemple de modèle de données\Exemple de mise en correspondance ».
2. Cliquez sur Supprimer.
3. Cliquez sur Oui.
4. Dans l'arborescence, sélectionnez « Exemple de modèle de données\Exemple de mise en correspondance (autre) ».
5. Cliquez sur Supprimer.
6. Cliquez sur Oui.
7. Dans l'arborescence, sélectionnez « Exemple de modèle de données\Exemple de format ».
8. Cliquez sur Supprimer.
9. Cliquez sur Oui.
10. Dans l'arborescence, sélectionnez « Exemple de modèle de données ».
11. Cliquez sur Supprimer.
12. Cliquez sur Oui.
13. Fermez la page.
    * Ouvrez la liste des référentiels ER pour le fournisseur ER actuel, Litware, Inc.  
14. Cliquez sur Référentiels.
15. Cliquez sur Afficher les filtres.
16. Entrez la valeur de filtre « LCS » dans le champ « Nom du type » à l'aide de l'opérateur de filtre « contient ».
17. Cliquez sur Ouvrir.
18. Dans l'arborescence, sélectionnez « Exemple de modèle de données ».
    * Notez que vous pouvez afficher une évaluation indiquant si les conditions préalables ont été remplies pour chaque version des configurations ER pour le référentiel actuel. Pour afficher cette évaluation, cliquez sur Vérifier les conditions préalables.   
19. Cliquez sur Vérifier les conditions préalables.
20. Cliquez sur Importer.
21. Cliquez sur Oui.
22. Fermez la page.
23. Fermez la page.
24. Fermez la page.
25. Accédez à Administration d'organisation > États électroniques > Configurations.
26. Dans l'arborescence, développez « Exemple de modèle de données ».
    * Notez que la configuration de mise en correspondance de modèle « Exemple de mise en correspondance » a été téléchargée avec la configuration de modèle de données sélectionnée. Les deux fichiers sont téléchargés ensemble, car la configuration « Exemple de mise en correspondance » a été définie comme implémentant le modèle de données sélectionné et qu'elle s'applique à Finance and Operations. La configuration « Exemple de mise en correspondance (autre) » n'a pas été téléchargée, car la condition pour la version d'application requise n'est pas remplie.   
    * Si vous vous connectez à Dynamics 365 for Finance and Operations, Enterprise Edition, enregistrez le même fournisseur, accédez au même projet LCS et téléchargez la même configuration de modèle de données, la configuration « Exemple de mise en correspondance (autre) » sera téléchargée, tandis que la configuration « Exemple de mise en correspondance » sera ignorée.  


