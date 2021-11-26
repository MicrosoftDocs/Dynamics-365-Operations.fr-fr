---
title: Résoudre les problèmes de synchronisation en direct
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la synchronisation en direct.
author: RamaKrishnamoorthy
ms.date: 08/19/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 69667f8b64c048f5957168d1af21a6c858bc0bad
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782577"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Résoudre les problèmes de synchronisation en direct

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique fournit des informations sur la résolution des problèmes de l’intégration de la double écriture entre les applications Finance and Operations et Microsoft Dataverse. Notamment elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la synchronisation en direct.

> [!IMPORTANT]
> Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d’administrateur système ou les identifiants d’administrateur du client Azure Active Directory (Azure AD). Chaque section explique si un rôle ou des informations d’identification spécifiques sont requis.

## <a name="live-synchronization-shows-an-error-when-you-create-a-row"></a>La synchronisation en direct affiche une erreur lorsque vous créez une ligne

Vous pouvez recevoir le message d’erreur suivant lorsque vous créez une ligne dans une application Finance and Operations :

*\[{\\« Erreur\\ » :{\\« Code\\ » :\\« 0x80072560\\ »,\\« message\\ » :\\« L’utilisateur n’est pas un membre de l’organisation.\\ »}}\], Le serveur distant a renvoyé une erreur : (403) Forbidden."}}".*

Pour résoudre le problème, suivez les étapes dans [Configuration requise et conditions préalables](requirements-and-prerequisites.md). Pour mener à bien ces étapes, les utilisateurs de l’application de double écriture créés dans Dataverse doivent avoir le rôle d’administrateur système. L’équipe propriétaire par défaut doit également avoir le rôle d’administrateur système.

## <a name="live-synchronization-shows-an-error-when-you-try-to-save-table-data"></a>La synchronisation en direct affiche une erreur lorsque vous essayez d’enregistrer les données de la table

**Rôle requis pour résoudre le problème :** Administrateur système

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayer d’enregistrer les données de la table dans une application Finance and Operations :

*Impossible d’enregistrer les modifications dans la base de données. L’unité de travail ne peut pas valider la transaction. Impossible d’écrire des données sur les UM de l’entité. Échec de l’écriture dans UnitOfMeasureEntity avec le message d’erreur Impossible de synchroniser avec les UM de l’entité.*

Pour résoudre le problème, assurez-vous que les données de référence préalables existent dans l’application Finance and Operations et Dataverse. Par exemple, si un enregistrement client appartient à un groupe de clients spécifique, assurez-vous que le groupe de clients existe dans Dataverse.

Si les données existent aux deux endroits, et si vous avez confirmé que le problème n’est pas lié aux données, procédez comme suit.

1. Ouvrez l’entité **DualWriteProjectConfigurationEntity** à l’aide du module complémentaire Excel. Pour utiliser le complément, activez le mode conception dans le module complémentaire Excel Finance and Operations et ajoutez **DualWriteProjectConfigurationEntity** à la feuille de calcul. Pour plus d’informations, voir [Afficher et mettre à jour les données d’entité avec Excel](../../office-integration/use-excel-add-in.md).
2. Sélectionnez et supprimez les enregistrements qui présentent des problèmes dans le mappage et le projet à double écriture. Il y aura deux enregistrements pour chaque mappage à double écriture.
3. Publiez les modifications à l’aide du complément Excel. Cette étape est importante car elle supprime les enregistrements de l’entité et des tables sous-jacentes.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Gérer les erreurs de privilège de lecture ou d’écriture lorsque vous créez des données dans une application Finance and Operations

Vous pouvez recevoir le message d’erreur « Bad Request » lorsque vous créez des données dans une application Finance and Operations.

![Exemple de message d’erreur « Bad Request ».](media/error_record_id_source.png)

Pour résoudre le problème, vous devez activer le privilège manquant en attribuant le rôle de sécurité correct à l’équipe des unités commerciales Dynamics 365 Sales ou Dynamics 365 Customer Service mappées.

1. Dans l’application Finance and Operations, recherchez l’unité commerciale mappée dans le jeu de connexions d’intégration de données.

    ![Cartographie de l’organisation.](media/mapped_business_unit.png)

