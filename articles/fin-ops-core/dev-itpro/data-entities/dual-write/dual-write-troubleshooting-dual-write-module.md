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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172758"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a>Résoudre les problèmes liés au module Double écriture dans les applications Finance and Operations

[!include [banner](../../includes/banner.md)]



Cette rubrique fournit des informations sur la résolution des problèmes de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service. Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés au module **Double écriture** dans les applications Finance and Operations.

> [!IMPORTANT]
> Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d'administrateur système ou les identifiants d'admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d'identification sont requis.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Vous ne pouvez pas charger le module Double écriture dans une application Finance and Operations

Si vous ne pouvez pas ouvrir la page **Double écriture** en sélectionnant la vignette **Double écriture** dans l'espace de travail **Gestion des données**, le service d'intégration de données est probablement en panne. Créez un ticket de support pour demander un redémarrage du service d'intégration de données.

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a>Erreur lorsque vous essayez de créer un nouveau mappage d'entité

**Informations d'identification requises pour résoudre le problème :** admin client Azure AD

Vous pouvez recevoir le message d'erreur suivant lorsque vous essayez de configurer une nouvelle entité pour la double écriture :

*Le code d'état de réponse n'indique pas la réussite : 401 (Non autorisé).*

Cette erreur se produit, car seul un admin client Azure AD peut ajouter un nouveau mappage d'entité.

Pour résoudre le problème, connectez-vous à l'application Finance and Operations en tant qu'admin client Azure AD. Vous devez également aller sur web.PowerApps.com et revalider votre connexion.

## <a name="error-when-you-open-the-dual-write-user-interface"></a>Erreur lorsque vous ouvrez l'interface utilisateur de double écriture

Vous pouvez recevoir le message d'erreur suivant lorsque vous essayez d'accéder à la double écriture à partir de l'espace de travail **Gestion des données** :

*login.microsoftonline.com a refusé de se connecter.*

Pour résoudre le problème, connectez-vous à l'aide d'une fenêtre InPrivate dans Microsoft Edge, une fenêtre de navigation privée dans Chromium ou une fenêtre de navigation privée dans Google Chrome. Vous devez également débloquer ou effacer les cookies tiers.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a>Erreur lorsque vous liez l'environnement pour la double écriture ou ajoutez un nouveau mappage d'entité

**Informations d'identification requises pour résoudre le problème :** admin client Azure AD

Vous pouvez rencontrer l'erreur suivante lors de la liaison ou de la création de cartes :

*Le code d'état de réponse n'indique pas la réussite : 403 (échange de jetons).<br> ID de session : \<votre identifiant de session\><br> ID d'activité racine : \<votre identifiant d'activité racine\>*

Cette erreur peut se produire si vous ne disposez pas des autorisations suffisantes pour lier la double écriture ou créer des cartes. Vous devez utiliser un compte admin client Azure AD pour lier les environnements et ajouter de nouveaux mappages d'entités. Cependant, après la configuration, vous pouvez utiliser un compte non administrateur pour surveiller l'état et modifier les mappages.

## <a name="error-when-you-stop-the-entity-mapping"></a>Erreur lorsque vous arrêtez le mappage d'entité

Vous pouvez recevoir le message d'erreur suivant lorsque vous essayez d'arrêter les mappages d'entités :

*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Le serveur distant a renvoyé une erreur : (403) Forbidden.*

Cette erreur se produit lorsque l'environnement Common Data Service associé n'est pas disponible.

Pour résoudre le problème, créez un ticket pour l'équipe d'intégration de données. Associez le suivi du réseau afin que l'équipe d'intégration de données puisse marquer les cartes comme **Pas en cours d'exécution** à l'arrière-plan.
