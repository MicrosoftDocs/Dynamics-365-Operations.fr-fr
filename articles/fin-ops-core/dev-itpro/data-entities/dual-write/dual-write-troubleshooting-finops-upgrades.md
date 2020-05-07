---
title: Résoudre les problèmes liés aux mises à niveau des applications Finance and Operations
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés aux mises à niveau des applications Finance and Operations.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 53df00de82b101aa02160d865a9c3bbebcfcae15
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275462"
---
# <a name="troubleshoot-issues-related-to-upgrades-of-finance-and-operations-apps"></a>Résoudre les problèmes liés aux mises à niveau des applications Finance and Operations

[!include [banner](../../includes/banner.md)]



Cette rubrique fournit des informations sur la résolution des problèmes de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service. Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés aux mises à niveau des applications Finance and Operations.

> [!IMPORTANT]
> Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d'administrateur système ou les identifiants d'admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d'identification sont requis.

## <a name="database-synchronization-errors"></a>Erreurs de synchronisation de base de données

**Rôle requis pour résoudre le problème :** Administrateur système

Vous pouvez recevoir un message d'erreur semblable à l'exemple suivant lorsque vous essayez d'utiliser l'entité **DualWriteProjectConfiguration** pour mettre à jour une application Finance and Operations vers Platform Update 30.

```console
Infolog diagnostic message: 'Cannot select a record in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

Pour régler le problème, procédez comme suit.

1. Connectez-vous à la machine virtuelle pour l'application Finance and Operations.
2. Ouvrez Visual Studio en tant qu'administrateur et ouvrez l'arbre d'objets d'application (AOA).
3. Recherchez **DualWriteProjectConfiguration**.
4. Dans l'AOA, faites un clic droit sur **DualWriteProjectConfiguration** et sélectionnez **Ajouter au nouveau projet**. Sélectionnez **OK** pour créer le nouveau projet qui utilise les options par défaut.
5. Dans l'Explorateur de solutions, cliquez avec le bouton droit sur **Propriétés du projet** et définissez **Synchroniser la base de données lors de la construction** sur la valeur **True**.
6. Générez le projet et confirmez que la génération a réussi.
7. Sur le menu **Dynamics 365**, sélectionnez **Synchroniser la base de données**.
8. Sélectionnez **Synchroniser** pour faire une synchronisation complète de la base de données.
9. Une fois la synchronisation complète de la base de données réussie, réexécutez l'étape de synchronisation de la base de données dans Microsoft Dynamics Lifecycle Services (LCS) et utilisez les scripts de mise à niveau manuelle le cas échéant, afin de pouvoir procéder à la mise à jour.

## <a name="missing-entity-fields-issue-on-maps"></a>Problème de champs d'entité manquants sur les cartes

**Rôle requis pour résoudre le problème :** Administrateur système

Sur la page **Double écriture**, vous pouvez recevoir un message d'erreur semblable à l'exemple suivant :

*Champ source manquant \<nom de domaine\> dans le schéma.*

![Exemple de message d'erreur de champ source manquant](media/error_missing_field.png)

Pour résoudre le problème, suivez d'abord ces étapes pour vous assurer que les champs se trouvent dans l'entité.

1. Connectez-vous à la machine virtuelle pour l'application Finance and Operations.
2. Accédez à **Espaces de travail \> Gestion de données**, sélectionnez la vignette **Paramètres de l'environnement**, puis, sur l'onglet **Paramètres d'entité**, sélectionnez **Actualiser la liste d'entités** pour actualiser les entités.
3. Accédez à **Espaces de travail \> Gestion des données**, sélectionnez l'onglet **Entités de données** et assurez-vous que l'entité est répertoriée. Si l'entité n'est pas répertoriée, connectez-vous à la machine virtuelle pour l'application Finance and Operations et assurez-vous que l'entité est disponible.
4. Ouvrez la page **Mappage d'entités** depuis la page **Double écriture** dans l'application Finance and Operations.
5. Sélectionnez **Actualiser la liste d'entités** pour remplir automatiquement les champs dans les mappages d'entités.

Si le problème n'est toujours pas résolu, procédez comme suit.

> [!IMPORTANT]
> Ces étapes vous guident tout au long du processus de suppression d'une entité, puis de son ajout à nouveau. Pour éviter les problèmes, assurez-vous de suivre exactement les étapes.

1. Dans l'application Finance and Operations, accédez à **Espaces de travail \> Gestion des données** et sélectionnez la vignette **Entités de données**.
2. Recherchez l'entité qui manque pour l'attribut. Cliquez sur **Modifier le mappage cible** dans la barre d'outils.
3. Sur le volet **Mapper l'échelonnement à la cible**, cliquez sur **Générer un mappage**.
4. Ouvrez la page **Mappage d'entités** depuis la page **Double écriture** dans l'application Finance and Operations.
5. Si l'attribut n'est pas renseigné automatiquement sur la carte, ajoutez-le manuellement en cliquant sur le bouton **Ajouter un attribut** puis sur **Enregistrer**. 
6. Sélectionnez le mappage, puis cliquez sur **Exécuter**.
