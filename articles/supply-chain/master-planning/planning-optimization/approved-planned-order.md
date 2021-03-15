---
title: Approuver les ordres prévisionnels
description: Cette rubrique décrit l’approbation des ordres prévisionnels pris en charge dans l’Optimisation de la planification.
author: ChristianRytt
manager: tfehr
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c29ede7ad8916a97b4a04b68f41961f79810e0c8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983567"
---
# <a name="approve-planned-orders"></a>Approuver les ordres prévisionnels

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des informations sur la mise à jour du statut des ordres prévisionnels dans l’Optimisation de la planification.

Notez que l’approbation des ordres prévisionnels est une étape facultative, sur la façon de créer un ordre confirmé à partir d’un ordre prévisionnel. Il est recommandé d’approuver les ordres prévisionnels modifiés, sinon les modifications seront ignorées et écrasées lors du prochain cycle de planification.

![Flux d’ordre prévisionnel](media/approved-planned-orders-1.png)

Le champ **Statut** vous aide à suivre votre progression en utilisant les valeurs suivantes :

- **Non traité :** Lorsque la planification génère des ordres prévisionnels, leur statut est *Non traité*. Les ordres prévisionnels avec ce statut seront supprimés lors du prochain cycle de planification.
- **Terminé :** Si vous décidez de ne pas confirmer un ordre prévisionnel, vous pouvez modifier le statut sur *Terminé* pour indiquer que vous avez terminé l’évaluation de cet ordre prévisionnel. Notez qu’un statut de *Non traité* et *Terminé* sont traités de la même manière par le système.
- **Approuvé :** Si vous souhaitez conserver les modifications ou prévoyez de confirmer un ordre prévisionnel, changez le statut sur *Approuvé*. Les ordres prévisionnels avec le statut *Approuvé* sont considérés comme un approvisionnement fixe et prévu par la planification, de sorte qu’ils ne sont pas modifiés ou supprimés pendant une exécution ultérieure de la planification. Pour ce faire, la logique de planification copie les ordres prévisionnels *Approuvés* de l’ancienne version de plan vers la nouvelle version de plan lors de la planification. Notez que les ordres prévisionnels *Approuvés* ne sont considérés comme des approvisionnements que dans le cadre du plan spécifique.

Vous pouvez gérer les ordres prévisionnels à partir de l’espace de travail **Planification**, de la liste **Ordre prévisionnel** ou des listes **Ordres de fabrication prévisionnels**, **Commandes fournisseur prévisionnelles** et **Transfert prévisionnel**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]