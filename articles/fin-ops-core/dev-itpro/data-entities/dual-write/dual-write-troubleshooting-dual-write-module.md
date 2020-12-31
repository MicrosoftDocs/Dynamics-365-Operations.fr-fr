---
title: Résoudre les problèmes liés au module Double écriture dans les applications Finance and Operations
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés au module Double écriture dans les applications Finance and Operations.
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
ms.openlocfilehash: 2241e7e6219f95115f55bc45a4d94550276e1e21
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683621"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a>Résoudre les problèmes liés au module Double écriture dans les applications Finance and Operations

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique fournit des informations sur la résolution des problèmes de l’intégration de la double écriture entre les applications Finance and Operations et Dataverse. Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés au module **Double écriture** dans les applications Finance and Operations.

> [!IMPORTANT]
> Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Vous ne pouvez pas charger le module Double écriture dans une application Finance and Operations

Si vous ne pouvez pas ouvrir la page **Double écriture** en sélectionnant la vignette **Double écriture** dans l’espace de travail **Gestion des données**, le service d’intégration de données est probablement en panne. Créez un ticket de support pour demander un redémarrage du service d’intégration de données.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>Erreur lorsque vous essayez de créer un mappage de table

**Informations d’identification requises pour résoudre le problème :** Le même utilisateur qui a configuré la double écriture.

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez de configurer une nouvelle entité pour la double écriture. Le seul utilisateur qui peut créer un mappage est celui qui a configuré la connexion à double écriture.

*Le code d’état de réponse n’indique pas la réussite : 401 (Non autorisé).*


## <a name="error-when-you-open-the-dual-write-user-interface"></a>Erreur lorsque vous ouvrez l’interface utilisateur de double écriture

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez d’accéder à la double écriture à partir de l’espace de travail **Gestion des données** :

*login.microsoftonline.com a refusé de se connecter.*

Pour résoudre le problème, connectez-vous à l’aide d’une fenêtre InPrivate dans Microsoft Edge, une fenêtre de navigation privée dans Chromium ou une fenêtre de navigation privée dans Google Chrome. Vous devez également débloquer ou effacer les cookies tiers.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>Erreur lorsque vous liez l’environnement pour la double écriture ou ajoutez un nouveau mappage de table

**Rôle requis pour corriger le problème :** Administrateur système dans les applications Finance and Operations et Dataverse.

Vous pouvez rencontrer l’erreur suivante lors de la liaison ou de la création de cartes :

*Le code d’état de réponse n’indique pas la réussite : 403 (échange de jetons).<br> ID de session : \<your session id\><br> ID d’activité racine : \<your root activity id\>*

Cette erreur peut se produire si vous ne disposez pas des autorisations suffisantes pour lier la double écriture ou créer des cartes. Cette erreur peut également se produire si l’environnement Dataverse a été réinitialisé sans dissocier la double écriture. Tout utilisateur ayant un rôle d’administrateur système dans les applications Finance and Operations et Dataverse peut relier les environnements. Seul l’utilisateur qui a configuré la connexion à double écriture peut ajouter de nouveaux mappages de tables. Après la configuration, tout utilisateur ayant un rôle d’administrateur système peut surveiller le statut et modifier les mappages.

## <a name="error-when-you-stop-the-table-mapping"></a>Erreur lorsque vous arrêtez le mappage de tables

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez d’arrêter les mappages de tables :

*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Le serveur distant a renvoyé une erreur : (403) Forbidden.*

Cette erreur se produit lorsque l’environnement Dataverse associé n’est pas disponible.

Pour résoudre le problème, créez un ticket pour l’équipe d’intégration de données. Associez le suivi du réseau afin que l’équipe d’intégration de données puisse marquer les cartes comme **Pas en cours d’exécution** à l’arrière-plan.

## <a name="error-while-trying-to-start-an-table-mapping"></a>Erreur lors de la tentative de démarrage d’un mappage de tables

Vous pouvez recevoir une erreur comme celle-ci lorsque vous essayez de définir cet état d’un mappage sur **Exécution en cours** :

*Impossible de terminer la synchronisation initiale des données. Erreur : échec de double écriture - échec de l’enregistrement du plug-in : impossible de créer des métadonnées de recherche en double écriture. La référence d’objet d’erreur n’est pas définie sur une instance d’un objet.*

Le correctif de cette erreur dépend de la cause de l’erreur :

+ Si le mappage a des mappages dépendants, assurez-vous d’activer les mappages dépendants de ce mappage de table.
+ Le mappage peut ne pas contenir de champs sources ou de destination. Si un champ de l’application Finance and Operations est manquant, suivez les étapes de la section [Problème de champs d’entité manquants sur les mappages](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps). Si un champ dans Dataverse est manquant, cliquez sur **Actualiser les tables** sur le mappage afin que les champs soient automatiquement remplis à nouveau dans le mappage.
