---
title: Le système ne peut pas trouver un ordre planifié pendant les opérations sur plusieurs ordres
description: Une erreur "La commande planifiée n’existe pas" se produit lorsque vous effectuez des opérations sur plusieurs commandes planifiées et qu’au moins deux commandes appartiennent au même ID d’article.
author: t-benebo
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo_ReqTransPoMarkChangeType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 0ece4a331b63b86e896c5b337a58185ed3ea1049
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920801"
---
# <a name="the-system-cant-find-a-planned-order-during-operations-on-multiple-orders"></a>Le système ne peut pas trouver un ordre planifié pendant les opérations sur plusieurs ordres

Code d’erreur : SYS24774

## <a name="symptoms"></a>Symptômes

Le message d’erreur suivant s’affiche lorsque vous essayez d’effectuer une opération sur plusieurs commandes planifiées en même temps et qu’au moins deux des commandes appartiennent au même ID d’article. Par exemple, l’erreur peut se produire lorsque les commandes sont confirmées ou que leur type de commande est modifié.

> L’ordre prévisionnel %1 n’existe pas.

## <a name="cause"></a>Cause

Lorsque le système confirme ou modifie le type d’une commande, il doit reconsidérer les commandes planifiées existantes pour l’article, afin de s’assurer que l’approvisionnement planifié correspond à la demande et à l’offre existante. Dans le cadre de ce processus, le système recrée les ordres planifiés pour l’article. Par conséquent, le deuxième ordre planifié que le système s’attend à traiter n’existe plus.

## <a name="workaround"></a>Solution de contournement

Approuvez les commandes avant de les traiter. De cette façon, les commandes ne seront pas supprimées lorsque le système traitera la première commande de l’article.
