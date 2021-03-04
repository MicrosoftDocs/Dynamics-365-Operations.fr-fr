---
title: Résoudre les problèmes des lancements partiels et des expéditions partielles
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de l'utilisation des lancements partiels et des expéditions partielles dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e89a430f90374733b23fadaf53f5bab598d67d62
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645946"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a>Résoudre les problèmes des lancements partiels et des expéditions partielles

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de l'utilisation des lancements partiels et des expéditions partielles dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>Le statut de validation d'une commande client reste Lancé partiellement même après la facturation de la commande client.

### <a name="issue-description"></a>Description du problème

Une commande client est un bon de livraison, mais un ou plusieurs articles y figurant ont un mode de livraison différent. Une fois la commande facturée, elle a toujours un statut de validation de *Lancé partiellement*.

Par exemple, une commande client comporte deux articles : un pour la livraison et un pour le retrait. La livraison et le retrait ont été effectués. Par conséquent, les deux lignes ont été facturées. Cependant, le statut du lancement est toujours affiché comme *Lancé partiellement*, ce qui est trompeur.

### <a name="issue-resolution"></a>Résolution du problème

Le statut de lancement s'applique uniquement aux lignes de commande où les articles sont activés pour la gestion de l'entrepôt. Par conséquent, le statut du lancement *Lancé partiellement* dans ce scénario. Microsoft a évalué ce problème et a déterminé qu'il s'agissait d'une limitation de fonctionnalité. Une extension peut être ajoutée dans le cadre du bon de livraison et du processus de facturation pour mettre à jour le statut du lancement.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]