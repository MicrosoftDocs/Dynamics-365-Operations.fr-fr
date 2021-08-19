---
title: L’article ne peut pas avoir de nomenclature ou de formule
description: Lorsque vous essayez de confirmer une commande, vous recevez un message d’erreur lors de la validation de l’article. Il indique que l’article ne peut pas avoir de nomenclature ou de formule.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 1e946adc3a04db60bf15ac7bb44163085e1c19802872964877d3929b1f79bf7d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730104"
---
# <a name="item-cant-have-a-bom-or-formula"></a>L’article ne peut pas avoir de nomenclature ou de formule

Code d’erreur : PRO2614

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer une commande, vous recevez le message d’erreur suivant lors de la validation de l’article :

> L’article ne peut pas avoir de nomenclature ou de formule

## <a name="resolution"></a>Résolution

Les articles qui ont une nomenclature ou une formule doivent être du type *Élément de planification*, *Nomenclature* ou *Formule*. Pour modifier le type d’un article, procédez comme suit.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Ouvrez le produit concerné.
1. Dans le raccourci **Ingénieur**, définissez le champ **Type de production** sur *Élément de planification*, *Nomenclature* ou *Formule*.
