---
title: Démarrage de l’optimisation de la planification
description: Cet article explique comment utiliser la fonctionnalité d’Optimisation de la planification.
author: t-benebo
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: b9595aece264f55c706ebc84010b927fae56b512
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900968"
---
# <a name="get-started-with-planning-optimization"></a>Mise en route de l’optimisation de la planification

[!include [banner](../../includes/banner.md)]

Comme [annoncé précédemment](../../get-started/removed-deprecated-features-scm-updates.md#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios), une optimisation de la planification est planifiée pour remplacer le moteur de planification principal intégré existant.

Si vous utilisez actuellement le moteur de planification principal intégré, vous devez commencer à planifier votre migration vers l’optimisation de la planification. Il est important de démarrer immédiatement le processus de migration car vos opérations peuvent être affectées quand l’obsolescence est appliquée. Pour éviter les problèmes de dernière minute quand l’obsolescence est appliquée, nous vous encourageons vivement à terminer la migration avant le 1er décembre 2020. 

La fonctionnalité d’optimisation de la planification ne prend actuellement pas en charge toutes les fonctionnalités disponibles dans le moteur de planification intégré à Supply Chain Management. Par conséquent, il est important d’évaluer si la fonctionnalité définie, qui est actuellement disponible dans Optimisation de la planification, répondra à vos attentes. La fonctionnalité d’optimisation de la planification n’est actuellement pas activée par défaut dans Dynamics Lifecycle Services (LCS), vous avez donc la possibilité de faire votre évaluation avant que la fonctionnalité ne soit activée.

> [!NOTE]
> Vous devez demander une exception pour la migration vers l’optimisation de la planification si votre processus de planification générale n’inclut pas la production (planification générale des ordres de fabrication planifiés générés) et si vous avez besoin du moteur de planification principal intégré au-delà de la version 10.0.15. À compter de la version 10.0.16, une erreur s’affiche dans les environnements au moment de l’exécution de la planification générale intégrée sans génération d’ordres de fabrication planifiés. L’optimisation de la planification doit être utilisée pour tous les nouveaux déploiements qui ne génèrent pas d’ordres de production planifiés au moment de la planification générale. Les propriétaires d’environnements existants exécutant le moteur de planification principal intégré sans génération d’ordres de production planifiés recevront un e-mail contenant des détails sur le processus d’exception. Nous vous recommandons de travailler avec un partenaire pour évaluer et planifier la migration vers l’optimisation de la planification.

Avant d’activer l’Optimisation de la planification, nous vous recommandons fortement d’évaluer les résultats de l’analyse de concordance d’Optimisation de la planification. Pour plus d’informations, voir [Analyse de concordance d’Optimisation de la planification](planning-optimization-fit-analysis.md).

## <a name="availability"></a>Disponibilité

Le complément Optimisation de la planification est actuellement disponible dans les zones géographiques Azure suivantes : États-Unis, Canada, Brésil, Europe, Royaume-Uni, Australie, Asie-Pacifique, Japon et Inde. Si vous essayez d’installer le complément à partir d’une autre région géographique, LCS affichera un message indiquant que cette zone géographique n’est pas prise en charge. Pour plus d’informations sur les zones géographiques Azure et les régions associées, consultez [Géographies Azure](https://azure.microsoft.com/global-infrastructure/geographies/#geographies).

Notez que Optimisation de la planification ne prend pas en charge les déploiements locaux de Dynamics 365 Supply Chain Management.

## <a name="licensing"></a>Gestionnaire de licences

Si vous pouvez exécuter la planification à l’aide de votre licence actuelle, vous n’avez pas à en acheter une supplémentaire pour commencer à utiliser Optimisation de la planification.

## <a name="install-and-enable-planning-optimization"></a>Installer et activer le complément Optimisation de la planification

Pour utiliser le complément Optimisation de la planification, vous devez vous assurer que tous les prérequis sont en place sur votre système, puis activer sa clé de licence et installer le complément Optimisation de la planification pour Dynamics 365 Supply Chain Management.

### <a name="prerequisites"></a>Conditions préalables

Avant d’installer le complément Optimisation de la planification, les conditions préalables suivantes doivent être remplies :

- Vous devez exécuter Supply Chain Management sur un environnement à haute disponibilité compatible LCS, niveau 2 ou supérieur (pas un environnement OneBox), avec Dynamics 365 Supply Chain Management version 10.0.7 ou les versions ultérieures. Si vous essayez d’installer le complément dans un environnement OneBox, l’installation ne se terminera pas et vous devrez annuler l’installation.

- Votre système doit être configuré pour l’intégration Power Platform. Pour plus d’informations, voir [Intégration de Microsoft Power Platform avec les applications Finance et Opérations](../../../fin-ops-core/dev-itpro/power-platform/overview.md).

### <a name="enable-the-planning-optimization-license"></a>Activer la licence du complément Optimisation de la planification

Pour utiliser le complément Optimisation de la planification, vous devez activer sa clé de configuration. Pour ce faire :

1. Mettez votre système en mode maintenance comme décrit dans [Mode maintenance](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Accédez à **Administration système \> Paramétrage \> Configuration des licences**.
1. Sur l’onglet **Clés de configuration**, cochez la case **Optimisation de la planification**.
1. Désactiver le mode maintenance comme décrit dans [Mode maintenance](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="install-the-planning-optimization-add-in"></a>Installer le complément Optimisation de la planification

Vous devez installer le complément depuis votre projet LCS et activer la fonctionnalité Optimisation de la planification depuis l’interface utilisateur de Supply Chain Management.

Pour installer le complément Optimisation de la planification :

1. Connectez-vous à LCS, et ouvrez l’environnement souhaité.
1. Accédez à **Détails complets**.
1. Faites défiler jusqu’à l’organisateur **Compléments d’environnement**.
1. Sélectionnez **Installer un nouveau complément**.
1. Sélectionnez **Optimisation de la planification**.
1. Suivez le guide d’installation, et acceptez les conditions générales du contrat.
1. Sélectionnez **Installer**.
1. Sur l’organisateur **Compléments d’environnement** devriez voir que le complément Optimisation de la planification est en cours d’installation.
1. Après quelques minutes **Installation** devrait passer à **Installé** (vous devrez peut-être actualiser la page). Après l’installation, vous pouvez activer Planning Optimization dans Dynamics 365 Supply Chain Management.

L’objectif principal de l’installation du complément Optimisation de la planification est de connecter le service et l’environnement. Par conséquent, vous devez installer le complément séparément sur chaque environnement dans lequel vous utiliserez l’Optimisation de la planification, quel que soit le code déplacé entre les environnements.

## <a name="integrate-planning-optimization-with-your-system"></a>Intégrer le complément Optimisation de la planification à votre système

Pour configurer si le complément de l’Optimisation de la planification doit être utilisée pour la planification, accédez à **Planification** \> **Paramétrage** \> **Paramètres d’intégration**.

### <a name="connection-status"></a>Statut de la connexion

Le statut de connexion indique le statut actuel de la connexion entre Supply Chain Management et le service Optimisation de la planification. Le tableau suivant présente les valeurs possibles.

| Statut de la connexion | Description | L’Optimisation de la planification peut-elle être utilisée ? |
|---|---|---|
| Connecté | Une connexion a été établie entre le service d’Optimisation de la planification et Supply Chain Management. | Oui |
| Activation de la connexion | Une demande pour activer la connexion au service d’Optimisation de la planification est actuellement en cours. | Non |
| Déconnecté | Il n’existe aucune connexion au service d’Optimisation de la planification. La connexion peut être activée depuis LCS, comme décrit précédemment dans cet article. | N° |
| Désactivation de la connexion | Une demande pour désactiver la connexion au service d’Optimisation de la planification est actuellement en cours. | Non |
| Récupération du statut | Le système est en attente des informations relatives au statut provenant d’Optimisation de la planification. | Non |

### <a name="the-use-planning-optimization-option"></a>Utilisation de l’option Optimisation de la planification

Le paramètre de l’option **Utiliser l’Optimisation de la planification** détermine quel moteur de planification est utilisé pour la planification :

- **Oui** – L’Optimisation de la planification est utilisée pour la planification.
- **Non** – Le moteur de planification intégré dans Supply Chain Management est utilisé pour la planification.

Ce paramètre s’applique à toutes les entités juridiques (sociétés). Il n’est pas possible d’utiliser l’optimisation de la planification dans certaines entités juridiques et la planification générale intégrée dans d’autres entités juridiques.

> [!NOTE]
> Si des traitements par lots existants de planification créés pour le moteur de planification intégré de Supply Chain Management sont déclenchés tandis que l’option **Utiliser l’Optimisation de la planification** est définie sur **Oui**, ces tâches échoueront.

### <a name="integration-with-the-setup"></a>Intégration à la configuration

Si l’Optimisation de la planification est activée, la planification est effectuée à l’aide du complément Optimisation de la planification. Dans ce cas, les résultats de la planification et le fonctionnalités sont concernés.

## <a name="additional-resources"></a>Ressources supplémentaires

[Conditions générales pour l’aperçu](https://go.microsoft.com/fwlink/?linkid=2015274)

[Vue d’ensemble de l’optimisation de la planification](planning-optimization-overview.md)

[Analyse de concordance d’optimisation de la planification](planning-optimization-fit-analysis.md)

[Afficher l’historique du plan et les journaux de planification](plan-history-logs.md)

[Appliquer les filtres à un plan](plan-filters.md)

[Annuler une tâche de planification](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
