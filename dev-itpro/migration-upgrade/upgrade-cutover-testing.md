---
title: "Test de basculement de mise à niveau"
description: "Cette rubrique explique comment tester les tâches qui ont lieu après la désactivation d'AX 2012 mais avant l'activation de Dynamics 365 for Finance and Operations, Enterprise Edition."
author: tariqbell
manager: AnnBe
ms.date: 05/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations, UnifiedOperations, Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 711ad5cc3aafacf209704349effb4e08019205ac
ms.contentlocale: fr-fr
ms.lasthandoff: 06/15/2017

---

# <a name="upgrade-cutover-testing"></a>Test de basculement de mise à niveau

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

*Basculement* est le terme que nous utilisons pour désigner le processus final de mise en service d'un nouveau système. Ce processus de basculement comprend les tâches qui ont lieu après la désactivation de Microsoft Dynamics AX 2012 mais avant l'activation de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. L'objectif du test de basculement de mise à niveau est de tester le processus de basculement, afin de garantir que le basculement réel vers la mise en service se passera en douceur pour toutes les personnes impliquées.

Un basculement implique deux flux de travail principaux :

- **Flux de travail technique** – Ce flux de travail est le processus d'exécution de la mise à niveau des données. Votre entreprise appliquera une limite au temps d'arrêt autorisé. Pendant ce temps d'arrêt, ni AX 2012 ni Finance and Operations ne seront disponibles. Ce flux de travail devra peut-être ajuster la procédure de mise à niveau des données pour respecter la limite de temps d'arrêt de l'entreprise.
- **Flux de travail fonctionnel** – Ce flux de travail comprend les tâches de configuration effectuées à l'issue de la mise à niveau des données. Toutes ces tâches doivent être documentées et quantifiées, et une ressource doit être affectée, car le flux de travail fonctionnel et le flux de travail technique doivent respecter la limite de temps d'arrêt de l'entreprise.

L'illustration suivante présente le processus global de basculement vers la mise en service lorsqu'il se produit dans l'environnement de production.

![Processus de basculement](./media/cutover_1.png)

Ce processus de basculement est différent d'une mise à niveau des données de base dans un environnement de bac à sable (sandbox) de plusieurs manières :

- La base de données AX 2012 n'est pas copiée mais seulement sauvegardée, et la base de données d'origine est modifiée. Cette approche est plus rapide, et la sauvegarde permet la restauration, si elle est requise.
- Comme l'environnement de production pour Finance and Operations a un accès limité, les tâches qui étaient précédemment effectuées sur l'instance sandbox du serveur d'objets d'application (AOS) sont désormais exécutées par l'équipe Microsoft DSE. Il s'agit notamment du téléchargement et de l'importation du fichier bacpac, et de l'exécution du package MajorversionDataUpgrade.zip.
- Nous avons ajouté les tâches suivantes :

    - Effectuez un test de détection de fumée.
    - Exécutez les tâches de configuration de l'application. Cette étape peut être importante, selon la fonctionnalité utilisée. Au cours de cette étape, l'équipe fonctionnelle configure une nouvelle fonctionnalité d'application afin qu'elle soit prête à être utilisée dans le système mis à niveau.
    - Autorisez les utilisateurs à réutiliser le système. Informez votre base d'utilisateurs que la mise à niveau est terminée et qu'ils peuvent réutiliser le système.

## <a name="technical-workstream"></a>Flux de travail technique

Le flux de travail technique implique différents membres de l'équipe technique : l'administrateur de la base de données, l'administrateur du système AX 2012, les administrateurs du serveur et les développeurs qui sont familiarisés avec AX 2012 et Finance and Operations. Cette rubrique décrit quelles tâches impliquent quels rôles.

Au cours du test de basculement, l'équipe technique se concentre sur les tests de performances et de fiabilité du processus de mise à niveau des données, pour s'assurer que la limite de temps d'arrêt de l'entreprise est respectée. Plusieurs éléments matériels et logiciels sont impliqués dans ce processus. Certains de ces éléments sont locaux, tandis que d'autres se trouvent dans le cloud Microsoft. En outre, plusieurs éléments du code personnalisé et du code standard de l'application sont impliqués. Le résultat de ce test devrait être la confiance dans le processus de basculement pour votre environnement.

### <a name="turn-off-the-ax-2012-aos-instances"></a>Désactiver les instances AOS AX 2012