2. Dans l’application d’engagement client, connectez-vous à l’environnement, accédez à **Paramètre \> Sécurité** et recherchez l’équipe de l’unité commerciale mappée.

    ![Équipe de l’unité commerciale cartographiée.](media/setting_security_page.png)

3. Ouvrez la page de l’équipe à modifier, puis sélectionnez **Gérer les rôles**.

    ![Bouton Gérer les rôles.](media/manage_team_roles.png)

4. Dans la boîte de dialogue **Gérer les rôles de l’équipe**, attribuez le rôle qui a le privilège de lecture/écriture pour les tables pertinentes, puis sélectionnez **OK**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a>Résoudre les problèmes de synchronisation dans un environnement Dataverse récemment modifié

**Rôle requis pour résoudre le problème :** Administrateur système

Vous pouvez recevoir le message d’erreur suivant lorsque vous créez des données dans une application Finance and Operations :

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Impossible de générer la charge utile pour vérifier CustCustomerV3Entity** », « logDateTime » : « 2019-08-27T18:51:52.5843124Z », « verboseError » : « Échec de la création de la charge utile avec l’erreur URI non valide : l’URI est vide. »}\], « isErrorCountUpdated » : true}*

Voici à quoi ressemble le message d’erreur dans l’application d’engagement client :

