---
title: Résoudre les problèmes liés aux mises à niveau des applications de finances et d’opérations
description: Cet article fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés aux mises à niveau des applications de finances et d’opérations.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: b75034cbc8ca7a24472cfec1ad93d3dfef4a8fdc
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111138"
---
# <a name="troubleshoot-issues-from-upgrades-of-finance-and-operations-apps"></a>Résoudre les problèmes liés aux mises à niveau des applications de finances et d’opérations

[!include [banner](../../includes/banner.md)]





Cet article fournit des informations sur le dépannage de l’intégration de la double-écriture entre les applications de finances et d’opérations et Dataverse. Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés aux mises à niveau des applications de finances et d’opérations.

> [!IMPORTANT]
> Certains des problèmes abordés dans cet article peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.

## <a name="database-synchronization-errors"></a>Erreurs de synchronisation de base de données

**Rôle requis pour résoudre le problème :** Administrateur système

Vous pouvez recevoir un message d’erreur semblable à l’exemple suivant lorsque vous essayez d’utiliser la table **DualWriteProjectConfiguration** pour mettre à jour une application de finances et d’opérations vers Platform Update 30.

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

Pour régler le problème, procédez comme suit.

1. Connectez-vous à la machine virtuelle pour l’application de finances et d’opérations.
2. Ouvrez Visual Studio en tant qu’administrateur et ouvrez l’arbre d’objets d’application (AOA).
3. Recherchez **DualWriteProjectConfiguration**.
4. Dans l’AOA, faites un clic droit sur **DualWriteProjectConfiguration** et sélectionnez **Ajouter au nouveau projet**. Sélectionnez **OK** pour créer le nouveau projet qui utilise les options par défaut.
5. Dans l’Explorateur de solutions, cliquez avec le bouton droit sur **Propriétés du projet** et définissez **Synchroniser la base de données lors de la construction** sur la valeur **True**.
6. Générez le projet et confirmez que la génération a réussi.
7. Sur le menu **Dynamics 365**, sélectionnez **Synchroniser la base de données**.
8. Sélectionnez **Synchroniser** pour faire une synchronisation complète de la base de données.
9. Une fois la synchronisation complète de la base de données réussie, réexécutez l’étape de synchronisation de la base de données dans Microsoft Dynamics Lifecycle Services (LCS) et utilisez les scripts de mise à niveau manuelle le cas échéant, afin de pouvoir procéder à la mise à jour.

## <a name="missing-table-columns-issue-on-maps"></a>Problème de colonnes de table manquantes sur les cartes

**Rôle requis pour résoudre le problème :** Administrateur système

Sur la page **Double écriture**, vous pouvez recevoir un message d’erreur semblable à l’exemple suivant :

*Champ source manquant \<field name\> dans le schéma.*

![Exemple de message d’erreur de colonne source manquante.](media/error_missing_field.png)

Pour résoudre le problème, suivez d’abord ces étapes pour vous assurer que les colonnes se trouvent dans la table.

1. Connectez-vous à la machine virtuelle pour l’application de finances et d’opérations.
2. Accédez à **Espaces de travail \> Gestion de données**, sélectionnez la vignette **Paramètres de l’environnement**, puis, sur l’onglet **Paramètres de table**, sélectionnez **Actualiser la liste de tables** pour actualiser les tables.
3. Accédez à **Espaces de travail \> Gestion des données**, sélectionnez l’onglet **Tables de données** et assurez-vous que la table est répertoriée. Si la table n’est pas répertoriée, connectez-vous à la machine virtuelle pour l’application de finances et d’opérations et assurez-vous que la table est disponible.
4. Ouvrez la page **Mappage de tables** depuis la page **Double écriture** dans l’application de finances et d’opérations.
5. Sélectionnez **Actualiser la liste de tables** pour remplir automatiquement les colonnes dans les mappages de tables.

Si le problème n’est toujours pas résolu, procédez comme suit.

> [!IMPORTANT]
> Ces étapes vous guident tout au long du processus de suppression d’une table, puis de son ajout à nouveau. Pour éviter les problèmes, assurez-vous de suivre exactement les étapes.

1. Dans l’application de finances et d’opérations, accédez à **Espaces de travail \> Gestion des données** et sélectionnez la vignette **Tables de données**.
2. Recherchez la table qui manque pour l’attribut. Cliquez sur **Modifier le mappage cible** dans la barre d’outils.
3. Sur le volet **Mapper l’échelonnement à la cible**, cliquez sur **Générer un mappage**.
4. Ouvrez la page **Mappage de tables** depuis la page **Double écriture** dans l’application de finances et d’opérations.
5. Si l’attribut n’est pas renseigné automatiquement sur la carte, ajoutez-le manuellement en cliquant sur le bouton **Ajouter un attribut** puis sur **Enregistrer**. 
6. Sélectionnez le mappage, puis cliquez sur **Exécuter**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
