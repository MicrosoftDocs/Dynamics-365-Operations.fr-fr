---
title: Échantillonnage des éléments de gestion de la qualité
description: Cette rubrique décrit comment configurer l’échantillonnage d’article.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 495bef32d63738e367167ee69f2028bc77945cc4
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956647"
---
# <a name="quality-management-item-sampling"></a>Échantillonnage des éléments de gestion de la qualité

L'échantillonnage d’article est utilisé dans le cadre d'une association de qualité. Il définit le montant de l'inventaire physique actuel qui doit être inspecté. L’échantillonnage peut être basé sur des quantités fixes, un pourcentage ou un contenant complet.

## <a name="set-up-item-sampling"></a>Paramétrer l’échantillonnage d’article

Procédez comme suit pour configurer l’échantillonnage d’article :

1. Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Échantillonnage d’article**.
1. Sélectionnez **Nouveau**.
1. Entrez une valeur dans le champ **Échantillonnage d’article**.
1. Dans le champ **Description**, entrez une valeur.
1. Entrez un nombre dans le champ **Valeur**. Cette valeur fait référence à la valeur de spécification de quantité sélectionnée dans le champ adjacent.
1. Dans la section **Processus**, cochez la case **Blocage total** si la quantité totale du lot ou de la ligne de commande doit être bloquée en cas d'échec d'un test. Si cette case à cocher est désactivée, seuls les éléments de l'ordre de qualité seront bloqués en cas d'échec d'un test.
1. Sélectionnez **Enregistrer**.
1. Fermez la page.

> [!NOTE]
> La fonctionnalité *Gestion de la qualité pour les processus d’entrepôt* fournit des capacités d’échantillonnage d’articles supplémentaires. Elle ajoute le concept de *portée d’échantillonnage de l’article* et permet de définir un contenant complet comme spécification de quantité. Si vous avez activé cette fonctionnalité, consultez [Gestion de la qualité pour les processus d’entrepôt](quality-management-for-warehouses-processes.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