> Une erreur inattendue s’est produite dans le code ISV. (ErrorType = ClientError) Exception inattendue depuis le plug-in (Execute) : Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: échec du traitement du compte de l’entité – (Échec de la tentative de connexion, car la partie connectée n’a pas répondu correctement après un temps donné, ou la connexion établie a échoué en raison de l’absence de réponse de l’hôte connecté.

Cette erreur se produit si l’environnement Dataverse est mal réinitialisé lorsque vous essayez de créer des données dans l’application Finance and Operations.

> [!IMPORTANT]
> Si vous avez reconnecté les environnements, vous devez arrêter tous les mappages d’entité avant de poursuivre les étapes d’atténuation.

Pour résoudre le problème, vous devez suivre les étapes à la fois dans Dataverse et dans l’application Finance and Operations.

1. Dans l’application Finance and Operations, procédez comme suit :

    1. Ouvrez l’entité **DualWriteProjectConfigurationEntity** à l’aide du module complémentaire Excel. Pour utiliser le complément, activez le mode conception dans le module complémentaire Excel Finance and Operations et ajoutez **DualWriteProjectConfigurationEntity** à la feuille de calcul. Pour plus d’informations, voir [Afficher et mettre à jour les données d’entité avec Excel](../../office-integration/use-excel-add-in.md).
    2. Sélectionnez et supprimez les enregistrements qui présentent des problèmes dans le mappage et le projet à double écriture. Il y aura deux enregistrements pour chaque mappage à double écriture.
    3. Publiez les modifications à l’aide du complément Excel. Cette étape est importante car elle supprime les enregistrements de l’entité et des tables sous-jacentes.
    4. Pour éviter les erreurs lorsque vous reconnectez les environnements Finance and Operations ou Dataverse, assurez-vous qu’il ne reste aucune configuration à double écriture.

2. Dans Dataverse, procédez comme suit :

    1. Connectez-vous à votre environnement Dataverse (par exemple,`https://*****.crm.dynamics.com/`).
    2. Accédez à **Paramètres avancés** \> **Recherche avancée**.
    3. Sélectionnez **Configuration d’exécution DualWrite**.
    4. Sélectionnez la colonne à afficher.
    5. Sélectionnez **Résultats** pour voir les configurations.
    6. Supprimez toutes les instances.

3. Dans l’application Finance and Operations, procédez comme suit :

    1. Ouvrez l’entité **DualWriteProjectConfigurationEntity** à l’aide du module complémentaire Excel. Pour utiliser le complément, activez le mode conception dans le module complémentaire Excel Finance and Operations et ajoutez **DualWriteProjectConfigurationEntity** à la feuille de calcul. Pour plus d’informations, voir [Afficher et mettre à jour les données d’entité avec Excel](../../office-integration/use-excel-add-in.md).
    2. Sélectionnez et supprimez les enregistrements qui présentent des problèmes dans le mappage et le projet à double écriture. Il y aura deux enregistrements pour chaque mappage à double écriture.
    3. Publiez les modifications à l’aide du complément Excel. Cette étape est importante car elle supprime les enregistrements de l’entité et des tables sous-jacentes.
    4. Pour éviter les erreurs lorsque vous reconnectez les environnements Finance and Operations ou Dataverse, assurez-vous qu’il ne reste aucune configuration à double écriture.

## <a name="live-synchronization-error-after-you-do-a-full-database-copy"></a>Erreur de synchronisation en direct après avoir effectué une copie complète de la base de données

Vous pouvez recevoir le message d’erreur suivant après avoir exécuté une copie complète de la base de données d’un système à un autre, puis avoir essayé d’exécuter une opération de base de données :

*SecureConfig Organization (???) ne correspond pas à l’organisation CRM réelle (???).*

Le message d’erreur est affiché à partir du plug-in d’exécution en double écriture pour garantir que la configuration à double écriture qui est configurée dans un système ne peut pas être utilisée dans un autre système.

Pour résoudre le problème, supprimez tous les enregistrements dans la table **msdyn_dualwriteruntimeconfig** après avoir restauré la base de données. Pour plus d’informations, consultez [Dissocier et reconnecter des environnements à double écriture](relink-environments.md).

## <a name="live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps"></a>Problèmes de synchronisation en direct causés par une syntaxe de filtre de requête incorrecte sur les mappages à double écriture

Même si l’expression de requête pour un filtre de mappage à double écriture est syntaxiquement correcte, elle peut ne pas fonctionner comme prévu. L’expression de filtre s’applique à une entité, et non à une source de données individuelle d’un objet de requête. Par conséquent, la requête SQL générée ne renvoie pas les résultats attendus.

Voici un exemple :

```dos
Query entity = PROJECTENTITY
Query expression = (ParentProject == "")
```

Vous pouvez vous attendre à ce que les projets qui n’ont pas de parent soient filtrés. Cependant, le filtre ne fonctionne pas car il est traduit en une requête qui ressemble à l’exemple suivant.

```sql
SELECT T1.RECID,T1.MODIFIEDDATETIME,T1.RECVERSION,T1.RECID,T1.DIMENSION,
T1.LOCATION,T1.PROJECTCONTROLLER,T1.PROJECTID,T1.PROJECTMANAGER,T1.REFERENCE,
T1.SALESMANAGER,T1.SCHEDULED,T1.RECVERSION#8,T1.RECVERSION#7,
T1.RECVERSION#6,T1.RECVERSION#5,T1.RECVERSION#4,T1.RECVERSION#3,
T1.RECVERSION#2,T1.RECID#8,T1.RECID#7,T1.RECID#6,T1.RECID#5,
T1.RECID#4,T1.RECID#3,T1.RECID#2,T1.PARTITION FROM PROJECTENTITY T1 
WHERE(((((((((((PARTITION=5637144576) AND (DATAAREAID=N'usmf')) AND 
((PARTITION#2=5637144576) OR (PARTITION#2 IS NULL))) AND 
((PARTITION#3=5637144576) OR (PARTITION#3 IS NULL))) AND 
((PARTITION#4=5637144576) OR (PARTITION#4 IS NULL))) AND 
((PARTITION#5=5637144576) OR (PARTITION#5 IS NULL))) AND 
((PARTITION#6=5637144576) OR (PARTITION#6 IS NULL))) AND 
((PARTITION#7=5637144576) OR (PARTITION#7 IS NULL))) AND 
((PARTITION#8=5637144576) OR (PARTITION#8 IS NULL))) AND 
((DATAAREAID#8=N'usmf') OR (DATAAREAID#8 IS NULL))) AND 
(PARENTPROJECT='')) 
ORDER BY T1.PROJECTID
```

Le résultat réel est que le champ `parentProject` est évalué comme `null`. Cependant, `null` n’est pas la même chose qu’une chaîne vide. En raison de cette incompatibilité, le filtre de requête ne renvoie pas de résultats valides.

Pour régler le problème, procédez comme suit.

1. Ajoutez une colonne calculée pouvant être ajoutée dans un modèle d’extension, et qui s’appuie sur une logique qui convertit `null` en chaîne vide.

    ```dos
    SysComputedColumn::if(SysComputedColumn::isNullExpression(ParentProject), SysComputedColumn::returnLiteral(""), fieldName);
    ```

2. Utilisez le filtre sur la nouvelle colonne calculée au lieu de la colonne par défaut.

Pour évaluer le filtre dans un environnement de développement, vous pouvez utiliser le code X++ suivant pour valider les résultats. Exécutez ce code en tant que programme autonome. Vous pouvez l’utiliser pour évaluer différents types de filtres applicables à une entité avant d’utiliser ces filtres sur des mappages à double écriture. La requête peut être exécutée sur la base de données pour évaluer les écarts.

```xpp
var entityName = "PROJECTENTITY";
var filterExpression = '(ParentProject == "")';
Query query = new Query();
query.literals(NoYes::Yes); 
QueryBuildDataSource qbd = query.addDataSource(tablename2id(entityName));
qbd.addRange(fieldname2id(qbd.table(),identifierStr(RecVersion))).value(filterExpression);
qbd.addSelectionField(fieldname2id(qbd.table(),identifierStr(RecId)));
QueryRun qRun = new QueryRun(query);
// This provides the actual sql statement to execute
var actualSqlStatement = query.getSQLStatement();
while(qRun.next())
{
    var rec = qRun.get(tableName2Id(entityName));
}
```

## <a name="data-from-finance-and-operations-apps-isnt-synced-to-dataverse"></a>Les données des applications Finance and Operations ne sont pas synchronisées avec Dataverse

Lors de la synchronisation en direct, vous pouvez rencontrer un problème où seule une partie des données est synchronisée à partir des applications Finance and Operations vers Dataverse, ou bien où les données ne sont pas du tout synchronisées.

> [!NOTE]
> Vous devez résoudre ce problème pendant le développement.

Avant de commencer à résoudre le problème, vérifiez les conditions préalables suivantes :

+ Assurez-vous que vos modifications personnalisées sont écrites dans une étendue de transaction unique.
+ Les événements commerciaux et la structure à double écriture ne gèrent pas les opérations `doinsert()`, `doUpdate()` et `recordset()`, ni les enregistrements où `skipBusinessEvents(true)` est marqué. Si votre code est à l’intérieur de ces fonctions, la double écriture ne sera pas déclenchée.
+ Les événements commerciaux doivent être enregistrés pour la source de données mappée. Certaines sources de données peuvent utiliser une jointure externe et peuvent être marquées comme en lecture seule dans les applications Finance and Operations. Ces sources de données ne sont pas suivies.
+ Les modifications ne seront déclenchées que si les modifications sont sur les champs mappés. Les modifications des champs non mappés ne déclencheront pas la double écriture.
+ Assurez-vous que les évaluations de filtre fournissent un résultat valide.

### <a name="troubleshooting-steps"></a>Étapes de résolution des problèmes

1. Passez en revue les mappages de champs sur la page d’administration de la double écriture. Si un champ n’est pas mappé entre les applications Finance and Operations et Dataverse, il ne sera pas suivi. Par exemple, dans l’illustration suivante, le champ **Description** est suivi à partir de Dataverse, mais pas à partir des applications Finance and Operations. Aucune modification de ce champ à l’intérieur des applications Finance and Operations ne sera suivie.

    ![Champ suivi.](media/live-sync-troubleshooting-1.png)

2. Déterminez si la source de données est suivie dans la définition des événements commerciaux. Par exemple, dans l’illustration suivante, aucun champ de la table **DefaultDimensionDAVs** ni des tables sous-jacentes ne sera suivi pour les modifications. Les sources de données qui utilisent une jointure externe et qui sont marquées comme en lecture seule ne sont pas suivies.

    ![Champ qui n’est pas suivi.](media/live-sync-troubleshooting-2.png)

3. Déterminez si les champs de la table mappée apparaissent dans la table **BUSINESSEVENTSDEFINITION**, comme indiqué dans l’illustration suivante. Si vous ne trouvez pas le champ que vous recherchez dans le résultat de la requête, il ne sera pas déclenché par la double écriture.

    ![Champ suivi dans la table.](media/live-sync-troubleshooting-3.png)

### <a name="sample-scenario"></a>Exemple de scénario

Dans les applications Finance and Operations, il y a une mise à jour de l’adresse d’un enregistrement de contact, mais la modification de l’adresse n’est pas synchronisée avec Dataverse. Ce scénario se produit parce qu’aucun enregistrement de la table **BusinessEventsDefinition** ne comporte la combinaison de la table et de l’entité affectées. Plus précisément, la table **LogisticsPostalAddress** n’est pas la source de données directe pour l’entité **smmContactpersonCDSV2Entity**. L’entité **smmContactpersonCDSV2Entity** a pour source de données l’entité **smmContactPersonV2Entity**, et l’entité **smmContactPersonV2Entity** a à son tour l’entité **LogisticsPostalAddressBaseEntity** comme source de données. La table **LogisticsPostalAddress** est la source de données de l’entité **LogisticsPostalAddressBaseEntity**.

Une situation similaire peut se produire dans certains schémas non standard, tels que les cas où la table qui est modifiée dans les applications Finance and Operations n’est pas liée de manière évidente à l’entité qui la contient. Par exemple, les données d’adresse principale sont calculées sur l’entité **smmContactPersonCDSV2Entity**. L’infrastructure à double écriture essaie de déterminer comment une modification apportée à une table sous-jacente est mappée en retour sur les entités. Habituellement, cette approche est suffisante. Cependant, dans certains cas, le lien est si complexe que vous devez être précis. Vous devez vous assurer que l’identifiant **RecId** de la table associée est directement disponible sur l’entité. Ajoutez ensuite une méthode statique pour surveiller les modifications de la table.

Par exemple, consultez la méthode **smmContactPersonCDSV2Entity::getEntityDataSourceToFieldMapping()**. **CustCustomerV3entity** et **VendVendorV2Entity** ont été modifiées pour gérer cette situation.

Pour régler le problème, procédez comme suit.

1. Ajoutez un champ **PrimaryPostalAddressRecId** à l’entité **smmContactPersonV2Entity**. Rendez-le interne.

    ![Champ ajouté à l’entité smmContactPersonV2Entity.](media/Troubleshoot_live_sync_issue_1.png)

2. Ajoutez le même champ à l’entité **smmContactPersonCDSV2Entity**.

    ![Champ ajouté à l’entité smmContactPersonCDSV2Entity.](media/Troubleshoot_live_sync_issue_2.png)

3. Ajoutez la méthode suivante à la classe **smmContactPersonCDSV2Entity**.

    ```xpp
    public static container getEntityDataSourceToFieldMapping(container mapping)
    {
        mapping += [[tablestr(smmContactPersonCDSV2Entity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)]];
        return mapping;
    }
    ```

4. Synchronisez la base de données et créez l’application.
5. Arrêtez tous les mappages à double écriture créés sur l’entité **smmContactPersonCDSV2Entity**.
6. Démarrez le mappage. Vous devriez voir la nouvelle table (**LogisticsPostalAddress** dans cet exemple) que vous avez commencé à suivre en utilisant la colonne **RefTableName** pour la ligne où la valeur **refentityname** est égale à **smmContactPersonCDSV2Entity** dans la table **BusinessEventsDefinition**.

## <a name="error-when-you-create-a-record-where-multiple-records-are-sent-from-a-finance-and-operations-app-to-dataverse-in-the-same-batch"></a>Erreur lorsque vous créez un enregistrement où plusieurs enregistrements sont envoyés d’une application Finance and Operations à Dataverse dans le même lot

Pour toute transaction, une application Finance and Operations crée des données dans un lot et les envoie sous forme de lot à Dataverse. Si deux enregistrements sont créés dans le cadre de la même transaction et qu’ils se font référence l’un à l’autre, vous pouvez recevoir un message d’erreur qui ressemble à l’exemple suivant dans l’application Finance and Operations :

*Impossible d’écrire des données dans l’entité aaa_fundingsources. Impossible de rechercher ebecsfs_contracts avec des valeurs {PC00...}. Impossible de rechercher aaa_fundingsources avec des valeurs {PC00...}. Échec des écritures dans aaa_fundingsources avec un message d’erreur Message d’exception : le serveur distant a renvoyé une erreur : (400) Bad Request.*

Pour résoudre le problème, créez des relations d’entité dans l’application Finance and Operations pour indiquer que les deux entités sont liées l’une à l’autre et que les enregistrements liés sont traités dans la même transaction.

## <a name="enable-verbose-logging-of-error-messages"></a>Activer la journalisation détaillée des messages d’erreur

Dans une application Finance and Operations, vous pouvez rencontrer des erreurs liées à l’environnement Dataverse. Le message d’erreur peut ne pas contenir le texte intégral du message, ou d’autres données pertinentes. Pour obtenir plus d’informations, vous pouvez activer la journalisation détaillée en définissant l’indicateur **IsDebugMode** qui est présent sur l’entité **DualWriteProjectConfigurationEntity** dans toutes les configurations de projet des applications Finance and Operations.

1. Ouvrez l’entité **DualWriteProjectConfigurationEntity** à l’aide du module complémentaire Excel. Pour utiliser le complément, activez le mode conception dans le module complémentaire Excel Finance and Operations et ajoutez **DualWriteProjectConfigurationEntity** à la feuille de calcul. Pour plus d’informations, voir [Afficher et mettre à jour les données d’entité avec Excel](../../office-integration/use-excel-add-in.md).
2. Définissez l’indicateur **IsDebugMode** sur **Oui** dans le projet.
3. Exécutez le scénario.
4. Les journaux détaillés sont disponibles dans la table **DualWriteErrorLog**. Pour rechercher des données à l’aide du navigateur de tables, utilisez l’URL suivante : `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`.
5. Pour capturer plus de journaux en mode débogage, installez la mise à jour dans [KB 4595434 (Correction des valeurs vides propagées dans la synchronisation en direct à double écriture)](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=c29ce15a80e6b3b4c01a722d9bdae1d7e71aa3662a044cfd0b765f736cfa98e9).

## <a name="error-when-you-add-an-address-for-a-customer-or-contact"></a>Erreur lors de l’ajout d’une adresse pour un client ou un contact

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez d’ajouter une adresse pour un client ou un contact dans les applications Finance and Operations ou Dataverse :

*Impossible d’écrire des données dans l’entité msdyn_partypostaladdresses. Les écritures dans DirPartyPostalAddressLocationCDSEntity ont échoué avec le message d’erreur : « La requête a échoué avec le code statut BadRequest et le code d’erreur CDS : message de réponse 0x80040265 : une erreur s’est produite dans le plug-in. Un enregistrement ayant les valeurs d’attribut ID d’emplacement existe déjà. La clé d’entité Location ID Key requiert que cet ensemble d’attributs contienne des valeurs uniques. Sélectionnez des valeurs uniques et réessayez. »*

Pour résoudre le problème, installez la version du package d’orchestration de la double écriture (2.2.2.60), afin que les clés des tables **Adress** soient définies comme indiqué dans le tableau suivant.

| Propriété | Valeur |
|---|---|
| Nom d’affichage | **Clé d’emplacementn** |
| Nom | **msdyn_locationkey** |
| Champs | **msdyn_locationid**, **parentid** |
| État | **Actifs** |
| Tâche système | Blanc |

## <a name="error-when-you-add-a-customer-in-dataverse"></a>Erreur lorsque vous ajoutez un client dans Dataverse

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayer d’ajouter un client dans Dataverse :

*« RecordError0 » : « Échec de l’écriture pour l’entité Customers V3 avec exception inconnue - Enregistrement de partie introuvable pour le type de partie "Organisation" »}.*

