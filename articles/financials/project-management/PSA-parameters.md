---
title: "Paramètres d'intégration de Project Service Automation"
description: "Vous pouvez configurer la valeur par défaut des données lors de l'intégration de Project Service Automation avec Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 12/13/2017
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
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 32f7f70c5b1071cef5a3360ccc09fa2d95fbf9a9
ms.contentlocale: fr-fr
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation-integration-parameters"></a>Paramètres d'intégration de Project Service Automation

Dans la page **Paramètres d'intégration de Project Service Automation**, vous pouvez configurer la valeur par défaut des données lors de l'intégration de Project Service Automation avec Finance and Operations. Les éléments suivants doivent être paramétrés pour que les projets soient correctement synchronisés entre Project Service Automation et Finance and Operations.

> [!NOTE]
> L'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités sont disponibles dans la version 8.0 de Dynamics 365 for Finance and Operations.




| **Onglet**                      | **Champ**                          | **Description**                    |
|------------------------------|------------------------------------|--------------------------------|
| **Général**                  | **Type de projet par défaut**               | Permet de sélectionner la valeur par défaut pour **Type de projet** lorsque les projets sont synchronisés à partir de Project Service Automation si vous n'avez pas fourni de valeur par défaut dans le modèle d'intégration. Lors de la synchronisation, les nouveaux projets ont le **Type de projet** défini sur cette valeur et peuvent être mis à jour lorsque les lignes de contrat de projet sont synchronisées à partir de Project Service Automation.               |
| **Général**                  | **Catégorie de temps**                      | Permet de sélectionner la valeur par défaut pour **Catégorie de temps** lorsque les estimations des heures sont synchronisées à partir de Project Service Automation. Lors de la synchronisation, les nouvelles prévisions des heures du projet dans Finance and Operations ont la **Catégorie** définie sur cette valeur lorsque les estimations des heures et les estimations réelles des heures sont synchronisées à partir de Project Service Automation.   |
| **Général**                  | **Catégorie de frais**                       | Permet de sélectionner la valeur par défaut pour **Catégorie de frais** lorsque les transactions réelles de frais sont synchronisées à partir de Project Service Automation. Lors de la synchronisation, les nouvelles transactions de frais dans Finance and Operations ont la **Catégorie** définie sur cette valeur lorsque les transactions réelles de frais sont synchronisées à partir de Project Service Automation.          |
| **Valeurs par défaut des groupes de projets**   | **Type de projet** | Cliquez sur **Nouveau** pour ajouter une ligne permettant de sélectionner le type de projet pour lequel définir le groupe de projets par défaut. Un type de projet spécifique ne peut être sélectionné qu'une seule fois dans la configuration.              
|                              | **Groupe de projets**          | Permet de sélectionner le groupe de projets par défaut pour le type de projet spécifié. Lorsque de nouveaux projets sont synchronisés à partir de Project Service Automation, le **Groupe de projets** est la valeur par défaut selon le type de projet si vous n'avez pas fourni de valeur par défaut dans le modèle d'intégration.  |
| **Valeurs par défaut du type de facturation**    | **Type de facturation** | Cliquez sur **Nouveau** pour ajouter une ligne permettant de sélectionner le type de facturation pour lequel définir la propriété de ligne par défaut. Un type de facturation spécifique ne peut être sélectionné qu'une seule fois dans la configuration.          |
|                              | **Propriété de ligne**| Permet de sélectionner la propriété de ligne par défaut pour le type de facturation spécifié. Lorsque de nouvelles estimations des heures, de nouvelles estimations des dépenses ou de nouvelles estimations réelles sont synchronisées dans Project Service Automation, la **Propriété de ligne** est la valeur par défaut selon le type de facturation.          |
| **Verrouillage de la fonctionnalité**    |                   | Permet de sélectionner la fonctionnalité à désactiver dans Finance and Operations pour les projets et les contrats provenant de Project Service Automation. Par exemple, vous pouvez choisir de désactiver la possibilité de modifier les contrats et les projets, de créer des structures de répartition du travail et de saisir des feuilles de temps dans Finance and Operations. Les champs comptables continuent à être activés, même s'ils sont rendus indisponibles par le paramètre. Par défaut, toutes les fonctionnalités sont activées.           |

