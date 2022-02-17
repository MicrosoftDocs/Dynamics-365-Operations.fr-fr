---
title: Étendre Talent avec Power Apps et Power Automate
description: Cet article décrit quelques exemples de scénarios d’extensibilité pour Microsoft Dynamics 365 Human Resources utilisant Microsoft Power Apps et Microsoft Power Automate.
author: negudava
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fedf9b35e5dc8372fd82c6308ec5b1452eab7e8f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070298"
---
# <a name="extend-with-power-apps-and-power-automate"></a>Extension avec Power Apps et Power Automate


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



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

Le modèle **Power Automate – Connexion et exécution SQL** se connecte à Microsoft SQL Server et active les requêtes SQL à exécuter.

Bien que ce modèle lise et mette à jour les tables SQL, vous pouvez l’étendre et l’utiliser pour d’autres scénarios. Par exemple, vous pouvez l’utiliser pour remplir une table intermédiaire dans Dataverse avec des enregistrements de SQL Server, et pour synchroniser périodiquement la table intermédiaire à l’aide d’un envoi incrémentiel de SQL Server.

Advanced Query est intégré à Flow pour permettre la transformation des données et la transmission incrémentielle.

Pour télécharger le modèle **Power Automate – Connexion et exécution SQL**, accédez à [Power Automate – Connexion et exécution SQL](https://go.microsoft.com/fwlink/?linkid=2081789) dans le Centre de téléchargement Microsoft.

## <a name="additional-resources"></a>Ressources supplémentaires

[Microsoft Power Platform](/power-platform/admin/admin-documentation)</br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
