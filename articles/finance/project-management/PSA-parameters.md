---
title: Paramètres d'intégration de Project Service Automation
description: Cette rubrique explique comment configurer la saisie des données par défaut lorsque vous intégrez Microsoft Dynamics 365 for Project Service Automation à Microsoft Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 03/03/2020
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
ms.openlocfilehash: cd09dad15112fd71bfd386e0072a77a4121c96e0
ms.sourcegitcommit: 236672932ffd0a758012ebb7b2df9bc51249c126
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096249"
---
# <a name="project-service-automation-integration-parameters"></a>Paramètres d'intégration de Project Service Automation

[!include[banner](../includes/banner.md)]

Sur la page **Paramètres d'intégration de Project Service Automation**, vous pouvez configurer comment les données par défaut sont saisies lorsque vous intégrez Dynamics 365 Project Service Automation à Dynamics 365 Finance. Pour que les projets soient correctement synchronisés entre Project Service Automation et Finance, vous devez paramétrer les champs suivants.

Pour ouvrir la page **Paramètres d'intégration de Project Service Automation**, accédez à **Gestion et comptabilité des projets** \> **Configuration** \> **Paramètres d'intégration Dynamics 365 for Project Service Automation**. 

> [!NOTE]
> - L'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités sont disponibles dans la version 8.0.
> - L'intégration des chiffres réels est disponible dans version 8.0.1 ou version ultérieure.


| Onglet                    | Champ                | Description |
|------------------------|----------------------|-------------|
| Général(e)                | Type de projet par défaut | Permet de sélectionner le type de projet par défaut. Lorsque les projets sont synchronisés à partir de Project Service Automation, cette valeur est utilisée si vous n'avez pas fourni de valeur par défaut dans le modèle d'intégration. Lors de la synchronisation, le champ **Type de projet** des nouveaux projets est défini sur cette valeur. Toutefois, la valeur peut être mise à jour lorsque les lignes de contrat du projet sont synchronisées depuis Project Service Automation. |
|                        | Catégorie de temps        | Permet de sélectionner la catégorie de temps par défaut. Cette valeur est utilisée lorsque les estimations d'heures sont synchronisées depuis Project Service Automation. Lorsque les estimations des heures et les estimations réelles des heures sont synchronisées à partir de Project Service Automation, le champ **Catégorie** des nouvelles prévisions d'heures du projet dans Finance est défini sur cette valeur. |
|                        | Catégorie de frais         | Permet de sélectionner la catégorie de frais par défaut. Cette valeur est utilisée lorsque les transactions réelles de frais sont synchronisées depuis Project Service Automation. Lorsque les transactions réelles de frais sont synchronisées à partir de Project Service Automation, le champ **Catégorie** des nouvelles transactions de frais dans Finance est défini sur cette valeur. |
| Valeurs par défaut des groupes de projets | Type de projet         | Cliquez sur **Nouveau** pour ajouter une ligne permettant de sélectionner le type de projet pour lequel définir le groupe de projets par défaut. Un type de projet spécifique ne peut être sélectionné qu'une seule fois dans la configuration. |
|                        | Groupe de projets        | Permet de sélectionner le groupe de projets par défaut pour le type de projet sélectionné. Lorsque de nouveaux projets sont synchronisés à partir de Project Service Automation, le champ **Groupe de projets** est défini sur la valeur par défaut du type de projet si vous n'avez pas fourni de valeur par défaut dans le modèle d'intégration. |
| Valeurs par défaut du type de facturation  | Type de facturation         | Cliquez sur **Nouveau** pour ajouter une ligne permettant de sélectionner le type de facturation pour lequel définir la propriété de ligne par défaut. Un type de facturation spécifique ne peut être sélectionné qu'une seule fois dans la configuration. |
|                        | Propriété de ligne        | Permet de sélectionner la propriété de ligne par défaut pour le type de facturation sélectionné. Lorsque de nouvelles estimations des heures, de nouvelles estimations des dépenses ou de nouvelles estimations réelles sont synchronisées dans Project Service Automation, le champ **Propriété de ligne** est défini sur la valeur par défaut du type de facturation. |
| Verrouillage de la fonctionnalité  | Non applicable       | Permet de sélectionner la fonctionnalité à désactiver dans Finance pour les projets et les contrats provenant de Project Service Automation. Par exemple, vous pouvez désactiver la possibilité de modifier les contrats et les projets, de créer des structures de répartition du travail et de saisir des feuilles de temps dans Finance. Les champs comptables continuent à être activés, même s'ils sont rendus indisponibles par le paramètre. Par défaut, toutes les fonctionnalités sont activées. |
