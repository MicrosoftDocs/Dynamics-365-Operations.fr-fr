---
title: Plusieurs transactions de stock pour les numéros de lot lorsque la mise à jour physique est désactivée
description: Plusieurs transactions de stock sont créées après avoir ajusté une ligne de commande d'achat pour les articles pour lesquels l'option Sur mise à jour physique du groupe de numéros de lot est définie sur Non.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventNumGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1fa54cdfdbc5608fb6c7114dced0f96bab47253e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026521"
---
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a>Plusieurs transactions de stock pour les numéros de lot lorsque la mise à jour physique est désactivée

Numéro de la base de connaissances : 4613390

## <a name="symptoms"></a>Symptômes

Plusieurs transactions de stock sont créées après avoir ajusté une ligne de commande d'achat pour les articles pour lesquels l'option **Sur mise à jour physique** du groupe de numéros de lot est définie sur *Non*.

Lorsque vous créez un élément où l'option **Sur mise à jour physique** du groupe de numéros de lot est définie sur *Non*, le système crée automatiquement un nouveau numéro de lot si vous modifiez une quantité de ligne d'achat et enregistrez la page de commande d'achat.

## <a name="resolution"></a>Résolution

Le paramètre **Sur mise à jour physique** des groupes de numéros de lot fonctionne de la manière suivante :

- Lorsque l'option est définie sur *Oui*, les nouveaux numéros de lot ne sont créés qu'après une mise à jour physique (par exemple, lorsque les articles sont expédiés ou reçus).
- Lorsque l'option est définie sur *Non*, un nouveau numéro de lot est créé chaque fois qu'une mise à jour applicable se produit (par exemple, lorsqu'une nouvelle quantité est ajoutée à une commande fournisseur).
