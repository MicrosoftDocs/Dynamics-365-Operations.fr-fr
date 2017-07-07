---
title: "Mise à niveau des données dans un environnement de bac à sable (sandbox)"
description: "Cette rubrique explique comment effectuer une mise à niveau des données d'AX 2012 vers Dynamics 365 for Finance and Operations dans un environnement de bac à sable (sandbox)."
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
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
ms.openlocfilehash: 7140bf740f37a5eb970a5103750a7095d12a33cc
ms.contentlocale: fr-fr
ms.lasthandoff: 06/15/2017

---

# <a name="data-upgrade-in-a-sandbox-environment"></a>Mise à niveau des données dans un environnement de bac à sable (sandbox)

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

Le résultat de cette tâche est une base de données mise à niveau que vous pouvez utiliser dans un environnement de bac à sable (sandbox). Un environnement de bac à sable (sandbox) est un environnement dans lequel les utilisateurs professionnels et les membres de l'équipe fonctionnelle peuvent valider la fonctionnalité d'application. Cette fonctionnalité inclut les personnalisations et les données importées depuis Microsoft Dynamics AX 2012.

Il est vivement recommandé d'exécuter le processus de mise à niveau des données dans un environnement de développement avant de l'exécuter dans un environnement de bac à sable (sandbox) partagé, car cette approche permet de réduire la durée globale nécessaire à une mise à niveau réussie des données. Pour plus d'informations, voir [Mise à niveau des données dans un environnement de développement](prepare-data-upgrade.md).

## <a name="overview-of-the-sandbox-data-upgrade-process"></a>Vue d'ensemble du processus de mise à niveau des données sandbox

Avant de commencer la mise à niveau des données dans un environnement de bac à sable (sandbox), vous devez avoir déjà mis à niveau les données dans un environnement de développement, comme expliqué dans [Mise à niveau des données dans un environnement de développement](prepare-data-upgrade.md). Les deux processus sont très similaires. La principale différence est qu'un environnement de bac à sable (sandbox) utilise la base de données Microsoft SQL Azure pour le stockage de données, alors qu'un environnement de développement utilise Microsoft SQL Server. Cette différence technique dans la couche de la base de données nécessite que vous modifiez légèrement la procédure de mise à niveau des données dans un environnement de bac à sable (sandbox), car une sauvegarde à partir de l'instance de la base de données AX 2012 ne peut pas être restaurée en base de données SQL.

![Processus de mise à niveau des données sandbox](./media/data-upgrade-sandbox.png)

Voici les principales étapes du processus de mise à niveau.

1. Créez une copie de la base de données AX 2012. Il est vivement recommandé d'utiliser une copie, car vous devez supprimer des objets dans la copie qui sera exportée.
2. Exportez la base de données copiée dans un fichier bacpac à l'aide d'un outil SQL Server gratuit nommé SQLPackage.exe. Cet outil fournit un type spécial de sauvegarde de base de données qui peut être importé dans la base de données SQL.
3. Téléchargez le fichier bacpac dans le stockage Azure.
4. Téléchargez le fichier bacpac sur le serveur d'objets d'application (AOS) de l'environnement de bac à sable (sandbox), puis importez-le à l'aide de SQLPackage.exe. Vous devez ensuite exécuter un script sur la base de données importée pour réinitialiser les utilisateurs de la base de données SQL.
5. Exécutez le package MajorVersionDataUpgrade.zip pour exécuter la mise à niveau des données sur la base de données importée.

## <a name="create-a-copy-of-the-ax-2012-database"></a>Créer une copie de la base de données AX 2012

Vous devez créer une copie de la base de données AX 2012 que vous mettez à niveau, car vous devez supprimer des objets de la base de données. Ces objets comprennent les utilisateurs de l'authentification Microsoft Windows. Ces modifications rendent la base de données modifiée inutilisable pour AX 2012. Au cours de cette étape, vous allez créer une copie de la base de données et supprimer ces objets.

