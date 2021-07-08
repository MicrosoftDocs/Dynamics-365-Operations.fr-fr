---
title: Le fournisseur n’est pas spécifié lorsque les commandes planifiées sont confirmées
description: Lorsque vous essayez de confirmer des commandes planifiées, vous recevez un message d’erreur indiquant qu’aucun fournisseur n’est spécifié.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cf41295045211f8a714194494028922d573c9e9e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294071"
---
# <a name="vendor-isnt-specified-when-planned-orders-are-firmed"></a>Le fournisseur n’est pas spécifié lorsque les commandes planifiées sont confirmées

Code d’erreur : SYS23532

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer des commandes planifiées, vous recevez le message d’erreur suivant :

> Fournisseur non précisé

## <a name="resolution"></a>Résolution

Pour spécifier un fournisseur, procédez comme suit.

1. Ouvrez la commande planifiée à laquelle il manque un fournisseur.
1. Dans le raccourci **Approvisionnement prévu**, dans le champ **Fournisseur**, sélectionnez un fournisseur.
