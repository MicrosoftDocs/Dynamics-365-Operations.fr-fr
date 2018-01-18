---
title: "Réinitialiser le mini-data warehouse d'états financiers"
description: "Cette rubrique décrit la procédure de réinitialisation du mini-data warehouse d'états financiers."
author: aolson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: aloson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 5b956dcc5a4a93033396ae0ffcf8b7aeba2cf3f2
ms.openlocfilehash: a07e8b5bae2c4f71e9212cd2f8080d2481769818
ms.contentlocale: fr-fr
ms.lasthandoff: 12/14/2017

---

# <a name="reset-the-financial-reporting-data-mart"></a>Réinitialiser le mini-data warehouse d'états financiers

[!include[banner](../includes/banner.md)]

Cette rubrique explique la procédure de réinitialisation du mini-data warehouse d'états financiers pour les versions suivantes :

- Version 7.2.6.0 et ultérieure de Microsoft Dynamics 365 for Finance and Operations Financial Reporting
- Version 7.0.10000.4 et ultérieure de Microsoft Dynamics 365 for Finance and Operations Financial Reporting
- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (local)

Pour obtenir la version 7.2.6.0 de Finance and Operations Financial Reporting, vous pouvez télécharger l'article KB 4052514 à l'adresse <https://fix.lcs.dynamics.com/Issue/Resolved?kb=4052514>.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a>Réinitialiser le mini-data warehouse d'états financiers pour la version 7.2.6.0 et ultérieure de Finance and Operations Financial Reporting

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a>Réinitialiser le mini-data warehouse d'états financiers à partir du concepteur d'états

> [!NOTE]
> Les étapes décrites dans ce processus sont prises en charge par la version 7.2.6.0 et ultérieure de Finance and Operations Financial Reporting. Si vous disposez d'une version antérieure, contactez l'équipe de support pour obtenir de l'aide.

Dans les scénarios spécifiques, vous devrez peut-être réinitialiser le mini-data warehouse pour les états financiers. Vous pouvez effectuer cette tâche dans le client Concepteur d'états. Voici quelques scénarios où vous devrez peut-être réinitialiser le mini-data warehouse :

- La base de données Finance and Operations a été restaurée, mais pas celle du mini-data warehouse.
- Des données incorrectes s'affichent pour une période.
- Le support technique vous demande de réinitialiser le mini-data warehouse dans le cadre d'une étape de dépannage.

La réinitialisation du mini-data warehouse doit être effectuée uniquement à des périodes où peu de traitements sont exécutés sur la base de données. Les états financiers seront indisponibles pendant le processus de réinitialisation.

#### <a name="reset-the-data-mart"></a>Réinitialiser le mini-data warehouse

Pour réinitialiser le mini-data warehouse, dans le concepteur d'états, dans le menu **Outils**, sélectionnez **Réinitialiser le mini-data warehouse**. La boîte de dialogue qui s'affiche comporte deux sections : **Statistiques** et **Réinitialiser**.

[![Boîte de dialogue Réinitialiser le mini-data warehouse](./media/Reset-72.jpg)](./media/Reset-72.jpg)

##### <a name="integration-attempts"></a>Tentatives d'intégration

La grille **Tentatives d'intégration** affiche le nombre de tentatives d'intégration de transactions par le système. Le système continue d'essayer d'intégrer les données au fil des jours si les premières tentatives sont infructueuses. Vous saurez que le mini-data warehouse doit être réinitialisé si le nombre de tentatives est égal à 8 ou plus, et s'il existe plusieurs enregistrements de combinaison de dimensions ou de transaction. Dans ce cas, un état des données ne sera pas généré.

##### <a name="data-status"></a>Statut des données

La grille **Statut des données** fournit un instantané des transactions, des taux de change et des valeurs de dimension dans le mini-data warehouse. Un grand nombre d'enregistrements périmés indique que plusieurs mises à jour des enregistrements ont été effectuées. Cette situation peut ralentir les délais de génération d'états.

##### <a name="misaligned-main-account-categories"></a>Catégories de compte principal non alignées

