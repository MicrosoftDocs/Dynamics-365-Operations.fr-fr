---
title: La planification génère des commandes planifiées pour les produits fantômes
description: Les commandes planifiées sont générées pour les produits fantômes après l'exécution de la planification principale.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026514"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a>La planification génère des commandes planifiées pour les produits fantômes

Numéro de la base de connaissances : 4614729

## <a name="symptoms"></a>Symptômes

Les commandes planifiées sont générées pour les produits fantômes après l'exécution de la planification principale.

## <a name="resolution"></a>Résolution

Le cadre de l'option **Fantôme** pour les produits lancés détermine le type de ligne par défaut sur la nomenclature (BOM). Quand l'option **Fantôme** est définie sur *Oui*, le système créera toujours des ordres planifiés pour l'article, mais l'option **Exigence dérivée directement** pour chaque ordre planifié sera définie sur *Oui*. Par conséquent, l'ordre de fabrication planifié ne peut pas être confirmé seul. Au lieu de cela, il sera toujours automatiquement inclus lorsque l'ordre de fabrication parent est confirmé. En outre, les lignes de nomenclature de l'ordre fantôme planifié seront incluses dans la nomenclature de l'ordre de fabrication parent.
