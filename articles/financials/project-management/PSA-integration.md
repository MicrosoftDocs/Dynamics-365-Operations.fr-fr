---
title: Project Service Automation
description: "Cette rubrique fournit des informations sur la solution d'intégration de Project Service Automation à Finance and Operations. Cette solution d'intégration utilise la fonction Intégration des données pour synchroniser les données entre les instances de Microsoft Dynamics 365 for Finance and Operations et de Microsoft Dynamics 365 for Project Service Automation via Common Data Service."
author: KimANelson
manager: AnnBe
ms.date: 06/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 841ea53f754f61c2930e77fdafc85eac72f47d7a
ms.openlocfilehash: 4b1d2ae69899a2937d47f6547ee4ba72b2d1ece4
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---

# <a name="project-service-automation"></a>Project Service Automation

[!include[banner](../includes/banner.md)]

La solution d'intégration de Project Service Automation avec Finance and Operations utilise la fonction Intégration des données pour synchroniser les données entre les instances de Microsoft Dynamics 365 for Finance and Operations et de Microsoft Dynamics 365 for Project Service Automation via Common Data Service. Les modèles d'intégration disponibles avec la fonction Intégration des données activent le flux de projets, de contrats de projet, de lignes de contrat de projet, de jalons de ligne de contrat de projet, de tâches de projet, de catégories de transaction de dépense, d'estimations des heures et d'estimations des dépenses entre Project Service Automation et Finance and Operations.

> [!NOTE]
> - Si vous utilisez Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, après avoir installé KB 4132657 et KB 4132660, vous pourrez utiliser les modèles pour intégrer les tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et les transactions réelles, ainsi que pour configurer le verrouillage des fonctionnalités. Si vous devez réinitialiser les répartitions comptables, nous vous recommandons d'installer également KB 4131710.
> - Si vous utilisez Finance and Operations 7.3.0, vous devez installer KB 4074835. Cela vous permet ensuite d'intégrer les projets à prix fixe.
> - Si vous utilisez Finance and Operations 7.3.0, et que vous apportez des transactions de frais de Project Service Automation, vous devez installer KB 4345320 pour inclure ces frais de la facture de projet.
> - Si vous utilisez la version 8.0 de Microsoft Dynamics 365 for Finance and Operations, vous pourrez utiliser l'intégration de tâche de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités.
> - Si vous utilisez la version 8.0.1 de Microsoft Dynamics 365 for Finance and Operations ou ultérieure, vous pourrez synchroniser des transactions réelles.

Avant de pouvoir intégrer Project Service Automation avec Finance and Operations, vous devez configurer les paramètres d'intégration de Project Service Automation. Pour plus d'informations, voir [Paramètres d'intégration de Project Service Automation](PSA-parameters.md).

Cette solution d'intégration active la synchronisation directe dans les scénarios suivants :

- Gérez les contrats de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.
- Créez des contrats dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.
- Gérez les lignes de contrat de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.
- Gérez les jalons de ligne de contrat de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.
- Gérez les tâches de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.
- Gérez les catégories de transaction de dépense dans Finance and Operations et synchronisez-les directement entre Finance and Operations et Project Service Automation.
- Créez des estimations des heures du projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.
- Créez des estimations des dépenses du projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.
- Créez du temps de projet, des dépenses et des transactions réelles de frais dans Project Service Automation, puis créez des transactions de projet dans le journal d'intégration Project Service Automation afin qu'elles puissent être validées dans Finance and Operations.

## <a name="data-synchronization"></a>Synchronisation des données

L'illustration suivante indique comment les données sont synchronisées dans le cadre de l'intégration entre Project Service Automation et Finance and Operations.

> [!NOTE]
> Tous les modèles ne sont pas disponibles actuellement. Les modèles seront disponibles dès qu'il seront terminés.

[![Intégration de Project Service Automation avec Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance-and-operations"></a>Configuration requise pour Finance and Operations

Pour utiliser la solution d'intégration de Project Service Automation avec Finance and Operations, vous devez installer Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 avec Platform Update 12 ou une version ultérieure.

## <a name="system-requirements-for-project-service-automation"></a>Configuration requise pour Project Service Automation

Pour utiliser la solution d'intégration de Project Service Automation avec Finance and Operations, vous devez installer les composants suivants :

- Microsoft Dynamics 365 for Project Service Automation, version 9.0.0.0 ou ultérieure
- Prospect pour une solution de disponibilités pour Microsoft Dynamics 365 for Sales, version 1.14.0.0 (v14) or ultérieure
- Solution d'intégration de Project Service Automation avec Finance and Operations pour Microsoft Dynamics 365 for Project Service Automation version 1.0.0.0 ou ultérieure

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a>Installer la solution d'intégration de Project Service Automation avec Finance and Operations dans votre instance de Project Service Automation

Téléchargez la solution d'intégration de Project Service Automation dans Finance and Operations depuis le [Centre de téléchargement Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=57016), et suivez les instructions fournies dans la solution.