Si vous utilisez une version antérieure à la version 7.2.1 de Microsoft Dynamics 365 for Finance and Operations Financial Reporting, vous devrez peut-être réinitialiser le mini-data warehouse si vous renommez des comptes et déplacez des comptes entre des catégories de compte. Ces actions peuvent entraîner un alignement incorrect des catégories de compte principal. Le champ **Catégories de compte principal non alignées** s'affiche si vous rencontrez ce problème.

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a>Réinitialiser le mini-data warehouse dans la version 7.2.6.0 de Finance and Operations Financial Reporting

Pour réinitialiser le mini-data warehouse dans la version 7.2.6.0 et antérieure de Finance and Operations Financial Reporting, dans la boîte de dialogue **Réinitialiser le mini-data warehouse**, activez la case à cocher **Réinitialiser le mini-data warehouse**, puis sélectionnez **OK**. Vous devez réinitialiser le mini-data warehouse uniquement pendant les interruptions planifiées.

[![Case à cocher Réinitialiser le mini-data warehouse](./media/Reset-72.jpg)](./media/Reset-72.jpg)

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a>Réinitialiser le mini-data warehouse et sélectionner un motif dans la version 7.3.0 de Microsoft Dynamics 365 for Finance and Operations Financial Reporting

Si vous déterminez qu'une réinitialisation du mini-data warehouse est nécessaire, activez la case à cocher **Réinitialiser le mini-data warehouse**, puis sélectionnez un motif dans le champ **Motif**. Les options suivantes sont disponibles :

- **Données manquantes ou incorrectes** – Sur la base des statistiques, vous avez déterminé que des données sont peut-être manquantes. Avant de continuer, nous vous recommandons de contacter le support technique pour déterminer la cause principale.
- **Restaurer la base de données** – La base de données Finance and Operations a été restaurée, mais pas celle du mini-data warehouse d'états financiers.
- **Autre** – Vous réinitialisez le mini-data warehouse pour un autre motif. Si vous êtes préoccupé par un problème, contactez le support technique pour l'identifier.

[![Réinitialiser le mini-data warehouse](./media/Integration.png)](./media/Integration.png)

> [!NOTE]
> Vérifiez que le chargement initial de toutes les tâches de réinitialisation du mini-data est terminé avant de commencer la réinitialisation. Pour ce faire, recherchez une valeur dans la colonne Heure de la dernière exécution sous **Outils** &gt; **Statut de l'intégration**.

#### <a name="clear-users-and-companies"></a>Effacer les utilisateurs et les sociétés

Activez la case à cocher **Effacer les utilisateurs et les sociétés** si vous avez restauré votre base de données, mais vous avez ensuite apporté des modifications aux utilisateurs ou sociétés. Vous devez rarement activer cette case à cocher.

Lorsque vous êtes prêt à démarrer le processus de réinitialisation, sélectionnez **OK**. Vous êtes invité à confirmer que vous êtes prêt à démarrer le processus. Notez que les états financiers ne seront pas disponibles lors de la réinitialisation et de l'intégration des données d'origine qui a lieu par la suite.

Si vous souhaitez examiner le statut de l'intégration, sélectionnez &gt; **Outils** **Statut de l'intégration** pour afficher la dernière date d'exécution de l'intégration et le statut.

