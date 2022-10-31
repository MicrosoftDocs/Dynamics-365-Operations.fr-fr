---
title: Amélioration des performances de l’activation de structure de compte
description: Cet article explique la nouvelle amélioration des performances du processus d’activation de la structure de compte.
author: RyanCCarlson2
ms.date: 10/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-10-08
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 42f8fcebba6465261489f74a9bb1dd46c2d5fa16
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2022
ms.locfileid: "9713997"
---
# <a name="account-structure-activation-performance-enhancement"></a>Amélioration des performances de l’activation de structure de compte

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Cette amélioration des performances vous permet d’activer les structures de compte plus rapidement en exécutant plusieurs mises à jour de transactions en même temps. De plus, la structure elle-même est marquée comme active après sa validation, et le traitement des transactions peut continuer pendant que les transactions non validées existantes sont mises à jour dans la nouvelle structure. Étant donné que les mises à jour des transactions peuvent prendre un certain temps, vous pouvez suivre l’état de votre activation en sélectionnant **Afficher le statut de l’activation** au-dessus de la grille de la page **Structures de compte**. Vous pouvez également afficher votre statut d’activation en sélectionnant **Afficher** dans le volet Action, puis en sélectionnant **Statut de l’activation** dans le menu déroulant.

[![Page Structures de compte.](./media/AccountStructure1.png)](./media/AccountStructure1.png)

Après avoir sélectionné **Afficher le statut de l’activation**, une boîte de dialogue apparaît pour afficher les tâches individuelles en cours d’exécution dans le cadre du processus d’activation. Pour chaque tâche, vous pouvez afficher le statut et, une fois la tâche terminée, la date et l’heure de fin.

[![Chronologie de l’activation de la structure de compte.](./media/AccountStructureTimeline.png)](./media/AccountStructureTimeline.png)

## <a name="account-structure-activation-tips"></a>Conseils d’activation de la structure de compte

La boîte de dialogue d’activation de la structure de compte qui s’affiche lorsque vous sélectionnez **Activer** pour un brouillon de structure de compte a une section d’onglet nommée **Mettre à jour les transactions non validées**. Cette section contient une option nommée **Forcer la mise à jour**. Vous pouvez sélectionner cette option pour mettre à jour toutes les transactions non validées dans la structure actuelle. Cependant, vous ne devez utiliser cette option que lorsqu’une erreur s’est produite ou que le support Microsoft vous a demandé de l’utiliser.

Voici quelques-uns des facteurs qui peuvent affecter les performances du processus d’activation :

- Un grand nombre d’enregistrements de journal non validés
- Un grand nombre d’enregistrements de document open source tels que des factures financières, des factures fournisseur et des documents connexes qui utilisent le cadre du document source et ont des répartitions comptables ouvertes
- La quantité de données dans TaxUncommitted
- La quantité de données budgétaires ouvertes
- Importer les données du journal pendant que les tâches d’activation sont toujours en cours d’exécution

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
