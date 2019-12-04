---
title: Prise en main de l'Optimisation de la planification
description: Cette rubrique explique comment utiliser la fonctionnalité d'Optimisation de la planification.
author: ChristianRytt
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 37c2acb2397b2a0ad69272c0645bd200a8d7910d
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773955"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a>Prise en main de l'Optimisation de la planification

La fonctionnalité d'Optimisation de la planification ne prend actuellement pas en charge toutes les fonctionnalités disponibles dans le moteur de planification intégré à Microsoft Dynamics 365 Supply Chain Management. Par conséquent, il est important d'évaluer si la fonctionnalité définie, qui est actuellement disponible dans Optimisation de la planification, répondra à vos attentes. Par défaut, la fonctionnalité d'Optimisation de la planification n'est pas activée dans Dynamics Lifecycle Services (LCS). Par conséquent, vous avez une possibilité de faire votre évaluation avant qu'elle ne s'est activée.

Éventuellement, Optimisation de la planification remplacera le moteur de planification de Supply Chain Management existant.

Avant d'activer l'Optimisation de la planification, nous vous recommandons fortement d'évaluer les résultats de l'analyse de concordance d'Optimisation de la planification. Pour plus d'informations, voir [Analyse de concordance d'Optimisation de la planification](planning-optimization-fit-analysis.md).

### <a name="licensing"></a>Gestionnaire de licences

Si vous pouvez exécuter la planification à l'aide de votre licence actuelle, vous n'avez pas à en acheter une supplémentaire pour commencer à utiliser Optimisation de la planification.

### <a name="install-the-add-in"></a>Installer le complément

Pour utiliser l'Optimisation de la planification, installez le complément d'Optimisation de la planification pour Dynamics 365 Supply Chain Management. Vous pouvez accéder au complément depuis votre projet LCS et activer la fonctionnalité d'Optimisation de la planification depuis l'interface utilisateur de Supply Chain Management.

1. Connectez-vous à LCS, et ouvrez l'environnement souhaité.
1. Accédez à **Détails complets**.
1. Sélectionnez **Mettre à jour**, ou faites défiler jusqu'à l'organisateur **Compléments d'environnement**.
1. Sélectionnez **Installer un nouveau complément**.
1. Sélectionnez **Optimisation de la planification**.
1. Suivez le guide d'installation, et acceptez les conditions générales du contrat.
1. Sélectionnez **Installer**.

### <a name="planning-optimization-integration"></a>Intégration d'Optimisation de la planification

Pour configurer si le complément de l'Optimisation de la planification doit être utilisée pour la planification, accédez à **Planification** \> **Paramétrage** \> **Intégration d'Optimisation de la planification** \> **Paramètres d'intégration**.

#### <a name="connection-status"></a>Statut de la connexion

Le statut de connexion indique le statut actuel de la connexion entre Supply Chain Management et le service Optimisation de la planification. Le tableau suivant présente les valeurs possibles.

| Statut de la connexion | Description | L'Optimisation de la planification peut-elle être utilisée ? |
|---|---|---|
| Connecté | Une connexion a été établie entre le service d'Optimisation de la planification et Supply Chain Management. | Oui |
| Activation de la connexion | Une demande pour activer la connexion au service d'Optimisation de la planification est actuellement en cours. | Non |
| Déconnecté | Il n'existe aucune connexion au service d'Optimisation de la planification. La connexion peut être activée depuis LCS, comme décrit précédemment dans cette rubrique. | Non |
| Désactivation de la connexion | Une demande pour désactiver la connexion au service d'Optimisation de la planification est actuellement en cours. | Non |
| Récupération du statut | Le système est en attente des informations relatives au statut provenant d'Optimisation de la planification. | Non |

#### <a name="the-use-planning-optimization-option"></a>Utilisation de l'option Optimisation de la planification

Le paramètre de l'option **Utiliser l'Optimisation de la planification** détermine quel moteur de planification est utilisé pour la planification :

- **Oui** – L'Optimisation de la planification est utilisée pour la planification.
- **Non** – Le moteur de planification intégré dans Supply Chain Management est utilisé pour la planification.

> [!NOTE]
> Si des traitements par lots existants de planification créés pour le moteur de planification intégré de Supply Chain Management sont déclenchés tandis que l'option **Utiliser l'Optimisation de la planification** est définie sur **Oui**, ces tâches échoueront.

### <a name="integration-with-the-setup"></a>Intégration à la configuration

Si l'aperçu Optimisation de la planification est activé, la planification est effectuée à l'aide du complément Optimisation de la planification. Dans ce cas, les résultats de la planification et le fonctionnalités sont concernés.

## <a name="related-resources"></a>Ressources associées

[Conditions générales pour l'aperçu](https://go.microsoft.com/fwlink/?linkid=2015274)

[Vue d'ensemble de l'optimisation de la planification](planning-optimization-overview.md)

[Analyse de concordance d'optimisation de la planification](planning-optimization-fit-analysis.md)

[Afficher l'historique du plan et les journaux de planification](plan-history-logs.md)

[Appliquer les filtres à un plan](plan-filters.md)

[Annuler une tâche de planification](cancel-planning-job.md)
