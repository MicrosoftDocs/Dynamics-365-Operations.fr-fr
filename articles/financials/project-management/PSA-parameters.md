---
title: Paramètres d'intégration de Project Service Automation
description: Cette rubrique explique comment configurer la saisie des données par défaut lorsque vous intégrez Microsoft Dynamics 365 for Project Service Automation à Microsoft Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
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
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: b58d2de323395db97d1f8ea146da55bba4e0f9c6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838982"
---
# <a name="project-service-automation-integration-parameters"></a>Paramètres d'intégration de Project Service Automation

[!include[banner](../includes/banner.md)]

Sur la page **Paramètres d'intégration de Project Service Automation**, vous pouvez configurer comment les données par défaut sont saisies lorsque vous intégrez Microsoft Dynamics 365 for Project Service Automation à Microsoft Dynamics 365 for Finance and Operations. Pour que les projets soient correctement synchronisés entre Project Service Automation et Finance and Operations, vous devez paramétrer les champs suivants.

> [!NOTE]
> - L'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités sont disponibles dans la version 8.0 de Microsoft Dynamics 365 for Finance and Operations.
> - L'intégration des chiffres réels est disponible dans Microsoft Dynamics 365 for Finance and Operations version 8.0.1 ou version ultérieure.
> - Si vous utilisez Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, après avoir installé KB 4132657 et KB 4132660, vous pourrez utiliser les modèles pour intégrer les tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et les transactions réelles, ainsi que pour configurer le verrouillage des fonctionnalités. Si vous devez réinitialiser les répartitions comptables, nous vous recommandons d'installer également KB 4131710.

| Onglet                    | Champ                | Description |
|------------------------|----------------------|-------------|
| Général                | Type de projet par défaut | Permet de sélectionner le type de projet par défaut. Lorsque les projets sont synchronisés à partir de Project Service Automation, cette valeur est utilisée si vous n'avez pas fourni de valeur par défaut dans le modèle d'intégration. Lors de la synchronisation, le champ **Type de projet** des nouveaux projets est défini sur cette valeur. Toutefois, la valeur peut être mise à jour lorsque les lignes de contrat du projet sont synchronisées depuis Project Service Automation. |
|                        | Catégorie de temps        | Permet de sélectionner la catégorie de temps par défaut. Cette valeur est utilisée lorsque les estimations d'heures sont synchronisées depuis Project Service Automation. Lorsque les estimations des heures et les estimations réelles des heures sont synchronisées à partir de Project Service Automation, le champ **Catégorie** des nouvelles prévisions d'heures du projet dans Finance and Operations est défini sur cette valeur. |
|                        | Catégorie de frais         | Permet de sélectionner la catégorie de frais par défaut. Cette valeur est utilisée lorsque les transactions réelles de frais sont synchronisées depuis Project Service Automation. Lorsque les transactions réelles de frais sont synchronisées à partir de Project Service Automation, le champ **Catégorie** des nouvelles transactions de frais dans Finance and Operations est défini sur cette valeur. |
| Valeurs par défaut des groupes de projets | Type de projet         | Cliquez sur **Nouveau** pour ajouter une ligne permettant de sélectionner le type de projet pour lequel définir le groupe de projets par défaut. Un type de projet spécifique ne peut être sélectionné qu'une seule fois dans la configuration. |
|                        | Groupe de projets        | Permet de sélectionner le groupe de projets par défaut pour le type de projet sélectionné. Lorsque de nouveaux projets sont synchronisés à partir de Project Service Automation, le champ **Groupe de projets** est défini sur la valeur par défaut du type de projet si vous n'avez pas fourni de valeur par défaut dans le modèle d'intégration. |
| Valeurs par défaut du type de facturation  | Type de facturation         | Cliquez sur **Nouveau** pour ajouter une ligne permettant de sélectionner le type de facturation pour lequel définir la propriété de ligne par défaut. Un type de facturation spécifique ne peut être sélectionné qu'une seule fois dans la configuration. |
|                        | Propriété de ligne        | Permet de sélectionner la propriété de ligne par défaut pour le type de facturation sélectionné. Lorsque de nouvelles estimations des heures, de nouvelles estimations des dépenses ou de nouvelles estimations réelles sont synchronisées dans Project Service Automation, le champ **Propriété de ligne** est défini sur la valeur par défaut du type de facturation. |
| Verrouillage de la fonctionnalité  | Non applicable       | Permet de sélectionner la fonctionnalité à désactiver dans Finance and Operations pour les projets et les contrats provenant de Project Service Automation. Par exemple, vous pouvez désactiver la possibilité de modifier les contrats et les projets, de créer des structures de répartition du travail et de saisir des feuilles de temps dans Finance and Operations. Les champs comptables continuent à être activés, même s'ils sont rendus indisponibles par le paramètre. Par défaut, toutes les fonctionnalités sont activées. |
