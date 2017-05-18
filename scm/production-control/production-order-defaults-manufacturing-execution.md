---
title: "Valeurs par défaut de l&quot;ordre de fabrication dans le module"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 70073
ms.assetid: 620944ae-3e20-444a-807e-65495f160904
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: cc12a8d75ead1577cf0b31a0dbf3ac072c47dc08
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="production-order-defaults-in-manufacturing-execution"></a>Valeurs par défaut de l'ordre de fabrication dans le module

[!include[banner](../includes/banner.md)]




Vous devez tenir compte soigneusement de tous les paramètres sur la page **Valeurs par défaut de l'ordre de fabrication** avant que les collaborateurs commencent à faire des enregistrements sur les tâches de production. Si votre société utilise la fonctionnalité multisite, vous souhaitez peut-être paramétrer différentes valeurs par défaut pour les ordres de fabrication pour chaque site. Les valeurs de commande par défaut pour l'intégration avec le contrôle de la production sont paramétrées dans les onglets suivants sur la page **Valeurs par défaut de l'ordre de fabrication** :

-   **Général** – Valeurs générales par défaut de commande pour les tâches de production dans le module Contrôle et suivi de la production.
-   **Début** – Valeurs de commande par défaut utilisées lorsque les tâches de production ou les opérations sont démarrées.
-   **Opérations** – Valeurs par défaut des commandes appliquées aux tâches ou aux opérations de production et aux commentaires sur les opérations durant le processus de production.
-   **Déclarer terminé** – Valeurs par défaut de commande appliquées lorsque les articles sont déclarés terminés lors de la dernière opération d'un ordre de fabrication.
-   **Contrôle de la quantité** – Valeurs par défaut de commande pour le contrôle des quantités de départ et en rétroaction sur les ordres de fabrication.

## <a name="types-of-production-jobs"></a>Types de tâches de production
Sous l'onglet **Opérations**, sélectionnez les types de tâches de production qui nécessitent l'enregistrement sur la page **Enregistrement de tâche**. Généralement, les travailleurs effectuent des enregistrements sur des tâches de paramétrage et de traitement. Toutefois, en cas d'application de la planification de tâche, vous pouvez sélectionner d'autres types de tâches, par exemple, de transport, sur lesquelles les collaborateurs doivent également effectuer des enregistrements lors du traitement d'un ordre de fabrication. **Important :** Assurez-vous que les types de tâches appropriés sont sélectionnés. Sinon, les tâches ne sont pas disponibles pour l'enregistrement sur la page **Enregistrement de tâche**. Harmonisez vos sélections avec les sélections effectuées dans la colonne **Gestion des tâches** sur la page **Groupes de gammes**. Si l'option **Gestion des tâches** est sélectionnée dans le groupe de gammes, ce type de tâche est signalé comme terminé dans l'ordre de fabrication. Cette génération d'états se produit quand la tâche est déclarée terminée dans le module Contrôle et suivi de la production. Si tous les types de tâches pour lesquelles l'option **Gestion des tâches** est sélectionnée sont déclarées terminées sur une opération, le module Contrôle et suivi de la production signale également l'opération comme terminée. **Remarque :** Certains types de tâches peuvent être signalés manuellement via les journaux de production. Dans ce cas, sélectionnez **Gestion des tâches** pour le type de tâche, mais ne sélectionnez pas le type de tâche pour l'enregistrement sous l'onglet **Opérations** sur la page **Valeurs par défaut de l'ordre de fabrication**.

## <a name="bom-consumption-and-picking-list-journals"></a>Consommation de nomenclature et journaux des prélèvements
Les matières peuvent être paramétrées de manière à être consommées automatiquement ou manuellement lors de la production. La consommation automatique est contrôlée par le principe d'effacement paramétré sur les lignes de la nomenclature, puis par le paramètre du champ **Consommation de nomenclature automatique** dans les valeurs par défaut de l'ordre de fabrication. La consommation automatique peut être paramétrée afin qu'elle se produise lorsqu'un ordre de fabrication est lancé ou déclaré terminé. Sinon, elle peut se produire au niveau des tâches lorsqu'une tâche est commencée ou terminée.

### <a name="controlling-material-consumption-when-a-production-order-is-started"></a>Contrôle de la consommation des matières au lancement d'un ordre de fabrication

La consommation de matières lors du démarrage d'un ordre de fabrication est contrôlée par le champ **Consommation de nomenclature automatique** sous l'onglet **Début**. Les valeurs disponibles sont les suivantes :

-   **Principe d'effacement** – Lorsqu'un ordre de fabrication est lancé, les quantités de matières seront consommées selon le principe d'effacement défini dans les lignes de la nomenclature de production. Seules les lignes de matière auxquelles le principe d'effacement est défini sur **Début** seront consommées au début de la production.
-   **Toujours** – Les quantités de matières qui sont proportionnelles à la quantité de départ seront toujours consommées.
-   **Jamais** – Les quantités de matières ne seront jamais consommées.

### <a name="controlling-material-consumption-when-a-production-job-is-started-or-completed"></a>Contrôle de la consommation de matières lors du lancement ou de la fin d'une tâche de fabrication

La consommation de matières au démarrage ou à la fin d'une tâche de fabrication est contrôlée par le champ **Consommation de nomenclature automatique** sous l'onglet **Opérations**. Les valeurs disponibles sont les suivantes :

-   **Principe d'effacement** – Lorsqu'une quantité sur une tâche de fabrication est commencée ou terminée, les quantités de matières seront consommées selon le principe d'effacement défini dans les lignes de la nomenclature de production. Seules les lignes de matière auxquelles le principe d'effacement est défini sur **Début** ou **Fin** seront consommées au début de la production.
-   **Toujours** – Les quantités de matières qui sont proportionnelles à la quantité démarrée sur la tâche seront toujours consommées.
-   **Jamais** – Les quantités de matières ne seront jamais consommées.

### <a name="controlling-material-consumption-when-a-production-order-is-reported-as-finished"></a>Contrôle de la consommation de matières lors de la déclaration de fin d'un ordre de fabrication.

La consommation de matières lors du processus Déclarer terminé pour un ordre de fabrication est contrôlée par le champ **Consommation de nomenclature automatique** sous l'onglet **Déclarer terminé**. Les valeurs disponibles sont les suivantes :

-   **Principe d'effacement** – Lorsqu'un ordre de fabrication est déclaré terminé, les quantités de matières seront consommées selon le principe d'effacement défini dans les lignes de la nomenclature de production. Seules les lignes de matière auxquelles le principe d'effacement est défini sur **Fin** seront consommées au début de la production.
-   **Toujours** – Les quantités de matières qui sont proportionnelles à la quantité signalée comme terminée seront toujours consommées.
-   **Jamais** – Les quantités de matières ne seront jamais consommées.