Lorsqu’un client est créé dans Dataverse, un nouveau numéro de partie est généré. Le message d’erreur s’affiche lorsque l’enregistrement du client, ainsi que la partie, est synchronisé avec les applications Finance and Operations, mais qu’il existe déjà un enregistrement client qui a un numéro de partie différent.

Pour résoudre le problème, recherchez le client via la recherche de partie. Si le client n’existe pas, créez un nouvel enregistrement client. Si le client existe, utilisez la partie existante pour créer le nouvel enregistrement client.

## <a name="error-when-you-create-a-new-customer-vendor-or-contact-in-dataverse"></a>Erreur lorsque vous créez un client, un fournisseur ou un contact dans Dataverse

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez de créer un client, un fournisseur ou un contact dans Dataverse :

*Impossible de mettre à jour le type de partie de « DirOrganization » à « DirPerson » ; il convient plutôt d’effectuer une suppression de la partie existante suivie d’une insertion avec le nouveau type.*

Dans Dataverse, il existe une souche de numéros sur la table **msdyn_party**. Lorsqu’un compte est créé dans Dataverse, une nouvelle partie est créée (par exemple **Partie-001** du type **Organisation**). Ces données sont envoyées à l’application Finance and Operations. Si l’environnement Dataverse est réinitialisé, ou si l’environnement Finance and Operations est lié à un autre environnement Dataverse, puis qu’un nouvel enregistrement de contact est créé dans Dataverse, une nouvelle valeur de partie commençant par **Partie-001** est créé. Cette fois, l’enregistrement de partie créé sera **Partie-001** du type **Personne**. Lorsque ces données sont synchronisées, les applications Finance and Operations affichent le message d’erreur précédent, parce que l’enregistrement de partie **Partie-001** du type **Organisation** existe déjà.

