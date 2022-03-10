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
ms.openlocfilehash: bf6eb0eb755de3f2842c235946bfd7ccad04ccf7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474722"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Vous ne pouvez pas importer un article à l'aide de l'entité Produits lancés V2

Numéro de la base de connaissances : 4611825

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez d'importer un élément à l'aide de l'entité *Produits lancés V2*, vous recevez un message d'erreur semblable à l'exemple suivant :

> Impossible de créer un enregistrement dans les éléments - groupes de dimensions de suivi (EcoResTrackingDimensionGroupItem). Numéro de l'article : 2040663, Lot. L'enregistrement existe déjà.

## <a name="resolution"></a>Résolution

Pour importer de nouveaux produits lancés, vous devez utiliser l'entité *Sortie de la création de produit V2* au lieu de l'entité *Produits lancés V2*.
