---
title: Résoudre les problèmes liés à la double écriture dans les applications Finance et Opérations
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés au module Double écriture dans les applications Finance et Opérations.
author: RamaKrishnamoorthy
ms.date: 04/12/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 58b20e38269922203b54173509e31c5e6f30c25b
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2022
ms.locfileid: "8565964"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a>Résoudre les problèmes liés à la double écriture dans les applications Finance et Opérations

[!include [banner](../../includes/banner.md)]



Cette rubrique fournit des informations sur le dépannage de l’intégration de la double-écriture entre les applications Finance et Opérations et Dataverse. Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés au module **Double écriture** dans les applications Finance et Opérations.

> [!IMPORTANT]
> Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Vous ne pouvez pas charger le module Double écriture dans une application Finance et Opérations

Si vous ne pouvez pas ouvrir la page **Double écriture** en sélectionnant la vignette **Double écriture** dans l’espace de travail **Gestion des données**, le service d’intégration de données est probablement en panne. Créez un ticket de support pour demander un redémarrage du service d’intégration de données.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>Erreur lorsque vous essayez de créer un mappage de table

**Informations d’identification requises pour résoudre le problème :** Le même utilisateur qui a configuré la double écriture.

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez de configurer une nouvelle table pour la double écriture. Le seul utilisateur qui peut créer un mappage est celui qui a configuré la connexion à double écriture.

*Le code d’état de réponse n’indique pas la réussite : 401 (Non autorisé).*

## <a name="error-when-you-open-the-dual-write-user-interface"></a>Erreur lorsque vous ouvrez l’interface utilisateur de double écriture

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez d’accéder à la double écriture à partir de l’espace de travail **Gestion des données** :

*login.microsoftonline.com a refusé de se connecter.*

Pour résoudre le problème, connectez-vous à l’aide d’une fenêtre InPrivate dans Microsoft Edge, une fenêtre de navigation privée dans Chromium ou une fenêtre de navigation privée dans Google Chrome. Vous devez également débloquer ou effacer les cookies tiers.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>Erreur lorsque vous liez l’environnement pour la double écriture ou ajoutez un nouveau mappage de table

**Rôle requis pour résoudre le problème :** administrateur système dans l’application Finance et Opérations et Dataverse.

Vous pouvez rencontrer l’erreur suivante lors de la liaison ou de la création de cartes :

```dos
Response status code does not indicate success: 403 (tokenexchange).
Session ID: \<your session id\>
Root activity ID: \<your root activity\> id
```

Cette erreur peut se produire si vous ne disposez pas des autorisations suffisantes pour lier la double écriture ou créer des cartes. Cette erreur peut également se produire si l’environnement Dataverse a été réinitialisé sans dissocier la double écriture. Tout utilisateur ayant un rôle d’administrateur système dans les applications Finance et Opérations et Dataverse peut relier les environnements. Seul l’utilisateur qui a configuré la connexion à double écriture peut ajouter de nouveaux mappages de tables. Après la configuration, tout utilisateur ayant un rôle d’administrateur système peut surveiller le statut et modifier les mappages.

## <a name="error-when-you-stop-the-table-mapping"></a>Erreur lorsque vous arrêtez le mappage de tables

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez d’arrêter les mappages de tables :

*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Le serveur distant a renvoyé une erreur : (403) Forbidden.*

Cette erreur se produit lorsque l’environnement Dataverse associé n’est pas disponible.

Pour résoudre le problème, créez un ticket pour l’équipe d’intégration de données. Associez le suivi du réseau afin que l’équipe d’intégration de données puisse marquer les cartes comme **Pas en cours d’exécution** à l’arrière-plan.

## <a name="enable-parallel-processing-in-finance-and-operations-apps-to-improve-performance"></a>Activer le traitement parallèle dans les applications Finance et Opérations pour améliorer les performances

L'activation du traitement parallèle peut réduire le temps nécessaire pour importer les données des applications Finance et Opérations dans les applications d'engagement client et Microsoft Dataverse. 

Pour activer le traitement parallèle dans les applications Finance et Opérations, procédez comme suit.

1. Connectez-vous à votre environnement Finance et Opérations.
2. Accédez à **Gestion des données > Paramètres de l'environnement**.
3. Sélectionnez **Paramètres d'entité** et sélectionnez **Configurer les paramètres d'exécution de l'entité**.
4. Ajoutez les paramètres pour le traitement parallèle :
    - **Seuil d'importation du nombre d'enregistrements** : le nombre d'enregistrements qui doit être atteint avant que le traitement parallèle ne soit activé.
    - **Nombre de tâches d'importation** : le nombre de threads (tâches) à exécuter en parallèle.
5. Cliquez sur **Enregistrer**.


## <a name="errors-while-trying-to-start-a-table-mapping"></a>Erreurs lors de la tentative de démarrage d’un mappage de tables

### <a name="unable-to-complete-initial-data-sync"></a>Impossible de terminer la synchronisation initiale des données

Vous pouvez recevoir une erreur telle que la suivante lorsque vous essayez d’exécuter la synchronisation initiale :

*Impossible de terminer la synchronisation initiale des données. Erreur : échec de double écriture – échec de l’enregistrement du plug-in : impossible de créer des métadonnées de recherche en double écriture. La référence d’objet d’erreur n’est pas définie sur une instance d’un objet.*

Vous pouvez recevoir une erreur comme celle-ci lorsque vous essayez de définir cet état d’un mappage sur **Exécution en cours**. Le correctif dépend de la cause de l’erreur :

+ Si le mappage a des mappages dépendants, assurez-vous d’activer les mappages dépendants de ce mappage de table.
+ Le mappage peut ne pas contenir de colonnes sources ou de destination. Si une colonne de l’application Finance et Opérations est manquant, suivez les étapes de la section [Problème de colonnes de table manquantes sur les mappages](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps). Si une colonne dans Dataverse est manquante, cliquez sur **Actualiser les tables** sur le mappage afin que les colonnes soient automatiquement remplies à nouveau dans le mappage.

### <a name="version-mismatch-error-and-upgrading-dual-write-solutions"></a>Erreur de non-concordance de version et mise à niveau des solutions à double écriture

Vous pouvez recevoir les messages d’erreur suivants lorsque vous essayez d’exécuter les mappages de tables :

+ *Groupes de clients (msdyn_customergroups) : Échec de la double écriture – La solution Dynamics 365 for Sales ’Dynamics365Company’ a une incompatibilité de version. Version : ’2.0.2.10’ Version requise : ’2.0.133’*
+ La solution *Dynamics 365 for Sales ’Dynamics365FinanceExtended’ a une incompatibilité de version. Version : ’1.0.0.0’ Version requise : ’2.0.227’*
+ La solution *Dynamics 365 for Sales ’Dynamics365FinanceAndOperationsCommon’ a une incompatibilité de version. Version : ’1.0.0.0’ Version requise : ’2.0.133’*
+ La solution *Dynamics 365 for Sales ’CurrencyExchangeRates’ a une incompatibilité de version. Version : ’1.0.0.0’ Version requise : ’2.0.133’*
+ La solution *Dynamics 365 for Sales ’Dynamics365SupplyChainExtended’ a une incompatibilité de version. Version : ’1.0.0.0’ Version requise : ’2.0.227’*

Pour résoudre les problèmes, mettez à jour les solutions de double écriture dans Dataverse. Assurez-vous de mettre à niveau vers la dernière solution qui correspond à la version de solution requise.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
