---
title: Étendre Talent avec Power Apps et Power Automate
description: Cet article décrit quelques exemples de scénarios d’extensibilité pour Microsoft Dynamics 365 Human Resources utilisant Microsoft Power Apps et Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core;Experience Apps;Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2e89347829ccd6569d568db42c79b5fea2316ba3
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527024"
---
# <a name="extend-with-power-apps-and-power-automate"></a>Extension avec Power Apps et Power Automate

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cet article décrit quelques exemples de scénarios d’extensibilité pour Microsoft Dynamics 365 Human Resources utilisant Microsoft Power Apps et Microsoft Power Automate. Vous pouvez importer le module de solution associé à chaque exemple dans l’environnement de Power Apps. Vous pouvez ensuite utiliser les modules comme orientation ou comme point de départ pour implémenter les scénarios qui s’appliquent à votre organisation.

> [!IMPORTANT]
> Pour utiliser les modèles et les applications décrits dans cette rubrique « en l’état », veillez à les tester pour vous assurer qu’ils couvrent tous les scénarios spécifiques à votre implémentation.

## <a name="prerequisites"></a>Conditions préalables

- Pour importer des modules, les utilisateurs doivent avoir l’autorisation **Créateur d’environnement**.
- Pour exporter ou importer des applications, les utilisateurs doivent disposer d’une licence Power Apps Plan 2 ou une licence d’essai Power Apps Plan 2.

## <a name="integration-with-microsoft-365-power-automate"></a>Intégration à Microsoft 365, Power Automate

L’application **Intégration à Microsoft 365** peut être utilisée pour extraire les informations d’équipe pour les utilisateurs connectés à partir de Microsoft 365. Il fait référence aux employés de Human Resources pour extraire les types d’identification des employés. Les responsables peuvent vérifier les dates d’expiration des types d’ID d’employé. Ils peuvent également envoyer un rappel par e-mail si le type d’ID d’employé arrive à expiration. Power Automate s’intègre à Power Apps pour envoyer ce rappel. La confirmation sera renvoyée à Power Apps à partir de Power Automate lorsque le rappel est envoyé. Les types d’identification comprennent le permis de conduire, le passeport et d’autres pièces d’identité acceptables.

Vous pouvez étendre cette application pour d’autres scénarios. Par exemple, vous pouvez l’utiliser pour afficher les informations de congés d’équipe, les événements de calendrier, et tout événement spécifique à une équipe.

Pour télécharger l’application **Intégration à Microsoft 365, Power Automate**, accédez à [Intégration à Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) dans le Centre de téléchargement Microsoft.

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate – Connexion et exécution SQL

Le modèle **Power Automate - Connexion et exécution SQL** se connecte à Microsoft SQL Server et active les requêtes SQL à exécuter.

Bien que ce modèle lise et mette à jour les tables SQL, vous pouvez l’étendre et l’utiliser pour d’autres scénarios. Par exemple, vous pouvez l’utiliser pour remplir une table intermédiaire dans Common Data Service avec des enregistrements de SQL Server, et pour synchroniser périodiquement la table intermédiaire à l’aide d’un envoi incrémentiel de SQL Server.

Advanced Query est intégré à Flow pour permettre la transformation des données et la transmission incrémentielle.

Pour télécharger le modèle **Power Automate – Connexion et exécution SQL**, accédez à [Power Automate – Connexion et exécution SQL](https://go.microsoft.com/fwlink/?linkid=2081789) dans le Centre de téléchargement Microsoft.

## <a name="additional-resources"></a>Ressources supplémentaires

[Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>