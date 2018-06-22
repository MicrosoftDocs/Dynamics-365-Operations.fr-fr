---
title: Project Service Automation
description: "Cette solution utilise la fonction Intégration des données pour synchroniser les données entre les instances de Microsoft Dynamics 365 for Finance and Operations et de Microsoft Dynamics 365 for Project Service Automation via Common Data Service (CDS)."
author: KimANelson
manager: AnnBe
ms.date: 11/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 0ad9e6ba7fe8dd915681da8e671ff210de887b1e
ms.contentlocale: fr-fr
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation"></a>Project Service Automation

La solution d'intégration de Project Service Automation avec Finance and Operations utilise la fonction Intégration des données pour synchroniser les données entre les instances de Microsoft Dynamics 365 for Finance and Operations et de Microsoft Dynamics 365 for Project Service Automation via Common Data Service (CDS). Les modèles d'intégration disponibles avec la fonction Intégration des données activent le flux de projets, de contrats de projet, de lignes de contrat de projet, de jalons de ligne de contrat de projet, de tâches de projet, de catégories de transaction de dépense, d'estimations des heures et d'estimations des dépenses entre Project Service Automation et Finance and Operations.

> [!NOTE] 
> Si vous utilisez Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, vous devez installer KB 4074835. Cela vous permet d'intégrer les projets à prix fixe.
>
> Si vous utilisez la version 8.0 de Dynamics 365 for Finance and Operations, vous pourrez utiliser l'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités.
>
> Si vous utilisez la version 8.0.1 de Dynamics 365 for Finance and Operations, vous pourrez synchroniser des transactions réelles.
>
> Si vous utilisez Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, après avoir installé KB 4132657 et KB 4132660, vous pourrez utiliser les modèles pour intégrer les tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et les transactions réelles, ainsi que pour configurer le verrouillage des fonctionnalités. Si vous devez réinitialiser les répartitions comptables, nous vous recommandons d'installer également KB 4131710.

Avant de pouvoir intégrer Project Service Automation avec Finance and Operations, vous devez configurer les paramètres d'intégration de Project Service Automation. Pour plus d'informations, voir Paramètres d'intégration de Project Service Automation.

Cette solution d'intégration active la synchronisation directe dans les scénarios suivants :

- Gérez les contrats de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.
- Créez des contrats dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.
- Gérez les lignes de contrat de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.
- Gérez les jalons de ligne de contrat de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.
- Gérez les tâches de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.
- Gérez les catégories de transaction de dépense dans Finance and Operations et synchronisez-les directement entre Finance and Operations et Project Service Automation.
- Créez des estimations des heures du projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.
- Créez des estimations des dépenses du projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.

## <a name="data-synchronization"></a>Synchronisation des données
L'illustration suivante indique comment les données sont synchronisées dans le cadre de l'intégration entre Project Service Automation et Finance and Operations.

> [!NOTE]
> Tous les modèles ne sont pas disponibles actuellement. Les modèles seront disponibles dès qu'il seront terminés.

[![Intégration de Project Service Automation avec Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance-and-operations"></a>Configuration requise pour Finance and Operations

Pour utiliser la solution d'intégration de Project Service Automation avec Finance and Operations, vous devez installer Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 avec Platform Update 12 ou une version ultérieure.

## <a name="system-requirements-for-project-service-automation"></a>Configuration requise pour Project Service Automation

Pour utiliser la solution d'intégration de Project Service Automation avec Finance and Operations, vous devez installer les composants suivants :

- Microsoft Dynamics 365 for Project Service Automation, version 9.0.0.0 ou ultérieure.
- Prospect pour une solution de disponibilités pour Dynamics 365 for Sales, version 1.14.0.0 (v14) or ultérieure.
- Solution d'intégration de Project Service Automation avec Operations pour Dynamics 365 for Project Service Automation version 1.0.0.0 ou ultérieure.

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a>Installer la solution d'intégration de Project Service Automation avec Finance and Operations dans votre instance de Project Service Automation