Pour résoudre le problème, modifiez la souche de numéros automatique pour le champ **msdyn_partynumber** de la table **msdyn_party** dans Dataverse en une autre séquence de numéros automatique.

## <a name="performance-issue-with-customer-or-contact-mappings"></a>Problème de performances avec les mappages de clients ou de contacts

Vous pouvez améliorer légèrement les performances de la synchronisation en direct pour les clients et les contacts en personnalisant la méthode **getEntityDataSourceToFieldMapping** (dans l’entité **CustCustomerV3Entity**) et la méthode **getEntityDataSourceToFieldMapping** (dans l’entité **smmContactPersonCDSV2Entity**). Ces personnalisations réduisent le nombre d’enregistrements dans la table **BusinessEventsDefinition**. Cette réduction du nombre d’enregistrements, à son tour, réduit le nombre d’événements qui sont déclenchés.

La méthode **getEntityDataSourceToFieldMapping** dans l’entité **CustCustomerV3Entity** s’assure qu’une mise à jour de l’adresse électronique ou postale du client déclenche des événements commerciaux, afin que les données mises à jour soient envoyées à Dataverse. Si vous n’utilisez pas tous les champs et n’avez pas besoin des informations en double écriture, commentez les lignes appropriées dans la méthode. Chaque champ et table suivi ajouté dans cette méthode ajoute un enregistrement dans la table **BusinessEventsDefinition** pour la combinaison de la table suivie et de l’entité suivie.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, AddressRecordId)],
        [identifierstr(DirPartyBaseEntity), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactURLRecordId)],
        [identifierstr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactPhoneRecordId)],
        [identifierstr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactEmailRecordId)],
        [identifierstr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactFaxRecordId)],
        [identifierstr(DirPartyBaseEntity4), tablenum(DirPartyLocation), fieldstr(CustCustomerV3Entity, DirPartyLocationRecordId)],
        [identifierstr(DirPartyBaseEntity5), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, InvoiceAddressRecordId)],
        [identifierstr(DirPartyBaseEntity6), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, DeliveryAddressRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(DirPartyTable), fieldstr(CustCustomerV3Entity, PartyRecordId)]];
    return mapping;
}
```

De manière similaire, la méthode **getEntityDataSourceToFieldMapping** dans l’entité **smmContactPersonCDSV2Entity** s’assure que toute mise à jour de l’adresse électronique ou postale du client déclenche des événements commerciaux, afin que les données mises à jour soient envoyées à Dataverse. Dans la méthode, vous pouvez commenter les lignes de tous les champs que vous n’utilisez pas.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)],
        [identifierStr(DirPartyBaseEntity), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PrimaryAddressLocation)],
        [identifierStr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactEmailRecordId)],
        [identifierStr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFaxRecordId)],
        [identifierStr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactPhoneRecordId)],
        [identifierStr(DirPartyBaseEntity4), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFacebookRecordId)],
        [identifierStr(DirPartyBaseEntity5), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTwitterRecordId)],
        [identifierStr(DirPartyBaseEntity6), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactURLRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactLinkedInRecordId)],
        [identifierStr(DirPartyBaseEntity8), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTelexRecordId)],
        [identifierStr(DirPartyBaseEntity9), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PartyRecordId)]];
    return mapping;
}
```

Après avoir mis à jour les méthodes, procédez comme suit.

1. Synchronisez la base de données et créez l’application.
2. Arrêtez tous les mappages à double écriture créés sur les entités **smmContactPersonCDSV2Entity** et **CustCustomerV3Entity**.
3. Démarrez les mappages. Vous devriez voir moins d’enregistrements dans les entité **smmContactPersonCDSV2Entity** et **CustCustomerV3Entity** et la table **BusinessEventsDefinition**, et les performances pourraient légèrement s’améliorer.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
