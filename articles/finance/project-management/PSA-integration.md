---
title: Vue d'ensemble de Project Service Automation
description: Cette rubrique fournit des informations relatives à Dynamics 365 Project Service Automation dans la solution d'intégration Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250551"
---
# <a name="project-service-automation-overview"></a>Vue d'ensemble de Project Service Automation

[!include[banner](../includes/banner.md)]

La solution d'intégration de Project Service Automation avec Finance utilise la fonction Intégration des données pour synchroniser les données entre les instances de Dynamics 365 Finance et Dynamics 365 Project Service Automation via Common Data Service. Les modèles d'intégration disponibles avec la fonction Intégration des données activent le flux de projets, de contrats de projet, de lignes de contrat de projet, de jalons de ligne de contrat de projet, de tâches de projet, de catégories de transaction de dépense, d'estimations des heures et d'estimations des dépenses entre Project Service Automation et Finance.

> [!NOTE]
> - Si vous utilisez la version 7.3.0, vous devez installer KB 4074835. Cela vous permet ensuite d'intégrer les projets à prix fixe.
> - Si vous utilisez la version 7.3.0, et que vous apportez des transactions de frais de Project Service Automation, vous devez installer KB 4345320 pour inclure ces frais de la facture de projet.
> - Si vous utilisez la version 8.0, vous serez en mesure d'utiliser l'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités.
> - Si vous utilisez la version 8.0.1 ou ultérieure, vous pourrez synchroniser les chiffres réels.

Avant de pouvoir intégrer Project Service Automation avec Finance, vous devez configurer les paramètres d'intégration de Project Service Automation. Pour plus d'informations, voir [Paramètres d'intégration de Project Service Automation](PSA-parameters.md).

Cette solution d'intégration active la synchronisation directe dans les scénarios suivants :

- Gérez les contrats de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.
- Créez des contrats dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.
- Gérez les lignes de contrats de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.
- Gérez les jalons des lignes de contrats de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.
- Gérez les tâches de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.
- Gérez les catégories de transaction de dépense dans Finance et synchronisez-les directement entre Finance et Project Service Automation.
- Créez des estimations des heures du projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.
- Créez des estimations des dépenses du projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.
- Créez du temps de projet, des dépenses et des transactions réelles de frais dans Project Service Automation, puis créez des transactions de projet dans le journal d'intégration Project Service Automation afin qu'elles puissent être validées dans Finance.

## <a name="data-synchronization"></a>Synchronisation des données

L'illustration suivante indique comment les données sont synchronisées dans le cadre de l'intégration entre Project Service Automation et Finance.

> [!NOTE]
> Tous les modèles ne sont pas disponibles actuellement. Les modèles seront disponibles dès qu'il seront terminés.

[![Intégration de Project Service Automation avec Finance](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance"></a>Configuration requise pour Finance

Pour utiliser la solution d'intégration de Project Service Automation avec Finance, vous devez installer Enterprise Edition 7.3 avec Platform Update 12 ou version ultérieure.

## <a name="system-requirements-for-project-service-automation"></a>Configuration requise pour Project Service Automation

Pour utiliser la solution d'intégration de Project Service Automation avec Finance, vous devez installer les composants suivants :

- Dynamics 365 Project Service Automation version 9.0.0.0 ou version ultérieure
- Prospect pour une solution de disponibilités pour Dynamics 365 Sales, version 1.14.0.0 (v14) or ultérieure.
- Solution Project Service Automation avec Finance pour Dynamics 365 Project Service Automation version 1.0.0.0 ou ultérieure

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a>Installer la solution d'intégration de Project Service Automation avec Finance dans votre instance de Project Service Automation

Téléchargez la solution d'intégration de Project Service Automation dans Finance depuis le [Centre de téléchargement Microsoft](https://www.microsoft.com/download/details.aspx?id=57016), et suivez les instructions fournies dans la solution.
