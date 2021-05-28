---
title: Vous ne pouvez pas importer un article à l'aide de l'entité Produits lancés V2
description: Vous ne pouvez pas importer un article à l'aide de l'entité Produits lancés V2.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended, DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8182f2f83f6a3e4cf54fe6fa64b25a2f461ff541
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026499"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Vous ne pouvez pas importer un article à l'aide de l'entité Produits lancés V2

Numéro de la base de connaissances : 4611825

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez d'importer un élément à l'aide de l'entité *Produits lancés V2*, vous recevez un message d'erreur semblable à l'exemple suivant :

> Impossible de créer un enregistrement dans les éléments - groupes de dimensions de suivi (EcoResTrackingDimensionGroupItem). Numéro de l'article : 2040663, Lot. L'enregistrement existe déjà.

## <a name="resolution"></a>Résolution

Pour importer de nouveaux produits lancés, vous devez utiliser l'entité *Sortie de la création de produit V2* au lieu de l'entité *Produits lancés V2*.