Cette étape doit être effectuée par l'administrateur de la base de données (DBA) ou une personne ayant des connaissances et une expérience similaires.

Pour créer une copie de la base de données, effectuez une sauvegarde de la base de données d'origine et restaurez-la sous un nouveau nom. Vérifiez qu'un espace suffisant est disponible pour les deux bases de données. Vous pouvez créer la copie sur un autre serveur. La version de l'instance de SQL Server qui exécute la base de données n'est pas importante.

Voici un exemple du code qui crée une copie de la base de données. Vous devez modifier cet exemple pour refléter les noms de vos bases de données spécifiques.

    BACKUP DATABASE [AxDB] TO  DISK = N'D:\Backups\axdb_copyForUpgrade.bak' WITH NOFORMAT, NOINIT,  
    NAME = N'AxDB_copyForUpgrade-Full Database Backup', SKIP, NOREWIND, NOUNLOAD, COMPRESSION,  STATS = 10
    GO

    RESTORE DATABASE [AxDB_copyForUpgrade] FROM  DISK = N'D:\Backups\axdb_copyForUpgrade.bak'   WITH  FILE = 1,  
    MOVE N'AXDBBuild_Data' TO N'F:\MSSQL_DATA\AxDB_copyForUpgrade.mdf',  
    MOVE N'AXDBBuild_Log' TO N'G:\MSSQL_LOGS\AxDB_CopyForUpgrade.ldf',  
    NOUNLOAD,  STATS = 5

Une fois la copie créée, exécutez le script Transact-SQL (T-SQL) suivant sur celle-ci.
TODO 

### <a name="export-the-copied-database-to-a-bacpac-file"></a>Exporter la base de données copiée dans un fichier bacpac

Exportez la base de données copiée dans un fichier bacpac à l'aide de l'outil SQLPackage.exe. Cette étape doit être effectuée par l'administrateur de la base de données ou un membre de l'équipe ayant des connaissances équivalentes.

Il est très important d'installer la dernière version de SQL Server Management Studio avant de commencer cette étape. Bien que SQLPackage soit présent dans les versions précédentes de Management Studio, il ne fonctionnera pas correctement pour cette étape sauf si vous installez d'abord la version la plus récente.

Cette étape est importante, car l'exportation devra être effectuée à nouveau pendant le temps d'arrêt avant la mise en service. Voici quelques conseils :

- Le processus bacpac utilise beaucoup de ressources d'E/S et du processeur. Par conséquent, exécutez l'exportation sur un ordinateur à forte puissance.
- SQLPackage doit être exécuté localement sur l'ordinateur qui héberge la base de données. N'exécutez pas SQLPackage sur un ordinateur portable local que vous connectez à l'ordinateur de la base de données, car ce processus utilise également beaucoup de ressources du réseau.

Ensuite, ouvrez une fenêtre **Invite de commandes** en tant qu'administrateur et exécutez les commandes suivantes.

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:export /ssn:localhost /sdn:<database to export> /tf:D:\Exportedbacpac\my.bacpac /p:CommandTimeout=1200 /p:VerifyFullTextDocumentTypesSupported=false

Voici une explication des paramètres :

- **ssn** (nom du serveur source) – Nom du serveur SQL Server d'exportation. Pour notre processus, ce paramètre doit toujours être défini sur **localhost**.
- **sdn** (nom de la base de données source) – Nom de la base de données à exporter.
- **tf** (fichier cible) – Chemin et nom du fichier d'exportation. Le dossier doit déjà exister, mais le fichier sera créé par le processus.
- **/p:CommandTimeout** – Valeur du délai d'expiration par requête. Ce paramètre permet d'exporter des tables volumineuses sans expiration du délai.

### <a name="upload-the-bacpac-file-to-azure-storage"></a>Télécharger le fichier bacpac dans le stockage Azure

