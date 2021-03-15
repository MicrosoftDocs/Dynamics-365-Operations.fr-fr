---
title: Résoudre les problèmes de synchronisation en direct
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la synchronisation en direct.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 59c8bd80b167cdfaa7a65e469f4dc7ebf8f50844
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744611"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Résoudre les problèmes de synchronisation en direct

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Cette rubrique fournit des informations sur la résolution des problèmes de l’intégration de la double écriture entre les applications Finance and Operations et Dataverse. Notamment elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la synchronisation en direct.

> [!IMPORTANT]
> Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-row-in-a-finance-and-operations-app"></a>La synchronisation en direct génère une erreur de type 403 Forbidden lorsque vous créez une ligne dans une application Finance and Operations

Vous pouvez recevoir le message d’erreur suivant lorsque vous créez une ligne dans une application Finance and Operations :

*\[{\\« Erreur\\ » :{\\« Code\\ » :\\« 0x80072560\\ »,\\« message\\ » :\\« L’utilisateur n’est pas un membre de l’organisation.\\ »}}\], Le serveur distant a renvoyé une erreur : (403) Forbidden."}}".*

Pour résoudre le problème, suivez les étapes dans [Configuration requise et conditions préalables](requirements-and-prerequisites.md). Pour valider ces étapes, les utilisateurs de l’application de double écriture créés dans Dataverse doivent avoir le rôle d’administrateur système. L’équipe propriétaire par défaut doit également avoir le rôle d’administrateur système.

## <a name="live-synchronization-for-any-table-consistently-throws-a-similar-error-when-you-create-a-row-in-a-finance-and-operations-app"></a>La synchronisation en direct pour toute table génère uniformément une erreur similaire lorsque vous créez une ligne dans une application Finance and Operations

**Rôle requis pour résoudre le problème :** Administrateur système

Vous pouvez recevoir un message d’erreur comme le suivant chaque fois que vous essayez d’enregistrer des données de table dans une application Finance and Operations :

*Impossible d’enregistrer les modifications dans la base de données. L’unité de travail ne peut pas valider la transaction. Impossible d’écrire des données sur les UM de l’entité. Échec de l’écriture dans UnitOfMeasureEntity avec le message d’erreur Impossible de synchroniser avec les UM de l’entité.*

Pour résoudre le problème, vous devez vous assurer que les données de référence préalables existent dans l’application Finance and Operations et Dataverse. Par exemple, si le client dans lequel vous vous trouvez dans l’application Finance and Operations appartient à un groupe de clients spécifique, assurez-vous que le groupe de clients existe dans Dataverse.

Si des données existent des deux côtés et si vous avez confirmé que le problème n’est pas lié aux données, procédez comme suit.

1. Arrêtez la table associée.
2. Connectez-vous à l’application Finance and Operations et assurez-vous que les lignes de la table défaillante existent dans les tables DualWriteProjectConfiguration et DualWriteProjectFieldConfiguration. Par exemple, voici à quoi ressemble la requête si la table **Clients** échoue.

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. S’il existe des lignes pour la table défaillante même après avoir arrêté le mappage de tables, supprimez les lignes liés à la table défaillante. Prenez note de la colonne **nom du projet** dans la table DualWriteProjectConfiguration et récupérez l’enregistrement dans la ligne DualWriteProjectFieldConfiguration en utilisant le nom du projet pour supprimer la ligne.
4. Démarrez le mappage de tables. Validez si les données sont synchronisées sans aucun problème.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Gérer les erreurs de privilège de lecture ou d’écriture lorsque vous créez des données dans une application Finance and Operations

Vous pouvez recevoir un message d’erreur de type « Bad Request » qui ressemble à l’exemple suivant lorsque vous créez des données dans une application Finance and Operations.

![Exemple de message d’erreur « Bad Request »](media/error_record_id_source.png)

Pour résoudre le problème, vous devez attribuer le rôle de sécurité correct à l’équipe de l’unité commerciale Dynamics 365 Sales ou Dynamics 365 Customer Service mappée pour activer le privilège manquant.

1. Dans l’application Finance and Operations, recherchez l’unité commerciale mappée dans le jeu de connexions d’intégration de données.

    ![Cartographie de l’organisation](media/mapped_business_unit.png)

2. Connectez-vous à l’environnement dans l’application pilotée par le modèle dans Dynamics 365, accédez à **Paramètre \> Sécurité** et recherchez l’équipe de l’unité commerciale mappée.

    ![Équipe de l’unité commerciale cartographiée](media/setting_security_page.png)

3. Ouvrez la page de l’équipe à modifier, puis sélectionnez **Gérer les rôles** pour ouvrir la boîte de dialogue **Gérer les rôles d’équipe**.

    ![Bouton Gérer les rôles](media/manage_team_roles.png)

4. Attribuez le rôle disposant du privilège de lecture/écriture aux tables concernées, puis sélectionnez **OK**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a>Résoudre les problèmes de synchronisation dans un environnement Dataverse récemment modifié

**Rôle requis pour résoudre le problème :** Administrateur système

Vous pouvez recevoir le message d’erreur suivant lorsque vous créez des données dans une application Finance and Operations :

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Impossible de générer la charge utile pour vérifier CustCustomerV3Entity** », « logDateTime » : « 2019-08-27T18:51:52.5843124Z », « verboseError » : « Échec de la création de la charge utile avec l’erreur URI non valide : l’URI est vide. »}\], « isErrorCountUpdated » : true}*

Voici à quoi ressemble l’erreur dans l’application pilotée par modèle dans Dynamics 365 :

*Une erreur inattendue s’est produite depuis le code ISV. (ErrorType = ClientError) Exception inattendue depuis le plug-in (Execute) : Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: échec du triatement du compte d’entité - (Échec de la tentative de connexion, car la partie connectée n’a pas répondu correctement après un temps donné, ou la connexion établie a échoué en raison de l’absence de réponse de l’hôte connecté*

Cette erreur se produit lorsque l’environnement Dataverse est mal réinitialisé lorsque vous essayez de créer des données dans l’application Finance and Operations.

Pour régler le problème, procédez comme suit.

1. Connectez-vous à la machine virtuelle Finance and Operations (VM), ouvrez SQL Server Management Studio (SSMS) et recherchez des lignes dans la table DUALWRITEPROJECTCONFIGURATIONENTITY où **internalentityname** équivaut à **Customers V3** et **externalentityname** équivaut à **accounts**. Voici à quoi ressemble la requête.

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. Utilisez le nom du projet à partir des résultats de la requête précédente pour exécuter la requête suivante.

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. Assurez-vous que la colonne **externalenvironmentURL** a l’URL Dataverse ou d’application appropriée. Supprimez toutes les lignes en double qui pointent vers la mauvaise URL Dataverse. Supprimez les lignes correspondantes dans les tables DUALWRITEPROJECTFIELDCONFIGURATION et DUALWRITEPROJECTCONFIGURATION.
4. Arrêter le mappage de tables et le redémarrer


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]