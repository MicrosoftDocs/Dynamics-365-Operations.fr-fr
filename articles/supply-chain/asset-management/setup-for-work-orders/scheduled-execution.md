---
title: Exécution planifiée
description: Cette rubrique explique l’exécution planifiée dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fae899bcfa8bb2566d1a9aee3f0dbe22bc219edf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825636"
---
# <a name="scheduled-execution"></a>Exécution planifiée

[!include [banner](../../includes/banner.md)]

 

Vous pouvez utiliser les niveaux de service de l’ordre de travail pour configurer l’exécution planifiée. (Pour plus d’informations sur les niveaux de service de l’ordre de travail, consultez [Niveau de service et description](service-level-and-description.md).) L’exécution planifiée fournit la flexibilité de la planification du travail pour les agents de maintenance, car vous pouvez paramétrer des exigences plus ou moins détaillées pour l’intervalle pendant lequel un ordre de travail doit être effectué. Par exemple, un agent de maintenance qui exécute une tâche plus rapidement que prévue dans un site de production peut être en mesure de passer à une autre tâche à proximité planifiée pour la semaine actuelle, mais pas nécessairement pour le jour actuel. Cette approche permet l’optimisation de la planification de l’agent et de l’exécution de la tâche.

La configuration de l’exécution planifiée, qui est associée aux ordres de travail, peut être générique ou spécifique. Vous pouvez paramétrer les lignes génériques qui ne sont pas limitées aux types d’ordre de travail, types d’actif spécifiques, etc. Sinon, vous pouvez créer des lignes d’exécution planifiées qui s’appliquent à un type d’ordre de travail, type d’actif, type de tâche de maintenance spécifique, etc.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **Exécution planifiée**.
2. Sélectionnez **Nouveau** pour créer une ligne d’exécution planifiée.
3. Dans les champs **Poste technique**, **Type d’ordre d’exécution**, **Type d’actif**, **Fabricant**, **Modèle**, **Catégorie du type de tâche de maintenance**, **Type de tâche de maintenance**, **Variante du type de tâche de maintenance** et **Transaction**, sélectionnez les valeurs telles que vous le souhaitez.
4. Dans le champ **Niveau de service**, sélectionnez un niveau de service de l’ordre de travail. Si vous laissez ce champ vide, vous effectuez le type le plus générique de la ligne d’exécution prévue. Pour un exemple d’une ligne générique, consultez le premier enregistrement dans l’illustration suivante. Cette ligne active tous les ordres de travail qui n’ont pas de niveau de service à planifier pour une date et une heure spécifiques.
5. Dans le champ **Exécution planifiée**, sélectionnez l’intervalle de temps.
6. Sélectionnez **Enregistrer**.

![Exécution planifiée](media/20-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]