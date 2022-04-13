---
title: Afficher, gérer et approuver les ordres prévisionnels
description: Cette rubrique fournit des informations sur l’affichage, la gestion et l’approbation des ordres prévisionnels dans l’Optimisation de la planification.
author: t-benebo
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: b8c17ab3934ec7bfaed710c33515243290bb8e2a
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468775"
---
# <a name="view-manage-and-approve-planned-orders"></a>Afficher, gérer et approuver les ordres prévisionnels

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des informations sur l’affichage, la gestion et l’approbation des ordres prévisionnels dans l’Optimisation de la planification.

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a>Afficher et gérer les ordres prévisionnels

Vous pouvez afficher et gérer les ordres prévisionnels sur n’importe quelle page de liste d’ordres prévisionnels. Accédez à l’un des emplacements suivants, en fonction du type d’ordres prévisionnels avec lesquels vous souhaitez travailler :

- Planification \> Espaces de travail \> Planification
- Planification \> Planification \> Ordres prévisionnels
- Contrôle de la production \> Ordres de fabrication \> Ordres de fabrication prévisionnels
- Approvisionnements \> Commandes fournisseur \> Commandes fournisseurs prévisionnelles
- Gestion des stocks \> Commandes entrantes \> Ordres de transfert prévisionnels
- Gestion des stocks \> Commandes sortantes \> Ordres de transfert prévisionnels

## <a name="view-and-edit-the-status-of-planned-orders"></a>Afficher et modifier le statut des ordres prévisionnels

Vous pouvez utiliser le **Statut** de chaque ordre prévisionnel pour suivre votre progression ou modifier le traitement d’un ordre prévisionnel. Les valeurs de **Statut** suivantes sont disponibles :

- **Non traité** – Lorsque la planification génère des ordres prévisionnels, ils reçoivent ce statut. Les ordres prévisionnels qui ont ce statut seront supprimés lors du prochain cycle de planification.
- **Terminé** – Ce statut indique que l’ordre prévisionnel est terminé. Si vous décidez de ne pas confirmer un ordre prévisionnel, vous pouvez modifier manuellement son statut sur *Terminé*. Notez traite les statuts *Non traité* et *Terminé* de la même manière.
- **Approuvé** – Ce statut indique que l’ordre prévisionnel est approuvé pour confirmation. Si vous souhaitez confirmer un ordre prévisionnel, vous pouvez modifier son statut sur *Approuvé*. Si vous souhaitez conserver les modifications apportées à un ordre prévisionnel ou si vous prévoyez de confirmer un ordre prévisionnel, changez son statut en *Approuvé*. Les ordres prévisionnels dont le statut est *Approuvé* sont considérés comme des approvisionnements fixes et attendus par la planification. Par conséquent, ils ne sont ni modifiés ni supprimés lors des exécutions ultérieures de la planification. Pour ce faire, la logique de planification copie les ordres prévisionnels qui ont un statut *Approuvé* de l’ancienne version du plan vers la nouvelle version du plan lors de la planification. Notez que les ordres prévisionnels qui ont le statut *Approuvé* ne sont considérés comme des approvisionnements que dans le cadre du plan directeur spécifique.

Pour modifier le statut d’un seul ordre prévisionnel, [ouvrez une page de liste d’ordres prévisionnels](#view-planned-orders), ouvrez l’ordre, puis effectuez l’une de ces étapes :

- Sur le raccourci **Général**, modifiez la valeur du champ **Statut**.
- Dans le volet Actions, sous l’onglet **Ordre prévisionnel**, dans le groupe **Processus**, sélectionnez **Modifier le statut**.
- Pour marquer l’ordre comme approuvé, dans le volet Actions, sélectionnez **Approuver**.

Pour modifier le statut de plusieurs ordres prévisionnels en même temps, [ouvrez une page de liste d’ordres prévisionnels](#view-planned-orders), activez la case à cocher pour chaque ordre que vous souhaitez modifier, puis effectuez l’une des étapes suivantes :

- Dans le volet Actions, sous l’onglet **Ordre prévisionnel**, dans le groupe **Processus**, sélectionnez **Modifier le statut**.
- Pour marquer les ordres comme approuvés, dans le volet Actions, sélectionnez **Approuver**.

## <a name="approve-planned-orders"></a>Approuver les ordres prévisionnels

L’approbation des ordres prévisionnels est une étape facultative dans le processus de création d’un ordre confirmé à partir d’un ordre prévisionnel.

L’illustration suivante montre comment utiliser la valeur **Statut** affectée à chaque ordre prévisionnel pour implémenter un workflow d’approbation. Pour mettre en œuvre un processus d’approbation, ajustez manuellement la valeur **Statut** pour chaque ordre prévisionnel comme décrit dans la section précédente.

![Flux d’ordre prévisionnel.](media/approved-planned-orders-1.png)

> [!TIP]
> Nous vous recommandons d’approuver tous les ordres prévisionnels modifiés. Sinon, les modifications seront ignorées et écrasées lors du prochain cycle de planification.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Ordres prévisionnels confirmés](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