Cette tâche implique l'administrateur du système AX 2012 et les administrateurs du serveur.

Les zones suivantes doivent être validées :

- **Traitements par lots en cours d'exécution au moment du basculement** – Un traitement par lots à long terme qui a déjà commencé à s'exécuter empêche l'arrêt du système. Planifiez à l'avance vos traitements par lots, afin de pouvoir arrêter vos instances AOS au moment souhaité. Vous devrez peut-être planifier les traitements par lots afin qu'ils soient terminés avant de désactiver AX 2012.
- **Systèmes intégrés** – Il se peut que d'autres systèmes soient intégrés à l'environnement AX 2012. Vous devez tenir compte de ces systèmes dans votre plan de désactivation d'AX 2012. Par exemple, vous devrez peut-être désactiver les systèmes intégrés quelque temps avant de désactiver AX 2012 proprement dit, afin que les transactions restantes puissent être terminées. La configuration requise pour les systèmes intégrés varie fortement d'une entreprise à l'autre. Par conséquent, votre équipe d'experts doit planifier ce scénario de manière indépendante.

### <a name="create-a-backup-of-the-ax-2012-database"></a>Créer une sauvegarde de la base de données AX 2012

Cette tâche implique l'administrateur de la base de données. La sauvegarde est utilisée si une restauration est requise. Elle est également utilisée comme un point de référence qui est conservé pendant une période et indique l'état du système au moment du basculement.

Les zones suivantes doivent être validées :

- Obtenez des minutages concrets pour le processus de sauvegarde.
- Ajustez les options de sauvegarde utilisées (par exemple, compression et non-compression), pour garantir l'expérience la plus rapide possible.

### <a name="export-the-database-to-bacpac"></a>Exporter la base de données dans bacpac

Cette tâche implique l'administrateur de la base de données. Le résultat de cette tâche est le fichier d'exportation qui sera téléchargé dans Microsoft Azure pour le nouveau système.

Les zones suivantes doivent être validées :

- Obtenez des minutages concrets pour le processus de sauvegarde.
- Optimisez le processus d'exportation pour garantir l'expérience la plus rapide possible. L'optimisation peut nécessiter les tâches suivantes :

    - Mesurez les ressources système pendant l'exportation, par exemple l'UC, les E/S de disque et la mémoire.
    - Si des goulots d'étranglement des ressources sont trouvés, créez un plan pour les atténuer. En général, vous atténuez ces goulots d'étranglement en augmentant les ressources requises.

### <a name="upload-the-bacpac-file-to-azure-storage"></a>Télécharger le fichier bacpac dans le stockage Azure

Cette tâche implique l'administrateur de la base de données ou les administrateurs du serveur. Pendant cette tâche, le fichier bacpac est déplacé dans Azure.

Les zones suivantes doivent être validées :

- Sélectionnez la machine qui est utilisée pour le téléchargement, et vérifiez que l'explorateur de stockage Azure est configuré et prêt à l'emploi.
- Obtenez des minutages concrets pour le processus de téléchargement en le mesurant plusieurs fois. Les temps de téléchargement varient, en fonction de la vitesse de votre connexion Internet et de l'emplacement géographique du centre de données Azure associé à votre emplacement.

### <a name="download-and-import-the-bacpac-file-to-the-azure-sql-database"></a>Télécharger et importer le fichier bacpac dans la base de données SQL Azure

Lorsque cette tâche a lieu pendant la mise en service, elle est effectuée par l'équipe Microsoft DSE. Toutefois, pendant le test de basculement, elle implique l'administrateur de la base de données. Le résultat de cette tâche est le fichier d'exportation qui sera téléchargé dans Azure pour le nouveau système.

Les zones suivantes doivent être validées :

- Obtenez des minutages concrets pour le processus d'importation.
- Optimisez le processus d'exportation pour garantir l'expérience la plus rapide possible. L'optimisation peut nécessiter les tâches suivantes :

    - Mesurez les ressources système pendant l'exportation. Voici quelques exemples :

        - **Sur l'ordinateur AOS :** UC, E/S de disque et mémoire
        - **Sur l'instance de la base de données SQL Azure :** débit de la base de données SQL. Vous pouvez surveiller le DTU SQL Azure dans Microsoft SQL Server Management Studio sur l'ordinateur AOS en consultant la vue système sys.dm_resource_stats.

    - Si des goulots d'étranglement des ressources sont trouvés, créez un plan pour les atténuer. En général, vous atténuez ces goulots d'étranglement en augmentant les ressources requises. Comme cette machine est hébergée par Microsoft, vous devez envoyer une demande à Microsoft pour augmenter les ressources si elles constituent un goulot d'étranglement.