[![Afficher le statut de l'intégration](./media/New-integration.PNG)](./media/New-integration.PNG)

> [!NOTE]
> La réinitialisation est terminée lorsque toutes les mises en correspondance affichent le statut RanToCompletion et que la fenêtre Statut de l'intégration indique « Intégration terminée » dans le coin inférieur gauche.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a>Réinitialiser le mini-data warehouse d'états financiers pour la version 7.0.10000.4 et ultérieure de Finance and Operations Financial Reporting

Si vous restaurez votre base de données Finance and Operations à partir d'une sauvegarde ou copiez la base de données à partir d'un autre environnement, vous devez suivre les étapes de cette section pour garantir que le mini-data warehouse d'états financiers utilise correctement la base de données Finance and Operations restaurée.

> [!NOTE]
> Les étapes de ce processus sont prises en charge pour la version 7.0.1 de l'application Microsoft Dynamics AX (mai 2016) (version d'application 7.0.1265.23014 et version 7.0.10000.4 de Financial Reporting) et ultérieure. Si vous disposez d'une version antérieure de Finance and Operations, contactez le support technique pour obtenir de l'aide.

### <a name="export-report-definitions"></a>Exporter des définitions d'état

Effectuez d'abord les étapes ci-après pour exporter les conceptions d'état à partir du concepteur d'états.

1. Dans le concepteur d'états, sélectionnez **Société** &gt; **Groupes de blocs élémentaires**.
2. Sélectionnez le groupe de blocs élémentaires à exporter, puis sélectionnez **Exporter**.

    > [!NOTE]
    > Pour Finance and Operations, un seul groupe de blocs élémentaires est pris en charge, **Valeur par défaut**.

3. Sélectionnez des définitions de rapport à exporter :

    - Pour exporter toutes les définitions d'état et les blocs élémentaires associés, sélectionnez **Sélectionner tout**.
    - Pour exporter des états, lignes, colonnes, organigrammes ou ensembles de dimensions spécifiques, sélectionnez l'onglet approprié, puis les éléments à exporter. Maintenez la touche Ctrl enfoncée pour sélectionner plusieurs articles dans un onglet. Lorsque vous sélectionnez des états à exporter, les lignes, colonnes, arborescences et ensembles de dimensions associés sont sélectionnés.

4. Sélectionnez **Exporter**.
5. Entrez un nom et sélectionnez un emplacement sûr où vous souhaitez enregistrer les définitions d'état exportées.
6. Sélectionnez **Enregistrer**.

Vous pouvez copier ou télécharger le fichier dans un emplacement sûr. Ainsi, le fichier pourra être importé dans un autre environnement ultérieurement. Pour plus d'informations sur l'utilisation d'un compte de stockage Microsoft Azure, voir [Transférer les données avec l'utilitaire de ligne de commande AzCopy](/azure/storage/storage-use-azcopy).

> [!NOTE]
> Microsoft ne fournit pas un compte de stockage dans le cadre de l'accord Finance and Operations. Vous devez acheter un compte de stockage ou utiliser le compte de stockage d'un abonnement Azure distinct.

> [!WARNING]
> Tenez compte du comportement du lecteur D sur les machines virtuelles Azure. Ne stockez pas définitivement vos groupes de blocs élémentaires exportés sur le lecteur D. Pour plus d'informations sur les lecteurs temporaires, voir [Présentation du lecteur temporaire sur les machines virtuelles Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

### <a name="stop-services"></a>Arrêter les services

Les services Microsoft Windows suivants maintiendront les connexions ouvertes dans la base de données Finance and Operations. Par conséquent, vous devez utiliser le Bureau à distance Microsoft pour vous connecter à tous les ordinateurs de l'environnement, puis utiliser services.msc pour arrêter ces services.

- Service de publication World Wide Web (sur tous les ordinateurs Application Object Servers [AOS])
- Service de gestion des traitements par lots Microsoft Dynamics 365 for Finance and Operations (sur les ordinateurs AOS non privés uniquement)
- Service de traitement Management Reporter 2012 (sur les ordinateurs Business Intelligence [BI] uniquement)

### <a name="reset"></a>Rétablir

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a>Télécharger le package MinorVersionDataUpgrade.zip le plus récent

Téléchargez le package MinorVersionDataUpgrade.zip le plus récent. Pour obtenir des instructions sur la recherche et le téléchargement de la version correcte du package de mise à niveau des données, voir [Télécharger le dernier package déployable de mise à niveau des données](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-package). 

Une mise à niveau n'est pas nécessaire pour télécharger le package MinorVersionDataUpgrade.zip. Par conséquent, vous devez simplement suivre les étapes décrites dans la section « Télécharger le dernier package déployable de mise à niveau des données » de cette rubrique. Vous pouvez ignorer toutes les autres étapes de la rubrique.

#### <a name="run-scripts-against-the-finance-and-operations-database"></a>Exécuter les scripts sur la base de données Finance and Operations

