---
title: Les conditions du workflow du journal de stock ne s’appliquent qu’au niveau du journal, et non au niveau de la ligne
description: Les conditions du workflow du journal de stock ne s’appliquent qu’au niveau du journal, et non au niveau de la ligne.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 46bdde7f09c639fbefd46162431762b056d521ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476335"
---
# <a name="inventory-journal-workflow-conditions-apply-at-the-journal-level-not-line-level"></a>Les conditions du workflow du journal de stock ne s’appliquent qu’au niveau du journal, et non au niveau de la ligne

## <a name="symptoms"></a>Symptômes

Vous pouvez rencontrer ce problème si, par exemple, vous essayez de configurer une condition du workflow du journal d’inventaire sur le montant du coût. Vous configurez la condition pour que l’étape 1 ne soit exécutée que lorsque le montant du coût est inférieur à 100. Vous configurez ensuite une autre condition pour que l’étape 2 ne soit exécutée que lorsque le montant du coût est supérieur ou égal à 100. Ensuite, lorsque le workflow est exécuté, l’historique du workflow n’affiche qu’une seule ligne et la première condition est toujours évaluée comme *vrai*, quelle que soit la valeur envoyée.

## <a name="workaround"></a>Solution de contournement

Dans la version actuelle, les conditions du workflow du journal ne s’appliquent qu’au niveau du journal, et non au niveau de la ligne. Ce comportement est fait exprès. Nous vous recommandons de définir vos critères de condition uniquement sur les attributs au niveau du journal.