Téléchargez le fichier bacpac dans le stockage Azure. Voir UsingStorageExplorer.docx TODO

### <a name="import-the-bacpac-file-into-sql-database"></a>Importer le fichier bacpac dans la base de données SQL

Au cours de cette étape, vous allez importer le fichier bacpac exporté dans l'instance de la base de données SQL utilisée par votre environnement de bac à sable (sandbox). Vous devez d'abord installer la dernière version de Management Studio sur votre ordinateur AOS sandbox. Vous importez ensuite le fichier à l'aide de l'outil SQLPackage.exe.

Vous effectuez ces tâches directement sur l'ordinateur AOS de votre environnement de bac à sable (sandbox), car des règles de pare-feu limitent l'accès à l'instance de la base de données SQL. Toutefois, l'accès est possible sur l'ordinateur AOS.

En ce qui concerne l'étape d'exportation, vous devez disposer de la dernière version de Management Studio avant de commencer l'importation. Cette étape ne fonctionnera pas si vous utilisez une version plus ancienne.

Pour des raisons de performances, il est recommandé de placer le fichier bacpac sur le lecteur D de l'ordinateur AOS. Sur les ordinateurs virtuels Azure, le lecteur D est un disque physique qui a généralement des performances plus élevées que les autres lecteurs disponibles.

Ouvrez une fenêtre **Invite de commandes** en tant qu'administrateur et exécutez les commandes suivantes.

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:import /sf:D:\Exportedbacpac\my.bacpac /tsn:<azure sql database server name>.database.windows.net /tu:sqladmin /tp:<password from LCS> /tdn:<New database name> /p:CommandTimeout=1200 /p:DatabaseEdition=Premium /p:DatabaseServiceObjective=P1

Voici une explication des paramètres :

- **tsn** (nom du serveur cible) – Nom du serveur SQL Azure d'importation. Le nom est disponible dans LCS. Ajoutez-lui le suffixe **.database.windows.net**.
- **tdn** (nom de la base de données cible) – Nom de la base de données d'importation. La base de données ne doit pas déjà exister. Elle sera créée par le processus d'importation.
- **sf** (fichier source) – Chemin et nom du fichier d'importation.
- **tp** (mot de passe cible) – Mot de passe SQL de l'instance de la base de données SQL cible.
- **tu** (utilisateur cible) – Nom d'utilisateur SQL de l'instance de la base de données SQL cible. Il est recommandé d'utiliser **sqladmin**. Vous pouvez récupérer le mot de passe de cet utilisateur à partir de votre projet LCS.
- **/p:CommandTimeout** – Valeur du délai d'expiration par requête. Ce paramètre permet d'exporter des tables volumineuses sans expiration du délai.
- **/p:DatabaseServiceObjective** – Niveau de service de la base de données créée. Vous pouvez vérifier la valeur de la base de données existante à l'aide de Management Studio. Cliquez avec le bouton droit sur la base de données, puis sélectionnez **Propriétés**.

Après avoir exécuté les commandes, l'avertissement suivant s'affiche. Vous pouvez l'ignorer.

![Erreur de bac à sable (sandbox)](./media/sandbox-2.png)
 
### <a name="run-the-majorversiondataupgradezip-package"></a>Exécuter le package MajorVersionDataUpgrade.zip

Exécutez le package déployable de mise à niveau des données comme décrit dans [Mettre à niveau les données dans des environnements de développement, de démonstration ou de bac à sable (sandbox)](upgrade-data-to-latest-update.md).

### <a name="upgrade-a-copy-of-the-database-in-a-development-environment"></a>Mettre à niveau une copie de la base de données dans un environnement de développement

Il est utile de mettre à niveau la même base de données dans un environnement de développement. Si une copie de la base de données est disponible pour les environnements de développement, il est beaucoup plus facile d'examiner les bogues trouvés dans l'environnement de bac à sable (sandbox) mis à niveau.