Exécutez les scripts suivants sur la base de données Finance and Operations (et non sur la base de données d'états financiers) :

- DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
- DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Ces scripts garantissent que les utilisateurs, les rôles et les paramètres de suivi de modifications sont corrects.

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a>Exécuter une commande Windows PowerShell pour réinitialiser la base de données

Sur l'ordinateur AOS, démarrez Microsoft Windows PowerShell en tant qu'administrateur et exécutez les commandes suivantes pour réinitialiser l'intégration entre Finance and Operations et les états financiers.

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

Voici une explication des paramètres dans la commande **Reset-DatamartIntegration** :

- Les valeurs valides pour **-Reason** sont **SERVICING**, **BADDATA** et **OTHER**.
- Le paramètre **-ReasonDetail** est texte libre.
- Les paramètres reason et reason detail sont stockés dans le contrôle de télémétrie/d'environnement.

> [!NOTE]
> Après avoir exécuté les commandes, vous êtes invité à entrer **O** pour confirmer la réinitialisation de la base de données.

#### <a name="restart-services"></a>Redémarrer les services

Utilisez services.msc pour redémarrer les services que vous avez arrêtés précédemment :

- Le service de publication World Wide Web (sur tous les ordinateurs AOS)
- Service de gestion des traitements par lots Microsoft Dynamics 365 for Finance and Operations (sur les ordinateurs AOS non privés uniquement)
- Service de traitement Management Reporter 2012 (sur les ordinateurs BI uniquement)

#### <a name="import-report-definitions"></a>Importer des définitions d'état

Importez vos conceptions d'états à partir du concepteur d'état à l'aide du fichier créé lors de l'exportation.

1. Dans le concepteur d'états, sélectionnez **Société** &gt; **Groupes de blocs élémentaires**.
2. Sélectionnez le groupe de blocs élémentaires à exporter, puis sélectionnez **Exporter**.

    > [!NOTE]
    > Pour Finance and Operations, un seul groupe de blocs élémentaires est pris en charge, **Valeur par défaut**.

3. Sélectionnez le bloc élémentaire **Valeur par défaut**, puis sélectionnez **Importer**.
4. Sélectionnez le fichier contenant les définitions d'état exportées, puis sélectionnez **Ouvrir**.
5. Dans la boîte de dialogue **Importer**, sélectionnez les définitions de rapport à importer :

    - Pour importer toutes les définitions d'état et les blocs élémentaires associés, sélectionnez **Sélectionner tout**.
    - Pour importer uniquement certains rapports, certaines lignes, colonnes, arborescences ou certains ensembles de dimensions, sélectionnez les rapports, les lignes, les colonnes, les arborescences ou les ensembles de dimensions à importer.

6. Sélectionnez **Importer**.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a>Réinitialiser le mini-data warehouse d'états financiers pour Finance and Operations (local)

1. Demandez à tous les utilisateurs de quitter le concepteur d'états et la zone États financiers de Finance and Operations.
2. Exécutez le script suivant sur la base de données d'états financiers (MRDB).

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ```

3. Tronquez ou supprimez tous les enregistrements de la table FINANCIALREPORTS dans la base de données Finance and Operations (AXDB).
4. Tronquez ou supprimez tous les enregistrements de la table FINANCIALREPORTVERSION, si cette table existe dans la base de données Finance and Operations. Si la table n'existe pas dans la base de données Finance and Operations, ignorez cette étape.
5. Exécutez le script **ResetDatamart.sql** sur la base de données d'états financiers. Ce script désactive l'intégration du mini-data warehouse, supprime toutes les données du mini-data warehouse, puis réactive l'intégration du mini-data warehouse.

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ------------------------------
    PRINT 'Drop archive tables'
    ------------------------------
    DECLARE @tableId nvarchar(max)
    DECLARE dropCursor CURSOR LOCAL FAST_FORWARD FOR
    SELECT Id FROM [Datamart].Archive
    OPEN dropCursor
    FETCH NEXT FROM dropCursor INTO @tableId
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'FactStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].FactStaging' + @tableId)
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationStaging' + @tableId)
        FETCH NEXT FROM dropCursor INTO @tableId
    END
    CLOSE dropCursor
    DEALLOCATE dropCursor
    IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationProcessing' and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationProcessing')
    ------------------------------
    PRINT 'Begin Truncating tables'
    ------------------------------
    DECLARE @tablename nvarchar(200)
    DECLARE @schemaname nvarchar(200)
    DECLARE clear_tables CURSOR
        FOR SELECT TABLE_NAME, TABLE_SCHEMA FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'Datamart' AND TABLE_TYPE='BASE TABLE'
    PRINT 'remove check constraints'
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename + '] NOCHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'delete data from tables and rebuild indexes'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
            IF(EXISTS (select TOP 1 1 from sys.foreign_keys where referenced_object_id = OBJECT_ID(@schemaname + '.' + @tablename)) OR
            EXISTS(SELECT TOP 1 1 FROM sys.sql_expression_dependencies sed
            INNER JOIN sys.objects o ON sed.referencing_id = o.[object_id]
            WHERE o.[type] = 'V' 
            AND referenced_schema_name = @schemaname
            AND referenced_entity_name = @tablename))
            BEGIN
            PRINT 'deleting from ' + @tablename
            EXEC('DELETE FROM [' + @schemaname + '].[' + @tablename + ']')
            END
            ELSE
            BEGIN
            PRINT 'truncating from ' + @tablename
            EXEC('TRUNCATE TABLE [' + @schemaname + '].[' + @tablename + ']')
            END
        END
        EXEC('ALTER INDEX ALL ON [' + @schemaname + '].[' + @tablename + '] REBUILD')
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'reenable check constraints'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename +'] WITH CHECK CHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    DEALLOCATE clear_tables
    ------------------------------
    PRINT 'Complete Truncating tables'
    ------------------------------
    ------------------------------
    PRINT 'Remove indexes from DimensionCombination'
    ------------------------------
    DECLARE @indexname nvarchar(200)
    DECLARE drop_indexes CURSOR
    FOR SELECT Name FROM sys.indexes WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]') AND is_primary_key = 0
    OPEN drop_indexes
    FETCH NEXT FROM drop_indexes INTO @indexname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('DROP INDEX [' + @indexname + '] on [Datamart].[DimensionCombination]')
        FETCH NEXT FROM drop_indexes INTO @indexname
    END
    CLOSE drop_indexes
    DEALLOCATE drop_indexes
    ------------------------------
    PRINT 'Drop Columns on DimensionCombination'
    ------------------------------
    DECLARE @objectname nvarchar(200)
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId', 'InactiveDimensions')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombination] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationResolving'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationResolving]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationResolving] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationStaging'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationStaging]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'OrganizationId', 'Description', 'SourceKey', 'OrganizationKey', 'FreshnessDate')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationStaging] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationUnreferenced'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationUnreferenced]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationUnreferenced] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionValueAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionValueAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('DimensionValueId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionValueAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on FactAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[FactAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('FactId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[FactAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalance'
    ------------------------------
    DECLARE @name nvarchar(200)
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalance'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    -- Rebuild dropped indexes that are dynamic
    EXEC [Datamart].ConfigureIndexesAndConstraints
    ------------------------------------------
    ------------------------------------------
    PRINT 'Reset the map tokens'
    UPDATE [Connector].[Map] SET InitalLoad = 0, ReaderToken=NULL, LastQuerySuccess='1900-01-01' WHERE MapId IN (SELECT t.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Reset the tasks'
    UPDATE [Scheduling].[TaskState] SET StateType = 0, Progress = 0.0, LastRunTime = NULL, NextRunTime = NULL WHERE TaskId IN (SELECT ts.[TaskId]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8'))
    PRINT 'Enable integration tasks, RunImmediately'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 1, StartBoundary = '1900-01-01' 
    WHERE Id in (SELECT [id] from @triggerIds WHERE taskTypeId = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Enable the Maintenance Task'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 0, StartBoundary = GETDATE() WHERE Id in
    (SELECT [id] from @triggerIds WHERE taskTypeId = 'D81C1197-D486-4FB7-AF8C-078C110893A0')
    ------------------------------------------
    ------------------------------------------
    ```

6. Après la réinitialisation, vous pouvez vérifier manuellement le rechargement des données en exécutant la requête suivante sur la base de données d'états financiers.

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    Confirmez que toutes les lignes ont une valeur **LastRunTime** et que **StateType** est défini sur **5**. La valeur **StateType** **5** indique que les données ont bien été rechargées. La valeur **7** indique un état d'erreur. Parfois, la carte Hiérarchie d'organisation présente cet état lorsqu'elle s'exécute pour la première fois. Toutefois, l'état d'erreur doit être automatiquement résolu.