### <a name="run-the-majorversiondataupgradezip-package"></a>Exécuter le package MajorVersiondataUpgrade.zip

Lorsque cette tâche a lieu pendant la mise en service, elle est effectuée par l'équipe Microsoft DSE. Toutefois, pendant le test de basculement, elle implique les développeurs. Pendant cette tâche, l'ancienne structure de la base de données devient la structure du nouveau système.

Le processus de synchronisation de la base de données s'exécute dans le cadre de cette tâche. La synchronisation de la base de données peut prendre beaucoup de temps dans certains cas, par exemple lorsqu'un index en cluster a été modifié sur une table, car cette opération est une opération coûteuse dans SQL.

Il est vivement recommandé d'exécuter d'abord votre processus d'analyse et de débogage dans un environnement de développement. Dans un environnement de bac à sable (sandbox), les options de débogage et d'analyse sont plus limitées. L'objectif est d'avoir peu ou pas de problèmes à résoudre pendant le test de basculement.

Les zones suivantes doivent être validées :

- Obtenez des minutages concrets pour le processus d'importation.
- Optimisez le processus pour garantir l'expérience la plus rapide. L'optimisation peut nécessiter les tâches suivantes :

    - Surveillez les performances des scripts de mise à niveau individuels via la table ReleaseUpdateScriptsExecution.
    - Ajustez les scripts pour optimiser les performances. Cette tâche peut nécessiter la personnalisation du code X++ d'un script pour l'optimiser pour votre ensemble de données.
    - Surveillez le DTU SQL Azure à l'aide de la surveillance Microsoft Dynamics Lifecycle Services (LCS) ou de la vue système sys.dm_resources_stats dans Management Studio. Si la limite des ressources est atteinte, vous devez demander un niveau de base de données plus élevé à l'équipe Microsoft DSE.

### <a name="roll-back-to-ax-2012"></a>Restaurer AX 2012

L'objectif de cette tâche est de restaurer la base de données à l'aide de la sauvegarde qui a été effectuée lors de la désactivation et de la réactivation d'AX 2012. L'état des systèmes intégrés devra également être restauré. Toutefois, comme les systèmes intégrés varient d'une entreprise à l'autre, vous devez planifier ce scénario de manière indépendante, selon vos circonstances spécifiques. Bien qu'il soit peu probable que vous ayez à effectuer une restauration, il est très important d'avoir un processus testé au cas où cela est nécessaire.

## <a name="functional-workstream"></a>Flux de travail fonctionnel

Après la mise à niveau des données, plusieurs tâches de configuration sont nécessaires dans le nouvel environnement. L'objectif de ce flux de travail est de documenter et de quantifier toutes les tâches de configuration, et d'affecter une ressource à chaque tâche, pour garantir que ces tâches peuvent être effectuées avec le flux de travail technique pendant le temps d'arrêt.

Généralement, les tâches fonctionnelles impliquent de modifier les valeurs de paramètres système spécifiques ou d'autres données de configuration. Ces tâches sont identifiées par le biais de la passe complète de tests fonctionnels, qui est une activité distincte du test de basculement. Lorsqu'une tâche de ce type est identifiée, elle doit être examinée avec la ressource fonctionnelle et votre développeur.

Des modifications plus importantes peuvent nécessiter d'écrire un nouveau script personnalisé de mise à niveau des données pour mettre à jour les données pendant le processus de mise à niveau des données. Toutefois, la ressource fonctionnelle peut exécuter manuellement de petites modifications via le nouveau système après la mise à niveau des données.

Les modifications plus importantes qui ont de nouveaux scripts de mise à niveau des données doivent être testées. Par conséquent, une ou plusieurs itérations supplémentaires du package MajorVersionDataUpgrade.zip doivent être exécutées. Il est important d'évaluer le coût de réexécution du package par rapport au coût de la saisie manuelle des données.

Pour chaque modification manuelle, une tâche doit être ajoutée au document du plan de basculement. Cette tâche doit afficher les informations suivantes :

-   Quelle est la tâche, et en quoi consiste-t-elle ?
-   Qui doit l'effectuer ?
-   Quelle est sa durée ?

